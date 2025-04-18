<script lang="ts">
	import '../app.css';
	import Nav from '$lib/nav.svelte';
	import Footer from '$lib/footer.svelte';
	import Analytics from '$lib/components/analytics.svelte';
	let { children } = $props();
</script>

<Analytics />

<div class="flex min-h-screen flex-col">
	<Nav />
	<main class="text-left sm:text-center">
		{@render children()}
	</main>
	<Footer />
</div>
