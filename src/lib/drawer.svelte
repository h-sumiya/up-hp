<script>
    import Fa from "svelte-fa";
    import {
        faInstagram,
        faXTwitter,
    } from "@fortawesome/free-brands-svg-icons";
    import { drawerOpen, instagramUrl, twitterUrl } from "./store";

    const close = () => {
        drawerOpen.set(false);
    };

    const textLinks = [
        {
            text: "About",
            href: "/about",
        },
        {
            text: "ニュース",
            href: "/news",
        },
        {
            text: "活動内容",
            href: "/activity",
        },
    ];
</script>

<div class="title">
    <h2>Menu</h2>
</div>
<div class="link">
    {#each textLinks as { text, href }}
        <div class="text-link">
            <a {href} on:click={close}>{text}</a>
        </div>
    {/each}
    <div class="icon-link">
        <a href={instagramUrl} target="_blank">
            <Fa icon={faInstagram} size="lg" />
        </a>
        <a href={twitterUrl} target="_blank">
            <Fa icon={faXTwitter} size="lg" />
        </a>
    </div>
</div>

<style>
    .title {
        text-align: center;
        margin: 40px;
    }

    .link {
        display: flex;
        flex-direction: column;
    }

    .text-link {
        font-size: x-large;
        margin: 10px 20px 0 20px;
        padding: 0 10px;
        border-bottom: solid 1px black;
    }

    .text-link::after {
        content: ">";
        float: right;
    }

    .icon-link {
        display: flex;
        justify-content: center;
        gap: 20px;
        margin-top: 20px;
    }
</style>
