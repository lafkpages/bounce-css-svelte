<script lang="ts">
	import type { OptionalColor } from '$lib';

	export let color: OptionalColor = null;
</script>

<button
	style:--color="var(--bounce-{color}-normal)"
	style:--shadow={color ? `var(--bounce-${color}-dark)` : null}
>
	<slot />
</button>

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
		background: var(--color);
		margin: 8px 0 8px 0;
		border: none;
	}

	button:hover,
	button:focus-visible {
		transform: translateX(5px) translateY(-5px);
		box-shadow: -5px 5px 0 0 var(--shadow, var(--bounce-gray)), -5px 5px 0 2px var(--bounce-black);
	}
</style>
