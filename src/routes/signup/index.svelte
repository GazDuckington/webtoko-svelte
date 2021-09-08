<script>
    import supabase from "$lib/db";

    let email, password;
    async function signUp() {
        const { user, session, error } =
        await supabase.auth.signUp({
            email,
            password
        })
        if (error) alert(error.message)
    }
</script>
<svelte:head>
    <title>Sign Up</title>
</svelte:head>
signup page