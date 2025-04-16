<script lang="ts">
	let { title, children, class: className = '' } = $props();
</script>

<div class="mb-4 rounded-lg bg-white p-6 text-left shadow-md dark:bg-zinc-700 {className}">
	<h2 class="mb-2 text-xl font-semibold">{title}</h2>
	{@render children()}
</div>
