<script lang="ts">
	import Section from '$lib/layout/section.svelte';

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
			name: 'City of Woodside',
			url: 'https://www.cityofwoodside.org/water',
			notes: ''
		},
		{
			category: '🗑️ Trash - ♻️ Recycling',
			name: 'Sanitation Service Company',
			url: 'https://portal.ssc-inc.com/User/Login?ReturnUrl=%2f',
			notes: 'Schedule pickups and more: https://ssc-inc.com/collection-schedule/'
		},
		{
			category: '🛜 Internet - Comcast',
			name: 'Comcast',
			url: 'https://www.xfinity.com/',
			notes: ''
		},
		{
			category: '🛜 Internet - Ziply Fiber',
			name: 'Ziply Fiber',
			url: 'https://www.ziplyfiber.com/',
			notes:
				'Installation is underway in Woodside and we expect gigabit fiber options from Ziply soon!'
		}
	];
</script>

<Section title="Utilities Companies">
	<ul class="flex flex-col gap-4 sm:grid sm:grid-cols-2 md:grid-cols-3">
		{#each utilities as utility}
			<li class="flex flex-col gap-2">
				<h2 class="text-lg font-bold">{utility.category}</h2>
				<a
					href={utility.url}
					target="_blank"
					rel="noopener noreferrer"
					class="text-lime-600 hover:text-lime-700"
				>
					{utility.name}
				</a>
				{#if utility.notes}
					<p class="text-sm text-gray-500 dark:text-gray-300">{utility.notes}</p>
				{/if}
			</li>
		{/each}
	</ul>
</Section>
