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
    <div></div>
</li>
{/if}

<style>
    li {
        position: relative;
    }

    a {
        color: #fff;
        text-transform: uppercase;
        letter-spacing: 4px;
        text-decoration: none;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
        transition-duration: 250ms;
    }

    a:hover {
        letter-spacing: 8px;
        transition-duration: 500ms;
    }

    div {
        /* content: ""; */
        width: 25vw;
        height: 2px;
        background-color: #fff;
        position: absolute;
        top: 50%;
        left: 0;
        transform: scaleX(0);
        transition: 500ms ease-in-out;
        transform-origin: left;
    }

    a:hover + div {
        transform: scaleX(1);
        transition: 250ms ease-in-out;
    }
</style>