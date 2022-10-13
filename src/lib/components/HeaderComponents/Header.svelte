<script>
	import Navigation from "$lib/components/HeaderComponents/Navigation.svelte";
</script>

<header>
	<a href="/" data-sveltekit-prefetch>
		<h1 class="logo">CMD Midterm</h1>
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
