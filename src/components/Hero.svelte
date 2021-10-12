<script>
    let backgroundImage = {
        src: '/public/assets/img/mountains.png',
        alt: 'Montanhas em pixel art',
    };
    let eventList = [
        {
            img: { src: 'http://picsum.photos/80', alt: 'Imagem Evento 1' },
            title: 'Evento 1',
        },
        {
            img: { src: 'http://picsum.photos/80', alt: 'Imagem Evento 2' },
            title: 'Evento 2',
        },
        {
            img: { src: 'http://picsum.photos/80', alt: 'Imagem Evento 3' },
            title: 'Evento 3',
        },
        {
            img: { src: 'http://picsum.photos/80', alt: 'Imagem Evento 4' },
            title: 'Evento 4',
        },
    ];
</script>

<div class="container">
    <div class="heading">
        <h1>Seu ecossistema para aprender e evoluir na programação</h1>
        <p>
            Embarque no foguete com milhares de devs para aprender
            desenvolvimento web, evoluir de forma contínua e se manter relevante
            no mercado.
        </p>
    </div>

    <div class="events-list">
        <ul>
            {#each eventList as event}
                <li>
                    <img src={event.img.src} alt={event.img.alt} />
                    <p>{event.title}</p>
                </li>
            {/each}
        </ul>
    </div>
</div>

<style>
    .container {
        padding: 3rem 8.75rem;
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

    .heading > h1 {
        font-size: var(--font-size-h1);
    }

    .heading > p {
        font-size: var(--font-size-p1);
        line-height: 1.5em;
    }

    .events-list {
        margin: 4rem auto;
        background-color: var(--clr-foreground-primary);
        border-radius: 6px;
        min-height: 9rem;
        width: fit-content;
        display: flex;
        align-items: center;
    }

    .events-list > ul {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .events-list > ul > li {
        list-style: none;
        display: flex;
        flex-direction: row;
        align-items: center;
        color: var(--clr-foreground-secondary);

        margin-right: 2rem;
    }

    .events-list > ul > li > * {
        margin-right: 1rem;
    }
</style>
