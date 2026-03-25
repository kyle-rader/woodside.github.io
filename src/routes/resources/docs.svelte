<script lang="ts">
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
		const extension = fileName.split('.').pop()?.toLowerCase() || '';
		
		return {
			name: fileNameWithoutExt,
			href: relativePath,
			fullPath: path,
			extension: extension
		};
	});

	// Helper function to filter out DOCX files when PDF versions exist
	function preferPdfOverDocx(files: typeof allFiles) {
		// Group files by their base name (without extension)
		const fileGroups = new Map<string, typeof allFiles>();
		
		files.forEach(file => {
			if (!fileGroups.has(file.name)) {
				fileGroups.set(file.name, []);
			}
			fileGroups.get(file.name)!.push(file);
		});
		
		// For each group, prefer PDF over DOCX
		const filtered: typeof allFiles = [];
		fileGroups.forEach((groupFiles) => {
			const pdfFile = groupFiles.find(f => f.extension === 'pdf');
			const docxFile = groupFiles.find(f => f.extension === 'docx');
			
			if (pdfFile) {
				// If PDF exists, use it
				filtered.push(pdfFile);
			} else if (docxFile) {
				// If no PDF but DOCX exists, use DOCX
				filtered.push(docxFile);
			} else {
				// If neither PDF nor DOCX, include all files (for other extensions)
				filtered.push(...groupFiles);
			}
		});
		
		return filtered;
	}

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
				'Also sometimes called “rules and regulations”. Neighborhoods with covenants and standards tend to be safer, look better, maintain better relationships with local governments, and better retain or increase the investments that homeowners have made in their properties.'
		}
	];

	// Dynamically get meeting minutes from /docs/minutes/ directory
	const meetingMinutes = preferPdfOverDocx(
		allFiles.filter(file => file.fullPath.includes('/docs/minutes/'))
	).sort((a, b) => a.name.localeCompare(b.name));

	// Dynamically get financials from /docs/books/ directory  
	const financials = preferPdfOverDocx(
		allFiles.filter(file => file.fullPath.includes('/docs/books/'))
	).sort((a, b) => a.name.localeCompare(b.name));

	// Dynamically get communications from /docs/comms/ directory (newest first)
	const communications = preferPdfOverDocx(
		allFiles.filter(file => file.fullPath.includes('/docs/comms/'))
	).sort((a, b) => b.name.localeCompare(a.name)); // Reverse sort for newest first

</script>

<Section title="📜 Documents" id="documents">
	<div class="mt-4 space-y-8">
		<!-- Rules & Regulations -->
		<div>
			<h3 id="rules-regulations" class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">
				<a href="#rules-regulations" class="hover:text-blue-600 dark:hover:text-blue-400 transition-colors">📋 Rules & Regulations</a>
			</h3>
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
			<h3 id="meeting-minutes" class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">
				<a href="#meeting-minutes" class="hover:text-blue-600 dark:hover:text-blue-400 transition-colors">📝 Meeting Minutes</a>
			</h3>
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
			<h3 id="financials" class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">
				<a href="#financials" class="hover:text-blue-600 dark:hover:text-blue-400 transition-colors">💰 Financials</a>
			</h3>
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

		<!-- Communications -->
		<div>
			<h3 id="communications" class="text-lg font-semibold mb-4 text-gray-800 dark:text-gray-200">
				<a href="#communications" class="hover:text-blue-600 dark:hover:text-blue-400 transition-colors">📧 Communications</a>
			</h3>
			{#if communications.length > 0}
				<ul class="list-disc list-inside space-y-2">
					{#each communications as doc}
						<li>
							<Link href={doc.href}>{doc.name}</Link>
						</li>
					{/each}
				</ul>
			{:else}
				<p class="text-sm text-gray-500 dark:text-gray-300 italic">No communications available at this time.</p>
			{/if}
		</div>
	</div>
</Section>
