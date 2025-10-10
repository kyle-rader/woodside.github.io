<script lang="ts">
	import { deserialize } from '$app/forms';
	import Link from '$lib/components/link.svelte';
	import Section from '$lib/layout/section.svelte';

	type Document = {
		title: string;
		href: string;
		description: string;
	};

	// Dynamically load all files from the docs directory
	const docModules = import.meta.glob('/static/docs/**/*', { as: 'url' });
	
	// Extract file information from the modules
	const allFiles = Object.keys(docModules).map((path) => {
		const fileName = path.split('/').pop() || '';
		const fileNameWithoutExt = fileName.replace(/\.[^/.]+$/, '');
		const relativePath = path.replace('/static', '');
		
		return {
			name: fileNameWithoutExt,
			href: relativePath,
			fullPath: path
		};
	});

	// Categorize files based on their directory and name
	const rulesAndRegulations: Document[] = [
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

	// Dynamically get meeting minutes from /docs/minutes/ directory
	const meetingMinutes = allFiles.filter(file => 
		file.fullPath.includes('/docs/minutes/')
	).sort((a, b) => a.name.localeCompare(b.name));

	// Dynamically get financials from /docs/books/ directory  
	const financials = allFiles.filter(file => 
		file.fullPath.includes('/docs/books/')
	).sort((a, b) => a.name.localeCompare(b.name));
	
</script>

<Section title="📜 Documents">
	<div class="mt-4 space-y-8">
		<!-- Rules & Regulations -->
		<div>
			<h3 class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">📋 Rules & Regulations</h3>
			<ul class="flex flex-col gap-4 sm:grid sm:grid-cols-2 md:grid-cols-3">
				{#each rulesAndRegulations as doc}
					<li class="flex flex-col gap-2">
						<Link href={doc.href}>{doc.title}</Link>
						<p class="text-sm text-gray-500 dark:text-gray-300">{doc.description}</p>
					</li>
				{/each}
			</ul>
		</div>

		<!-- Meeting Minutes -->
		<div>
			<h3 class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">📝 Meeting Minutes</h3>
			<ul class="list-disc list-inside space-y-2">
				{#each meetingMinutes as doc}
					<li>
						<Link href={doc.href}>{doc.name}</Link>
					</li>
				{/each}
			</ul>
		</div>

		<!-- Financials -->
		<div>
			<h3 class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">💰 Financials</h3>
			{#if financials.length > 0}
				<ul class="list-disc list-inside space-y-2">
					{#each financials as doc}
						<li>
							<Link href={doc.href}>{doc.name}</Link>
						</li>
					{/each}
				</ul>
			{:else}
				<p class="text-sm text-gray-500 dark:text-gray-300 italic">No financial documents available at this time.</p>
			{/if}
		</div>
	</div>
</Section>
