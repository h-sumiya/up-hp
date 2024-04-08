<script>
    import Margin from "../../../lib/header/margin.svelte";
    import { instagramUrl } from "../../../lib/store";
</script>

<svelte:head>
    <title>2024年新歓パーティーのお知らせ</title>
    <meta
        name="description"
        content="4/13に新歓パーティーを開催します。"
    />
</svelte:head>

<Margin />

<div class="body">
    <h1>2024年新歓パーティーのお知らせ</h1>
    <p>4/13に、レンタルスペースで、<span>新歓パーティー</span>を開催します。</p>
    <p>
        Unibased Programming の活動内容についての紹介や、楽しいアクティビティを行う予定です。
    </p>
    <p>
        この機会に、Unbiased Programming に興味を持ってくれた方と、サークルメンバーとの仲が深まることを期待しています。
    </p>
    <p>
        詳細や参加方法については、
        <a href={instagramUrl}>インスタグラム</a>
        でご確認ください。
    </p>
</div>

<style>
    .body {
        margin: 0 auto;
        max-width: 800px;
        padding: 1rem;
    }

    h1 {
        font-size: 2rem;
        margin: 1rem 0;
    }

    p {
        margin: 1rem 0;
    }

    span {
        font-weight: bold;
    }

    a {
        border-bottom: solid 1px var(--up-color);
    }
</style>
