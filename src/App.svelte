<script lang="ts">
	import FeedbackList from "./components/FeedbackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";
	import FeedbackForm from "./components/FeedbackForm.svelte";

	let feedback = [
		{id:1, name:"John", comment:"Good job!",rating:5},
		{id:2, name:"Carl", comment:"Yeeeah!",rating:3},
		{id:3, name:"Buggius", comment:"Very bad!",rating:1},
	]

	$: count = feedback.length;
	$: average = feedback.reduce((a,b) => a+b.rating, 0) / count;

	const deleteFeedback = ({detail}) => {
		feedback = feedback.filter(f => f.id !== detail)
	}
</script>

<main class="container">
	<FeedbackStats count={count} average={average} />
	<!-- 44.36 https://www.youtube.com/watch?v=3TVy6GdtNuQ -->
	<FeedbackForm />
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>

<style>

</style>
