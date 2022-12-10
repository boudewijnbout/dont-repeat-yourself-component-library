<script>
	import Hero from "$lib/components/IndexComponents/Hero.svelte";
	import Introduction from "$lib/components/IndexComponents/Introduction.svelte";
	import Cursor from "$lib/components/Cursor.svelte";
	import {StandardSection} from "cmd-midterm-components";
	export let data;
</script>

<main>
	<Cursor />
	<Hero heroTitle={data.page.title}>
		<Introduction introduction={data.page.introduction} />
	</Hero>
	
	<StandardSection sections={[
		{
			title: '1.0 Beoogde leerresultaten',
			links: [
				{ text: 'Humanity-centered digital designers', href: '/' },
				{ text: 'Competenties', href: '/' },
				{ text: 'Werkveld en maatschappij', href: '/' },
				{ text: 'Ontwikkelingen', href: '/' },
				{ text: `Ambities en dillema's`, href: '/' }
			]
		},
		{
			title: '2.0  Onderwijsleeromgeving',
			links: [
				{ text: 'Onderwijsvisie en didactiek', href: '/' },
				{ text: 'Curriculumopbouw', href: '/' },
				{ text: 'Borging onderwijskwaliteit', href: '/' },
				{ text: 'Onderwijs en praktijk', href: '/' },
				{ text: 'Onderwijs en onderzoek', href: '/' },
				{ text: 'Internationalisering', href: '/' },
				{ text: 'Studenten begeleiding', href: '/' },
				{ text: 'Digitale en analoge voorzieningen', href: '/' },
				{ text: `Ambities en dillema's`, href: '/' }
			]
		},
		{
			title: '3.0  Toetsing',
			links: [
				{ text: 'Toetsbeleid en -plan', href: '/' },
				{ text: 'Toetsprogramma en -praktijk', href: '/' },
				{ text: 'Toetsing en feedback', href: '/' },
				{ text: 'Borging en kwaliteit', href: '/' },
				{ text: `Ambities en dillema's`, href: '/' }
			]
		},
		{
			title: '4.0  Gerealiseerde leerresultaten',
			links: [
				{ text: 'Afstudeerproces', href: '/' },
				{ text: 'Borging afstudeerniveau vanuit examencommissie', href: '/' },
				{ text: `Ambities en dillema's`, href: '/' }
			]
		}
	]} />
</main>
