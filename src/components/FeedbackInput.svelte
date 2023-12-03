<script>
  import RatingBar from "./RatingBar.svelte";

  let rating = 10;
  let disabled = true;

  const handleChange = (e) => (disabled = e.target.value.length <= 12);
</script>

<section>
  <h2>How much would you rate your service with us?</h2>

  <form>
    <RatingBar {rating} />

    <div class="input-container">
      <input type="text" placeholder="Write your feedback..." on:input={handleChange} />
      <input type="submit" {disabled} />
    </div>
  </form>

  {#if disabled}
    <small>The feedback msut be 12 character or more</small>
  {:else}
    <small>Thank you for writing to us!</small>
  {/if}
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    gap: 1.25em;
    padding: 1.6em 1.8em;
    background-color: #d6d6d6;
    color: #151515;
    text-align: center;
    border-radius: 0.6em;
  }

  h2 {
    padding-inline: 1em;
  }

  .input-container {
    display: flex;
    padding: 0.35em;
    margin-top: 1.65em;
    background-color: #efefef;
    border-radius: 0.5em;
  }

  input {
    border-radius: 0.5em;
  }

  input[type="text"] {
    flex-grow: 1;
    padding: 0.5em 0.65em;
    font-weight: 600;
    color: #252525;
    background-color: transparent;
    font-weight: 600;
  }

  input[type="submit"] {
    padding: 0.75em 1.5em;
    background-color: #332b61;
    color: #c7c7c7;
    cursor: pointer;
  }

  input[type="submit"]:disabled {
    background-color: #cfcfcf;
    color: #454545;
    font-weight: 600;
    cursor: not-allowed;
  }

  small {
    font-weight: 500;
  }
</style>
