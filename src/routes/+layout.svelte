<main>
    <slot>

    </slot>
    <nav>
        <ul>
            <li>
                <a href="/">Home</a>
                <a href="/child-scroll">Child Scroll</a>
            </li>
        </ul>
    </nav>
</main>

<style>
    nav {
        position: fixed;
        bottom: 0;
    }
</style>