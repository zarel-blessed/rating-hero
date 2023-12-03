<script>
  export let feedbacks;
  $: len = feedbacks.length;
  $: averageRating = len === 0 ? 0 : feedbacks.reduce((i, fb) => i + fb.rating, 0) / len;
</script>

<section class="stat-container">
  <span>{len} feedbacks</span>
  <span>{averageRating.toPrecision(2)} average</span>
</section>

<style>
  .stat-container {
    display: flex;
    justify-content: space-between;
    color: #dfdfdf;
  }
</style>
