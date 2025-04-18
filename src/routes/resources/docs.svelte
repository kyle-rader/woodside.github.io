<script lang="ts">
	import { deserialize } from '$app/forms';
	import Link from '$lib/components/link.svelte';
	import Section from '$lib/layout/section.svelte';

	let docs = [
		{
			title: 'Bylaws',
			href: '/docs/wca_bylaws.pdf',
			description:
				"These Bylaws establish and protect the rights, and specify the duties and responsibilities of our organization's members."
		},
		{
			title: 'Bylaws (Amended)',
			href: '/docs/wca_bylaws_amended.pdf',
			description: 'Amended in 1999.'
		},
		{
			title: 'Covenants (CC&Rs)',
			href: '/docs/wca_covenants.pdf',
			description:
				'Neighborhoods with covenants and standards tend to be safer, look better, maintain better relationships with local governments, and better retain or increase the investments that homeowners have made in their properties.'
		}
	];
</script>

<Section title="📜 Documents">
	<ul class="mt-4 flex flex-col gap-4 sm:grid sm:grid-cols-2 md:grid-cols-3">
		{#each docs as doc}
			<li class="flex flex-col gap-2">
				<Link href={doc.href}>{doc.title}</Link>
				<p class="text-sm text-gray-500 dark:text-gray-300">{doc.description}</p>
			</li>
		{/each}
	</ul>
</Section>
