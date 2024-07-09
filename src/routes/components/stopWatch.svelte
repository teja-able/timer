<script>
     const STATE {
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
</script>