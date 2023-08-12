<script lang="ts">
  import Footprint from "./assets/footprint.json"

  const jsonLength = Object.keys(Footprint).length;
  
  let entry = Math.floor(Math.random() * jsonLength) + 1;

  function newFootprint() {
    entry = Math.floor(Math.random() * jsonLength) + 1;
  }
</script>

<main>
 
  <h1 class="text-red-600 font-bold text-6xl">
    Pheu Thai Digital Footprint
  </h1>
  <a href={Footprint[entry].link} target="_blank">
    <h1 class="text-3xl font-bold text-white mt-6">
      "{Footprint[entry].quote}" 
      <span class="italic font-normal text-xl">
        - {Footprint[entry].person}
      </span>
    </h1>
  </a>

  <button class="mt-10 p-4 rounded text-blue-700 bg-white" on:click={newFootprint}>
    หาดิจิตอลฟุตพริ้นท์อันใหม่
  </button>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
