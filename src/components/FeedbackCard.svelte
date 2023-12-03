<script>
  import { createEventDispatcher } from "svelte";
  import { slide, scale } from "svelte/transition";

  export let feedback;

  const dispatch = createEventDispatcher();

  const handleDelete = (feedbackId) => {
    dispatch("delete-feedback", feedbackId);
  };
</script>

<article transition:scale>
  <span class="rating-ring">
    {feedback.rating}
  </span>

  <div class="content-container">
    <p>{feedback.content}</p>
    <button class="delete-icon" on:click={() => handleDelete(feedback._id)}>
      &times;
    </button>
  </div>
</article>

<style>
  article {
    position: relative;
    background-color: #d6d6d6;
    color: #252525;
    padding: 1.6em 1.8em;
    border-radius: 0.6em;
  }

  .rating-ring {
    display: grid;
    place-items: center;
    position: absolute;
    inset: 0 auto auto 0;
    background-color: #db3080;
    width: 42px;
    height: 42px;
    border-radius: 50%;
    color: #e9e9e9;
    transform: translate(-30%, -30%);
  }

  .content-container {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 1em;
    font-size: 0.935em;
  }

  .delete-icon {
    font-size: 1.45rem;
    cursor: pointer;
    background-color: transparent;
    height: 10px;
    transform: translateY(-0.35em);
  }

  p {
    font-weight: 500;
  }
</style>
