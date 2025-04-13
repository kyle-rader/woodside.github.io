<script lang="ts">
	import Facebook from './components/facebook.svelte';
	const imgUrl =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml/badge.svg?branch=main';
	const deployAction =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml';
</script>

<footer class="mt-auto p-4 sm:mt-auto sm:w-80 md:w-1/2">
	<div class="mx-auto flex justify-between">
		<a href={deployAction} target="_blank" rel="noopener noreferrer">
			<img src={imgUrl} alt="Deploy to GitHub Pages" />
		</a>
		<Facebook />
	</div>
</footer>
