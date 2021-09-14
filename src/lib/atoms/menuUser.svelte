<script>
import { user } from "$lib/db";
import Button from "./button.svelte";
import Linky from "./linky.svelte";

</script>

{#if $user}
    <Linky href="profile">Profile</Linky>
    <Button href="logout">Logout</Button>
{:else}
    <Linky href="signin">Sign In</Linky>
    <Linky href="signup">Sign Up</Linky>
{/if}