<script>
    import Margin from "../../../lib/header/margin.svelte";
    import { instagramUrl } from "../../../lib/store";
</script>

<svelte:head>
    <title>外資系就活ドットコム様に協賛していただきました。</title>
    <meta
        name="description"
        content="外資系就活ドットコム様に協賛していただき、様々なイベントを開催します。"
    />
</svelte:head>

<Margin />

<div class="body">
    <h1>外資系就活ドットコム様に協賛していただきました</h1>
    <p>
        この度 Unbiased Programming は、
        外資系・日系超一流企業を目指す学生のための就活活動サイト
    </p>
    <p>
        「<a href="https://gaishishukatsu.com/"　target="blank">外資就活ドットコム</a>」
        を運営する、
        <a href="https://howtelevision.co.jp/"　target="blank">株式会社ハウテレビジョン</a>様
        にご協賛いただくこととなりました。
    </p>
    <p>
        このご協賛を受け、Unbiased Programming はさらに活動の幅を広げていきます。
    </p>
    <p>
        今後、外資就活ドットコム様と<span>イベントの共催</span>も行いますので、続報をお待ちください。
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
