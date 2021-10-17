<script>
    import { fly } from 'svelte/transition';

    let teamsList = [
        {
            name: 'byron.solutions',
            desc: 'A byron.solutions é uma empresa júnior que atua no ramo de consultoria em TI, com soluções em desenvolvimento de sistemas, de sites e inclusão digital de pequenas empresas. É composta por alunos dos cursos de Sistemas da Informação, Ciência da Computação e Engenharia da Computação.',
            instagram: 'byron.solutions',
        },
        {
            name: 'Black Bee',
            desc: 'A Black Bee Drones conquistou o terceiro lugar e arrancou elogios de todos os organizadores que ficaram extremamente surpresos com o fato de termos vindo de tão longe, termos sido tão bem-sucedidos logo na primeira participação e contarmos apenas com integrantes de graduação.',
            instagram: 'blackbeedrones',
        },
        {
            name: 'Dev-U',
            desc: 'Os membros se envolvem com o desenvolvimento de jogos para as diversas plataformas, tendo enfoque na Mobile e PC, visando também participar de competições como game jams e disseminar conhecimento acerca das áreas de criação de jogos, através da divulgação de materiais.',
            instagram: 'devunifei',
        },
        {
            name: 'Maratona de Programação',
            desc: 'Os membros se envolvem com o desenvolvimento de jogos para as diversas plataformas, tendo enfoque na Mobile e PC, visando também participar de competições como game jams e disseminar conhecimento acerca das áreas de criação de jogos, através da divulgação de materiais.',
            instagram: 'devunifei',
        },
    ];
</script>

<div class="container">
    <h1 class="section-title">Aprenda com quem domina o assunto!</h1>

    <ul class="card-section">
        {#each teamsList as team}
            <li class="card">
                <h2 class="card-title">{team.name}</h2>

                <p class="card-text">{team.desc}</p>

                <div class="instagram-link">
                    <img
                        src="/assets/img/instagram-icon.svg"
                        alt="Logotipo do Instagram"
                    />
                    <a href="http://instagram.com/{team.instagram}"
                        >@{team.instagram}</a
                    >
                </div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .container {
        padding: 3rem 8.75rem;
        background-color: var(--clr-background-terciary);
    }

    .section-title {
        font-family: var(--font-family-primary);
        color: var(--clr-foreground-secondary);
        font-size: var(--font-size-h1);
        max-width: 600px;
        margin: 0 0 4rem 0;
    }

    .card-section {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: auto;
        justify-content: center;
        justify-items: center;
        gap: 2rem;
        padding: 0;
    }

    .card {
        max-width: 20rem;
        background-color: var(--clr-background-secondary);
        list-style: none;
        padding: 1.5rem;
        padding-top: 2.5rem;

        font-family: var(--font-family-primary);
        color: var(--clr-foreground-secondary);

        display: flex;
        flex-direction: column;
        justify-content: space-between;

        background-image: url(/assets/img/card-blob-top-left.svg),
            url(/assets/img/card-blob-bottom-right.svg);
        background-size: 30%;
        background-position: top left, bottom right;
        background-repeat: no-repeat;
    }

    .card-title {
        font-size: var(--font-size-h3);
    }

    .card-text {
        line-height: var(--font-line-height);
        font-size: var(--font-size-p2);
        font-weight: 400;
    }

    .instagram-link {
        display: flex;
        flex-direction: row;

        justify-content: baseline;
        align-items: center;
        gap: 0.5rem;
    }

    .instagram-link > a {
        text-decoration: none;
        color: var(--clr-foreground-secondary);
    }

    @media only screen and (min-width: 1440px) {
        .card-section {
            grid-template-columns: 20rem 20rem 20rem 20rem;
        }
    }

    @media only screen and (min-width: 768px) and (max-width: 1439px) {
        .card-section {
            grid-template-columns: 20rem 20rem;
        }
    }
</style>
