<script lang="ts">
    import {createEventDispatcher} from "svelte";
    import Card from "./Card.svelte";
    export let item = {}

    const dispatch = createEventDispatcher();

    const handleDelete = (id) => {
        dispatch("delete-feedback", id)
    }
</script>

<Card>
    <div class="name">
        {item.name}
    </div>
    <div class="num-display">
        {item.rating}
    </div>
    <div class="delete" on:click={() => handleDelete(item.id)}>X</div>
    <div class="text-display">
        {item.comment}
    </div>
</Card>

<style>
    .name {
        font-size: 1.5em;
        font-weight: bold;
    }
    .num-display {
        position: absolute;
        top: -10px;
        left: -10px;
        width: 50px;
        height: 50px;
        background: #f3bc02;
        color:#fff;
        border-radius: 50%;
        padding: 10px;
        text-align: center;
        font-size: 19px;
    }

    .delete{
        position: absolute;
        top:10px;
        right: 20px;
        cursor: pointer;
    }
</style>
