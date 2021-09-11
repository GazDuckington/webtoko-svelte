<script lang="ts">
    import {authClick} from "$lib/auth";
    import Button from "$lib/atoms/button.svelte";
import GoogleForm from "./googleForm.svelte";
    export let mode: string;
</script>

<div class="provider">
    <p class="pb-1">{mode} dengan akun google anda</p>
    <GoogleForm mode={mode}/>
    <form on:submit|preventDefault={()=>authClick(mode)}>
        <p>atau, gunakan email</p>
        <input type="email" name="email" placeholder="email" required>
        <input type="password" name="password" placeholder="password" required minlength="10">
        <div class="submit">
            <Button tp="secondary">
                {mode}
            </Button>
        </div>
    </form>
</div>

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