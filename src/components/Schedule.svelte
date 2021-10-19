<script>
    let daysList = [
        {
            id: 1,
            tabTitle: 'Segunda-feira (01/11)',
            title: 'byron.solutions',
            subtitle: 'Portfólio completo do zero',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
            ],
        },
        {
            id: 2,
            tabTitle: 'Quarta-feira (03/11)',
            title: 'byron.a',
            subtitle: 'Portfólio completo do zero',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
            ],
        },
        {
            id: 3,
            tabTitle: 'Quinta-feira (04/11)',
            title: 'byron.solutions',
            subtitle: 'Portfólio completo do zero',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
            ],
        },
        {
            id: 4,
            tabTitle: 'Sexta-feira (05/11)',
            title: 'byron.solutions',
            subtitle: 'Portfólio completo do zero',
            schedule: [
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
                },
                {
                    title: '13h30 - 15h00',
                    description:
                        'Teoria: Contextualização, teoria e conceitos iniciais, entendendo a aplicação, base da linguagem python e biblioteca OpenCV.',
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

                    <code class="tab-code">
                        def main(): <br />
                        &nbsp;&nbsp print("Hello, SEPROG!")
                    </code>
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

                    <button class="enroll-button">Quero participar</button>
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

        width: 100%;
        margin: 2rem 0;
    }

    .heading {
        font-size: var(--font-size-h1-mobile);
        font-weight: var(--font-weight-h1);
        margin: 3rem 1.5rem;
    }

    .tabs-section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        border-radius: 0.5rem;
        border: 1px solid #000;
        background-color: var(--clr-background-secondary);
        margin: 0 1.5rem;
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
        color: var(--clr-foreground-primary);
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

        filter: drop-shadow(0.125rem 0.25rem 0.25rem hsla(0, 0%, 0%, 0.25));
    }

    @media only screen and (min-width: 1440px) {
        .tabs-button {
            display: block;
        }

        .list-expander {
            display: none;
        }
    }
    @media only screen and (min-width: 768px) and (max-width: 1439px) {
        .tabs-button {
            display: block;
        }

        .list-expander {
            display: none;
        }
    }
</style>
