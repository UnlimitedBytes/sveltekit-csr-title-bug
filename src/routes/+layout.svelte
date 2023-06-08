<script>
    import { page } from '$app/stores';
    let defaultLink = false;
</script>

<ul data-sveltekit-reload={defaultLink ? '' : 'off'}>
    <li class:active={$page.url.pathname === '/'}>
        <a href="/">Home</a>
    </li>

    <li class:active={$page.url.pathname === '/about'}>
        <a href="/about">About</a>
    </li>
</ul>

<main>
    <slot />
</main>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        background: #222;
        color: #fff;
        font-family: sans-serif;
    }

    ul {
        display: flex;
        width: 100%;
        background: #111;
        list-style: none;
        padding: 0;
        margin: 0;
    }

    li {
        color: inherit;
    }

    a {
        display: inline-block;
        text-decoration: none;
        color: inherit;
        padding: 1rem;
    }

    li.active a {
        background: #222;
    }

    main {
        max-width: 600px;
        padding: 0 1rem;
    }
</style>
