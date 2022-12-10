<script>
	import * as helpers from "@prismicio/helpers";

	export let introduction;
</script>

<article>
	{@html helpers.asHTML(introduction)}
</article>

<style>
	article {
		gap: 1rem;
		display: flex;
		flex-direction: column;
	}

	@media (min-width: 40rem) {
		article {
			width: 85%;
		}
	}

	@media (min-width: 50rem) {
		article {
			width: 70%;
		}
	}

	@media (min-width: 60rem) {
		article {
			width: 65%;
		}

		@media (min-width: 68.75rem) {
			article {
				width: 60%;
			}
		}

		@media (min-width: 81.25rem) {
			article {
				width: 85%;
				font-size: 0.9rem;
			}
		}
	}
</style>
