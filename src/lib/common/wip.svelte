<script>
    import Margin from "../header/margin.svelte";
    import Back from "./mark_koujichu.webp";
</script>

<div class="back">
    <img src={Back} alt="mark_koujichu" loading="lazy" />
</div>

<div class="container">
    <h2>こちらのページは準備中です</h2>
    <p>こちらのページは準備中です。完成までもうしばらくお待ちください。</p>
</div>

<style>
    .back {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        opacity: 0.2;
        position: absolute;
    }

    img {
        width: 100%;
        max-width: 600px;
    }

    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 20px;
        padding: 20px;
    }
</style>
