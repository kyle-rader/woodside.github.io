<script lang="ts">
	let { title, children, class: className = '', title_center = false, id } = $props();
	
	// Create a URL-friendly ID from the title if no ID is provided
	const anchorId = id || title.toLowerCase().replace(/[^a-z0-9\s]/g, '').replace(/\s+/g, '-');
</script>

<div class="mb-4 rounded-lg bg-white p-6 text-left shadow-md dark:bg-zinc-700 {className}">
	<h2 id={anchorId} class="mb-2 text-xl font-semibold {title_center ? 'text-center' : ''}">
		<a href="#{anchorId}" class="hover:text-blue-600 dark:hover:text-blue-400 transition-colors">
			{title}
		</a>
	</h2>
	{@render children()}
</div>
