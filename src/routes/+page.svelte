<script>
	import img from "$lib/top/news/imgs/document_syorui_pen.png";
	import Card from "../lib/top/news/card.svelte";
	import Carousel from "./../lib/top/carousel/carousel.svelte";
</script>

<svelte:head>
	<title>Unbiased Programming</title>
	<meta
		name="description"
		content="上智大学のプログラミングサークルUnbiased Programmingの公式サイトです。"
	/>
</svelte:head>

<Carousel />

<div class="short-about">
	<h2 class=temp>キャッチフレーズを入れる</h2>
	<p class=temp>
		Unbiased Programmingは上智大学のプログラミングサークルです。
		説明を入れる
	</p>
</div>

<div class="section-title">
	<h2>News</h2>
</div>
<div class="cards">
	<Card
		title="入会希望者の方へ"
		description="入会申請フォーム及び質問窓口を設置しました。"
	>
		<img src={img} alt="document_syorui_pen" loading="lazy" />
		<div class="src">いらすとや</div>
	</Card>

	<Card
		title="外資系就活ドットコム様と提携しました。"
		description="外資系就活ドットコム様と提携し様々なイベントを開催することになりました。"
	></Card>
</div>
<div class="section-title">
	<h2>Activity</h2>
</div>
<div class="cards">
	<Card
		title="サイトを公開しました。"
		description="SOMAからUnbiased Programmingへの改名に伴い新たなWEBサイトを公開しました。"
	></Card>
</div>

<style>
	.short-about {
		text-align: center;
		padding: 20px;
	}

	.short-about h2 {
		font-size: x-large;
	}

	.cards {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 20px;
		padding: 20px;
	}

	.cards img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.src {
		position: absolute;
		bottom: 0;
		right: 10px;
		font-size: small;
		font-size: 0.6rem;
	}

	.section-title > h2{
		text-align: center;
		margin-top: 40px;
		font-size: x-large;
	}

	.temp::after {
		content: "仮の文章です。";
		font-size: 0.6rem;
		color: red;
		position: absolute;
	}
</style>
