<script>
	let name = "John Doe";
	let points = 100;

	const addPoint = () => {
		points += 1
	};

	const removePoint = () => {
		points -= 1
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
</style>

<div class="container">
	<div class="card">
		<h1>{name}</h1>
		<h3>{points}</h3>
		<button class="btn" on:click={addPoint}>
			+1
		</button>
		<button class="btn btn-dark" on:click={removePoint}>
			-1
		</button>
	</div>
</div>