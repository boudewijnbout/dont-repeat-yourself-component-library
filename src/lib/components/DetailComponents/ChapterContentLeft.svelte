<script>
	import * as helpers from "@prismicio/helpers";

	export let contentLeft;
</script>

<div>
	{@html helpers.asHTML(contentLeft)}
</div>

<style>
	div {
		margin-bottom: 1.5rem;
	}
</style>
