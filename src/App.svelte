<script lang="ts">
  import Pages from "./lib/Pages.svelte";
  import Top from "./lib/Top.svelte";
  import VerticalRule from "./lib/VerticalRule.svelte";
  import Menu from "./lib/Menu.svelte";

  $: index = 0;
  function next() {
    index++;
  }
  function previous() {
    index--;
  }
  let innerWidth = 0;
  $: menu = false;
  function toggleMenu() {
    menu = !menu;
  }
</script>

<svelte:window bind:innerWidth />

<main>
  {#if menu}
    <Menu {toggleMenu} />
  {/if}
  {#if innerWidth > 700}
    <Top {index} {next} {previous} {toggleMenu}></Top>
    <VerticalRule />
    {#if index == 0}
      <Pages>
        <h1 slot="left">{index}</h1>
        <h1 slot="right">Το Μπιτόνι</h1>
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
  {:else}
    <h1>Mobile</h1>
  {/if}
</main>

<style>
  main {
    height: 100%;
  }
</style>
