<script lang="ts">
	let { title, children } = $props();
</script>

<div class="rounded-md bg-gray-100 p-4 dark:bg-zinc-800">
	<h3 class="mb-2 text-lg font-bold">{title}</h3>
	{@render children()}
</div>
