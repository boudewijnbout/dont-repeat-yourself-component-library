<script>
	import { cursor } from "$lib/stores/cursor";

	export let showOnPx = 150;

	let hidden = true;

	function goTop() {
		document.body.scrollIntoView();
	}

	function scrollContainer() {
		return document.documentElement || document.body;
	}

	function handleOnScroll() {
		if (!scrollContainer()) {
			return;
		}

		if (scrollContainer().scrollTop > showOnPx) {
			hidden = false;
		} else {
			hidden = true;
		}
	}
</script>

<svelte:window on:scroll={handleOnScroll} />

<button
	on:mouseenter={() =>
		cursor.set({
			scale: "1.5",
			color: "rgba(0, 0, 0, 0.15)",
			border: "2px dashed #000",
		})}
	on:mouseleave={() =>
		cursor.set({
			scale: "1",
			color: "rgba(0,0,0,0.15)",
			border: "none",
		})}
	class="back-to-top"
	on:click={goTop}
	class:hidden>↑</button
>

<style>
	.back-to-top {
		right: 0;
		bottom: 5rem;
		height: 2.375rem;
		width: 2.375rem;
		z-index: 98;
		position: fixed;
		outline: none;
		background-color: var(--color-black);
		border: none;
		padding: 0.5rem;
		border-top-left-radius: 10px;
		border-bottom-left-radius: 10px;
		transform: translateX(0);
		transition: 0.3s;
		color: #fff;
		font-size: 1.5rem;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
	}

	.back-to-top.hidden {
		transform: translateX(100%);
	}
</style>
