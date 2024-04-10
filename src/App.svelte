<script lang="ts">
  import Pages from "./lib/Pages.svelte";
  import Top from "./lib/Top.svelte";
  import VerticalRule from "./lib/VerticalRule.svelte";
  import Menu from "./lib/Menu.svelte";
  import MobileTop from "./lib/MobileTop.svelte";
  import SinglePage from "./lib/SinglePage.svelte";
  import MobileFooter from "./lib/MobileFooter.svelte";

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

  const pages = ["Home", "Zines", "About", "Contact"];
</script>

<svelte:window bind:innerWidth />

<main>
  {#if menu}
    <Menu {toggleMenu} {innerWidth} bind:value={index} />
  {/if}
  {#if innerWidth > 700}
    <Top {index} {next} {previous} {toggleMenu} />
    <VerticalRule />
    {#if index == 0}
      <Pages>
        <h1 slot="right">{pages[0]}</h1>
      </Pages>
    {:else if index == 1}
      <Pages>
        <h1 slot="left">{pages[0]}</h1>
        <h1 slot="right">{pages[1]}</h1>
      </Pages>
    {:else if index == 2}
      <Pages>
        <h1 slot="left">{pages[1]}</h1>
        <h1 slot="right">{pages[2]}</h1>
      </Pages>
    {:else if index == 3}
      <Pages>
        <h1 slot="left">{pages[2]}</h1>
        <h1 slot="right">{pages[3]}</h1>
      </Pages>
    {:else if index == 4}
      <Pages>
        <h1 slot="left">{pages[3]}</h1>
      </Pages>
    {/if}
  {:else}
    <MobileTop {toggleMenu} />
    {#if index == 0}
      <SinglePage>
        <h1 slot="content">{pages[0]}</h1>
      </SinglePage>
    {:else if index == 1}
      <SinglePage>
        <h1 slot="content">{pages[1]}</h1>
      </SinglePage>
    {:else if index == 2}
      <SinglePage>
        <h1 slot="content">{pages[2]}</h1>
      </SinglePage>
    {:else if index == 3}
      <SinglePage>
        <h1 slot="content">{pages[3]}</h1>
      </SinglePage>
    {/if}
    <MobileFooter {index} {next} {previous} />
  {/if}
</main>

<style>
  main {
    height: 100%;
  }
</style>
