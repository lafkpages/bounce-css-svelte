<h1>Bounce.css for Svelte</h1>

<hr />

<h3>Text</h3>
{#each { length: 6 } as _, i}
	{@const n = i + 1}
	{@const tag = `h${n}`}
	<svelte:element this={tag}>Heading {n}</svelte:element>
{/each}
<p>Paragraph</p>
