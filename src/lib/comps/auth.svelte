<script>
    import Linky from "$lib/atoms/linky.svelte";
    import AuthForm from "$lib/comps/authForm.svelte";
    import {user} from "$lib/db";

    export let view = "sign in" || "sign up";
</script>

{#if $user}
    <h1>you are already logged in</h1>
{:else}

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

{/if}

<style lang="postcss">
    .wrapper {
        @apply p-1 rounded m-20;
        @apply flex flex-col items-center space-y-1;
    }
</style>