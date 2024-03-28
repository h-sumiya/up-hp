<script>
	import { browser } from "$app/environment";
	import { onMount } from "svelte";
	import Large from "./large.svelte";
	import Small from "./small.svelte";
	import { drawerOpen, headerIsLarge } from "../store";

	let top = 0;

	let before = 0;

	onMount(() => {
		window.addEventListener("scroll", () => {
			const scroll = window.scrollY;
			if (scroll < h) {
				if (scroll < before) {
					top = top = Math.max(-scroll, top);
				} else {
					top = -scroll;
				}
			} else {
				const diff = scroll - before;
				if (scroll < before) {
					top = Math.min(0, top - diff);
				} else {
					top = Math.max(-h, top - diff);
				}
			}
			before = scroll;
		});
	});
	let h;
	let w;
	if (browser) {
		w = window.innerWidth;
	}
	$: $headerIsLarge = w > 768;
	const autoClose = (isLarge) => {
		if (isLarge) {
			drawerOpen.set(false);
		}
	};
	$: autoClose($headerIsLarge);
</script>

<header style="top: {top}px" bind:clientHeight={h} bind:clientWidth={w}>
	{#if $headerIsLarge}
		<Large />
	{:else}
		<Small />
	{/if}
</header>

<style>
	header {
		position: fixed;
		width: 100%;
		z-index: 1000;
		right: calc(var(--drawer-slide) * 1px);
	}
</style>
