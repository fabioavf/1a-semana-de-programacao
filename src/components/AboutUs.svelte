<script>
    import EnrollButton from './EnrollButton.svelte';
    let teamsList = [
        {
            name: 'byron.solutions',
            desc: 'A byron.solutions é uma empresa júnior que atua no ramo de consultoria em TI, com soluções em desenvolvimento de sistemas, de sites e inclusão digital de pequenas empresas. É composta por alunos dos cursos de Sistemas da Informação, Ciência da Computação e Engenharia da Computação.',
            instagram: 'byron.solutions',
        },
        {
            name: 'Black Bee Drones',
            desc: 'A Black Bee Drone é a primeira equipe de drones autônomos da América Latina, formada em 2015, referência em sua área de pesquisa. O desenvolvimento de tais VANTs ocorre para a participação em campeonatos, como o IMAV, que acontece todos os anos em um país diferente.',
            instagram: 'blackbeedrones',
        },
        {
            name: 'Dev-U',
            desc: 'A Dev-U é um projeto de extensão da UNIFEI que teve início em 2018, nossa missão é desenvolver jogos e capacitar membros para o mercado de trabalho. O projeto tem 4 áreas, sendo elas: AudioVisual, Programação, Gestão&Marketing e Game Design.',
            instagram: 'devunifei',
        },
        {
            name: 'Maratona de Programação',
            desc: 'A Maratona de Programação é uma competição focada em criatividade, desafios, trabalho em equipe e habilidade de resolver problemas. Participar da competição pode ajudar a abrir portas e conhecer novas realidades, tanto culturalmente quanto profissionalmente. Junte-se às mentes mais afiadas!',
            instagram: '',
        },
    ];
</script>

<div class="container">
    <h1 class="section-title">Aprenda com quem domina o assunto!</h1>

    <ul class="card-section">
        {#each teamsList as team}
            <li class="card drop-shadow">
                <h2 class="card-title">{team.name}</h2>

                <p class="card-text">{team.desc}</p>

                <div class="instagram-link">
                    <img
                        style={team.instagram == '' ? 'display: none;' : ''}
                        src="/assets/img/instagram-icon.svg"
                        alt="Logotipo do Instagram"
                    />
                    <a
                        style={team.instagram == '' ? 'display: none;' : ''}
                        href="http://instagram.com/{team.instagram}"
                        target="_blank">@{team.instagram}</a
                    >
                </div>
            </li>
        {/each}
    </ul>

    <EnrollButton text="Faça parte com os melhores!" />
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;

        max-width: 50rem;
        margin: 2rem 1.5rem !important;
    }

    .section-title {
        font-size: var(--font-size-h1-mobile);
        font-weight: var(--font-weight-h1);
        margin-bottom: 3rem;
        text-align: center;
    }

    .card-section {
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: auto;
        justify-items: center;
        gap: 2rem;
        width: 100%;
        margin-bottom: 1rem;
        /* padding: 0 1.5rem; */
    }

    .card {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        gap: 3rem;

        list-style: none;
        max-width: 20rem;
        padding: 1.5rem;
        padding-top: 2.5rem;
        border-radius: 0.5rem;

        background-color: var(--clr-background-secondary);
        font-family: var(--font-family-primary);
        color: var(--clr-foreground-secondary);

        background-image: url(/assets/img/card-blob-top-left.svg),
            url(/assets/img/card-blob-bottom-right.svg);
        background-size: 6rem;
        background-position: top left, bottom right;
        background-repeat: no-repeat;
    }

    .card-title {
        text-align: center;
        font-size: var(--font-size-h2-mobile);
        font-weight: 700;
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
        height: 30px;
    }

    .instagram-link > a {
        text-decoration: none;
        color: var(--clr-foreground-secondary);
    }

    @media only screen and (min-width: 768px) {
        .container {
            width: 100%;
        }
        .card-section {
            grid-template-columns: 1fr 1fr;
        }

        .card:nth-child(odd) {
            justify-self: baseline;
        }

        .card:nth-child(even) {
            justify-self: end;
        }
    }

    @media only screen and (min-width: 1368px) {
        .container {
            max-width: 75rem;
        }
        .card-section {
            grid-template-columns: 1fr 1fr 1fr 1fr;
            gap: 1rem;
        }

        .card {
            gap: 1rem;
            padding: 2.5rem 1rem;
        }
    }
</style>
