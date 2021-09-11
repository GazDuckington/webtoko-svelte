<script>
    import GoogleIcon from "../atoms/GoogleIcon.svelte";
    export let mode;
</script>

<button on:click={()=>authClickGoogle(mode)}>
    <div class="flex space-x-2 justify-center">
        <GoogleIcon/>
        <span>{mode} dengan google</span>
    </div>
</button>
    
<style>
button {
    @apply p-1 font-semibold;
    @apply border-2 rounded;
    @apply text-gray-500 border-gray-500;
    &:hover {
        @apply text-white bg-gray-500;
    }
}
</style>