<script>
    import Link from "./link.svelte";
    import Icon from "./../logo/icon.svelte";
    import Logo from "./../logo/logo.svelte";
    import Fa from "svelte-fa";
    import {
        faInstagram,
        faXTwitter,
    } from "@fortawesome/free-brands-svg-icons";
    import { instagramUrl, twitterUrl } from "../store";
</script>

<div class="inner">
    <a href="/" class="logo-con">
        <div class="icon"><Icon size="30" /></div>
        <Logo scale="3.8" />
    </a>
    <div class="s"></div>

    <Link href="/about" title="About" ditail="サークル情報" />
    <Link href="/activity" title="Activity" ditail="活動内容" />
    <Link href="/news" title="News" ditail="ニュース" />
    <a
        href={instagramUrl}
        target="_blank"
    >
        <Fa icon={faInstagram} size="lg" />
    </a>
    <a href={twitterUrl} target="_blank">
        <Fa icon={faXTwitter} size="lg" />
    </a>
</div>

<style>
    .inner {
        background: rgba(255, 255, 255, 0.8);
        box-shadow:
            1.1px 1.1px 2.2px rgba(0, 0, 0, 0.02),
            2.5px 2.5px 5.3px rgba(0, 0, 0, 0.028),
            4.8px 4.8px 10px rgba(0, 0, 0, 0.035),
            8.5px 8.5px 17.9px rgba(0, 0, 0, 0.042),
            15.9px 15.9px 33.4px rgba(0, 0, 0, 0.05),
            38px 38px 80px rgba(0, 0, 0, 0.07);
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255, 255, 255, 0.3);

        margin: 1.5rem;
        border-radius: 9999px;
        display: flex;
        align-items: center;
        padding: 10px 20px;
        height: 70px;
        gap: 20px;
    }

    .logo-con {
        display: flex;
        align-items: center;
    }

    .icon {
        margin-right: 5px;
    }

    .s {
        flex: 1;
    }
</style>
