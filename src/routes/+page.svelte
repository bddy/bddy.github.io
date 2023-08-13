<script lang="ts">
	import Card from '$lib/ui/card/card.svelte';

	let activeId: number = 1;

	$: isSelected = (id: number) => {
		return activeId === id;
	};

	function handleClick(event: CustomEvent<{ id: number }>) {
		activeId = event.detail.id;
	}
</script>

<div class={`grid highlight-${activeId}`}>
	<Card id={1} isSelected={isSelected(1)} on:click={handleClick} />
	<Card id={2} isSelected={isSelected(2)} on:click={handleClick} />
	<Card id={3} isSelected={isSelected(3)} on:click={handleClick} />
	<Card id={4} isSelected={isSelected(4)} on:click={handleClick} />
	<Card id={5} isSelected={isSelected(5)} on:click={handleClick} />
	<Card id={6} isSelected={isSelected(6)} on:click={handleClick} />
	<Card id={7} isSelected={isSelected(7)} on:click={handleClick} />
	<Card id={8} isSelected={isSelected(8)} on:click={handleClick} />
	<Card id={9} isSelected={isSelected(9)} on:click={handleClick} />
</div>

<style lang="scss">
	.grid {
		box-sizing: border-box;
		height: 100vh;
		width: 100vw;
		padding: var(--spacing-xl);

		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		grid-template-rows: 1fr 1fr 1fr;
		column-gap: var(--spacing-sm);
		row-gap: var(--spacing-sm);

		transition: 250ms ease-in-out;
	}

	.highlight-1 {
		grid-template-columns: 2fr 1fr 1fr;
		grid-template-rows: 2fr 1fr 1fr;
	}

	.highlight-2 {
		grid-template-columns: 1fr 2fr 1fr;
		grid-template-rows: 2fr 1fr 1fr;
	}

	.highlight-3 {
		grid-template-columns: 1fr 1fr 2fr;
		grid-template-rows: 2fr 1fr 1fr;
	}

	.highlight-4 {
		grid-template-columns: 2fr 1fr 1fr;
		grid-template-rows: 1fr 2fr 1fr;
	}

	.highlight-5 {
		grid-template-columns: 1fr 2fr 1fr;
		grid-template-rows: 1fr 2fr 1fr;
	}

	.highlight-6 {
		grid-template-columns: 1fr 1fr 2fr;
		grid-template-rows: 1fr 2fr 1fr;
	}

	.highlight-7 {
		grid-template-columns: 2fr 1fr 1fr;
		grid-template-rows: 1fr 1fr 2fr;
	}

	.highlight-8 {
		grid-template-columns: 1fr 2fr 1fr;
		grid-template-rows: 1fr 1fr 2fr;
	}

	.highlight-9 {
		grid-template-columns: 1fr 1fr 2fr;
		grid-template-rows: 1fr 1fr 2fr;
	}
</style>
