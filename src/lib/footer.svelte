<script lang="ts">
	import Facebook from './components/facebook.svelte';
	const imgUrl =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml/badge.svg?branch=main';
	const deployAction =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml';
</script>

<footer class="mt-auto py-4">
	<div class="container mx-auto flex items-center justify-between px-4 text-center">
		<a href={deployAction} target="_blank" rel="noopener noreferrer">
			<img src={imgUrl} alt="Deploy to GitHub Pages" />
		</a>
		<Facebook />
	</div>
</footer>
