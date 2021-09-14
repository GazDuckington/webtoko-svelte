<h1>
   <slot></slot>
</h1>

<style lang="postcss">
    @keyframes bg-animation {
        0% {background-position: left}
        50% {background-position: right}
        100% {background-position: left}
    }
    h1 {
        @apply text-transparent bg-clip-text font-black;
        @apply bg-gradient-to-tr from-purple-500 via-pink-500 to-yellow-500;
        margin: 0 0 .5em;
        text-transform: uppercase;
        font-size: 3rem;
        background-size: 300%;
        transition: background-position 1s;
        line-height: .8;
        margin: 0;
        /* animation: bg-animation 25s infinite alternate; */
    }
    h1:hover {
        background-position: right;
    }
</style>