<script>
    import Header from './components/Header.svelte';
    import Hero from './components/Hero.svelte';
</script>

<svelte:head>
    <link rel="stylesheet" href="/node_modules/normalize.css/normalize.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
        href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap"
        rel="stylesheet"
    />
</svelte:head>

<Header />
<Hero />

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        background-color: var(--clr-background-primary);
    }

    :global(:root) {
        font-size: 16px;

        --clr-foreground-primary: #04d361;
        --clr-foreground-secondary: #f4f4f4;
        --clr-background-primary: #141414;
        --clr-background-secondary: #28282f;

        --font-family-primary: Roboto, sans-serif;
        --font-size-h1: 3.5rem;
        --font-size-h2: 3rem;
        --font-size-h3: 2.5rem;
        --font-size-h4: 2rem;
        --font-size-p1: 1.125rem;
        --font-size-p2: 1rem;
        --font-line-height: 1.5rem;
    }
</style>
