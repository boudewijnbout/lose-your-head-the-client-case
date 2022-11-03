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
		display: grid;
		grid-template-columns: 1fr;
		/* grid-gap: 2rem; */
		grid-gap: 1rem;
		padding: 1rem;
	}

	@media (min-width: 60rem) {
		section {
			padding: 3rem 2rem;
		}

		h2 {
			font-size: 3rem;
		}
	}

	@media (min-width: 68.75rem) {
		section {
			padding: 3rem 2rem;
			grid-template-columns: 1fr 1fr;
		}
	}
	@media (min-width: 81rem) {
		section {
			padding: 6rem 5rem;
			grid-gap: 0;
		}
		h2 {
			font-size: 3rem;
		}
	}
</style>
