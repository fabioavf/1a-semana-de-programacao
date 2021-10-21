<script>
    import * as animateScroll from 'svelte-scrollto';

    let daysList = [
        {
            id: 1,
            tabTitle: 'Segunda-feira (01/11)',
            title: 'byron.solutions',
            subtitle: 'Desenvolvimento de um portfólio pessoal',
            language: 'javascript',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: O mini-curso terá como objetivo o ensinamento do ciclo básico do desenvolvimento web, contemplando HTML, CSS e JS.',
                },
                {
                    title: '16h00 - 18h30',
                    description:
                        'Teoria: Será proposto o desenvolvimento de um portfólio pessoal para os alunos participantes.',
                },
                {
                    title: '19h30 - 20h30',
                    description:
                        'Palestra: 	"Não é preciso anos de estudo para ser desenvolvedor"',
                },
            ],
        },
        {
            id: 2,
            tabTitle: 'Quarta-feira (03/11)',
            title: 'Black Bee Drones',
            subtitle: 'Visão computacional',
            language: 'python',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Serão abordados os seguintes tópicos sobre Visão Computacional: contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '16h00 - 18h30',
                    description:
                        'Prática: Para o desafio, um projeto de identificação de itens em datasets que serão disponibilizados pelos membros da equipe. Os alunos deverão criar uma aplicação para fazer a detecção.',
                },
                {
                    title: '19h30 - 20h30',
                    description: 'Palestra: Visão Computacional',
                },
            ],
        },
        {
            id: 3,
            tabTitle: 'Quinta-feira (04/11)',
            title: 'Dev-U',
            subtitle: 'Programação de Jogos',
            language: 'csharp',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: C#; Introdução a MonoBehaviours e o Conceito de GameLoop; Editor Unity.',
                },
                {
                    title: '16h00 - 18h30',
                    description:
                        'Prática: Dado um projeto 2D da Unity com os recursos gráficos já pré-disponibilizados, escrever um código-fonte e utilizando a biblioteca matemática do C#, implementar a lei da gravitação de Newton em corpos rígidos.',
                },
                {
                    title: '19h30 - 20h30',
                    description: 'Palestra: Desenvolvimento de "serious games"',
                },
            ],
        },
        {
            id: 4,
            tabTitle: 'Sexta-feira (05/11)',
            title: 'Maratona de programação',
            subtitle: '',
            language: 'cpp',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Apresentação de um simulado de maratona de programação com problemas computacionais a serem resolvidos.',
                },
                {
                    title: '16h00 - 18h30',
                    description: 'Prática: Resolução dos problemas propostos.',
                },
                {
                    title: '19h30 - 20h30',
                    description: 'Palestra: Maratona de programação',
                },
            ],
        },
    ];

    let activeTab = 1;

    const handleClick = (tabValue) => () => (activeTab = tabValue);

    $: handleExpander = () => {
        if (activeTab >= daysList.at(0).id && activeTab < daysList.at(-1).id) {
            activeTab++;
        } else {
            activeTab = daysList.at(0).id;
        }
    };
</script>

