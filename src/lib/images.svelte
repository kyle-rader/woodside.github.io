<script lang="ts">
	import Section from './layout/section.svelte';

	let images = [
		{
			src: '/img/arial_1.jpg',
			alt: 'Arial photo of the inned park off Woodside Way'
		},
		{
			src: '/img/deer_1.jpg',
			alt: 'Photo of 4 deer in the front park off Woodside Way'
		},
		{
			src: '/img/easter_egg_hunt_1.jpg',
			alt: 'Group photo of one of the Easter Egg Hunts'
		}
	];
</script>

<Section title="📸 Community Photos">
	<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
		{#each images as image}
			<a href={image.src} target="_blank" rel="noopener noreferrer">
				<img src={image.src} alt={image.alt} class="rounded-lg" />
			</a>
		{/each}
	</div>
</Section>
