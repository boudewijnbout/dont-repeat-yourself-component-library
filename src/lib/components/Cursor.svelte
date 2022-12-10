<script>
	import { cursor as cursorStore } from "$lib/stores/cursor";
	import { onMount } from "svelte";

	let cursor;

	let m = { x: null, y: null };

	onMount(() => {
		cursor.style.display = "block";
	});

	$: {
		if (cursor) {
			cursor.style.backgroundColor = $cursorStore.color;
			cursor.style.transform = `scale(${$cursorStore.scale})`;
			cursor.style.border = $cursorStore.border;
		}
	}

	function handleMouseMove(e) {
		m.x = e.clientX - cursor.clientWidth / 2;
		m.y = e.clientY - cursor.clientHeight / 2;
	}
</script>

<svelte:window on:mousemove={handleMouseMove} />
<div class="cursor" style="left: {m.x}px; top: {m.y}px" bind:this={cursor} />

<style>
	div {
		background-color: rgba(255, 240, 33, 0.5);
		width: 50px;
		height: 50px;
		position: fixed;
		transition: cubic-bezier(0.17, 0.67, 0.83, 0.67);
		transition-duration: 200ms;
		transition-timing-function: ease-out;
		border-radius: 50%;
		pointer-events: none;
		left: -50px;
		top: 0;
		z-index: 999;
		visibility: hidden;
	}

	@media (min-width: 68.75rem) {
		div {
			visibility: visible;
		}
	}
</style>
