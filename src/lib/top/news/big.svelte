<script>
    import Fa from "svelte-fa";
    import {
        faInstagram,
        faXTwitter,
    } from "@fortawesome/free-brands-svg-icons";
    import { formUrl } from "../../store";
</script>

<div class="area">
    <div class="item">
        <div class="min-title">入会申請はこちらから</div>
        <button>
            <a href={formUrl}>
                <div class="go">入会申請フォーム</div>
            </a>
        </button>
        <div class="min-title">質問、相談等はこちらから</div>
        <div class="icons">
            <a
                href="https://www.instagram.com/unbiased_programming"
                target="_blank"
            >
                <Fa icon={faInstagram} size="lg" />
            </a>
            <a href="https://twitter.com/teamsoma_sophia" target="_blank">
                <Fa icon={faXTwitter} size="lg" />
            </a>
        </div>
    </div>
    <div class="text">
        <h2>Unbiased Programmingはいつでも入会を受け付けております。</h2>
    </div>
</div>

<style>
    .area {
        background-color: var(--up-color);
        width: 100%;
        position: relative;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        --width: min(max(30vw, 400px), calc(100vw - 100px));
        padding: 10vw 0;
    }

    .item {
        width: var(--width);
        min-height: min(30vw, 400px);
        padding: 20px;
        background-color: rgb(236, 236, 236);
        border-radius: 3px;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .text {
        width: var(--width);
        height: 100%;
        padding: 20px;
        color: white;

        display: flex;
        align-items: center;
    }

    .icons {
        display: flex;
        justify-content: center;
        gap: 20px;
        padding: 20px;
    }

    .min-title {
        font-size: x-large;
        text-align: center;
        padding: 20px 0 0 0; 
    }

    button {
        width: 200px;
        font-size: 16px;
        font-weight: 600;
        color: #fff;
        cursor: pointer;
        margin: 20px;
        height: 55px;
        text-align: center;
        border: none;
        background-size: 300% 100%;

        border-radius: 50px;
        -o-transition: all 0.4s ease-in-out;
        -webkit-transition: all 0.4s ease-in-out;
        transition: all 0.4s ease-in-out;

        background-image: linear-gradient(
            to right,
            #667eea,
            #764ba2,
            #6b8dd6,
            #8e37d7
        );
        box-shadow: 0 4px 15px 0 rgba(116, 79, 168, 0.75);
    }

    button:hover {
        background-position: 100% 0;
        -o-transition: all 0.4s ease-in-out;
        -webkit-transition: all 0.4s ease-in-out;
        transition: all 0.4s ease-in-out;
    }

    button:focus {
        outline: none;
    }

    button a {
        color: white;
        text-decoration: none;
    }
</style>
