<script lang="ts">
    import {goto} from "$app/navigation"
    import Button from "$lib/atoms/button.svelte";
    import GoogleForm from "./googleForm.svelte";
    import supabase from "$lib/db";
    
    export let mode: string;
    let notif = "";
    let email, password;

    async function signin() {
        const { user, session:sesh, error } = await supabase.auth.signIn({
            email,
            password,
        })
        if (error) { alert(error.message) }
        else { goto('/')}
    }
    async function signup() {
        const { user, session: sesh, error } = await supabase.auth.signUp({
            email,
            password,
        })
        if (error) { alert(error.message) }
        else { goto('/') }
    }
</script>


{notif}

{#if mode == 'sign up'}
<div class="provider">
    <p class="pb-1">{mode} dengan akun google anda</p>
    <GoogleForm mode={mode}/>
    <form on:submit|preventDefault={signup}>
        <p>atau, gunakan email</p>
        <input bind:value={email} type="email" name="email" id="email" placeholder="email" required>
        <input bind:value={password} type="password" name="password" id="password" placeholder="password" required minlength="10">
        <div class="submit">
            <Button tp="secondary">
                {mode}
            </Button>
        </div>
    </form>
</div>
{:else if mode == 'sign in'}
<div class="provider">
    <p class="pb-1">{mode} dengan akun google anda</p>
    <GoogleForm mode={mode}/>
    <form on:submit|preventDefault={signin}>
        <p>atau, gunakan email</p>
        <input bind:value={email} type="email" name="email" id="email" placeholder="email" required>
        <input bind:value={password} type="password" name="password" id="password" placeholder="password" required minlength="10">
        <div class="submit">
            <Button tp="secondary">
                {mode}
            </Button>
        </div>
    </form>
</div>
{/if}

<style lang="postcss">
    .submit {
        @apply text-right;
    }
    form, .provider {
        @apply flex flex-col space-y-2;
    }

    form {
        @apply border-2 rounded p-1;
    }

    input {
        @apply items-center border-2 rounded p-1.5 pt-0.5;
    }
</style>