<script>
    import Header from './components/Header.svelte';
    import Hero from './components/Hero.svelte';
    import AboutUs from './components/AboutUs.svelte';
    import Footer from './components/Footer.svelte';
    import Schedule from './components/Schedule.svelte';
    import Form from './components/Form.svelte';
</script>

<Header />
<Hero />
<AboutUs />
<Schedule />
<!-- <Form /> -->
<Footer />

<style>
    :global(body) {
        background-color: var(--clr-background-primary);

        display: flex;
        flex-direction: column;
        align-items: center;
    }

    :global(:root) {
        --clr-foreground-primary: #2871bb;
        --clr-foreground-primary-lighter: #3697fb;
        --clr-foreground-primary-darker: #173e67;
        --clr-foreground-secondary: #f5f3f3;
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