<div class="container">
    <h1 class="heading">O que preparamos para você</h1>

    <div class="tabs-section drop-shadow">
        <div class="tabs-list">
            {#each daysList as day}
                <button
                    class="tabs-button {activeTab === day.id ? 'active' : ''}"
                    on:click={handleClick(day.id)}
                    >{day.tabTitle}
                </button>
            {/each}

            <button
                class="tabs-button list-expander"
                on:click={handleExpander()}
            >
                <img
                    src="/assets/img/double-right.png"
                    alt="Seta dupla apontando à direita"
                />
            </button>
        </div>
        {#each daysList as day}
            <div
                class="tabs"
                style={activeTab === day.id ? '' : 'display: none;'}
            >
                <div class="left-tab-section">
                    <div class="tab-heading">
                        <h2 class="tab-title">{day.title}</h2>
                        <h3 class="tab-subtitle">{day.subtitle}</h3>
                    </div>

                    <img
                        id="codeSnippet"
                        src="/assets/img/hello-{day.language}.png"
                        alt=""
                    />
                </div>

                <div class="right-tab-section">
                    <ul class="tab-schedule">
                        {#each day.schedule as timeframe}
                            <li class="tab-schedule-item">
                                <h4 class="tab-schedule-item-time">
                                    {timeframe.title}
                                </h4>
                                <p class="tab-schedule-item-desc">
                                    {timeframe.description}
                                </p>
                            </li>
                        {/each}
                    </ul>

                    <button
                        on:click={() =>
                            animateScroll.scrollTo({
                                element: '#subscriptionForm',
                                offset: -220,
                            })}
                        class="enroll-button">Quero participar</button
                    >
                </div>
            </div>
        {/each}
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        gap: 3rem;

        /* width: 100%; */
        max-width: 50rem;
        margin: 2rem 1.5rem;
    }

    .heading {
        font-size: var(--font-size-h1-mobile);
        font-weight: var(--font-weight-h1);
        /* margin: 3rem 1.5rem; */
    }

    .tabs-section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        width: 100%;
        border-radius: 0.5rem;
        border: 1px solid #000;
        background-color: var(--clr-background-secondary);
    }

    .tabs-list {
        width: 100%;
        display: flex;
        flex-direction: row;
    }

    .tabs-button {
        display: none;
        position: relative;
        flex-grow: 1;
        background-color: var(--clr-background-primary);
        height: 5rem;
        border: none;
        border-right: 1px solid #000;
        border-bottom: 1px solid #000;
        border-radius: 0;
        color: var(--clr-foreground-secondary-faded);
        font-weight: 700;
        cursor: pointer;
    }

    .tabs-button.active {
        display: block;
        color: var(--clr-foreground-secondary);
        background-color: var(--clr-background-secondary);
    }

    .tabs-button.active::after {
        content: '';
        position: absolute;
        border-top: var(--clr-foreground-primary) solid 0.25rem;
        top: 0;
        left: 0;
        right: 0;
    }

    .list-expander {
        display: block;
    }

    #codeSnippet {
        width: 100%;
        padding: 0;
    }

    .tabs-button:last-child {
        border-right: none;
    }

    .tabs {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        padding: 2rem;
        color: var(--clr-foreground-secondary);
        height: auto;
    }

    .tab-heading {
    }

    .tab-title {
        font-size: 22px;
        font-weight: 700;
        line-height: 28px;
    }

    .tab-subtitle {
        color: var(--clr-foreground-primary-lighter);
        letter-spacing: 1.5px;
    }

    .tab-code {
        display: block;
        border: 1px solid black;
        border-radius: 0.5rem;
        background-color: var(--clr-background-primary);
        padding: 1rem;
        font-size: 12px;

        font-family: monospace;
    }

    .left-tab-section {
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }

    .right-tab-section {
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }

    .tab-schedule {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        max-width: 600px;
    }

    .tab-schedule-item {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .tab-schedule-item-time {
        font-weight: 700;
        width: fit-content;
        padding-bottom: 0.375rem;
        border-bottom: 2px solid var(--clr-foreground-primary);
    }

    .tab-schedule-item-time::after {
        content: '';
        width: 100%;
    }

    .tab-schedule-item-desc {
        line-height: 24px;
    }

    .enroll-button {
        font-weight: 500;
        color: var(--clr-foreground-secondary);

        background-color: var(--clr-foreground-primary);
        border: none;
        border-radius: 0.25rem;
        width: 100%;
        padding: 0.5rem 0;
        cursor: pointer;
        transition: 100ms;

        filter: drop-shadow(0.125rem 0.25rem 0.25rem hsla(0, 0%, 0%, 0.25));
    }

    .enroll-button:hover,
    .enroll-button:focus {
        background-color: var(--clr-foreground-primary-darker);
    }
    @media only screen and (min-width: 768px) {
        .container {
            width: 100%;
        }
        .tabs-button {
            display: block;
        }

        .list-expander {
            display: none;
        }
    }
</style>
