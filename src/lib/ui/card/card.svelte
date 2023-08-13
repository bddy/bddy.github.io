<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let id: number;
	export let isSelected: boolean = false;

	const dispatch = createEventDispatcher<{ click: { id: number } }>();

	function handleClick() {
		dispatch('click', { id });
	}
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
	class="card"
	class:card--selected={isSelected}
	role="button"
	tabindex="0"
	on:click={handleClick}
>
	<h1>Hello World from {id}! 🚀</h1>
	<div class="content">
		{#if isSelected}
			I'm <strong>selected</strong>! 😊
		{:else}
			I'm <strong>not</strong> selected... 🥲
		{/if}
	</div>
</div>

<style lang="scss">
	@mixin elevated($height) {
		$translation: calc($height/2 * -1);

		transform: translate($translation, $translation);

		-webkit-box-shadow: $height $height 0px 0px #000000;
		box-shadow: $height $height 0px 0px #000000;
	}

	.card {
		box-sizing: border-box;
		height: 100%;
		widows: 100%;
		border: solid 2px var(--color-text);
		border-radius: var(--spacing-sm);
		padding: var(--spacing-sm);

		-webkit-box-shadow: 5px 5px 0px 0px #000000;
		box-shadow: 5px 5px 0px 0px #000000;

		cursor: pointer;

		&--selected {
			@include elevated(var(--spacing-xs));

			background-color: aqua;
		}

		&:hover {
			@include elevated(var(--spacing-xs));
		}

		transition: all 150ms ease-in;
	}
</style>
