<!-- <!-- <script lang="ts">
    import { onMount } from 'svelte';
    import Time from "./components/time.svelte";
    import States from './components/States.svelte';



    
    enum STATE {
      NEW,
      RUNNING,
      PAUSED,
    }
  
    let state: STATE = STATE.NEW;
    let startTime: number = 0;
    let elapsedTime: number = 0;
    let timerInterval: number = 0;
    let laps: number[] = [];

  
    const start = () => {
      state = STATE.RUNNING;
      startTime = Date.now() - elapsedTime;
      timerInterval = setInterval(() => {
        elapsedTime = Date.now() - startTime;
      }, 10); 
    };

    const recordLap = () => {
  if (state === STATE.RUNNING) {
    laps = [...laps, elapsedTime];
  }
};

  
    const pause = () => {
      state = STATE.PAUSED;
      clearInterval(timerInterval); 
    };
  
    const reset = () => {
      state = STATE.NEW;
      clearInterval(timerInterval); 
      startTime = 0;
      elapsedTime = 0;

    };
  
    const resetList = () => {
      laps=[]
      
      
    };
    const formatElapsedTime = (milliseconds: number): string => {
      const hours = Math.floor(milliseconds / (1000 * 60 * 60));
      const minutes = Math.floor((milliseconds % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((milliseconds % (1000 * 60)) / 1000);
      const centiseconds = Math.floor((milliseconds % 1000) / 10);
  
      return `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}.${centiseconds.toString().padStart(2, '0')}`;
    };
  

    onMount(() => {
      elapsedTime = 0;
    });
  </script> -->
  

  <!-- <main class="h-screen bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 flex items-center  justify-center">
    
    <div class="sm:flex">
      <div class="glass w-[300px] h-[280px] bg-gradient-to-r from-pink-500 via-purple-500 to-indigo-500 p-6">
        <Time />
        <h1 class="text-2xl text-center text-white p-1">SUPER STOP WATCH</h1>
        <hr>
        <p class="text-center p-1 max-w-max text-xl text-white">Elapsed Time: {formatElapsedTime(elapsedTime)}</p>
        <div class="text-right">
          {#if state === STATE.NEW}
            <button class="mr-2 text-xl text-green-500 font-bold px-2 border-green-400 border rounded" on:click={start}>Start</button>
          {:else if state === STATE.RUNNING}
          <button class="mr-2 text-xl text-red-500 font-bold px-2 border-red-400 border rounded" on:click={recordLap}>Lap</button>
      
            <button class="mr-2 text-xl text-red-500 font-bold px-2 border-red-400 border rounded" on:click={reset}>Reset</button>
            <button class="mr-2 text-xl text-white font-bold px-2 border-white border rounded" on:click={pause}>Pause</button>
          {:else if state === STATE.PAUSED}
          <button class="mr-2 text-xl text-red-500 font-bold px-2 border-red-400 border rounded" on:click={reset}>Reset</button>
          <button class="mr-2 text-xl text-black font-bold px-2 border-black border rounded" on:click={start}>Resume</button>
          
          {/if}
        
          
          
        </div>
       
      </div>
      <div class=" justify-center glass w-[300px] h-[280px] w-max-w bg-gradient-to-b from-pink-500 via-indigo-500 to-purple-500">
        
        <div class="text-xl text-white text-center scroll-m-10">
          Laps:
          {#each laps as lap, index}
            <p>Lap {index + 1}: {formatElapsedTime(lap)}</p>
          {/each}
        </div>
        <div class="flex justify-center p-1">
            <button class="mr-2 text-xl text-yellow-400 font-bold px-2 border-yellow-400 border rounded" on:click={resetList}>resetList</button></div>
      </div>
      
    </div>
  
  </main>

  
  <style>
    .glass {
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      border-radius: 20px;
    }
    .scroll-m-10{
        max-height: 240px; 
  overflow-y: auto; 
    }
  </style>
  


  <States/> -->
  <script>
    import PracticeTime from "./components/practiceTime.svelte";
  </script>
  <PracticeTime />
  <div> 
    <div class="outer-circle border-2 border-black h-48 w-48 rounded-full flex items-center justify-center relative">
      <div class="text absolute top-1 left-1/2 transform -translate-x-1/2">60</div>
      <div class="text absolute bottom-1 left-1/2 transform -translate-x-1/2">30</div>
      <div class="text absolute top-1/2 left-[25px] transform -translate-y-1/2 -translate-x-full">45</div>
      <div class="text absolute top-1/2 right-[25px] transform -translate-y-1/2 translate-x-full">15</div>
      <div class="inner-circle border-2 border-black h-32 w-32 rounded-full flex  justify-center ">
          <div class="clock-sec h-[60px] rounded-[50px] w-2 border border-black bg-black  origin-bottom animate-spin "></div>
      </div>
  
    </div></div>
    <style>

/* @keyframes rotateHand {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
} */

.clock-sec {
  animation: spin 60s linear infinite;
}

</style>

