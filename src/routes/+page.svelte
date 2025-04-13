<script lang="ts">
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import InvoiceRequest from '$lib/components/InvoiceRequest.svelte';
	// const nextMeeting = new Date('February 1, 2026');
	const nextMeeting = 'February, 2026 - Date TBD';
	const contactEmail = 'woodsidebhamhoa@googlegroups.com';
	const invoiceSubject = 'Woodside HOA Dues Invoice Request';
	const invoiceBody = 'Please send me an invoice for the dues for the year.';

	const googleMapsUrl =
		'https://www.google.com/maps/@48.7802007,-122.4310919,427a,35y,92.86h,48.09t/data=!3m1!1e3?entry=ttu&g_ep=EgoyMDI1MDQwOS4wIKXMDSoASAFQAw%3D%3D';
</script>

<Container>
	<!-- Welcome Section -->
	<header class="mb-6 text-center">
		<h1 class="mb-4 text-2xl font-bold md:text-3xl">
			Welcome to the <abbr title="Woodside Community Association">WCA</abbr>
		</h1>
		<p class="text-lg text-gray-600 dark:text-gray-300">
			A <a
				href={googleMapsUrl}
				target="_blank"
				class="text-lime-600 hover:underline dark:text-lime-400">neighborhood community</a
			> in Bellingham, WA
		</p>
	</header>

	<img src="/img/woodside_sign.jpg" alt="Woodside Sign" class="mx-auto mb-4 sm:w-3/4 md:w-1/2" />

	<Section
		title="📢 Announcements"
		class="rounded-lg bg-white text-center shadow-md md:mx-auto md:w-1/2 dark:bg-zinc-700"
	>
		<div class="space-y-2">
			<p class="text-gray-700 dark:text-gray-200">Next HOA Meeting:</p>
			<p class="text-gray-700 dark:text-gray-200">{nextMeeting}</p>
		</div>
	</Section>

	<h2 class="mb-4 text-center text-xl font-bold">Quick Links</h2>
	<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
		<a href="/dues" class="rounded-lg bg-white p-4 shadow-md dark:bg-zinc-700">
			<span class="font-semibold">💸 Paying Dues</span>
			<p class=" text-gray-500 dark:text-gray-300">Pay by check or online</p>
		</a>
		<a href="/faq" class="rounded-lg bg-white p-4 shadow-md dark:bg-zinc-700">
			<span class="font-semibold">📖 Rules FAQ</span>
			<p class=" text-gray-500 dark:text-gray-300">Common CC&R and Bylaws Guidelines</p>
		</a>
		<a href="/resources" class="rounded-lg bg-white p-4 shadow-md dark:bg-zinc-700">
			<span class="font-semibold">📄 Resources</span>
			<p class=" text-gray-500 dark:text-gray-300">
				Local businesses, meeting minutes, CC&Rs, ByLaws, etc.
			</p>
		</a>
		<a href="mailto:{contactEmail}" class="rounded-lg bg-white p-4 shadow-md dark:bg-zinc-700">
			<span class="font-semibold">📧 Contact</span>
			<p class=" text-gray-500 dark:text-gray-300">Email: {contactEmail}</p>
		</a>
	</div>
</Container>
