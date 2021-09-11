<script>
  import "../app.postcss";
  import Navbar from "$lib/comps/navbar.svelte";
</script>

<div class="body">
    <!-- navigation bar -->
    <div class="navbar">
        <Navbar />
    </div>
    <!-- content -->
    <div class="content">
        <slot />
    </div>
</div>

<!-- footer -->
<div class="footer" />

<style>
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
