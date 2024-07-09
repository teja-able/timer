<script>
    // Define the enumeration
    const STATE = {
      NEW: 'NEW',
      RUNNING: 'RUNNING',
      PAUSED: 'PAUSED'
    };
  
    // Declare a variable to store the current state
    let currentState = STATE.NEW;
  
    // Function to change the state
    function changeState(newState) {
      currentState = newState;
    }
  </script>
  
  <!-- HTML Template -->
  <main>
    <h1>Current State: {currentState}</h1>
  
    <!-- Buttons to change the state -->
    <button on:click={() => changeState(STATE.NEW)}>New</button>
    <button on:click={() => changeState(STATE.RUNNING)}>Running</button>
    <button on:click={() => changeState(STATE.PAUSED)}>Paused</button>
  </main>
  
  <style>
    main {
      text-align: center;
      padding: 1em;
    }
  
    button {
      margin: 0.5em;
    }
  </style>
  