<script>
    let innerWidth;
    let iframeWidth = 800;
</script>

<svelte:window bind:innerWidth />

<div class="container">
    <h1 class="section-title">Evolua conosco!</h1>

    <iframe
        id="subscriptionForm"
        src="https://docs.google.com/forms/d/e/1FAIpQLScFOAmQZc8YvdwNBydNqz0xmqyctL9NhzP3nUNByLzhHXE1Rg/viewform?embedded=true"
        width={innerWidth < iframeWidth + 64 ? innerWidth - 64 : iframeWidth}
        height="1550"
        frameborder="0"
        marginheight="0"
        marginwidth="0">Loading…</iframe
    >
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;

        /* width: 100%; */
        max-width: 50rem;
        height: auto;
        margin: 2rem 1.5rem;
        margin-top: 4rem;
    }

    .section-title {
        font-size: var(--font-size-h1-mobile);
        font-weight: var(--font-weight-h1);
        margin-bottom: 3rem;
    }

    iframe {
        /* margin: 0 1.5rem; */
        background-color: white;
        border-radius: 0.5rem;
    }
</style>
