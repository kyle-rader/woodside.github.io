<script lang="ts">
	import { facebookUrl, contactEmail } from '$lib';
	import FacebookIcon from '$lib/components/facebook_icon.svelte';

	const quick_links = [
		{
			href: '/dues',
			icon: '💸',
			title: 'Paying Dues',
			description: 'Pay by check or online'
		},
		{
			href: '/faq',
			icon: '📖',
			title: 'Rules FAQ',
			description: 'Common CC&R and Bylaws Guidelines'
		},
		{
			href: '/resources',
			icon: '🏠',
			title: 'Resources',
			description: 'Links to utilities, local businesses, HOA documents, etc.'
		},
		{
			href: `mailto:${contactEmail}`,
			icon: '📧',
			title: 'Contact',
			description: `Email: ${contactEmail}`
		}
	];
</script>

<h2 class="mb-4 text-center text-xl font-bold">Quick Links</h2>
<div class="mb-4 grid grid-cols-1 gap-4 md:grid-cols-2">
	{#each quick_links as { href, icon, title, description }}
		<a
			{href}
			class="rounded-lg bg-white p-4 shadow-md hover:bg-zinc-100 dark:bg-zinc-700 dark:hover:bg-zinc-600"
		>
			<span class="font-semibold">{icon} {title}</span>
			<p class=" text-gray-500 dark:text-gray-300">{description}</p>
		</a>
	{/each}
	<a
		href={facebookUrl}
		target="_blank"
		rel="noopener noreferrer"
		class="rounded-lg bg-white p-4 shadow-md hover:bg-zinc-100 dark:bg-zinc-700 dark:hover:bg-zinc-600"
	>
		<span class="font-semibold">
			<FacebookIcon /> FB Group
		</span>
		<p class=" text-gray-500 dark:text-gray-300">
			Join the Woodside Community Facebook Group to see events
		</p>
	</a>
</div>
