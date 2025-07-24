<script>
  let code = "";
  let correct = false;
  let guessed = false;
  const answer = "parel";
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
        src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExa2xxc3Mzd3RjNm5pMW91OWl0YWd0cjM5eHIybzhtbnRnbHJsMTByOCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Pzd4dARLvaoDK/giphy.gif"
      />
    {/if}
    <form on:submit|preventDefault={checkAnswer}>
      <input type="text" placeholder="vul in..." bind:value={code} />
      <button type="submit">Guess</button>
    </form>
  {:else}
    <div>
      <h1>Parels, dat zijn jullie stuk voor stuk!</h1>
      <video autoplay loop preload="auto">
        <source src="nyn.mp4" type="video/mp4" />
      </video>
    </div>
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
    max-width: 90%;
  }
  video {
    width: 90%;
  }
</style>
