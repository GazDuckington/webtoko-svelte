<script>
    let href;
</script>
<a href={href} {...$$restProps}>
    <slot></slot>
</a>

<style>
    a {
        @apply bg-clip-text;
    }
    a:hover{
        @apply text-transparent bg-gradient-to-tr from-green-500 to-blue-500;
    }
</style>