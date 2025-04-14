<script lang="ts">
	import { contactEmail } from '$lib';
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import InvoiceRequest from './InvoiceRequest.svelte';
</script>

<Container>
	<Section title="💵 Paying Dues Online">
		<p class="mb-3 text-gray-600 dark:text-gray-300">
			Amount: <code class="font-semibold">$206</code>
			<br />
			Due: annually on March 1st.
		</p>
		<InvoiceRequest />
		<p class="mt-4 text-gray-600 dark:text-gray-300">
			If you do not have an email client that can open the new email template, please send an email
			to <code class="font-bold">{contactEmail}</code> with the subject "Invoice Request" and include
			your name and address.
		</p>
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
