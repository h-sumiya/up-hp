<script>
	import Margin from './../../lib/header/margin.svelte';
	import aboutus from "./img/IMG_1663.jpg";

</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="background"> 
	<ul class="circles">
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
	</ul>
</div>
<div class="justify"></div>

<div class="contena">
	<Margin />
	<div class="section1">
		<h1 class="title_top">Our</h1>
		<h1 class="title_bottom">Philosophy</h1>
		<div class="trapezium"></div>
	</div>
	<div class="flex">
		<!-- <img src={aboutus} alt=""> -->
		<div class="text">
				<h3><strong>~ 偏見のない学びを、すべての人に ~</strong></h3>
				<p>
					「プログラミングは理系男性のやるもの」<br>
					「自分のキャリアには関係ない」<br>
					「自分では習得できない」<br>
				</p>
				<p>
					今世の中では、プログラミングに対する様々な偏見が蔓延しています。
				</p>
		</div>
	</div>

	<section>
		<img src={aboutus} alt="picture of Unbiased Programming's members">
		<div class = "text max50">
			<h1>活動理念</h1>
			<h3><strong>~ 偏見のない学びを、すべての人に ~</strong></h3>
			<p>
				「プログラミングは理系男性のやるもの」<br>
				「自分のキャリアには関係ない」<br>
				「自分では習得できない」<br>
			</p>
			<p>
				今世の中では、プログラミングに対する様々な偏見が蔓延しています。
			</p>
			<p>
				私たちは、それらの偏見を是正し、
				<strong>すべての人がプログラミング学習に挑戦できる環境やきっかけをつくる</strong>
				ことを目的とし、活動しています。
			</p>
		</div>
	</section>

	<section>
		<div class="text">
			<br>
			<h2>団体詳細 :</h2>
			<section>
				<p>
					活動場所：上智大学<br>
					活動頻度：週一回程度<br>
					所属人数：15人程度（男女比7:3）<br>
					サークル費：通期3000円

				</p>
			</section>
		</div>
	</section>
</div>





<style>
	.background {
        position: sticky;	
        background: linear-gradient(#ffffff, #d5d5d5);
        background-size: cover;
        background-position: center;
        height: 100vh;
        top: 0;
        left: 0;
        z-index: -1;
    }

	.justify {
		position: relative;
		height: 720px;
		width: 5px;
	}

    .contena {
        position: absolute;
        top: 0;
        left: 0;
    }

	.section1 {
		/* position: sticky; */
		position: relative;
		height: 130px;
		width: 100vw;
		top: 0;
        left: 0;
		z-index: 0;
	}

    h1 {
        font-size: 2rem;
        margin: 1rem 0;
    }

    p {
        margin: 1rem 0;
    }

	img {
		object-fit: cover;
		width: 40vw;
		top: 0;
		left: 0;
	}

	section {
		display: flex;
		padding: 1rem;
	}

	.text {
		padding-left: 20px;
	}

	.max50 {
		max-width: 50vw;
	}

	.title_top {
		width: 100vw;
		color: #262626;
		font-size: 68px;
		font-family: arial;
		font-weight: bold;
		padding-left: 20px;
		position: relative;
		background: linear-gradient(#f5f5f5, #e0e0e0);
		height: 55px;
	}

	.title_bottom {
		color: #6c6c6c;
		font-size: 68px;
		font-family: arial;
		font-weight: bold;
		padding-left: 20px;
		position: relative;
		top: -15px;
		left: 0;
		width: 50vw;
	}

	.trapezium {
		position: relative;
		top: -111px;
		left: -20px;
		height: 74px;
		width: calc(300px + 30vw);
		background: linear-gradient(#e0e0e0, #c0c0c0);
		transform: skewX(-30deg);
		/* border-top: 79px solid;
		border-right: 25px solid transparent; */
		z-index: -1;
	}

	.text {
		width: calc(100vw - 60px);
		padding-left: 30px;
	}

	h3 {
		padding: 15px
	}

	p {
		margin: 1rem 0;
	}
	/* img {
		position: relative;
		object-fit: cover;
		height: 300px;
		top: -1px;
		left: 0;
		z-index: -1;
		opacity: 0.3;

	} */

	.flex {
		display: flex;
		flex-wrap: wrap;
	}

	.circles{
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		overflow: hidden;
	}

	.circles li{
		position: absolute;
		display: block;
		list-style: none;
		width: 20px;
		height: 20px;
		background: rgba(255, 255, 255, 0.4);
		animation: animate 25s linear infinite;
		bottom: -150px;
		
	}

	.circles li:nth-child(1){
		left: 25%;
		width: 80px;
		height: 80px;
		animation-delay: 0s;
	}


	.circles li:nth-child(2){
		left: 10%;
		width: 20px;
		height: 20px;
		animation-delay: 2s;
		animation-duration: 12s;
	}

	.circles li:nth-child(3){
		left: 70%;
		width: 20px;
		height: 20px;
		animation-delay: 4s;
	}

	.circles li:nth-child(4){
		left: 40%;
		width: 60px;
		height: 60px;
		animation-delay: 0s;
		animation-duration: 18s;
	}

	.circles li:nth-child(5){
		left: 65%;
		width: 20px;
		height: 20px;
		animation-delay: 0s;
	}

	.circles li:nth-child(6){
		left: 75%;
		width: 110px;
		height: 110px;
		animation-delay: 3s;
	}

	.circles li:nth-child(7){
		left: 35%;
		width: 150px;
		height: 150px;
		animation-delay: 7s;
	}

	.circles li:nth-child(8){
		left: 50%;
		width: 25px;
		height: 25px;
		animation-delay: 15s;
		animation-duration: 45s;
	}

	.circles li:nth-child(9){
		left: 20%;
		width: 15px;
		height: 15px;
		animation-delay: 2s;
		animation-duration: 35s;
	}

	.circles li:nth-child(10){
		left: 85%;
		width: 150px;
		height: 150px;
		animation-delay: 0s;
		animation-duration: 11s;
	}

	@keyframes animate {

		0%{
			transform: translateY(0) rotate(0deg);
			opacity: 1;
			border-radius: 0;
		}

		100%{
			transform: translateY(-1000px) rotate(720deg);
			opacity: 0;
			border-radius: 50%;
		}

	}
</style>