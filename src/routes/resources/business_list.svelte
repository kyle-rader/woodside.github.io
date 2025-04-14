<script lang="ts">
	import Section from '$lib/layout/section.svelte';
	import Link from '$lib/components/link.svelte';

	export let title: string;
	export let businesses: Array<{
		name: string;
		website: string;
		mapUrl: string;
		distanceMiles: number;
		note?: string;
		icon?: string;
	}>;

	function trimUrl(url: string): string {
		return url.replace(/^https?:\/\/(www\.)?/, '');
	}
</script>

<Section {title}>
	<ul class="flex flex-col gap-4 sm:grid sm:grid-cols-2 md:grid-cols-3">
		{#each businesses as business}
			<li class="flex flex-col gap-2">
				<h2 class="text-lg font-bold">{business.name}</h2>
				<div class="flex flex-col gap-1">
					<Link href={business.website}>🌐 {trimUrl(business.website)}</Link>
					<Link href={business.mapUrl}>🗺️ View on Google Maps</Link>
					<code class="text-sm">📍 {business.distanceMiles} miles away</code>
					{#if business.note}
						<p class="text-sm text-gray-600 dark:text-gray-300">{business.note}</p>
					{/if}
				</div>
			</li>
		{/each}
	</ul>
</Section>
