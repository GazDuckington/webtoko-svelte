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

<!-- navigation bar -->
<div class="navbar">
    <Navbar />
</div>

<div class="body">    
    <!-- content -->
    <div class="content">
        <slot />
        <p>
        </p>

    <p class="w-96 overflow-scroll">
        {JSON.stringify($user)}
    </p>
    </div>
</div>

<!-- footer -->
<div class="footer" />

<style lang="postcss">
    .body {
        @apply flex flex-col static p-1;
        @apply bg-gradient-to-tr from-green-500 to-blue-300;
        background-size: 300%;
        animation: bg-animation 25s infinite alternate;
    }
    .content {
        @apply h-screen bg-white rounded mt-10 p-1;
        background-filter: blur(30px);
    }

</style>
