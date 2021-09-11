<script>
    import Linky from "$lib/atoms/linky.svelte";
    import AuthForm from "$lib/comps/authForm.svelte";

    export let view = "sign in" || "sign up";
</script>

<dev class="wrapper">
    <div>
        <AuthForm mode={view}/>
    </div>

    <div>
        {#if view == "sign in"}
        <Linky href="signup">belum punya akun?</Linky>
        {:else}
        <Linky href="signin">sudah punya akun?</Linky>
        {/if}
    </div>
</dev>

<style>
    .wrapper {
        @apply p-1 rounded m-20;
        @apply flex flex-col items-center space-y-1;
    }
</style>