<script>
  export let index;
  export let next;
  export let previous;
</script>

<ul>
  <li class="left">
    {#if index > 0}
      <button on:click={previous}>Previous</button>
    {/if}
  </li>
  <li class="right">Menu</li>
  <li class="left">Home</li>
  <li class="right">
    {#if index < 3}
      <button on:click={next}>Next</button>
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
  }
</style>
