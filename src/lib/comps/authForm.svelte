<script lang="ts">
    import {authClick} from "$lib/auth";
    import Button from "$lib/atoms/button.svelte";
    export let mode: string;
</script>

<div class="provider">
    <Button type="secondary" accent={true} on:click={()=>authClick(mode)}>
        {mode}
    </Button>
</div>

<style>
</style>