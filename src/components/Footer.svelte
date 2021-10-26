<script>
    let organizerList = [
        {
            name: 'byron.solutions',
            site: 'http://byronsolutions.com',
        },
        {
            name: 'Black Bee Drones',
            site: 'https://blackbeedrones.com/',
        },
        {
            name: 'Dev-U',
            site: 'https://dev-unifei.github.io/',
        },
        {
            name: 'Maratona de Programação',
            site: '',
        },
    ];

    let logoUnifei = {
        src: '/assets/img/logo-unifei.png',
        alt: 'Logotipo da Universidade Federal de Itajubá',
    };

    let logoImc = {
        src: '/assets/img/logo-imc.png',
        alt: 'Logotipo do Instituto de Matemática e Computação',
    };
</script>

<div class="divider" />

<footer>
    <div class="logo-section">
        <img
            class="logo"
            src="/assets/img/logo-horizontal.png"
            alt="Logotipo da 1a Semana de Programação da Unifei"
        />
        <p>I Semana de Programação</p>
        <p>Todos os direitos reservados</p>
    </div>
    <div class="organizers-section">
        <h4>Organizadores</h4>
        <ul>
            {#each organizerList as organizer}
                <li>
                    <a
                        class="organizer-item"
                        href={organizer.site}
                        target="_blank">{organizer.name}</a
                    >
                </li>
            {/each}
        </ul>
    </div>
    <div class="unifei-section">
        <img src={logoUnifei.src} alt={logoUnifei.alt} />
        <img src={logoImc.src} alt={logoImc.alt} />
    </div>
</footer>
<div class="divider" />

<div class="byron-section">
    <p>Desenvolvido por</p>

    <a href="http://byronsolutions.com" target="_blank">
        <img
            src="/assets/img/logo-byron-branca.png"
            alt="Logotipo da byron.solutions"
        />
    </a>
</div>

<style>
    footer {
        padding: 2.5rem 1.5rem;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        gap: 2rem;
    }

    footer > div {
        width: 100%;
    }

    .logo-section,
    .organizers-section {
        font-size: var(--font-size-p1);
        line-height: 28px;
    }

    .organizers-section > h4 {
        font-size: var(--font-size-h2-mobile);
        font-weight: 700;
        margin-bottom: 0.75rem;
    }

    .organizer-item {
        color: var(--clr-foreground-secondary);
    }

    .organizer-item:hover,
    .organizer-item:focus {
        outline: none;
        text-decoration: none;
        border-bottom: 2px solid var(--clr-foreground-primary);
    }

    .unifei-section {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 2rem;
    }

    .unifei-section > img {
        width: 100%;
        max-width: 20rem;
        /* max-height: 10rem; */
    }

    .logo {
        width: 12.5rem;
    }

    .byron-section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        margin: 1.5rem 0;
    }

    .divider {
        width: 100%;
        margin: 0 1.5rem;
        border-bottom: 2px solid var(--clr-background-secondary);
    }

    @media only screen and (min-width: 768px) {
        footer {
            flex-direction: row;
            align-items: flex-start;
            padding: 2rem 4rem;
        }

        .byron-section {
            flex-direction: row;
            gap: 1rem;
        }
    }
</style>
