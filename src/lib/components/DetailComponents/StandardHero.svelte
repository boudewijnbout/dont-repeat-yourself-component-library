<script>
	import * as helpers from "@prismicio/helpers";
	import { cursor } from "$lib/stores/cursor";

	export let standardHeaderTitle;
	export let standardHeaderIntroduction;
	export let standardNumber;
</script>

<section
	on:mouseenter={() =>
		cursor.set({
			color: "rgba(0, 0, 0, 0.15)",
		})}
	on:mouseleave={() =>
		cursor.set({
			color: "rgba(255, 240, 33, 0.5)",
		})}
>
	<h2>{`${standardNumber}.0`} {standardHeaderTitle}</h2>
	{@html helpers.asHTML(standardHeaderIntroduction)}
</section>

<style>
	section {
		background-color: var(--color-cmd-yellow);
		border-left: 3px solid var(--color-black);
		border-right: 3px solid var(--color-black);
		border-bottom: 3px solid var(--color-black);
		height: 15rem;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		justify-content: center;
	}

	@media (min-width: 45rem) {
		section {
			height: 15rem;
		}

		h2 {
			font-size: 2rem;
		}
	}

	@media (min-width: 60rem) {
		section {
			padding: 3rem 2rem;
		}

		h2 {
			font-size: 2.5rem;
		}
	}

	@media (min-width: 60rem) {
		section {
			height: 10rem;
		}
	}

	@media (min-width: 68.75rem) {
		section {
			padding: 3rem 2rem;
			grid-template-columns: 1fr 1fr;
			display: grid;
			grid-gap: 1rem;
		}
	}
	@media (min-width: 81rem) {
		section {
			padding: 6rem 5rem;
			height: 10rem;
		}
		h2 {
			font-size: 3rem;
		}
	}
</style>
