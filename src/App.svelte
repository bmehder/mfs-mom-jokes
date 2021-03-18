<svelte:options tag="mfs-mom-jokes" />

<script>
  import { jokeData } from "./jokeData.js";
  import { onMount } from "svelte";

  let randomNumber = 0;
  const getRandomNumber = () =>
    (randomNumber = Math.floor(Math.random() * jokeData.length));
  onMount(() => getRandomNumber());
</script>

<article>
  <h4>Mother's Day Jokes</h4>
  <button on:click={getRandomNumber}>Get Another Joke</button>
  <div>
    <p>{jokeData[randomNumber].q}</p>
    <p><em>{jokeData[randomNumber].a}</em></p>
  </div>
</article>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  article {
    margin: auto;
    padding: 2em;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: rgba(217, 77, 166, 0.5);
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1em;
    color: white;
    border-radius: 16px;
  }
  h4 {
    margin: 1em 0;
    font-size: 1.5em;
    text-align: center;
    text-shadow: 0 0 4px rgba(0, 0, 0, 0.5);
  }
  button {
    width: 100%;
    padding: 1em;
    background: rgba(217, 77, 166, 1);
    outline: none;
    border: none;
    border-radius: 4px;
    font-weight: bold;
    font-size: 1em;
    line-height: 1.5;
    color: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.32);
    transition: all 400ms;
    text-transform: uppercase;
  }
  button:hover {
    background-image: linear-gradient(
      to bottom,
      transparent,
      rgba(0, 0, 0, 0.05)
    );
    box-shadow: none;
  }
  button:focus {
    outline: none;
  }
  div {
    width: 100%;
    margin: 1em 0;
    padding: 2em;
    background: #fff;
    color: #333;
    font-size: 18px;
    line-height: 1.5;
    text-align: center;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.32);
  }
  p {
    margin-bottom: 0.5em;
  }
</style>
