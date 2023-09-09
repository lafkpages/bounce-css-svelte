<script lang="ts">
	import Button from '$lib/components/Button.svelte';
</script>

<nav>
	<div>
		<div class="logo">
			<h3>B</h3>
		</div>
	</div>

	<div class="buttons">
		<Button href="/demo">View demo page</Button>
		<Button href="/#how-anchor" color="cyan">Use library</Button>
	</div>
</nav>

<style>
	.buttons {
		display: flex;
		gap: 16px;
	}
</style>
