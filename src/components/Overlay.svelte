<script>
    import { fade } from 'svelte/transition'
    export let overlay = false;
</script>

{#if overlay}
<div in:fade={{duration: 400}} out:fade={{duration: 800, delay:300}}>
    <slot></slot>
</div>
{/if}

<style>
    div {
        position: fixed;
        z-index: 9;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.7);
    }
</style>