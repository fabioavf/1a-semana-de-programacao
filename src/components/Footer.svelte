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
    ];
</script>

<footer>
    <div class="footer-wrapper">
        <div class="logo-section">
            <img
                src="http://picsum.photos/228/90"
                alt="Logotipo da 1a Semana de Programação da Unifei"
            />
            <p>I Semana de Programação</p>
            <p>Todos os direitos reservados</p>
        </div>
        <div class="organizers-section">
            <h4>Organizadores</h4>
            <ul>
                {#each organizerList as organizer}
                    <li><a href={organizer.site}>{organizer.name}</a></li>
                {/each}
            </ul>
        </div>
        <div class="social-section">
            <h4>Redes Sociais</h4>
        </div>
    </div>

    <p>
        Desenvolvido por <a href="http://byronsolutions.com">
            <img
                src="/assets/img/logo-byron-branca.png"
                alt="Logotipo da byron.solutions"
            />
        </a>
    </p>
</footer>

<style>
    footer {
        display: flex;
        flex-direction: column;
    }

    footer > p {
        text-align: center;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.5rem;
        color: var(--clr-foreground-secondary);
        font-size: var(--font-size-h4);
    }

    footer > p > a {
        height: 45px;
        text-decoration: none;
    }

    .footer-wrapper {
        height: 16rem;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-start;
        background-color: var(--clr-background-primary);
        padding: 3rem 8.75rem;

        color: var(--clr-foreground-secondary);
    }

    footer > * {
        flex: 1;
    }

    .logo-section p,
    .organizers-section a {
        font-size: var(--font-size-p1);
    }

    footer h4 {
        font-size: var(--font-size-h4);
    }

    .organizers-section > ul {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        margin: 0;
        padding: 0;
    }

    .organizers-section > ul > li {
        list-style: none;
    }

    .organizers-section a {
        text-decoration: none;
        color: var(--clr-foreground-secondary);
    }
</style>
