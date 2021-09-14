<script>
    import Logo from "$lib/atoms/logo.svelte";
    import {fly} from "svelte/transition";
    import Linky from "$lib/atoms/linky.svelte";
    import MenuUser from "$lib/atoms/menuUser.svelte";

    let show = false;
</script>

{#if show}
    <div class="mobile" on:click={()=>(show=!show)}
         transition:fly={{x:250}}
         >
        <div class="mobile-menu">
            <Logo/>
            <p class="subtitle">Cart</p>
            <p class="subtitle">Accounts</p>
            <div class="hl"></div>
            <MenuUser/>
            <p class="subtitle">Miscellaneous</p>
            <div class="hl"></div>
            <Linky href="blog">Blog</Linky>
        </div>
    </div>
{/if}
<!-- mobile menu button -->
<button class="burger" on:click="{()=>(show=!show)}">
    {#if show}
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd" />
        </svg>
    {:else}
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd" />
        </svg>
    {/if}
</button>

<style lang="postcss">
    .burger {
        @apply border-2 p-1 rounded-md fixed z-50 bottom-4 right-4 w-8 h-8 block md:hidden;
        @apply bg-gray-100 border-gray-500 shadow-sm;
        @apply text-gray-500;
    }

    .mobile {
        @apply w-3/4 h-full bottom-0;
        @apply fixed right-0 block p-2;
        @apply shadow-xl border-l-2 border-gray-500 bg-white;
    }

    .mobile-menu {
        @apply flex flex-col;
        @apply h-full overflow-hidden;
    }

    .subtitle {
        @apply font-semibold py-1 text-gray-800;
    }
</style>