<script>
  import { onMount, afterUpdate } from 'svelte';
  import { fade } from 'svelte/transition';
  import { goto } from '$app/navigation';
  
  let showBackground = false;
  let showBlackBox = false;
  let showButton = false;
  let mounted = false;

  onMount(() => {
    showBackground = true;
    showBlackBox = true;
    showButton = true;
    mounted = true;
  });

  afterUpdate(() => {
    if (mounted) {
      // Force a re-render by toggling a class
      document.body.classList.add('mounted');
      setTimeout(() => document.body.classList.remove('mounted'), 0);
    }
  });

  function goBack() {
    goto('/?showGifs=true', { replaceState: true });
  }
</script>

<div class="container" class:with-background={showBackground}>
  <h1>Beste Kaktusfrucht mit Eisschlauch und Milchbase</h1>
  {#if showBlackBox}
    <div class="black-box" transition:fade>
      <h2>Zum start etwas mildes</h2>
      <video controls>
        <source src="/NewMexico.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Jetzt ein bisschen was fruchtiges</h2>
      <video controls>
        <source src="/Everybody_Lore.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Der Bruder hat übertrieben</h2>
      <video controls>
        <source src="/domenik.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Er kann sich nicht kontrollieren, muss halt mehr rauchen</h2>
      <video controls>
        <source src="/moisbalti.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Er kann sich noch weniger kontrollieren</h2>
      <video controls>
        <source src="/centifinished.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Wo ALLES angefangen hat</h2>
      <video controls>
        <source src="/Memelol.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Etwas Schnupftabak</h2>
      <video controls>
        <source src="/Memelol_Valorant.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      <h2>Bro's trippin'</h2>
      <video controls>
        <source src="/Oscar_Lore.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
    </div>
  {/if}
  {#if showButton}
    <button on:click={goBack} transition:fade>Zurück</button>
  {/if}
</div>

<style>
  :global(body) {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
  }

  .container {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    background-image: url('/shisha2.jpg'); /* Changed from shisha.jpg to shisha2.jpg */
    background-size: cover;
    background-position: center;
    opacity: 0;
    transition: opacity 1s ease-in-out;
  }

  .with-background {
    opacity: 1;
  }

  h1, h2 {
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

  h2 {
    font-size: 2rem;
    margin-bottom: 20px;
  }

  .black-box {
    width: 95%;
    min-height: calc(100vh - 150px);
    background-color: black;
    margin-top: 20px;
    margin-bottom: 20px;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    overflow-y: auto;
    padding: 20px;
    box-sizing: border-box;
  }

  video {
    width: 100%;
    max-height: 50vh;
    object-fit: contain;
    margin-bottom: 20px;
  }

  button {
    position: fixed;
    bottom: 20px;
    left: 20px;
    font-size: 2rem;
    font-weight: bold;
    color: pink;
    background-color: black;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  }
</style>