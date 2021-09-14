<script>
    import "../app.postcss";
    import Navbar from "$lib/comps/navbar.svelte";
    import supabase from "$lib/db";
    import { session } from "$app/stores";
    import { user } from "$lib/db";
    import {browser} from "$app/env";

    // supabase.auth.onAuthStateChange((event, sesh) => {
    //     $session = sesh;
    // })
    $: console.log($session)
</script>

<div class="body">
    <!-- navigation bar -->
    <div class="navbar">
        <Navbar />
    </div>
    <!-- content -->
    <div class="content">
        <slot />
        <p>
            {JSON.stringify($user)}
        </p>

    <p class="w-96 overflow-scroll">
        {JSON.stringify($session)}
    </p>
    </div>
</div>

<!-- footer -->
<div class="footer" />

<style lang="postcss">
    .navbar {
        @apply w-full;
    }
    .body {
        @apply flex flex-col static;
        @apply bg-gradient-to-tr from-green-500 to-blue-300;
        background-size: 300%;
        animation: bg-animation 25s infinite alternate;
    }
    .content {
        @apply h-screen bg-white rounded-b pt-12;
        background-filter: blur(30px);
    }

</style>
