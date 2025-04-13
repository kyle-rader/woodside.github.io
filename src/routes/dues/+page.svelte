<script lang="ts">
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import InvoiceRequest from '$lib/components/InvoiceRequest.svelte';
</script>

<Container>
	<Section title="💵 Paying Dues Online">
		<p class="mb-3 text-gray-600 dark:text-gray-300">
			Amount: <code class="font-semibold">$205</code>
			<br />
			Due: annually on March 1st.
		</p>
		<InvoiceRequest />
	</Section>

	<Section title="📫 Paying Dues by Check">
		<p class="mb-3 text-gray-600 dark:text-gray-300">
			Amount: <code class="font-semibold">$200</code>
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
