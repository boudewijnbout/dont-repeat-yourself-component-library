<script>
	import { cursor } from "$lib/stores/cursor";
	import { page } from "$app/stores";

	let isActive = false;

	export function toggleNavMenu() {
		isActive = !isActive;

		isActive
			? document.body.classList.add("freeze")
			: document.body.classList.remove("freeze");
	}

	export function closeNavMenu() {
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
		on:click={closeNavMenu}
		class:active={$page.url.pathname === "/beoogde-leerresultaten"}
		>Beoogde leerresultaten</a
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
		on:click={closeNavMenu}
		class:active={$page.url.pathname === "/onderwijsleeromgeving"}
		>Onderwijsleeromgeving</a
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
		on:click={closeNavMenu}
		class:active={$page.url.pathname === "/toetsing"}>Toetsing</a
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
		on:click={closeNavMenu}
		class:active={$page.url.pathname === "/gerealiseerde-leerresultaten"}
		>Gerealiseerde leerresultaten</a
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
		z-index: 99;
	}

	nav.active a {
		background-color: var(--color-cmd-yellow);
		filter: brightness(85%);
		width: 85%;
		padding: 0.5rem;
	}

	a {
		position: relative;
	}

	nav a.active {
		background-color: var(--color-black);
		color: #fff;
		padding: 0.35rem 0.35rem 0.35rem 0.5rem;
	}

	a.active::before {
		display: none;
	}

	a::before {
		content: "";
		position: absolute;
		top: 0;
		right: 0;
		width: 6px;
		height: 6px;
		border-radius: 50%;
		left: 50%;
		z-index: -1;
		background-color: var(--color-cmd-yellow);
		border: 1px solid var(--color-black);
		transition: all 250ms;
		display: none;
	}

	a:hover::before {
		right: auto;
		top: -0.6rem;
		z-index: 1;
	}

	button {
		all: unset;
		display: block;
		position: relative;
		z-index: 1;
		cursor: pointer;
		z-index: 99;
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

		nav a.active {
			background: linear-gradient(45deg, transparent 5%, var(--color-black) 5%);
		}

		a::before {
			display: block;
		}

		button {
			display: none;
		}
	}
</style>
