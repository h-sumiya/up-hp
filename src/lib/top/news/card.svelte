<script>
    export let title = "";
    export let description = "";
    export let href = null;
</script>

<div class="container">
    <div class="thumb">
        <slot />
    </div>
    <div class="content">
        <div class="title">{title}</div>
        <div class="description">{description}</div>
        {#if href !== null}
            <a {href}>
                <button>Read More</button>
            </a>
        {:else}
            <div class="margin" />
        {/if}
    </div>
</div>

<style>
    .container {
        flex: 1;
        min-width: 200px;
        max-width: 300px;
        background-color: rgba(255, 255, 255, 0.877);
        border-radius: 12px;
        position: relative;
        margin-top: 24px;
        flex-shrink: 0;

        border: solid 1px rgba(0, 0, 0, 0.1);
        box-shadow:
            0.1px 0.1px 0.3px rgba(0, 0, 0, 0.02),
            0.3px 0.1px 0.8px rgba(0, 0, 0, 0.028),
            0.6px 0.3px 1.5px rgba(0, 0, 0, 0.035),
            1.1px 0.4px 2.7px rgba(0, 0, 0, 0.042),
            2.1px 0.8px 5px rgba(0, 0, 0, 0.05),
            5px 2px 12px rgba(0, 0, 0, 0.07);
    }

    .thumb {
        position: absolute;
        border-radius: 12px;
        left: 13px;
        top: -24px;
        width: calc(100% - 26px);
        aspect-ratio: 1.81;
        background-color: rgb(118, 118, 255);
        overflow: hidden;
    }

    .content {
        padding: calc(55% - 24px) 20px 0 20px;
        display: flex;
        flex-direction: column;
        height: 100%;
    }

    .title {
        font-size: 1.3rem;
    }

    .description {
        flex-grow: 1;
        margin-top: 5px;
        opacity: 0.85;
        font-size: 0.9rem;
    }

    button {
        margin-top: 20px;
        margin-bottom: 20px;
        padding: 10px 20px;
        background-color: #3b82f6;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        color: white;

        box-shadow:
            1.5px 1.8px 3.6px rgba(0, 0, 0, 0.024),
            4.1px 5px 10px rgba(0, 0, 0, 0.035),
            9.9px 12.1px 24.1px rgba(0, 0, 0, 0.046),
            33px 40px 80px rgba(0, 0, 0, 0.07);

        transition: background-color 0.3s;
    }

    button:hover {
        background-color: #2563eb;
    }

    .margin {
        margin-top: 20px;
    }
</style>
