<script>
  import Space from "./Space.svelte";
</script>

<style>
  main {
    width: 475px;
    margin: 0 auto;
    height: 1080px;
  }
  .row {
    display: flex;
  }
  button {
    width: 100%;
    margin-top: 20px;
    border-radius: 0;
    font-size: 30px;
    background-color: lightblue;
    cursor: pointer;
  }
  button:hover {
    outline: none;
  }
</style>

<main>
  <h1>Tic Tac Toe</h1>
  <h2>Number of people playing:</h2>
  <h2>Player X</h2>
  <div class="row">
    <Space space="X" />
    <Space space="X" />
    <Space space="X" />
  </div>
  <div class="row">
    <Space space="X" />
    <Space space="X" />
    <Space space="X" />
  </div>
  <div class="row">
    <Space space="X" />
    <Space space="X" />
    <Space space="X" />
  </div>
  <button>New Game</button>
</main>

<Space space="X" />
