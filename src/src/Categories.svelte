<script>
    let categories = [
        { name: "Government" },
        { name: "Transport" },
        { name: "Food" },
        { name: "Fun" },
        { name: "Cinema" },
        { name: "Pubs" },
    ];
</script>

<div class="parent">
    {#each categories as { name }}
        <div class="item"><a href="/categories/{name.toLowerCase()}"> {name} </a></div>
    {/each}
</div>

<style>
    .parent {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        gap: 1em;
    }
    .item {
        text-align: center;
        width: 40%;
        min-height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        border: solid 1px black;
        border-radius: 5px;
    }
</style>
