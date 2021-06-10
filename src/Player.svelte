<script>
	export let name;
	export let points;
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

<div class="card">
	<h1 class="card-header">
		{name}
		<button class="btn-toggle" on:click={toggleControls}>
			{#if showControls} - {:else} + {/if}
		</button>
	</h1>
	<h3 class="points-display"> Points: {points} </h3>
	{#if showControls}
        <div class="controls">
            <div class="controls-btns">
                <button class="btn" on:click={addPoint}>
                    +1
                </button>
                <button class="btn btn-dark" on:click={removePoint}>
                    -1
                </button>
            </div>
            <div class="controls-pointsInput">
                <input type="number" bind:value={points} />
            </div>
        </div>
	{/if}
</div>