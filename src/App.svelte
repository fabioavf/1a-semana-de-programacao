<script>
    import Header from './components/Header.svelte';
    import Hero from './components/Hero.svelte';
    import AboutUs from './components/AboutUs.svelte';
    import Footer from './components/Footer.svelte';
    import Schedule from './components/Schedule.svelte';

    let y;

    $: console.log(y);
</script>

<svelte:window bind:scrollY={y} />

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
        href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap"
        rel="stylesheet"
    />
</svelte:head>

<Header />
<Hero />
<AboutUs />
<Schedule />
<Footer />

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        background-color: var(--clr-background-primary);
        /* overflow: hidden; */
        overflow-x: hidden;
    }

    :global(:root) {
        font-size: 16px;

        --clr-foreground-primary: #04d361;
        --clr-foreground-primary-lighter: #b0eaaa;
        --clr-foreground-primary-darker: #282c35;
        --clr-foreground-secondary: #d7d4d4;
        --clr-foreground-secondary-faded: #737373;

        --clr-background-primary: #242424;
        --clr-background-secondary: #28282f;
        --clr-background-terciary: #0b0911;

        --font-family-primary: Roboto, sans-serif;
        --font-size-h1: 3.5rem;
        --font-size-h2: 3rem;
        --font-size-h3: 2rem;
        --font-size-h4: 1.5rem;
        --font-size-p1: 1.125rem;
        --font-size-p2: 1rem;
        --font-line-height: 1.5rem;
    }
</style>
