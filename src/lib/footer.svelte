<script lang="ts">
	import Facebook from './components/facebook.svelte';
	const currentYear = new Date().getFullYear();
</script>

<footer class="mt-auto py-4">
	<div class="container mx-auto flex items-center justify-between px-4 text-center">
		<p>&copy; {currentYear} Woodside Community Association. All rights reserved.</p>
		<div class="mt-2">
			<Facebook />
		</div>
	</div>
</footer>
