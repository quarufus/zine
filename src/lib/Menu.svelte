<script>
  export let toggleMenu;
</script>

<div>
  <button on:click={toggleMenu}>⤬</button>
  <ul>
    <li>Home</li>
    <li>Zines</li>
    <li>About</li>
    <li>Contact</li>
  </ul>
</div>

<style>
  div {
    width: calc(50% - 1px);
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
  button {
    text-align: right;
    font-size: 2em;
    margin: 10px 30px;
    float: right;
  }
</style>
