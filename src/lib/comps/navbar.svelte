<script>
import Linky from "$lib/atoms/linky.svelte";

    import Logo from "$lib/atoms/logo.svelte";
    import Modal from "$lib/atoms/modal.svelte";
    import {slide} from "svelte/transition";

    let qcart = false;
    let show = false;
    function toggle(){
        if (show) {
            show = false;
        } else {
            show = true;
        }
    }

    function qCart(){
        if (qcart) {
            qcart = false;
        } else {
            qcart = true;
        }
    }
</script>

<div class="navbar">
    <div class="navlogo">
        <Logo/>
    </div>
    <div class="menus">
        <div class="primary">
            <a href="signin">Sign In</a>
            <a href="signup">Sign Up</a>
            <a href="blog">Blog</a>
        </div>
        <div class="cart">
            <button on:click={qCart}>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z" />
                </svg>
            </button>
        </div>
    </div>
</div>
{#if show}
    <div class="mobile" transition:slide={{duration:300}}>
        <div class="mobile-menu flex flex-col">
            <Logo/>
            <p class="subtitle">Accounts</p>
            <div class="hl"></div>
            <Linky href="signin">Sign In</Linky>
            <Linky href="signup">Sign Up</Linky>
            <p class="subtitle">Miscellaneous</p>
            <div class="hl"></div>
            <Linky href="blog">Blog</Linky>
        </div>
    </div>
{/if}
<!-- mobile menu button -->
<button class="burger" on:click="{toggle}">
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

<!-- quick cart -->
{#if qcart}
    <Modal>
        <div class="quick-cart rounded">
            <div class="flex justify-between p-1  bg-gradient-to-r from-green-500">
                <h1 class="text-white">Cart</h1>
                <button class="text-red-500" on:click={qCart}>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.707 7.293a1 1 0 00-1.414 1.414L8.586 10l-1.293 1.293a1 1 0 101.414 1.414L10 11.414l1.293 1.293a1 1 0 001.414-1.414L11.414 10l1.293-1.293a1 1 0 00-1.414-1.414L10 8.586 8.707 7.293z" clip-rule="evenodd" />
                </svg>
                </button>
            </div>
            <div class="cart-view p-2">
                <ul>
                    <li>something for nothing</li>
                    <li>something for nothing</li>
                    <li>something for nothing</li>
                </ul>
            </div>
        </div>
    </Modal>
{/if}
<style>
    .quick-cart {
        @apply max-w-full mx-48 my-10 flex flex-col justify-between shadow-2xl;
        @apply bg-white;
    }
    .quick-cart h1 {
        @apply font-semibold;
    }
    .hl {
        @apply h-1 w-full bg-gradient-to-r from-blue-500;
    }
    .mobile {
        @apply fixed border-2 rounded-md bottom-4 right-4 z-50 block p-5;
        @apply shadow-xl bg-gradient-to-br from-gray-300;
        height: 93%;
        width: 95.5%;
        backdrop-filter: blur(10px);
    }

    .mobile-menu {
        @apply h-full overflow-scroll;
    }

   ::-webkit-scrollbar {
      @apply h-1 w-1;
   }

   ::-webkit-scrollbar-track {
   }

   ::-webkit-scrollbar-thumb {
       @apply bg-gray-500;
   }

    .burger {
        @apply border-2 p-1 rounded-md fixed z-50 bottom-4 right-4 w-8 h-8 block md:hidden;
        @apply bg-gradient-to-tl from-gray-300 shadow-sm;
    }

    .navbar {
        @apply p-2 pb-0;
        @apply flex rounded-t-md space-x-1 justify-between sticky w-full;
        @apply shadow-sm font-semibold bg-white;
    }

    .primary {
        @apply hidden md:flex md:space-x-1;
    }

    .menus {
        @apply flex space-x-1;
    }

    .subtitle {
        @apply font-semibold py-1 text-gray-800;
    }

    .cart:hover {
        @apply text-green-500;
    }
</style>