<script>
import Linky from "$lib/atoms/linky.svelte";

    import AuthForm from "$lib/comps/authForm.svelte";
    import GoogleForm from "$lib/comps/googleForm.svelte";

    export let view = "sign in" || "sign up";
</script>

<dev class="wrapper">
    <p class="left-0">{view} dengan akun google anda</p>
    <GoogleForm mode={view}/>

    <AuthForm mode={view}/>

    {#if view == "sign in"}
        <Linky href="signup">belum punya akun?</Linky>
    {:else}
        <Linky href="signin">sudah punya akun?</Linky>
    {/if}
</dev>

<style>
    .wrapper {
        @apply flex flex-col items-center;
    }
    p::after, p::before {
        content: "";
    }
</style>