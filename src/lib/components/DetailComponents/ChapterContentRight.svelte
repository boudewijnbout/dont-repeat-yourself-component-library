<script>
	import * as helpers from "@prismicio/helpers";

	export let contentRight;
</script>

{#if contentRight.length > 0}
	<div>
		{@html helpers.asHTML(contentRight)}
	</div>
{/if}

<style>
	div {
		margin-bottom: 1.5rem;
	}
</style>
