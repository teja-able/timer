<script>

</script>
<main>
    <div class="outer-circle border-2 border-black h-48 w-48 rounded-full flex items-center justify-center relative">
        <div class="text absolute top-1 left-1/2 transform -translate-x-1/2">60</div>
        <div class="text absolute bottom-1 left-1/2 transform -translate-x-1/2">30</div>
        <div class="text absolute top-1/2 left-[25px] transform -translate-y-1/2 -translate-x-full">45</div>
        <div class="text absolute top-1/2 right-[25px] transform -translate-y-1/2 translate-x-full">15</div>
        <div class="inner-circle border-2 border-black h-32 w-32 rounded-full flex  justify-center ">
            <div class="clock-hr h-[60px] rounded-[50px] w-2 border border-black bg-black  origin-bottom animate-spin"></div>
        </div>
      </div> 
</main>
<style>
    .clock-hr{
        animation: spin 3600s linear infinite;
    }
</style>