<script lang="ts">
	import { facebookUrl } from '$lib';
	import FacebookIcon from './facebook_icon.svelte';
</script>

<a
	href={facebookUrl}
	target="_blank"
	rel="noopener noreferrer"
	class="text-blue-600 hover:text-blue-900"
	aria-label="Visit Woodside Community Facebook Page"
>
	<FacebookIcon />
</a>
