<script>
  import { createEventDispatcher } from 'svelte';

  export let score;

  const dispatch = createEventDispatcher();

  function handleRestart() {
    dispatch('restart');
  }
</script>

<div class="result">
  <h2>Quiz Results</h2>
  <p>Your score: {score} / {questions.length}</p>
  <button on:click={handleRestart}>Restart Quiz</button>
</div>

<style>
  /* Add your CSS styles here */
</style>
