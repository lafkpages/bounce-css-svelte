<script lang="ts">
	import { colors } from '$lib';

	import Button from '$lib/components/Button.svelte';
	import Input from '$lib/components/Input.svelte';
	import Link from '$lib/components/Link.svelte';
	import Mark from '$lib/components/Mark.svelte';

	let inputsValue = '';
</script>

<main>
	<h3>What is this?</h3>
	<p>
		<span class="rainbow">bounce.css Svelte</span> is a component library in Svelte that you can use
		to create simple websites!
	</p>

	<h3>How to use?</h3>
	<p>TODO</p>

	<h3>What about crediting?</h3>
	<p>TODO</p>

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

	<p class="mark-text">
		Lorem ipsum dolor, sit amet <Mark>consectetur adipisicing</Mark> elit. Numquam dolorem natus cumque
		porro at vel omnis, enim placeat eligendi aliquam a earum alias architecto ducimus excepturi quisquam
		quaerat similique veniam.
	</p>

	<hr />

	<h3>Buttons</h3>

	<div class="buttons">
		{#each colors as color}
			<Button {color}>Button</Button>
			<Button {color} disabled>Disabled</Button>
		{/each}
	</div>

	<hr />

	<h3>Links</h3>

	<div class="links">
		{#each [null, ...colors] as color}
			<Link href="#" {color}>Link</Link>
		{/each}
	</div>

	<hr />

	<h3>Inputs</h3>

	<p>
		You wrote: {#if inputsValue}{inputsValue}{:else}
			<i>nothing</i>
		{/if}
	</p>

	{#each colors as color}
		<Input {color} placeholder="Input" bind:value={inputsValue} />
	{/each}
	<Input disabled placeholder="Disabled" bind:value={inputsValue} />
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		padding-bottom: 32px;
	}

	.marks {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.mark-text {
		margin-top: 16px;
	}

	.buttons {
		display: grid;
		grid-template-columns: auto auto;
		width: max-content;
		gap: 32px 16px;
	}

	.links {
		display: flex;
		gap: 32px;
		flex-wrap: wrap;
	}
</style>
