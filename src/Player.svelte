<script>
	import Navbar from "./Navbar.svelte";

	let name = "John Doe";
	let points = 100;
	let showControls = false;

	const addPoint = () => {
		points += 1
	};

	const removePoint = () => {
		points -= 1
	};

	const toggleControls = () => {
		showControls = !showControls
	};
</script>

<style>
	/* main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	} */
	h1 {
		color: #ff3e00;
	}
    h3 {
        margin-bottom: 10px;
    }
</style>

<Navbar />

<div class="container">
	<div class="card">
		<h1>
			{name}
			<button class="btn-toggle" on:click={toggleControls}>
				{#if showControls} - {:else} + {/if}
			</button>
		</h1>
		<h3>Points: {points}</h3>
		{#if showControls}
			<button class="btn" on:click={addPoint}>
				+1
			</button>
			<button class="btn btn-dark" on:click={removePoint}>
				-1
			</button>
			<input type="number" bind:value={points} />
		{/if}
	</div>
</div>