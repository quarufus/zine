<script lang="ts">
  export let index: number;
  export let next;
  export let previous;
  export let toggleMenu;

  const title = ["Home", "Zines", "About", "Contact", "End"];
</script>

<ul>
  <li class="left">
    {#if index > 0}
      <button on:click={previous}>&lt- {title[index - 1]}</button>
    {/if}
  </li>
  <li class="right"><button on:click={toggleMenu}>Menu</button></li>
  <li class="left">{title[index]}</li>
  <li class="right">
    {#if index < 4}
      <button on:click={next}>{title[index + 1]} -></button>
    {/if}
  </li>
</ul>

<style>
  ul {
    list-style: none;
    display: flex;
    border-bottom: 2px solid black;
    margin: 0;
    padding: 0;
  }
  .left {
    text-align: left;
  }
  .right {
    text-align: right;
    align-items: right;
  }
  li {
    padding: 20px;
    float: left;
    width: 25%;
    font-weight: 500;
  }
</style>
