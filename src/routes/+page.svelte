<script>
	import siteImg from "$lib/activity/thumbnail/site.jpg";
	import sinkanImg from "$lib/news/thumbnail/sinkan_party.png";
	import freshImg from "$lib/news/thumbnail/fresh.jpg";
	import gssktLogo from "$lib/news/thumbnail/gsskt_logo.png";
	import Big from "../lib/top/news/big.svelte";
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
	<h2>全ての人に、偏見のない学びを</h2>
	<br />
	<p>
		Unbiased Programming は上智大学のインカレプログラミングサークルです。<br
		/>
		性別・所属・文理選択など、その人の属性にとらわれずに、<br />
	</p>
	<h4>" すべての人がプログラミングに挑戦できる機会 "</h4>
	<p>
		を提供することを目標に、プログラミングの学習やイベントの開催など、<br />
		日々様々な活動を行っています。
	</p>
</div>
<Big />
<div class="section-title">
	<h2>News</h2>
</div>
<div class="cards">
	<Card
		title="2024年新歓パーティーのお知らせ"
		description="4/13に新歓パーティーを開催します。"
		href="/news/welcome2024"
	>
		<img src={sinkanImg} class="cov" alt="fresh" loading="lazy" />
	</Card>
	<Card
		title="2024年フレマンのお知らせ"
		description="4/9,10に開催されるフレッシュマンウィークに参加します。"
		href="/news/fresh2024"
	>
		<img src={freshImg} class="cov" alt="fresh" loading="lazy" />
	</Card>
	<Card
		title="外資系就活ドットコム様に協賛していただきました。"
		description="外資系就活ドットコム様に協賛していただき、様々なイベントを開催します。"
		href="/news/gsskt"
	>
		<div class="gsskt">
			<img src={gssktLogo} alt="GSSKT" loading="lazy" />
		</div>
	</Card>
</div>
<div class="section-title">
	<h2>Activity</h2>
</div>
<div class="cards bottom">
	<Card
		title="サイトを公開しました。"
		description="SOMAからUnbiased Programmingへの改名に伴い新たなWEBサイトを公開しました。"
		href="/activity/site"
	>
		<img
			src={siteImg}
			class="cov"
			alt="Svelte + Cloudflare"
			loading="lazy"
		/>
		<div class="src">DALL.E</div>
	</Card>
</div>

<style>
	.short-about {
		text-align: center;
		padding: 20px;
		margin-bottom: 40px;
	}

	.short-about h2 {
		text-align: center;
		font-size: xx-large;
	}

	.short-about p {
		margin: auto;
		max-width: 563px;
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

	.cards .cov {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.src {
		position: absolute;
		bottom: 0;
		right: 10px;
		font-size: small;
		font-size: 0.6rem;
		color: white;
	}

	.section-title > h2 {
		text-align: center;
		margin-top: 40px;
		font-size: x-large;
	}

	.bottom {
		margin-bottom: 40px;
	}

	.gsskt {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: rgb(151, 151, 151);
	}
</style>
