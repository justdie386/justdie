<script>
	import Projects from './projects.svelte';
	import Skills from './skills.svelte';
	import Passions from './passions.svelte';

	const options = [Projects, Skills, Passions];
	let currentSelection = options[0];
	function updateSelection(choice) {
		currentSelection = options[choice];
	}
</script>

<body>
	<h1>Welcome</h1>
	<nav>
		<button on:click={() => updateSelection(0)}>Projects</button>
		<button on:click={() => updateSelection(1)}>Skillset</button>
		<button on:click={() => updateSelection(2)}>Passions</button>
	</nav>
	<main>
		<svelte:component this={currentSelection} />
	</main>
</body>

<style>
	@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@500&display=swap');
	:root,
	body {
		padding: 10px;
		margin-left: auto;
		margin-right: auto;
		max-height: 100%;
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: stretch;
		background-color: #24243f;
		color: black;
		font-family: JetBrains Mono, monospace;
		overflow: hidden;
	}

	nav {
		display: flex;
		gap: 1rem;
	}

	main {
		display: flex;
		flex-direction: column;
		align-items: start;
	}
	button {
		font-size: revert;
		width: 100px;
		height: 40px;
		border-radius: 5px;
		border: none;
		background-color: #282854;
		color: black;
		transition: ease 200ms;
		font-family: JetBrains Mono, monospace;
		box-shadow: 0 0 5px 1px black;
	}
	button:hover{
		transform: scale(120%);
	}
</style>
