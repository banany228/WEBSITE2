<script>
  import { onMount } from 'svelte';
  import Question from '$lib/Question.svelte';
  import Result from '$lib/Result.svelte';

  let questions = [
    {
      id: 1,
      question: 'What is the capital of France?',
      options: ['Paris', 'London', 'Berlin', 'Madrid'],
      answer: 'Paris',
      selected: null
    },
    // Add more questions similarly
  ];

  let score = 0;

  function calculateScore() {
    score = questions.filter(q => q.selected === q.answer).length;
  }

  function restartQuiz() {
    questions.forEach(q => {
      q.selected = null;
    });
    score = 0;
  }

  onMount(() => {
    calculateScore();
  });
</script>

<h1>Quiz Game</h1>

{#each questions as question}
  <Question {question} bind:selected={question.selected} />
{/each}

<Result {score} on:restart={restartQuiz} />

<style>
  /* Add your CSS styles here */
</style>
