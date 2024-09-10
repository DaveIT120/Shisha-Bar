<script>
  import { goto } from '$app/navigation';

  function navigateToShitposts() {
    goto('/shitposts');
  }

  function navigateToPhonkEdits() {
    goto('/phonk-edits');
  }
</script>

<div class="container">
  <h1>Willkommen in Davids Shisha Bar</h1>
  <div class="gif-container">
    <div class="gif-wrapper left">
      <a href="/shitposts" on:click|preventDefault={navigateToShitposts}>
        <img src="/shitpost.gif" alt="Shitpost GIF" class="gif">
      </a>
    </div>
    <div class="gif-wrapper right">
      <a href="/phonk-edits" on:click|preventDefault={navigateToPhonkEdits}>
        <img src="/phonk.gif" alt="Phonk GIF" class="gif">
      </a>
    </div>
  </div>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
  }

  .container {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-image: url('/shisha.jpg');
    background-size: cover;
    background-position: center;
  }

  h1 {
    font-size: 3rem;
    font-weight: bold;
    text-align: center;
    color: pink;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    background-color: black;
    padding: 10px;
    border-radius: 5px;
    margin-top: 20px;
    width: 95%;
    max-width: 95%;
    box-sizing: border-box;
  }

  .gif-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-grow: 1;
    width: 95%;
    padding: 20px;
    box-sizing: border-box;
  }

  .gif-wrapper {
    flex: 0 0 45%; /* Adjusted from 48% to 45% */
    height: 80vh; /* Set a fixed height */
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .gif {
    width: 600px; /* Increased from whatever it was before */
    height: 600px; /* Increased from whatever it was before */
    object-fit: cover;
    border-radius: 10px;
  }
</style>