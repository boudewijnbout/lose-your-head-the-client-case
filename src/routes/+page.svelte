<script>
	import Hero from "$lib/components/IndexComponents/Hero.svelte";
	import Introduction from "$lib/components/IndexComponents/Introduction.svelte";
	import Standard from "$lib/components/IndexComponents/Standard.svelte";
	import StandardChapter from "$lib/components/IndexComponents/StandardChapter.svelte";
	import StandardSection from "$lib/components/IndexComponents/StandardSection.svelte";
	import Cursor from "$lib/components/Cursor.svelte";
	import Footer from "$lib/components/Footer.svelte";

	export let data;
</script>

<main>
	<Cursor />
	<Hero heroTitle={data.page.title} />
	<Introduction
		introduction={data.page.introduction}
		introductionTitle="Midterm"
	/>

	<StandardSection>
		{#each data.standards as standard}
			<Standard
				standardUID={`/${standard.title}`}
				standardTitle={`${standard?.standardnumber}.0 ${standard.title}`}
			>
				{#each standard.chapters as chapter, i}
					<StandardChapter>
						chapterTitle={`${standard.standardnumber}.${i + 1} ${
							chapter.data.title
						}`}
						chapterUID={`${chapter.uid}`}
						standardUID={`${standard.uid}`}
					</StandardChapter>
				{/each}
			</Standard>
		{/each}
	</StandardSection>
</main>
