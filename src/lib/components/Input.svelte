<script lang="ts">
	import type { Color } from '$lib/index.js';

	export let color: Color = 'cyan';
	export let disabled = false;
	export let placeholder: string | null = null;
	export let value = '';
</script>

<input
	type="text"
	style:--color-normal="var(--bounce-{color}-normal)"
	{disabled}
	{placeholder}
	bind:value
/>

<style>
	input {
		text-align: left;
		font-size: 16px;
		line-height: 24px;
		font-family: Clash Display Semibold;
		color: var(--bounce-black);
		padding: 8px;
		border-radius: 2px;
		outline: 2px solid var(--bounce-gray);
		cursor: pointer;
		background: var(--bounce-light-gray);
		transition: transform 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5),
			box-shadow 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5);
		width: fit-content;
		margin: 8px 0 8px 0;
		border: none;
	}

	input:not(:disabled):hover,
	input:not(:disabled):focus-visible {
		transform: translateX(5px) translateY(-5px);
		outline: 2px solid var(--bounce-black);
		box-shadow: -5px 5px 0 0 var(--bounce-gray), -5px 5px 0 2px var(--bounce-black);
	}

	input:not(:disabled):focus-visible {
		outline-color: var(--color-normal);
	}

	input:not(:disabled):active {
		box-shadow: -3px 3px 0 0 var(--bounce-gray), -3px 3px 0 2px var(--bounce-black);
		transform: translateX(2px) translateY(-2px);
		outline: 2px solid var(--bounce-black);
	}

	input:disabled {
		background: var(--bounce-white);
		color: var(--bounce-gray);
		outline: 2px solid var(--bounce-gray);
		cursor: not-allowed;
	}
</style>
