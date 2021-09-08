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
    <div class="bg">
        <div class="content">
            <slot />
        </div>
    </div>
</div>

<!-- footer -->
<div class="footer" />

<style>
    @keyframes bg-animation {
        0% {background-position: left}
        50% {background-position: right}
        100% {background-position: left}
    }
    .bg {
        @apply w-full h-full p-1 pt-11;
        @apply bg-gradient-to-tr from-green-500 to-blue-300;
        background-size: 300%;
        animation: bg-animation 5s infinite;
    }
    .navbar {
        @apply fixed w-full p-1;
    }
    .body {
        @apply flex flex-col;
    }
    .content {
        @apply h-screen bg-white p-1 rounded-b;
        /* background-image: url(/2159510.jpg); */
        background-position: center;
        background-size: 155%;
    }

</style>
