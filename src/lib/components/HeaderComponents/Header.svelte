<script>
	import Navigation from "$lib/components/HeaderComponents/Navigation.svelte";
	import { cursor } from "$lib/stores/cursor";
</script>

<header>
	<a href="/" data-sveltekit-prefetch>
		<h1
			on:mouseenter={() =>
				cursor.set({
					scale: "1.5",
					color: "rgba(0, 0, 0, 0.15)",
					border: "2px dashed #000",
				})}
			on:mouseleave={() =>
				cursor.set({
					scale: "1",
					color: "rgba(255, 240, 33, 0.5)",
					border: "none",
				})}
			class="logo"
		>
			CMD Midterm
		</h1>
	</a>
	<Navigation />
</header>

<style>
	header {
		background-color: var(--color-white);
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 1rem;
		border: 3px solid var(--color-black);
	}

	h1 {
		font-size: 1.5rem;
	}

	a {
		color: var(--color-black);
	}

	@media (min-width: 60rem) {
		header {
			padding: 1rem 2rem;
		}
	}

	@media (min-width: 81.25rem) {
		header {
			padding: 1rem 5rem;
		}
	}
</style>
