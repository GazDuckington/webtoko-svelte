<script>
    let href;
</script>
<a href={href} {...$$restProps}>
    <slot></slot>
</a>

<style>
    a {
        @apply font-mono;
        @apply bg-gradient-to-tr from-green-500 to-blue-500;
        font-size: 12px;
        text-decoration: none;
        background-repeat: no-repeat;
        background-position: bottom left;
        background-size: 0% 3px;
        transition: background-size 500ms ease-in-out;
    }
    a:hover{
        background-size: 100% 3px;
        color: inherit;
    }
</style>