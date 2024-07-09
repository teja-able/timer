<script>
  import { onDestroy, onMount } from 'svelte';

  const dateFormatterTime = new Intl.DateTimeFormat('en', {
    hour: 'numeric',
    minute: '2-digit',
    second: '2-digit',
    hour12: true
  });

  const dateFormatterWeekday = new Intl.DateTimeFormat('en', {
    weekday: 'long',
   
  });
  const dateFormatterDate = new Intl.DateTimeFormat('en', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  });

  let currentTime = dateFormatterTime.format(new Date()); // Initial value for time
  let currentWeekday = dateFormatterWeekday.format(new Date()); // Initial value for date
  let currentDate = dateFormatterDate.format(new Date()); // Initial value for date

  // Update time every second
  const interval = setInterval(() => {
    currentTime = dateFormatterTime.format(new Date());
  }, 1000); // Update every second

  // Clean up interval on component destruction
  onDestroy(() => {
    clearInterval(interval);
  });
</script>

<main>
  <div class="container">
    <p>Date: {currentDate}</p>
    <p>Day: {currentWeekday}</p>
    <p>Time: {currentTime}</p>
  </div>
</main>

<style>
  .container {
    background-image: linear-gradient(to right, red,violet);
    color: white;
    text-align: center;
    margin-top: 50px;
  }
</style>
