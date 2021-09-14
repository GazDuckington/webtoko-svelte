<script>
</script>
    <div class="modal">
        <slot></slot>
    </div>

<style lang="postcss">
    .modal {
        @apply bg-gray-500 bg-opacity-30 w-full h-full fixed;
        backdrop-filter: blur(20px);
    }
</style>