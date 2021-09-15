<script>
import Button from "$lib/atoms/button.svelte";
import MenuUser from "$lib/atoms/menuUser.svelte";
import Title from "$lib/atoms/title.svelte";
import {products} from "$lib/db";

// products.subscribe((value) => {value});
</script>

<svelte:head>
    <title>Home</title>
</svelte:head>

<Title>
    Gradient Title
</Title>

<MenuUser/>
 <Button>Test</Button>
<!-- {#each $products as p}
{p}
{/each} -->