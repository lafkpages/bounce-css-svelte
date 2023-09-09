<script lang="ts">
	import type { OptionalColor } from '$lib/index.js';

	export let color: OptionalColor = null;
	export let href: string;
</script>

<a {href} style:--color-normal={color ? `var(--bounce-${color}-normal)` : null} on:click>
	<slot />
</a>

<style>
	a {
		text-decoration: none;
		color: var(--bounce-black);
		font-size: 16px;
		padding: 2px 4px;
		border-radius: 2px;
		transition: transform 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5),
			box-shadow 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.5);
		width: fit-content;
		background: var(--bounce-white);
		line-height: 20px;
		outline: 1px solid var(--bounce-black);
		display: inline-block;
	}

	a:hover,
	a:focus-visible {
		outline: 1px solid var(--bounce-black);
		transform: translateX(3px) translateY(-3px);
		box-shadow: -3px 3px 0 0 var(--color-normal, var(--bounce-gray)),
			-3px 3px 0 1px var(--bounce-black);
	}

	a:active {
		outline: 1px solid var(--bounce-black);
		transform: translateX(1.5px) translateY(-1.5px);
		box-shadow: -1.5px 1.5px 0 0 var(--color-normal, var(--bounce-gray)),
			-1.5px 1.5px 0 1px var(--bounce-black);
	}
</style>
