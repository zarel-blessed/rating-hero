<script>
  import Stats from './components/Stats.svelte';
  import FeedbackCard from './components/FeedbackCard.svelte';
    import FeedbackInput from './components/FeedbackInput.svelte';

  let feedbacks = [
    {
      _id: '201148693',
      rating: 9,
      content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptates quam eaque perferendis?'
    },
    {
      _id: '201448693',
      rating: 10,
      content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptates quam eaque perferendis. Quam eaque perferendis'
    },
    {
      _id: '201848693',
      rating: 8,
      content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
    },
  ];

  const deleteFeedback = (e) => {
    const feedbackId = e.detail;
    feedbacks = feedbacks.filter((fb) => fb._id !== feedbackId);
  };
</script>

<main class="container">
  <FeedbackInput />

  <Stats {feedbacks} />

  {#each feedbacks as feedback (feedback._id)}
    <FeedbackCard {feedback} on:delete-feedback={deleteFeedback} />
  {/each}
</main>