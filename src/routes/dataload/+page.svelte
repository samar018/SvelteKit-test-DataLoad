<!-- Plot.svelte -->
<svelte:head>
  <title>Plot</title>
  <meta name="description" content="About this Plot" />
</svelte:head>
<!-- App.svelte -->
<script>
  import { load } from './loadData.js';
  import DisplayData from './DisplayData.svelte';

  // Fetch data using the loadData.js module
  let jsonData;
  load().then((data) => {
    jsonData = data.jsonData;
  });
</script>

<main>
  <h1>Data Display Page</h1>
  {#if jsonData}
    <DisplayData data={jsonData} />
  {:else}
    <p>Loading JSON data...</p>
  {/if}
</main>

<style>
  /* Add styling for the component here */
</style>
