<script>
	/*
	全ページのレイアウトを定義するファイルです。
	このファイルを変更する場合は影響範囲をよく確認してください。
	*/
	import { browser } from "$app/environment";
	import Drawer from "./../lib/drawer.svelte";
	import { drawerOpen } from "./../lib/store.js";
	import Header from "$lib/header/Header.svelte";
	import Footer from "../lib/footer/Footer.svelte";
	import "./styles.css";
	import { tweened } from "svelte/motion";
	import { cubicOut } from "svelte/easing";

	const drawerSlide = tweened(0, {
		duration: 300,
		easing: cubicOut,
	});

	$: $drawerOpen ? drawerSlide.set(300) : drawerSlide.set(0);

	$: if (browser) {
		$drawerOpen
			? (document.body.style.overflow = "hidden")
			: (document.body.style.overflow = "auto");
	}
</script>

<div style:--drawer-slide={$drawerSlide}>
	<Header />

	{#if $drawerSlide > 0}
		<div
			class="cover"
			tabindex="0"
			role="button"
			on:click={() => drawerOpen.update((v) => !v)}
		></div>
	{/if}

	<div class="app">
		<main>
			<slot />
		</main>

		<Footer />
	</div>

	{#if $drawerSlide > 0}
		<div class="drawer">
			<Drawer />
		</div>
	{/if}
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		transform: translateX(calc(var(--drawer-slide) * -1px));
	}

	main {
		flex: 1;
	}

	.cover {
		position: fixed;
		top: 0;
		right: calc(var(--drawer-slide) * 1px);
		width: 100vw;
		height: 100vh;
		background-color: rgba(0, 0, 0, calc(0.5 * var(--drawer-slide) / 300));
		z-index: 99;
	}

	.drawer {
		position: fixed;
		top: 0;
		right: calc(-300px + var(--drawer-slide) * 1px);
		width: 300px;
		height: 100vh;
		box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
		z-index: 100;
	}
</style>
