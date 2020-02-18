<script>
  let name = "Undefined";
  export let age = 15;
</script>

<style>
  div {
    border: 1px solid red;
  }
</style>

<main>
  {#if age < 20}
    <div>Сосать</div>
  {/if}
</main>
