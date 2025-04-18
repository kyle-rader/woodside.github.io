<script lang="ts">
	import Section from '$lib/layout/section.svelte';
	import FacebookIcon from '$lib/components/facebook_icon.svelte';
	import Link from '$lib/components/link.svelte';

	let events = [
		{
			title: 'Next HOA Meeting',
			date: 'February, 2026 - Date TBD',
			location: 'TBD',
			fbLink: null,
			clearOn: '2026-03-15'
		},
		{
			title: 'Easter Egg Hunt 2025',
			date: 'April 19th, 2025 @ 11:00 AM',
			location: 'At the park on Woodside Way.',
			fbLink: 'https://fb.me/e/2uGUbSOD6',
			clearOn: '2025-04-20'
		}
	];

	let futureEvents = events.filter((event) => new Date(event.clearOn) > new Date());
</script>

<Section
	title="📢 Upcoming Community Events"
	title_center={true}
	class="gap-4 rounded-lg bg-white shadow-md dark:bg-zinc-700"
>
	<div class="mt-4 flex flex-col gap-4 sm:flex-row sm:flex-wrap">
		{#each futureEvents as event}
			<div class="min-w-[300px] flex-1 rounded-lg border p-4 sm:max-w-[calc(50%-1rem)]">
				<div class="flex flex-col gap-2">
					<h3 class="text-lg font-bold">{event.title}</h3>
					<p class="text-gray-700 dark:text-gray-200">
						🗓️ {event.date}
						{#if event.location}
							<br />📍 {event.location}
						{/if}
					</p>
					{#if event.fbLink}
						<Link href={event.fbLink}>
							<span class="text-blue-500">
								<FacebookIcon /> View Event on Facebook
							</span>
						</Link>
					{/if}
				</div>
			</div>
		{/each}
	</div>
</Section>
