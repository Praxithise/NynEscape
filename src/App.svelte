<script>
  let code = "";
  let correct = false;
  let guessed = false;
  const answer = "house";
  function checkAnswer() {
    if (code.toLowerCase() === answer) {
      correct = true;
    } else {
      guessed = true;
      correct = false;
    }
  }
</script>

<main class={correct && "correct"}>
  {#if !correct}
    {#if guessed}
      <img
        src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExajNnY3dmZmVjd3dmZnJ4anFtZnljN205dTBxcGZlNW5pM2FvNGt0MCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Yycc82XEuWDaLLi2GV/giphy.gif"
      />
    {/if}
    <form on:submit|preventDefault={checkAnswer}>
      <input type="text" bind:value={code} />
      <button type="submit">Guess</button>
    </form>
  {:else}
    <h1>
      Who brought Allison the idea to let the bases buy her a house with
      DeKoor's money?
    </h1>
  {/if}
</main>

<style>
  * {
    color: white;
    font-size: 2rem;
  }
  h1 {
    font-size: 6rem;
    padding: 0;
    margin-top: 0;
    line-height: 1.1;
  }
  @media (max-width: 800px) {
    h1 {
      font-size: 4rem;
    }
  }

  @media (max-width: 480px) {
    h1 {
      font-size: 3rem;
    }
  }

  main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100%;
    background-color: #022672;
  }

  form {
    margin-top: 2rem;
  }

  button {
    border-radius: 0;
    background-color: transparent;
  }
  input {
    color: #022672;
    margin-bottom: 2rem;
  }
</style>
