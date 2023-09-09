<script lang="ts">
	import { colors } from '$lib';

	import Button from '$lib/components/Button.svelte';
	import Mark from '$lib/components/Mark.svelte';
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

	<hr />

	<h3>Mark</h3>

	<div class="marks">
		{#each colors as color}
			<Mark {color}>Mark</Mark>
		{/each}
	</div>

	<hr />

	<h3>Buttons</h3>

	<div class="buttons">
		{#each colors as color}
			<Button {color}>Button</Button>
			<Button {color} disabled>Disabled</Button>
		{/each}
	</div>
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
	}

	.marks {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.buttons {
		display: grid;
		grid-template-columns: auto auto;
		width: max-content;
		gap: 32px 16px;
	}
</style>
