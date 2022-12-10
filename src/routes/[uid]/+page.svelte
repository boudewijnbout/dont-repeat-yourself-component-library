<script>
	import ChapterSection from "$lib/components/DetailComponents/ChapterSection.svelte";
	import ChapterContentLeft from "$lib/components/DetailComponents/ChapterContentLeft.svelte";
	import ChapterContentRight from "$lib/components/DetailComponents/ChapterContentRight.svelte";
	import StandardHero from "$lib/components/DetailComponents/StandardHero.svelte";
	import Cursor from "$lib/components/Cursor.svelte";
	import StandardNavigation from "$lib/components/DetailComponents/StandardNavigation.svelte";
	import StandardNavigationLink from "../../lib/components/DetailComponents/StandardNavigationLink.svelte";

	export let data;
</script>

<main>
	<Cursor />

	<StandardHero
		standardHeaderTitle={data.standard.data.title}
		standardHeaderIntroduction={data.standard.data.introduction}
		standardNumber={data.standard.data.standardnumber}
	/>

	{#each data.standard.data.chapters as chapter, i}
		<ChapterSection
			chapterTitle={chapter.data.title}
			chapterNumber={`${data.standard.data.standardnumber}.${i + 1}`}
			chapterUID={chapter.uid}
		>
			<ChapterContentLeft contentLeft={chapter.data.contentleft} />
			<ChapterContentRight contentRight={chapter.data.contentright} />
		</ChapterSection>
	{/each}
	<StandardNavigation
		navigationLink={data.standard.uid}
		standardHeaderTitle={data.standard.data.title}
	>
		{#each data.standard.data.chapters as chapter}
			<StandardNavigationLink
				chapterLink={`${data.standard.uid}/#${chapter.uid}`}
				chapter={chapter.data.title}
			/>
		{/each}
	</StandardNavigation>
</main>
