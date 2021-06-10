<script>
	import Navbar from "./Navbar.svelte";
	import Player from "./Player.svelte";

	let players = [
		{
			name: "John Doe",
			points: 53
		},
		{
			name: "Sam Smith",
			points: 45
		},
		{
			name: "Sara Wilson",
			points: 47
		}
	];
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

<Navbar />
<div class="container">
	{#if players.length === 0}
		<p> No Players </p>
	{:else}
		{#each players as player}
			<Player name={players.name} points={players.points} />
		{/each}
	{/if}
</div>