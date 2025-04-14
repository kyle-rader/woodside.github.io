<script lang="ts">
	let { href, children, class: className = '' } = $props();
</script>

<a
	{href}
	target="_blank"
	rel="noopener noreferrer"
	class="text-lime-600 hover:text-lime-700 dark:text-lime-400 dark:hover:text-lime-300 {className}"
>
	{@render children()}
</a>
