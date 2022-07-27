<script lang="ts">
    import FeedbackItem from "./FeedbackItem.svelte";
    export let feedback = [];

</script>


<div>
    Feedback list:
    {#each feedback as feed (feed.id)}
        <FeedbackItem item={feed} on:delete-feedback />
    {/each}
</div>
