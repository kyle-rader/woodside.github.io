<script lang="ts">
	import Section from '$lib/layout/section.svelte';
	import Link from '$lib/components/link.svelte';
	let utilities = [
		{
			category: '⚡️ Electricity',
			name: 'Puget Sound Energy',
			url: 'https://www.pse.com/',
			notes: ''
		},
		{
			category: '🔥 Gas',
			name: 'Cascade Natural Gas',
			url: 'https://customer.cngc.com/login',
			notes: ''
		},
		{
			category: '💧 Water',
			name: 'City of Bellingham',
			url: 'https://cob.org/services/utilities/water-utility',
			notes: ''
		},
		{
			category: '🗑️ Trash - ♻️ Recycling',
			name: 'Sanitation Service Company',
			url: 'https://portal.ssc-inc.com/User/Login?ReturnUrl=%2f',
			notes: ''
		},
		{
			category: '🛜 Internet - Xfinity',
			name: 'Xfinity',
			url: 'https://www.xfinity.com/',
			notes: 'Provides up to 1000+ Gbps download and 35 Mpbs upload.'
		},
		{
			category: '🛜 Internet - Ziply Fiber',
			name: 'Ziply Fiber',
			url: 'https://www.ziplyfiber.com/',
			notes: 'Coming soon! Gigabit+ fiber options (both download and upload)! Expected in 2025.'
		}
	];
</script>

<Section title="🔌 Utilities">
	<ul class="mt-4 flex flex-col gap-4 sm:grid sm:grid-cols-2 md:grid-cols-3">
		{#each utilities as utility}
			<li class="flex flex-col gap-2">
				<h2 class="text-lg font-bold">{utility.category}</h2>
				<Link href={utility.url}>{utility.name}</Link>
				{#if utility.notes}
					<p class="text-sm text-gray-500 dark:text-gray-300">{utility.notes}</p>
				{/if}
			</li>
		{/each}
	</ul>
</Section>
