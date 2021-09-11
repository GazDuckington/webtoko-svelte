<script>
    import AuthForm from "$lib/comps/authForm.svelte";
    import GoogleForm from "$lib/comps/googleForm.svelte";

    export let view = "sign in" || "sign up";
</script>

<dev class="wrapper">
    <p class="left-0">{view} with your google account</p>
    <GoogleForm mode={view}/>
    <AuthForm mode={view}/>
</dev>

<style>
    .wrapper {
        @apply flex flex-col items-center;
    }
</style>