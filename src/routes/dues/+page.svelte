<script lang="ts">
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
</script>

<svelte:head>
	<script async src="https://js.stripe.com/v3/buy-button.js"></script>
</svelte:head>

<Container>
	<Section id="online" title="💵 Pay dues automatically online">
		<p class="mb-3 text-gray-600 dark:text-gray-300">
			Due: annually on <code class="font-semibold">March 1st</code>.
		</p>

		<stripe-buy-button
			buy-button-id="buy_btn_1SyJfXCa7WtRwkztoDEo3ofT"
			publishable-key="pk_live_51SyHwfCa7WtRwkztfbwS7zLBJakUipENjDtL3MQA5DuBfqQ6tt8X7bNWbj32P7DjXqXWQEAg4siUufsCVScdnxaS00mLvaWYBc"
		>
		</stripe-buy-button>
	</Section>

	<Section id="check" title="📫 Paying Dues by Check">
		<p class="mb-3 text-gray-600 dark:text-gray-300">
			Amount: <code class="font-semibold">$300</code>
			<br />
			Due: annually on March 1st.
		</p>

		<p>Make checks payable to:</p>
		<pre
			class="rounded-md bg-gray-100 p-2 text-gray-600 dark:bg-zinc-800 dark:text-gray-300">WCA</pre>
		<br />
		<p>Mail to:</p>
		<pre class="rounded-md bg-gray-100 p-2 text-gray-600 dark:bg-zinc-800 dark:text-gray-300">
WCA
PO Box 28548
Bellingham, WA 98228</pre>
	</Section>
</Container>

<style>
	:global(div:has(h2#online)) {
		text-align: center;
	}

	stripe-buy-button {
		display: block;
		width: 100%;
		margin: 0 auto;
	}
</style>
