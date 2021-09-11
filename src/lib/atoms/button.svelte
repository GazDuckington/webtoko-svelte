<script lang="ts">
    let link: string;
    let tipe: string = "primary";
    const inverse: boolean = false;
    
    export let href = link;
    export let type = tipe;
    export let accent = inverse;
</script>

{#if href}
    <a href={href} class={type}>
        <slot></slot>
    </a>
{:else}
    <button class={type} class:accent={accent}>
        <slot></slot>
    </button>
{/if}

<style>
    a, button {
        @apply font-semibold;
    }

    .primary {
        @apply bg-red-500 text-white; 
        @apply rounded-md p-1.5;
        &:hover {
            @apply bg-red-400;
        }
    }

    .secondary {
        @apply bg-green-500 text-white; 
        @apply rounded-md p-1.5;
        &:hover {
            @apply bg-green-400;
        }
    }

    .primary.accent {
        @apply text-red-500 bg-white border-red-500;
        @apply rounded-md p-1.5 border-2;
        &:hover {
            @apply bg-red-400 text-white border-red-400;
        }
    }
    .secondary.accent {
        @apply text-green-500 bg-white border-green-500;
        @apply rounded-md p-1.5 border-2;
        &:hover {
            @apply bg-green-400 text-white border-green-400;
        }
    }
</style>