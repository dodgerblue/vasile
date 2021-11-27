<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    let categories = [
        { name: "Government" },
        { name: "Transport" },
        { name: "Food" },
        { name: "Fun" },
        { name: "Cinema" },
        { name: "Weather" },
    ];


    export let page = null;
    const select = val => () => page = val
</script>

<div class="parent">
    {#each categories as { name }}
        <button class="item" on:click={select(name.toLowerCase())}>
            {name} 
        </button>
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
