<script lang="ts">
	import Facebook from './components/facebook.svelte';
	let pages = [
		{
			name: 'Home',
			href: '/'
		},
		{
			name: 'Dues',
			href: '/dues'
		},
		{
			name: 'FAQ',
			href: '/faq'
		},
		{
			name: 'Resources',
			href: '/resources'
		}
	];
</script>

<nav class="mx-auto mt-4 flex flex-col">
	<h2 class="mt-2 text-center text-xl font-bold sm:text-2xl md:text-3xl">
		Woodside Community Association
	</h2>
	<ul class="mt-2 flex w-full flex-row justify-between">
		{#each pages as page}
			<li><a href={page.href} class="sm:text-lg">{page.name}</a></li>
		{/each}
		<li><Facebook /></li>
	</ul>
	<hr class="my-2 border-gray-300" />
</nav>

<style lang="scss">
	a:hover {
		text-decoration: underline;
	}
</style>
