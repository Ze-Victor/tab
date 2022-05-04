<div class="buttons">
    <button
      class={ index === selection ? 'selected' : '' }
      on:click={ e => clicked(index) } >
      { buttonText }
    </button>
  </div>

<script lang="ts">

  import { createEventDispatcher } from 'svelte'

  export let buttonText: string = ''
  export let selection: number
  export let index: number

  console.log(buttonText)

  const dispatcher = createEventDispatcher()

  function clicked(idx: number) {
    console.log('Clicou no botão ', idx)
    dispatcher('selection', idx)
  }
</script>

<style>
  button {
    margin-right: 10px;
    background-color: #ccc;
    border: 1px solid rgb(118, 118, 118);
    border-radius: 3px;
    padding: 2px 5px;
  }
  .selected {
    font-weight: bold;
    background-color: #aaa;
  }
  .buttons {
    margin-bottom: 10px;
  }
</style>