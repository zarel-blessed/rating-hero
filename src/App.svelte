<script>
  import Stats from "./components/Stats.svelte";
  import FeedbackCard from "./components/FeedbackCard.svelte";
  import FeedbackInput from "./components/FeedbackInput.svelte";

  let feedbacks = JSON.parse(localStorage.getItem("feedbacks")) || [];

  const deleteFeedback = (e) => {
    const feedbackId = e.detail;

    localStorage.setItem(
      "feedbacks",
      JSON.stringify(feedbacks.filter((fb) => fb._id !== feedbackId))
    );

    feedbacks = feedbacks.filter((fb) => fb._id !== feedbackId);
  };
</script>

<main class="container">
  <FeedbackInput bind:feedbacks />

  <Stats {feedbacks} />

  {#each feedbacks as feedback (feedback._id)}
    <FeedbackCard {feedback} on:delete-feedback={deleteFeedback} />
  {/each}
</main>
