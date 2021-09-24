<script>
    export let change = false;
</script>

<div class="menu-bars" on:click class:change={change}>
    <div class="bar1"></div>
    <div class="bar2"></div>
    <div class="bar3"></div>
</div>

<style>
    .menu-bars {
        position: fixed;
        top: 1rem;
        right: 2rem;
        z-index: 10;
        display: inline;
        cursor: pointer;
    }

    .bar1,
    .bar2,
    .bar3 {
        width: 35px;
        height: 5px;
        background-color: #fff;
        margin: 6px 0;
        transition: 0.4s;
    }

    .change .bar1 {
        transform: rotate(-45deg) translate(-9px, 6px);
    }

    .change .bar2 {
        opacity: 0;
    }

    .change .bar3 {
        transform: rotate(45deg) translate(-8px, -8px);
    }
</style>