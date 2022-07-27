<script lang="ts">
	import FeedbackList from "./components/FeedbackList.svelte";

	let feedback = [
		{id:1, name:"John", comment:"Good job!",rating:5},
		{id:2, name:"Carl", comment:"Yeeeah!",rating:3},
		{id:3, name:"Buggius", comment:"Very bad!",rating:1},
	]

	// Min 36:18 https://www.youtube.com/watch?v=3TVy6GdtNuQ
	const deleteFeedback = ({detail}) => {
		feedback = feedback.filter(f => f.id !== detail)
	}
</script>

<main class="container">
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>

<style>

</style>
