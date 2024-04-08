<script>
    import Margin from "../../../lib/header/margin.svelte";
    import { instagramUrl } from "../../../lib/store";
</script>

<svelte:head>
    <title>2024年フレマンのお知らせ</title>
    <meta
        name="description"
        content="4/9,10に開催されるフレッシュマンウィークに参加します。"
    />
</svelte:head>

<Margin />

<div class="body">
    <h1>2024年フレマンのお知らせ</h1>
    <p>4/9,10に開催されるフレッシュマンウィークに参加します。</p>
    <p>
        当日は<span>東門</span>の近くにてブースを設置します。
    </p>
    <p>
        サークルの活動内容などを紹介する予定ですので、ぜひお立ち寄りください。
    </p>
    <p>
        雨天時は9号館地下のカフェ内、<span>右奥</span>にブースが移動します。
    </p>
    <p>
        最新情報は
        <a href={instagramUrl}>インスタグラム</a>
        でお知らせします。
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
