<script lang="ts">
	import '$lib/styles.css';

	import Button from '$lib/components/Button.svelte';
</script>

<nav>
	<div>
		<div class="logo">
			<h3>B</h3>
		</div>
	</div>

	<div>
		<Button>View demo page</Button>
	</div>
</nav>

<div class="main">
	<slot />
</div>
