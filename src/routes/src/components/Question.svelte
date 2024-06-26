<script>
  export let question;
  export let selected;
</script>

<div class="question">
  <p>{question.question}</p>
  <ul>
    {#each question.options as option}
      <li>
        <label>
          <input type="radio" bind:checked={selected} value={option} />
          {option}
        </label>
      </li>
    {/each}
  </ul>
</div>

<style>
  /* Add your CSS styles here */
</style>
