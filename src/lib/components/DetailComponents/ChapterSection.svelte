<script>
	export let chapterTitle;
	export let chapterNumber;
	export let chapterUID;
</script>

<section id={chapterUID}>
	<div>
		<span>{chapterNumber}</span>
		<h3>{chapterTitle}</h3>
	</div>
	<article class="content">
		<slot />

		<hr />
	</article>
</section>

<style>
	section {
		border-left: 3px solid var(--color-black);
		border-right: 3px solid var(--color-black);
		grid-template-columns: 0.3fr 1.1fr;
		grid-template-areas: "spanArea articleArea";
		padding: 1rem;
	}

	div {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
	}

	span {
		background-color: var(--color-cmd-yellow);
		padding: 0.25rem;
		font-size: 1.3rem;
		display: inline-block;
		margin-bottom: -2px;
		border: 2px solid var(--color-black);
	}

	h3 {
		font-size: 1.3rem;
		border: 2px solid var(--color-black);
		padding: 0.25rem;
		margin-bottom: 1rem;
	}

	.content {
		grid-area: articleArea;
	}

	hr {
		border-top: 1px solid #fafafa;
	}

	@media (min-width: 60rem) {
		section {
			padding: 3rem 2rem;
		}
	}

	@media (min-width: 81.25rem) {
		section {
			padding: 2rem 5rem;
			display: grid;
			grid-gap: 3rem;
		}

		div {
			position: sticky;
			align-self: start;
			justify-self: start;
			grid-area: spanArea;
			top: 1rem;
		}
	}
</style>
