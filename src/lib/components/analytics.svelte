<script lang="ts">
	import { browser, dev } from '$app/environment';
	let id = 'G-DBZHQCP815';
</script>

{#if !dev && browser}
	<!-- Google tag (gtag.js) -->
	<script async src="https://www.googletagmanager.com/gtag/js?id={id}"></script>
	<script>
		window.dataLayer = window.dataLayer || [];
		function gtag() {
			dataLayer.push(arguments);
		}
		gtag('js', new Date());
		gtag('config', '{id}');
	</script>
{/if}
