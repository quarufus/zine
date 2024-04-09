<script lang="ts">
  import Pages from "./lib/Pages.svelte";
  import Top from "./lib/Top.svelte";
  import VerticalRule from "./lib/VerticalRule.svelte";

  $: index = 0;
  function next() {
    index++;
  }
  function previous() {
    index--;
  }
</script>

<main>
  <Top {index} {next} {previous}></Top>
  <VerticalRule />
  {#if index == 0}
    <Pages>
      <h1 slot="left">{index}</h1>
      <h1 slot="right">1</h1>
    </Pages>
  {:else if index == 1}
    <Pages>
      <h1 slot="left">1</h1>
      <h1 slot="right">2</h1>
    </Pages>
  {:else if index == 2}
    <Pages>
      <h1 slot="left">2</h1>
      <h1 slot="right">3</h1>
    </Pages>
  {:else if index == 3}
    <Pages>
      <h1 slot="left">3</h1>
      <h1 slot="right">4</h1>
    </Pages>
  {/if}
</main>

<style>
  main {
    height: 100%;
  }
</style>
