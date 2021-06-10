<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    let player = {
        name: "",
        points: 0 
    };

    const onSubmit = (e) => {
        e.preventDefault();
        dispatch("addplayer", player);
        player ={
            name: '',
            points: 0
        };
    };
</script>

<form class="playerForm" on:submit={onSubmit}>
    <input type="text" placeholder="Player Name" 
        bind:value={player.name} />
    <input type="text" placeholder="Player Points" 
        bind:value={player.points} />
    <div class="submit-input">
        <input type="submit" class="btn-submitPlayer" value="Add Player" />
    </div>
</form>