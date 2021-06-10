<script>
	import Navbar from "./Navbar.svelte";
	import Player from "./Player.svelte";

	let players = [
		{
			name: "John Doe",
			points: 45
		},
		{
			name: "Sam Smith",
			points: 53
		},
		{
			name: "Sara Wilson",
			points: 47
		},
	];
</script>

<Navbar />

<div class="container">
	{#if players.length === 0}
		<p> No Players </p>
	{:else}
		{#each players as player}
			<Player name={player.name} points={player.points} />
		{/each}
	{/if}
</div>