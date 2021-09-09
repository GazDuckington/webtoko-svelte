<script>
    import {slide} from "svelte/transition";
    
    let show = false;
</script>

<div class="flex flex-col">

<!-- quick cart -->
{#if show}
<div transition:slide={{duration:300}} >
    <div class="quick-cart" on:click={()=>(show=!show)}>
        hewwo
    </div>
</div>
{/if}

<!-- buttom -->
<button on:click={()=>(show=!show)}>
<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
    <path d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z" />
</svg>
</button>
</div>

<style>
    .quick-cart {
        @apply fixed rounded-md right-0 mt-5 mr-2 z-50 block p-5;
        @apply shadow-xl border-2 border-white bg-gradient-to-bl from-gray-300;
        backdrop-filter: blur(10px);
    }

    button:hover {
        @apply text-green-500;
    }
</style>