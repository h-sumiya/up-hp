<script>
    import Margin from "../../../lib/header/margin.svelte";
</script>

<svelte:head>
    <title>サイトを公開しました。</title>
    <meta
        name="description"
        content="SOMAからUnbiased Programmingへの改名に伴い新たなWEBサイトを公開しました。"
    />
</svelte:head>

<Margin />

<div class="body">
    <h1>ホームページを公開しました。</h1>
    <p>
        この度、SOMAからUnbiased
        Programmingへの改名に伴い新たなWEBサイトを公開しました。
    </p>
    <p>このサイトはSvelteとCloudflare Pagesを使用して構築されています。</p>
    <p>
        ソースコードは
        <a
            href="https://github.com/h-sumiya/up-hp"
            target="_blank"
            rel="noopener noreferrer">GitHub</a
        >
        で公開されています。
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

    a {
        border-bottom: solid 1px var(--up-color);
    }
</style>
