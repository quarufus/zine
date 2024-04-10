<script lang="ts">
  export let toggleMenu;
  export let innerWidth: number;
  export let value: number;
  let width: number;
  $: if (innerWidth > 700) {
    width = 50;
  } else {
    width = 100;
  }
  function select(num: number) {
    value = num;
    toggleMenu();
  }
</script>

<div style="--width: {width}%">
  <button id="but" on:click={toggleMenu}>Close</button>
  <ul>
    <li>
      <button on:click={() => select(0)}>Home</button>
    </li>
    <li><button on:click={() => select(1)}>Zines</button></li>
    <li><button on:click={() => select(2)}>About</button></li>
    <li><button on:click={() => select(3)}>Contact</button></li>
  </ul>
</div>

<style>
  div {
    width: var(--width);
    position: absolute;
    height: 100%;
    background-color: white;
    z-index: 1;
    text-align: left;
  }
  ul {
    list-style: none;
    font-size: 6em;
  }
  #but {
    text-align: right;
    margin: 21px 20px;
    float: right;
  }
</style>
