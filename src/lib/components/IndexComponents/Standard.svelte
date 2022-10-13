<script>
	export let standardUID;
	export let standardTitle;
</script>

<section>
	<a href={standardUID}>{standardTitle}</a>
	<ul><slot /></ul>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
	}

	a {
		color: var(--color-black);
		font-size: 1.3rem;
		font-weight: 700;
		padding-bottom: 0.5rem;
		margin-bottom: 0.5rem;
		border-bottom: 3px solid var(--color-black);
	}
</style>
