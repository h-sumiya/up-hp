<script>
    import Link from "./link.svelte";
    import Icon from "./../logo/icon.svelte";
    import Logo from "./../logo/logo.svelte";
    import { drawerOpen } from "../store";
</script>

<div class="inner">
    <a href="/" class="logo-con">
        <div class="icon"><Icon size="24" /></div>
    <div class="logo"><Logo scale="3.2" /></div>
    </a>
    <div
        class="menu"
        on:click={() => drawerOpen.update((v) => !v)}
        class:open={$drawerOpen}
        role="button"
        tabindex="0"
    >
        <div class="top"></div>
        <div class="middle"></div>
        <div class="bottom"></div>
    </div>
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
        height: 48px;

        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }

    .logo-con {
        display: flex;
        align-items: center;
    }

    .icon {
        margin-right: 5px;
    }

    .logo {
        margin-top: 2px;
    }

    .menu {
        position: absolute;
        right: 20px;
        width: 40px;
        height: 40px;
    }

    .menu div {
        width: calc(100% - 14px);
        left: 7px;
        height: 4px;
        background-color: black;
        border-radius: 2px;
        transition: all 0.3s;
        position: absolute;
    }

    .top {
        top: 10px;
    }

    .middle {
        top: 18px;
    }

    .bottom {
        bottom: 10px;
    }

    .open > .top {
        transform: translateY(8px) rotate(45deg);
    }

    .open > .middle {
        opacity: 0;
    }

    .open > .bottom {
        transform: translateY(-8px) rotate(-45deg);
    }
</style>
