<script>
    import * as animateScroll from 'svelte-scrollto';

    export let text;
</script>

<button
    on:click={() =>
        animateScroll.scrollTo({ element: '#subscriptionForm', offset: -100 })}
    class="button-enroll"
>
    <img src="assets/img/down-arrow.png" alt="Seta apontando para baixo" />
    {text}
</button>

<style>
    .button-enroll {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.25rem;

        background-color: transparent;
        border: none;
        color: var(--clr-foreground-secondary);
        margin: 1rem 0;
        cursor: pointer;
    }

    .button-enroll:focus {
        background-color: transparent;
        color: var(--clr-foreground-primary);
    }
</style>
