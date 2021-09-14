<script lang="ts">
    import supabase from "$lib/db";
    import GoogleIcon from "../atoms/GoogleIcon.svelte";
    export let mode;

    async function handleGoogle() {
        const { user, error } = await supabase.auth.signIn({
            provider: 'google'
        })
        if (error) { alert(error.message) }
        else { console.log(user) }
    }    
</script>

<button on:click={handleGoogle}>
    <div class="flex space-x-2 justify-center">
        <GoogleIcon/>
        <span>{mode} dengan google</span>
    </div>
</button>
    
<style lang="postcss">
button {
    @apply p-1 font-semibold;
    @apply border-2 rounded;
    @apply text-gray-500 border-gray-500;
    &:hover {
        @apply text-white bg-gray-500;
    }
}
</style>