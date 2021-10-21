<script>
    let outerWidth;
    let iframeWidth = 768;
</script>

<svelte:window bind:outerWidth />

<div class="container">
    <iframe
        id="subscriptionForm"
        src="https://docs.google.com/forms/d/e/1FAIpQLScFOAmQZc8YvdwNBydNqz0xmqyctL9NhzP3nUNByLzhHXE1Rg/viewform?embedded=true"
        width={outerWidth < iframeWidth + 24 ? outerWidth - 24 : iframeWidth}
        height="1550"
        frameborder="0"
        onload="resizeIframe(this)"
        marginheight="0"
        marginwidth="0">Loading…</iframe
    >
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;

        width: 100%;
        height: auto;
        margin: 2rem 0;
    }

    iframe {
        background-color: white;
        border-radius: 0.5rem;
    }
</style>
