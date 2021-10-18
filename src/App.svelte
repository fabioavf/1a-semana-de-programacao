<script>
    import Header from './components/Header.svelte';
    import Hero from './components/Hero.svelte';
    import AboutUs from './components/AboutUs.svelte';
    import Footer from './components/Footer.svelte';
    import Schedule from './components/Schedule.svelte';
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
        href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap"
        rel="stylesheet"
    />
    <link
        rel="stylesheet"
        href="https://meyerweb.com/eric/tools/css/reset/reset.css"
    />
</svelte:head>

<Header />
<Hero />
<AboutUs />
<Schedule />

<!-- <Footer /> -->
<style>
    :global(body) {
        background-color: var(--clr-background-primary);
    }

    :global(:root) {
        --clr-foreground-primary: #47729d;
        --clr-foreground-primary-lighter: #5f98d2;
        --clr-foreground-primary-darker: #283f57;
        --clr-foreground-secondary: #f5f4f4;
        --clr-foreground-secondary-faded: #737373;

        --clr-background-primary: #242424;
        --clr-background-secondary: #28282f;
        --clr-background-terciary: #0b0911;

        --font-family-primary: Montserrat, sans-serif;
        --font-size-h1: 3.5rem;
        --font-size-h2: 3rem;
        --font-size-h3: 2rem;
        --font-size-h4: 1.5rem;
        --font-size-p1: 1.125rem;
        --font-size-p2: 1rem;
        --font-size-h1-mobile: 2rem;
        --font-size-h2-mobile: 1.5rem;
        --font-size-p-mobile: 1rem;
        --font-weight-h1: 700;
        --font-line-height: 1.5rem;

        font-family: var(--font-family-primary);
        font-weight: 400;
        font-size: 16px;
        line-height: var(--font-line-height);
    }

    :global(body) {
        color: var(--clr-foreground-secondary);
    }

    :global(.drop-shadow) {
        filter: drop-shadow(0 0 0.25rem hsla(0, 0%, 0%, 0.5));
    }
</style>
