<script>
    import { instagramUrl, twitterUrl } from "../store";
</script>

<footer>
    <div class="links">
        <div class="internal">
            <div class="title">内部リンク</div>
            <a href="/about">About</a>
            <a href="/news">ニュース</a>
            <a href="/activity">活動内容</a>
        </div>
        <div class="external">
            <div class="title">外部リンク</div>
            <a href="https://www.unbiasedlearning.org" target="_blank"
                >Unbiased Learning</a
            >
            <a href="https://gaishishukatsu.com" target="_blank"
                >外資就活ドットコム</a
            >
            <a href="https://www.sophia.ac.jp/jpn/" target="_blank">
                上智大学
            </a>
        </div>
        <div class="sns">
            <div class="title">SNS</div>
            <a href={instagramUrl} target="_blank">Instagram</a>
            <a href={twitterUrl} target="_blank">Twitter</a>
        </div>
    </div>
    <div>© 2024 Unbiased Programming</div>
</footer>

<style>
    .links {
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: top;
        gap: 20px;
        margin-bottom: 20px;
    }

    .title {
        font-size: 1.2rem;
        border-bottom: solid 1px;
        padding: 0 5px;
    }

    .links a {
        display: block;
        padding: 0 7px;
    }

    footer {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 12px;
        background-color: #f0f0f0; /* temp */
    }
</style>
