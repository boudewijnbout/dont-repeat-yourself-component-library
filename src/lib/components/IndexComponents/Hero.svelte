<script>
	export let heroTitle;

	import { cursor } from "$lib/stores/cursor";
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
	<h2>
		{heroTitle}
	</h2>
	<slot />
</section>

<style>
	section {
		background-color: var(--color-cmd-yellow);
		display: grid;
		grid-template-columns: 1fr;
		grid-gap: 2rem;
		border-left: 3px solid var(--color-black);
		border-right: 3px solid var(--color-black);
		border-bottom: 3px solid var(--color-black);
		padding: 1rem;
	}

	h2 {
		font-size: 2rem;
	}

	@media (min-width: 50rem) {
		h2 {
			width: 80%;
		}
	}

	@media (min-width: 60rem) {
		section {
			padding: 3rem 2rem;
		}

		h2 {
			font-size: 3rem;
		}
	}

	@media (min-width: 81.25rem) {
		section {
			grid-template-columns: 1fr 1fr;
			grid-gap: 5rem;
			padding: 6rem 5rem;
		}

		h2 {
			font-size: 3.5rem;
			width: auto;
		}
	}
</style>
