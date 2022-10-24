<script>
	import { cursor } from "$lib/stores/cursor";
	import * as helpers from "@prismicio/helpers";

	export let introductionTitle;
	export let introduction;
</script>

<section>
	<div>
		<h3>
			{introductionTitle}
		</h3>
		{@html helpers.asHTML(introduction)}
	</div>
	<figure
		on:mouseenter={() =>
			cursor.set({
				color: "rgba(0, 0, 0, 0.5)",
			})}
		on:mouseleave={() =>
			cursor.set({
				color: "rgba(255, 240, 33, 0.5)",
			})}
	>
		<img src="images/cmd-laptop.png" alt="Laptop" />
	</figure>
</section>

<style>
	section {
		background-color: var(--color-white);
		padding: 2rem 1rem;
		gap: 1rem;
		display: flex;
		flex-direction: column;
	}

	div {
		gap: 1rem;
		display: flex;
		flex-direction: column;
	}

	h3 {
		font-size: 1.5rem;
		margin-bottom: 1rem;
	}

	figure {
		background-color: var(--color-cmd-yellow);
		padding: 2rem 3rem;
		text-align: center;
		width: 50vw;
		margin: auto;
		clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
	}

	@media (min-width: 40rem) {
		section {
			flex-direction: row;
			align-items: center;
			justify-content: center;
			padding: 3rem;
		}
	}

	@media (min-width: 60rem) {
		h3 {
			font-size: 2rem;
		}
	}
</style>
