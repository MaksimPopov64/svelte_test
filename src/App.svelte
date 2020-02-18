<script>
  import Component from "./Component.svelte";
  let name = "Pisia";
  let src = `https://sun9-69.userapi.com/c858028/v858028497/2453f/4WQrwD0FDFA.jpg?ava=1`;
  let htmlString = `<em>Hui</em>`;
  let inputValue;
  let counter = 0;
  let value = "Hello";
  function handleChange() {
    name = "Changed";
  }

  $: counterClass = counter % 2 === 0 ? "red" : "blue";
  $: upperName = name.toUpperCase();
  $: lowerName = name.toLowerCase();

  $: {
    console.log(`${name}`);
  }

  $: {
    if (counter % 10 === 0) {
      counterClass = "green";
    }
  }

  $: error = !isValid(value);

  function isValid(value) {
    return value.length >= 5 && value.length < 10;
  }
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  :global(p) {
    color: blue;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  img {
    width: 100px;
    border: 1px dotted green;
  }

  .red {
    color: red;
  }

  .blue {
    color: blue;
  }

  .green {
    color: green;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hell {upperName}</h1>
  <h1>ggg {name}</h1>
  <h2>yyy {lowerName}</h2>
  <img {src} alt="" />
  <p>
    {@html htmlString}
  </p>
  <button on:click={handleChange}>Change</button>
  <h1 class={counterClass}>{counter}</h1>
  <button on:click={() => counter++}>Add</button>
  <input type="text" bind:value={name} />
  <input type="text" bind:value class:red={error} class:green={!error} />
  {#if value.length < 5}
    <p>Маловат</p>
  {:else if value.length > 10}
    <p>Большеват</p>
  {/if}
  <Component age={19} />
</main>
