<script>
    import { fly } from 'svelte/transition'
    export let href;
    export let title;
    export let flyIn;
    export let flyOut;
    export let visible = false;
</script>

{#if visible}
<li in:fly={flyIn} out:fly={flyOut}>
    <a {href} on:click>{title}</a>
</li>
{/if}

<style>
    a {
        color: #fff;
        text-transform: uppercase;
        letter-spacing: 4px;
        text-decoration: none;
        display: block;
        text-align: center;
        position: relative;
        top: 47.5%;
        transition-duration: 250ms;
    }

    a:hover {
        letter-spacing: 8px;
        transition-duration: 500ms;
    }

    a::before {
        content: "";
        width: 25vw;
        height: 2px;
        background-color: #fff;
        position: absolute;
        top: 47.5%;
        left: 0;
        transform: scaleX(0);
        transition: 500ms ease-in-out;
        transform-origin: left;
    }

    a:hover::before {
        transform: scaleX(1);
        transition: 250ms ease-in-out;
    }
</style>