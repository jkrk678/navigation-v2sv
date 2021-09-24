<nav>
    <ul>
        <slot></slot>
    </ul>
</nav>

<style>
    nav, ul {
        height: 100vh;
        margin: 0;
        padding: 0;
    }

    ul {
        display: flex;
        flex-direction: column;
        justify-content: stretch;
        list-style: none;
    }
</style>