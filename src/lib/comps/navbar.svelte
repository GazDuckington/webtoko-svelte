<script>
    import Linky from "$lib/atoms/linky.svelte";
    import Logo from "$lib/atoms/logo.svelte";
import MenuUser from "$lib/atoms/menuUser.svelte";
    import Mobile from "./mobile.svelte";
    import QuickCart from "./quickCart.svelte";
</script>


<div class="navbar">
    <div class="navlogo">
        <Logo/>
    </div>
    <div class="menus">
        <div class="primary">
            <MenuUser/>
        </div>
        <div class="cart">
           <QuickCart/>
        </div>
    </div>
</div>
<Mobile/>

<style lang="postcss">

    .navbar {
        @apply p-2 fixed w-full;
        @apply flex space-x-1 justify-between;
        @apply shadow-sm bg-white;
    }
    .primary {
        @apply hidden md:flex gap-1;
    }

    .menus {
        @apply flex space-x-1;
    }

</style>