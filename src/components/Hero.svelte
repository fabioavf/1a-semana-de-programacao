<script>
    import Carousel from '@beyonk/svelte-carousel';

    let backgroundImage = {
        src: '/public/assets/img/mountains.png',
        alt: 'Montanhas em pixel art',
    };
    let eventList = [
        {
            img: {
                src: '/assets/img/movie-ticket.svg',
                alt: 'Imagem Evento 1',
            },
            title: 'HTML / CSS / JS básico',
        },
        {
            img: {
                src: '/assets/img/movie-ticket.svg',
                alt: 'Imagem Evento 2',
            },
            title: 'Python',
        },
        {
            img: {
                src: '/assets/img/movie-ticket.svg',
                alt: 'Imagem Evento 3',
            },
            title: 'C# e Unity',
        },
        {
            img: {
                src: '/assets/img/movie-ticket.svg',
                alt: 'Imagem Evento 4',
            },
            title: 'Maratona de Programação',
        },
    ];

    let width;

    $: console.log(width);
</script>

<svelte:window bind:outerWidth={width} />

<div class="container">
    <div class="heading">
        <h1 class="heading-title">
            Seu ecossistema para aprender e evoluir na programação
        </h1>
        <p class="heading-subtitle">
            Embarque no foguete com milhares de devs para aprender
            desenvolvimento web, evoluir de forma contínua e se manter relevante
            no mercado.
        </p>
    </div>

    <div class="events-section">
        <ul class="events-list">
            {#each eventList as event}
                <li class="event">
                    <div class="img-wrapper">
                        <img src={event.img.src} alt={event.img.alt} />
                    </div>
                    <p>{event.title}</p>
                </li>
            {/each}
        </ul>
    </div>
</div>

<style>
    .container {
        padding: 3rem 8.75rem;
        /* height: 100vh; */
        background-image: url(/assets/img/mountains.png);
        background-size: contain;
        background-repeat: no-repeat;
        background-position: bottom;
    }

    .heading {
        margin-top: 6rem;

        max-width: 600px;

        font-family: var(--font-family-primary);
        color: var(--clr-foreground-secondary);
    }

    .heading-title {
        font-size: var(--font-size-h1);
    }

    .heading-subtitle {
        font-size: var(--font-size-p1);
        line-height: 1.5em;
    }

    .events-section {
        margin: 4rem auto;
        background-color: var(--clr-foreground-primary);
        border-radius: 6px;
        min-height: 9rem;
        width: fit-content;
        display: flex;
        align-items: center;
    }

    .events-list {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 1fr 1fr 1fr 1fr;

        justify-content: center;
        align-items: center;
        gap: 3rem;
        padding: 1rem 2rem;
    }

    .event {
        list-style: none;
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 1.5rem;
        color: var(--clr-foreground-secondary);
    }

    .event > p {
        font-weight: 500;
        color: var(--clr-background-primary);
    }

    .img-wrapper {
        aspect-ratio: 1 / 1;
        width: 6rem;
        height: 6rem;
        border-radius: 0.25rem;
        background-color: var(--clr-background-primary);

        display: flex;
        justify-content: center;
        align-items: center;
    }

    .img-wrapper > img {
        width: 3.5rem;
    }

    @media only screen and (min-width: 1440px) {
        .events-list {
            grid-template-columns: 1fr 1fr 1fr 1fr;
            grid-template-rows: 1fr;
        }
    }

    @media only screen and (min-width: 768px) and (max-width: 1439px) {
        .events-list {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: 1fr 1fr;
        }
    }
</style>
