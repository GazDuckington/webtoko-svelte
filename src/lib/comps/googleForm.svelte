<script>
    import {authClickGoogle} from "$lib/auth";
    import GoogleIcon from "../atoms/GoogleIcon.svelte";
    export let mode;
</script>

<button on:click={()=>authClickGoogle(mode)}>
    <div><GoogleIcon/></div>
    <div>{mode}</div>
</button>

<style>
    button {
        @apply flex align-middle space-x-2 p-2 font-bold;
        @apply border-2 border-gray-500 rounded text-gray-500;
    }
    button:hover {
        @apply bg-gray-500 text-white;
    }

</style>