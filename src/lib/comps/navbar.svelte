<script>
    import Linky from "$lib/atoms/linky.svelte";
    import Logo from "$lib/atoms/logo.svelte";
    import Mobile from "./mobile.svelte";
import QuickCart from "./quickCart.svelte";
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
           <QuickCart/>
        </div>
    </div>
</div>
<Mobile/>

<style lang="postcss">

    .navbar {
        @apply p-2 fixed w-full;
        @apply flex space-x-1 justify-between;
        @apply shadow-sm font-semibold bg-white;
    }
    .primary {
        @apply hidden md:flex md:space-x-1;
    }

    .menus {
        @apply flex space-x-1;
    }

</style>