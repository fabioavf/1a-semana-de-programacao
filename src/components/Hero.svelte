<script>
    import * as animateScroll from 'svelte-scrollto';

    import Carousel from '@beyonk/svelte-carousel';
    import EnrollButton from './EnrollButton.svelte';

    let backgroundImage = {
        src: '/assets/img/mountains.png',
        alt: 'Montanhas em pixel art',
    };
    let eventList = [
        {
            img: {
                src: '/assets/img/logo-byron-square.png',
                alt: 'Imagem Evento 1',
            },
            title: 'HTML / CSS / JS',
        },
        {
            img: {
                src: '/assets/img/logo-blackbee.png',
                alt: 'Imagem Evento 2',
            },
            title: 'Python',
        },
        {
            img: {
                src: '/assets/img/logo-devu.png',
                alt: 'Imagem Evento 3',
            },
            title: 'C# e Unity',
        },
        {
            img: {
                src: '/assets/img/logo-maratona.png',
                alt: 'Imagem Evento 4',
            },
            title: 'C++',
        },
    ];
</script>

<div class="bg-container">
    <div class="container">
        <div class="heading">
            <div class="heading-right">
                <h1 class="heading-title">De 01 a 05 de Novembro!</h1>
            </div>
            <div class="heading-left">
                <h1 class="heading-title">Faça parte dessa evolução!</h1>
                <p class="heading-subtitle">
                    Se atualize com a evolução da tecnologia! Será uma semana de
                    aprendizados em desenvolvimento web, visão computacional,
                    programação em jogos e maratona de programação!
                </p>
            </div>
        </div>

        <div class="events-wrapper">
            <div class="events-section">
                <ul class="events-list">
                    {#each eventList as event}
                        <button
                            on:click={() =>
                                animateScroll.scrollTo({
                                    element: '#schedule',
                                    offset: -60,
                                })}
                            class="event drop-shadow"
                        >
                            <div class="img-wrapper">
                                <img src={event.img.src} alt={event.img.alt} />
                            </div>
                            <p>{event.title}</p>
                        </button>
                    {/each}
                </ul>
            </div>
            <EnrollButton text="Conheça nossa programação!" />
        </div>
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;

        max-width: 45rem;

        margin: 2rem 1.5rem;
        /* margin-bottom: 2rem; */
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

    .heading-left,
    .heading-right {
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
        border: none;
        cursor: pointer;
        min-width: 16rem;

        color: var(--clr-foreground-secondary);
        background-color: var(--clr-foreground-primary);
        border-radius: 0.5rem;
        padding: 1rem 1.5rem;
        text-align: center;
        line-height: 150%;
        transition: 200ms;
    }

    .event:focus,
    .event:hover {
        background-color: var(--clr-foreground-primary-darker);
    }

    .events-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .img-wrapper {
        background-color: var(--clr-background-primary);
        border-radius: 0.25rem;
        height: 5.75rem;
        width: 5.75rem;
        position: relative;
    }

    .img-wrapper > img {
        border-radius: 0.25rem;
        width: 100%;
        position: absolute;
        inset: 0;
    }

    .event > p {
        font-weight: 500;
    }

    .events-section {
        margin-bottom: 1rem;
    }

    @media only screen and (min-width: 768px) {
        .heading {
            text-align: left;
            padding: 0;
        }

        .heading-left,
        .heading-right {
            text-align: left;
        }

        .container {
            width: 100%;
        }
        .events-list {
            grid-template-columns: 1fr 1fr;
        }
    }

    @media only screen and (min-width: 1368px) {
        .heading {
            width: 100%;
            flex-direction: row-reverse;
            align-self: baseline;
        }

        .heading-left {
            max-width: 37.5rem;
        }

        .container {
            height: 40rem;
            max-width: 75rem;

            justify-content: space-around;
        }
        .bg-container {
            display: flex;
            flex-direction: column;
            align-items: center;

            width: 100%;
            background-image: url(/assets/img/mountains.png);
            background-repeat: no-repeat;
            background-size: contain;
            background-position: bottom;
        }
        .events-list {
            grid-template-columns: 1fr 1fr 1fr 1fr;
            /* background-color: var(--clr-foreground-primary); */
        }

        .event {
            flex-direction: row;
            justify-content: flex-start;
            /* width: 15rem; */

            text-align: left;
        }
    }
</style>
