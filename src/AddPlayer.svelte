<script>
    let player = {
        name: "",
        points: 0 
    };
</script>

<form class="playerForm">
    <input type="text" placeholder="Player Name" 
        bind:value={player.name} />
    <input type="text" placeholder="Player Points" 
        bind:value={player.points} />
    <input type="submit" class="btn-submitPlayer" value="Add Player" />
</form>