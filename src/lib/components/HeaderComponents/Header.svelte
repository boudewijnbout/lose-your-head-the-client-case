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
	h1 {
		text-align: center;
		color: black;
		text-shadow: #fff021 0.1em 0em;
	}

	header {
		text-align: center;
		text-decoration: none;
		color: black;
		background-color: #fff021;
		padding: 0.75em 1rem;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	a {
		color: black;
	}

	h1 {
		font-size: 1.5rem;
	}

	@media (min-width: 60rem) {
		header {
			flex-direction: column;
			padding: 0;
			background-color: transparent;
		}

		a {
			padding: 1.5rem;
			display: inline-block;
		}

		h1 {
			font-size: 1.75rem;
		}
	}
</style>
