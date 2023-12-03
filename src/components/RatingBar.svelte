<script>
  export let rating;
</script>

<form>
  <input
    id="one"
    name="rating"
    type="radio"
    value="ONE"
    checked={rating === 1}
    on:click={() => (rating = 1)}
  />
  <label for="one">1</label>

  <input
    id="two"
    name="rating"
    type="radio"
    value="TWO"
    checked={rating === 2}
    on:click={() => (rating = 2)}
  />
  <label for="two">2</label>

  <input
    id="three"
    name="rating"
    type="radio"
    value="THREE"
    checked={rating === 3}
    on:click={() => (rating = 3)}
  />
  <label for="three">3</label>

  <input
    id="four"
    name="rating"
    type="radio"
    value="FOUR"
    checked={rating === 4}
    on:click={() => (rating = 4)}
  />
  <label for="four">4</label>

  <input
    id="five"
    name="rating"
    type="radio"
    value="FIVE"
    checked={rating === 5}
    on:click={() => (rating = 5)}
  />
  <label for="five">5</label>

  <input
    id="six"
    name="rating"
    type="radio"
    value="SIX"
    checked={rating === 6}
    on:click={() => (rating = 6)}
  />
  <label for="six">6</label>

  <input
    id="seven"
    name="rating"
    type="radio"
    value="SEVEN"
    checked={rating === 7}
    on:click={() => (rating = 7)}
  />
  <label for="seven">7</label>

  <input
    id="eight"
    name="rating"
    type="radio"
    value="EIGHT"
    checked={rating === 8}
    on:click={() => (rating = 8)}
  />
  <label for="eight">8</label>

  <input
    id="nine"
    name="rating"
    type="radio"
    value="NINE"
    checked={rating === 9}
    on:click={() => (rating = 9)}
  />
  <label for="nine">9</label>

  <input
    id="ten"
    name="rating"
    type="radio"
    value="TEN"
    checked={rating === 10}
    on:click={() => (rating = 10)}
  />
  <label for="ten">10</label>
</form>

<style>
  form {
    display: flex;
    justify-content: space-between;
  }

  input {
    display: none;
  }

  label {
    display: grid;
    place-items: center;
    width: 38px;
    height: 38px;
    background: #a6a6a6;
    border-radius: 50%;
    cursor: pointer;
  }

  input[type="radio"]:checked + label {
    background-color: #db3080;
    color: #e9e9e9;
  }
</style>
