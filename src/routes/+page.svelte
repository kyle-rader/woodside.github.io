<script lang="ts">
	import Container from '$lib/layout/container.svelte';
	import { facebookUrl, contactEmail } from '$lib';
	import FacebookIcon from '$lib/components/facebook_icon.svelte';
	import Link from '$lib/components/link.svelte';
	import Images from '$lib/images.svelte';
	import Events from '$lib/components/events.svelte';
	import QuickLinks from '$lib/components/quick_links.svelte';

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
			A neighborhood community in <Link href={googleMapsUrl}>📍 Bellingham, WA</Link>
		</p>
	</header>

	<img src="/img/woodside_sign.jpg" alt="Woodside Sign" class="mx-auto mb-4 sm:w-3/4" />

	<Events />
	<QuickLinks />
	<Images />
</Container>
