<script lang="ts">
    import {goto} from "$app/navigation"
    import Button from "$lib/atoms/button.svelte";
    import GoogleForm from "./googleForm.svelte";
    
    export let mode: string;

    async function signin(e) {
        const res = await fetch("/api/signin", {
            method: 'post',
            body: new FormData(e.target)
        })
        if (res.ok) {goto('/') }
        else { alert(await res.text()) }
    }
    async function signup(e) {
        const res = await fetch("/signup", {
            method: 'post',
            body: new FormData(e.target)
        })
        if (res.ok) { goto('/') }
        else { alert(await res.text()) }
    }
</script>

{#if mode == 'sign up'}
<div class="provider">
    <p class="pb-1">{mode} dengan akun google anda</p>
    <GoogleForm mode={mode}/>
    <form on:submit|preventDefault={signup}>
        <p>atau, gunakan email</p>
        <input type="email" name="email" id="email" placeholder="email" required>
        <input type="password" name="password" id="password" placeholder="password" required minlength="10">
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
    <form on:submit|preventDefault={()=>signin}>
        <p>atau, gunakan email</p>
        <input type="email" name="email" id="email" placeholder="email" required>
        <input type="password" name="password" id="password" placeholder="password" required minlength="10">
        <div class="submit">
            <Button tp="secondary">
                {mode}
            </Button>
        </div>
    </form>
</div>
{/if}

<style>
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