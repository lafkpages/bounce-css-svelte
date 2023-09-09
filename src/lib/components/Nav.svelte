<script lang="ts">
	import Button from '$lib/components/Button.svelte';
</script>

<nav>
	<div>
		<Button color="cyan" rounded>
			<h3>B</h3>
		</Button>
		<h3 class="rainbow">bounce.css Svelte</h3>
	</div>

	<div class="buttons">
		<Button href="/demo">View demo page</Button>
		<Button href="/#how-anchor" color="cyan">Use library</Button>
	</div>
</nav>

<style>
	nav > div {
		display: flex;
		gap: 8px;
	}

	.buttons {
		gap: 16px;
	}
</style>
