<script>
	import Navbar from "./Navbar.svelte";
	import Player from "./Player.svelte";
	import AddPlayer from "./AddPlayer.svelte";

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

	const addPlayer = (e) => {
		const newPlayer = e.detail;
		players = [...players, newPlayer];
	};

	const removePlayer = (e) => {
		players = players.filter(player => player.name !== e.detail);
	};
</script>

<Navbar />

<div class="container">
	<div class="form">
		<AddPlayer on:addplayer={addPlayer} />
	</div>
	{#if players.length === 0}
		<p> No Players </p>
	{:else}
		{#each players as player}
			<Player name={player.name} points={player.points} on:removeplayer={removePlayer} />
		{/each}
	{/if}
</div>