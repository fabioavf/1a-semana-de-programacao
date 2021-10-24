<script>
    let logo = {
        src: 'assets/img/logo.svg',
        alt: 'Logo da 1a Semana de Programação',
    };
    let navItems = [
        { name: 'Início', id: '#inicio' },
        { name: 'Projetos', id: '#projetos' },
        { name: 'Programação', id: '#programacao' },
        { name: 'Passagem', id: '#passagem' },
    ];

    let y;
</script>

<svelte:window bind:scrollY={y} />

<nav class="navbar {y < 60 ? '' : 'anav-hide'}">
    <ul class="nav-list">
        {#each navItems as item, i}
            {#if i == navItems.length / 2}
                <li class="nav-item nav-logo">
                    <img src={logo.src} alt={logo.alt} />
                </li>
            {/if}

            <li class="nav-item"><a href={item.id}>{item.name}</a></li>
        {/each}
    </ul>
</nav>

<style>
    .navbar {
        position: fixed;
        left: 0;
        right: 0;
        top: 0;

        background-color: var(--clr-background-primary);
        padding: 0 0;
        z-index: 1;

        filter: drop-shadow(0.125rem 0 0.25rem hsla(0, 0%, 0%, 0.5));
    }

    .nav-hide {
        display: none;
        transition: all ease-in-out 2000ms;
    }

    .nav-list {
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .nav-item {
        display: none;
    }

    .nav-logo {
        display: block;
    }

    .nav-logo img {
        height: 5rem;
        width: auto;
        z-index: 2;
    }

    .nav-item > a {
        color: var(--clr-foreground-secondary);
    }

    .nav-item > a:hover {
        color: var(--clr-foreground-primary);
        text-decoration: none;
    }

    @media only screen and (min-width: 768px) {
        .nav-item {
            list-style: none;
            margin-right: 2rem;

            font-family: var(--font-family-primary);
            font-size: var(--font-size-p2);
            font-weight: 700;
        }
    }
</style>
