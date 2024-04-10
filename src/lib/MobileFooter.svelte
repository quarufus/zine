<script>
  export let index;
  export let next;
  export let previous;

  const title = ["Home", "Zines", "About", "Contact"];
</script>

<ul>
  <li class="left">
    {#if index > 0}
      <button on:click={previous}>&lt- {title[index - 1]}</button>
    {/if}
  </li>
  <li class="right">
    {#if index < 3}
      <button on:click={next}>{title[index + 1]} -></button>
    {/if}
  </li>
</ul>

<style>
  ul {
    list-style: none;
    display: flex;
    border-top: 2px solid black;
    margin: 0;
    padding: 0;
    bottom: 0;
    position: absolute;
    width: 100%;
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
    width: 50%;
    font-weight: 500;
  }
</style>
