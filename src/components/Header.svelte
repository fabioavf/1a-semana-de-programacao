<script>
    let logo = {
        src: 'http://picsum.photos/80/40',
        alt: 'Logo da 1a Semana de Programação',
    };
    let navItems = [
        { name: 'Início', id: '#inicio' },
        { name: 'Projetos', id: '#projetos' },
        { name: 'Programação', id: '#programacao' },
        { name: 'Passagem', id: '#passagem' },
    ];
</script>

<nav>
    <ul>
        {#each navItems as item, i}
            {#if i == navItems.length / 2}
                <li><img src={logo.src} alt={logo.alt} /></li>
            {/if}

            <li><a href={item.id}>{item.name}</a></li>
        {/each}
    </ul>
</nav>

<style>
    nav {
        position: fixed;
        left: 0;
        right: 0;
        top: 0;

        background-color: transparent;
        min-height: 88px;
        padding: 1rem 0;
    }

    nav > ul {
        margin: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    nav > ul > li {
        list-style: none;
        margin-right: 2rem;

        font-family: var(--font-family-primary);
        font-size: var(--font-size-p2);
        font-weight: 700;
    }

    nav > ul > li > a {
        color: var(--clr-foreground-secondary);
    }

    nav > ul > li > a:hover {
        color: var(--clr-foreground-primary);
        text-decoration: none;
    }
</style>
