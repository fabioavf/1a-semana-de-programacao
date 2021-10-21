<script>
    import * as animateScroll from 'svelte-scrollto';

    export let text;
</script>

<button
    on:click={() =>
        animateScroll.scrollTo({ element: '#subscriptionForm', offset: -220 })}
    class="button-enroll"
>
    <span id="arrow" />

    {text}
</button>

<style>
    .button-enroll {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.25rem;

        transition: 100ms;
        background-color: transparent;
        border: none;
        color: var(--clr-foreground-secondary);
        margin: 1rem 0;
        cursor: pointer;
    }

    #arrow {
        mask: url(/assets/img/down-arrow.svg);
        mask-size: 100%;
        mask-repeat: no-repeat;
        background-color: var(--clr-foreground-secondary);
        width: 1.5rem;
        height: 1.5rem;
        transition: 100ms;
    }

    button:hover #arrow,
    button:focus #arrow {
        background-color: var(--clr-foreground-primary);
    }

    .button-enroll:hover,
    .button-enroll:focus {
        color: var(--clr-foreground-primary);
    }
</style>
