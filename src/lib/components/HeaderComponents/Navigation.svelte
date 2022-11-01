<script>
	import { cursor } from "$lib/stores/cursor";
	import { page } from "$app/stores";

	let isActive = false;

	function toggleNavMenu() {
		isActive = !isActive;

		isActive
			? document.body.classList.add("freeze")
			: document.body.classList.remove("freeze");
	}
	function closeNavMenu() {
		isActive = false;
		document.body.classList.remove("freeze");
	}
</script>

<nav
	on:mouseenter={() =>
		cursor.set({
			scale: "1",
			color: "rgba(0, 0, 0, 0.15)",
			border: "none",
		})}
	on:mouseleave={() =>
		cursor.set({
			scale: "1",
			color: "rgba(255, 240, 33, 0.5)",
			border: "none",
		})}
	class:active={isActive}
>
	<a
		href="/beoogde-leerresultaten"
		data-sveltekit-prefetch
		on:mouseenter={() =>
			cursor.set({
				scale: "1.5",
				color: "rgba(0, 0, 0, 0.15)",
				border: "2px dashed #000",
			})}
		on:mouseleave={() =>
			cursor.set({
				scale: "1",
				color: "rgba(0,0,0,0.15)",
				border: "none",
			})}
		class:active={$page.url.pathname === "/beoogde-leerresultaten"}
		on:click={closeNavMenu}>Beoogde leerresultaten</a
	>
	<a
		href="/onderwijsleeromgeving"
		data-sveltekit-prefetch
		on:mouseenter={() =>
			cursor.set({
				scale: "1.5",
				color: "rgba(0, 0, 0, 0.15)",
				border: "2px dashed #000",
			})}
		on:mouseleave={() =>
			cursor.set({
				scale: "1",
				color: "rgba(0,0,0,0.15)",
				border: "none",
			})}
		class:active={$page.url.pathname === "/onderwijsleeromgeving"}
		on:click={closeNavMenu}>Onderwijsleeromgeving</a
	>
	<a
		href="/toetsing"
		data-sveltekit-prefetch
		on:mouseenter={() =>
			cursor.set({
				scale: "1.5",
				color: "rgba(0, 0, 0, 0.15)",
				border: "2px dashed #000",
			})}
		on:mouseleave={() =>
			cursor.set({
				scale: "1",
				color: "rgba(0,0,0,0.15)",
				border: "none",
			})}
		class:active={$page.url.pathname === "/toetsing"}
		on:click={closeNavMenu}>Toetsing</a
	>
	<a
		href="/gerealiseerde-leerresultaten"
		data-sveltekit-prefetch
		on:mouseenter={() =>
			cursor.set({
				scale: "1.5",
				color: "rgba(0, 0, 0, 0.15)",
				border: "2px dashed #000",
			})}
		on:mouseleave={() =>
			cursor.set({
				scale: "1",
				color: "rgba(0,0,0,0.15)",
				border: "none",
			})}
		class:active={$page.url.pathname === "/gerealiseerde-leerresultaten"}
		on:click={closeNavMenu}>Gerealiseerde leerresultaten</a
	>
</nav>
<button on:click={toggleNavMenu} class:active={isActive}>
	<span />
	<span />
	<span />
</button>

<style>
	nav {
		display: none;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 1.5rem;
	}

	nav a {
		position: relative;
	}

	nav a.active {
		background: linear-gradient(45deg, transparent 5%, var(--color-black) 5%);
		color: #fff;
		padding: 0.35rem 0.35rem 0.35rem 0.5rem;
	}

	nav a::before {
		content: "";
		position: absolute;
		bottom: -0.3rem;
		right: 0;
		width: 0;
		height: 2px;
		background-color: var(--color-black);
		transition: width 1s cubic-bezier(0.25, 1, 0.5, 1);
		display: none;
		z-index: 30;
	}

	nav a:hover::before {
		left: 0;
		right: auto;
		width: 100%;
	}

	nav.active {
		position: fixed;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		font-size: 1.3rem;
		font-weight: bold;
		gap: 0.8rem;
		inset: 0;
		width: 100%;
		height: 100vh;
		background-color: var(--color-cmd-yellow);
		overflow: hidden;
		z-index: 20;
	}

	nav.active a {
		background-color: var(--color-cmd-yellow);
		filter: brightness(85%);
		width: 85%;
		padding: 0.5rem;
	}

	button {
		all: unset;
		display: block;
		position: relative;
		z-index: 1;
		cursor: pointer;
		z-index: 30;
	}

	button span {
		display: block;
		width: 2rem;
		height: 0.2rem;
		margin-bottom: 5px;
		position: relative;
		background-color: var(--color-black);
		border-radius: 6px;
		transform-origin: 0 0;
		transition: 0.4s;
	}

	button span:last-child {
		margin: 0;
	}

	button.active span:nth-child(1) {
		transform: translate(0px, -2px) rotate(45deg);
	}

	button.active span:nth-child(2) {
		opacity: 0;
		transform: translateX(15px);
	}

	button.active span:nth-child(3) {
		transform: translate(-3px, 3px) rotate(-45deg);
	}

	@media (min-width: 60rem) {
		nav {
			display: flex;
		}

		nav a::before {
			display: block;
		}

		button {
			display: none;
		}
	}
</style>
