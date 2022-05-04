<div  class="boxPane">
	<div class="tabPane">
		<div class="buttons">
			{#each tab as tabItem, index (tabItem)}
			<Buttons
				buttonText={tabItem.buttonText}
				selection={currentButton}
				index={index}
				on:selection={e => onSelection(e.detail)}
			/>
			{/each}
		</div>
		<h2>{currentButton >= 0 ? tab[currentButton].description : 'Clique em um botão' }</h2>
	</div>
</div>


<script lang="ts">
import Buttons from './buttons.svelte'

const tab = [
	{
		description: 'Texto do Tab 1',
		buttonText: 'Tab 1'
	},
	{
		description: 'Texto do Tab 2',
		buttonText: 'Tab 2'
	},
	{
		description: 'Texto do Tab 3',
		buttonText: 'Tab 3'
	}
]
let currentButton: number


function onSelection(option: number) {
  currentButton = option
  console.log(`opção selecionada ${option}`)
}

</script>

<style>
	.boxPane {
		display: flex;
		justify-content: center;
		padding-top: 50px;
	}
	.tabPane {
		padding: 20px;
		margin: 10px 0;
		width: 800px;
		border-radius: 10px;
		border: 1px solid #aaa;
		background-color: #f0f0f0;
	}
	.buttons {
		display: flex;
	}
</style>