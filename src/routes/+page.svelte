<script lang="ts">
	import { colors } from '$lib';
</script>

<main>
	<h1>Bounce.css for Svelte</h1>

	<hr />

	<h3>Text</h3>

	{#each { length: 6 } as _, i}
		{@const n = i + 1}
		{@const tag = `h${n}`}
		<svelte:element this={tag}>Heading {n}</svelte:element>
	{/each}
	<p>Paragraph</p>

	<hr />

	<h3>Lists</h3>

	<ul>
		{#each colors as color}
			<li class={color}>List item</li>
		{/each}
	</ul>

	<ol>
		{#each colors as color}
			<li class={color}>List item</li>
		{/each}
	</ol>
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
	}
</style>
