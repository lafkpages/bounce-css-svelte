<script lang="ts">
	import type { OptionalColor } from '$lib';

	export let color: OptionalColor = null;
	export let disabled = false;
	export let href: string | null = null;
</script>

<svelte:element
	this={href ? 'a' : 'button'}
	{href}
	style:--color-normal={color ? `var(--bounce-${color}-normal)` : null}
	style:--color-dark={color ? `var(--bounce-${color}-dark)` : null}
	style:--color-light={disabled ? `var(--bounce-${color}-light)` : null}
	{disabled}
	on:click
>
	<slot />
</svelte:element>

<style>
	button {
		font-size: 16px;
		line-height: 24px;
		font-family: Clash Display Semibold;
		color: var(--bounce-black);
		padding: 8px 32px;
		border-radius: 2px;
		outline: 2px solid var(--bounce-black);
		cursor: pointer;
		transition: transform 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5),
			box-shadow 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5);
		width: fit-content;
		background: var(--color-normal);
		margin: 8px 0 8px 0;
		border: none;
	}

	button:not(:disabled):hover,
	button:not(:disabled):focus-visible {
		transform: translateX(5px) translateY(-5px);
		box-shadow: -5px 5px 0 0 var(--color-dark, var(--bounce-gray)),
			-5px 5px 0 2px var(--bounce-black);
	}

	button:not(:disabled):active {
		transform: translateX(2px) translateY(-2px);
		box-shadow: -3px 3px 0 0 var(--color-dark, var(--bounce-gray)),
			-3px 3px 0 2px var(--bounce-black);
	}

	button:disabled {
		background-color: var(--color-light);
		cursor: not-allowed;
		color: var(--color-dark);
		outline-color: var(--color-dark);
	}
</style>
