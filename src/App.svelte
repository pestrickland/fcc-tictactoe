<script>
  import Space from "./Space.svelte";
  import gameStore from "./game-store.js";
  let board = ["", "", "", "", "", "", "", "", ""];
  let nextPlayer = "";
  let winner;
  let numberOfPeeps = 0;
  gameStore.subscribe((data) => {
    if (!data) {
      return;
    }

    winner = data.winner;
    nextPlayer = data.nextPlayer;
    board = data.board;
    numberOfPeeps = data.numberOfPeeps;
  });
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
  <h2>Number of people playing: {numberOfPeeps}</h2>
  {#if winner == 'TIE'}
    <h2>Tie game</h2>
  {:else if winner}
    <h2>Player {winner} won</h2>
  {:else}
    <h2>Player {nextPlayer}</h2>
  {/if}
  <div class="row">
    <Space space={board[0]} />
    <Space space={board[1]} />
    <Space space={board[2]} />
  </div>
  <div class="row">
    <Space space={board[3]} />
    <Space space={board[4]} />
    <Space space={board[5]} />
  </div>
  <div class="row">
    <Space space={board[6]} />
    <Space space={board[7]} />
    <Space space={board[8]} />
  </div>
  {#if winner}<button>New Game</button>{/if}
</main>
