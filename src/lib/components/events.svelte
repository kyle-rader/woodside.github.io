<script lang="ts">
	import Section from '$lib/layout/section.svelte';
	import FacebookIcon from '$lib/components/facebook_icon.svelte';
	import Link from '$lib/components/link.svelte';

	let events = [
		{
			title: 'Next Annual Meeting',
			date: 'February 2, 2026 @ 6:30 PM',
			location: 'Location found in mailed notice',
			fbLink: null,
			clearOn: '2026-02-03'
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
