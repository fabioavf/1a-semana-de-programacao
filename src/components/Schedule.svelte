<script>
    import { fade } from 'svelte/transition';

    let daysList = [
        {
            id: 1,
            tabTitle: 'Segunda-feira (01/11)',
        },
        {
            id: 2,
            tabTitle: 'Quarta-feira (03/11)',
        },
        {
            id: 3,
            tabTitle: 'Quinta-feira (04/11)',
        },
        {
            id: 4,
            tabTitle: 'Sexta-feira (05/11)',
        },
    ];

    let activeTab = 1;

    const handleClick = (tabValue) => () => (activeTab = tabValue);
</script>

<div class="container">
    <h1>O que preparamos para você</h1>

    <div class="tabs-section">
        <div class="tabs-list">
            {#each daysList as day}
                <button
                    class={activeTab === day.id ? 'active' : ''}
                    on:click={handleClick(day.id)}
                    >{day.tabTitle}
                </button>
            {/each}
        </div>
        {#each daysList as day}
            <div
                class="tabs"
                style={activeTab === day.id ? '' : 'display: none;'}
            >
                {day.tabTitle}
            </div>
        {/each}
    </div>
</div>

<style>
    .container {
        padding: 3rem 8.75rem;
        background-color: var(--clr-background-primary);
    }

    h1 {
        color: var(--clr-foreground-secondary);
    }

    .tabs-section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        border-radius: 0.5rem;
        border: 1px solid #000;
        background-color: var(--clr-background-secondary);
    }

    .tabs-list {
        width: 100%;
        display: flex;
        flex-direction: row;
    }

    .tabs-list > button {
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

    button.active {
        color: var(--clr-foreground-secondary);
        background-color: var(--clr-background-secondary);
    }

    button.active::after {
        content: '';
        position: absolute;
        border-top: var(--clr-foreground-primary) solid 0.25rem;
        top: 0;
        left: 0;
        right: 0;
    }

    .tabs-list > button:last-child {
        border-right: none;
    }

    .tabs {
        padding: 2rem;
        color: var(--clr-foreground-secondary);
        height: 27.25rem;
    }
</style>
