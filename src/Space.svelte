<script>
  export let space = "";
  export let winner;
  $: won = space === winner;
</script>

<style>
  .space {
    border: solid 1px gray;
    height: 125px;
    width: 125px;
    flex: 1;
    font-size: 75px;
    text-align: center;
    line-height: 125px;
    cursor: pointer;
  }
  .winning {
    color: purple;
  }
</style>

<div class:winning={won} on:click class="space">{space}</div>
