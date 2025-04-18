<script lang="ts">
	import { contactEmail } from '$lib';
	import Facebook from './components/facebook.svelte';
	import Link from './components/link.svelte';
	const imgUrl =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml/badge.svg?branch=main';
	const deployAction =
		'https://github.com/kyle-rader/woodside.github.io/actions/workflows/deploy.yml';
</script>

<footer class="mt-auto mb-2 p-4 sm:mt-auto md:mx-auto md:w-4xl">
	<div class="mx-auto flex items-center justify-between">
		<a href={deployAction} target="_blank" rel="noopener noreferrer">
			<img src={imgUrl} alt="Deploy to GitHub Pages" />
		</a>
		<Link href="mailto:{contactEmail}">Contact Us</Link>
		<Facebook />
	</div>
</footer>
