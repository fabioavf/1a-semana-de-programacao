<script>
    import Carousel from '@beyonk/svelte-carousel';
    import EnrollButton from './EnrollButton.svelte';

    let backgroundImage = {
        src: '/assets/img/mountains.png',
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

<div class="container" style="--background-url: url({backgroundImage.src});">
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
                <li class="event drop-shadow">
                    <div class="img-wrapper">
                        <img src={event.img.src} alt={event.img.alt} />
                    </div>
                    <p>{event.title}</p>
                </li>
            {/each}
        </ul>
    </div>

    <EnrollButton text="Inscreva-se!" />
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;

        padding-top: 8rem;
        margin-bottom: 2rem;
    }

    .heading {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 1rem;

        padding: 0 1.5rem;
        text-align: center;
        margin-bottom: 3rem;
    }

    .heading-title {
        font-size: var(--font-size-h1-mobile);
        font-weight: var(--font-weight-h1);
    }

    .heading-subtitle {
        font-size: var(--font-size-p-mobile);
        line-height: var(--font-line-height);
    }

    .events-list {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: auto;
        gap: 1rem;
    }

    .event {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 1rem;

        background-color: var(--clr-foreground-primary);
        border-radius: 0.5rem;
        padding: 1rem 1.5rem;
        text-align: center;
        line-height: 150%;
    }

    .img-wrapper {
        background-color: var(--clr-background-primary);
        border-radius: 0.25rem;
    }

    .img-wrapper > img {
        padding: 1rem;
    }

    .event > p {
        font-weight: 500;
    }

    .events-section {
        margin-bottom: 1rem;
    }

    @media only screen and (min-width: 768px) {
        /* .container {
            padding-left: 10rem;
            padding-right: 10rem;
        } */
        /* .heading-title {
            text-align: left;
        } */
        .events-list {
            grid-template-columns: 1fr 1fr;
        }
    }
</style>
