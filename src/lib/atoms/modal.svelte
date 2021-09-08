<div class="modal">
    <slot></slot>
</div>

<style>
    .modal {
        @apply bg-gray-800 bg-opacity-30 w-full h-full fixed;
        backdrop-filter: blur(20px);
    }
</style>