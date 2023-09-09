<script lang="ts">
	import type { Color } from '$lib';

	export let color: Color = 'cyan';
</script>

<div style:--color-light="var(--bounce-{color}-light)">
	<slot />
</div>

<style>
	div {
		display: inline;
		outline: 2px solid var(--color-light);
		background-color: var(--color-light);
		width: max-content;
	}
</style>
