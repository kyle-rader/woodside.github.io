<script lang="ts">
	import { contactEmail } from '$lib';
	import Link from '$lib/components/link.svelte';
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import FaqItem from './faq_item.svelte';
</script>

<Container>
	<Section title="❓ Frequently Asked Questions" class="flex flex-col gap-4">
		<FaqItem title="What is the trash/recycling/compost 🗑️/♻️/🍂 schedule?">
			You can find your schedule on
			<Link href="https://ssc-inc.com/collection-schedule/"
				>the <abbr title="Sanitation Service Company">SSC</abbr> website here</Link
			>.
		</FaqItem>

		<FaqItem title="👥 Who is the board?">
			<p class="mb-4">
				The board is made up of 5 members of the neighborhood that have volunteered at an annual HOA
				meeting and were approved by the members attending the meeting.
			</p>

			<p class="mb-2">The roles includes:</p>
			<ul class="list-disc pl-4">
				<li>President - oversees the board and ensures the community is running smoothly</li>
				<li>Vice President - helps the president with the operations of the community</li>
				<li>
					Secretary - maintains the website, Facebook group, and keeps track of the minutes from the
					board meetings
				</li>
				<li>
					Treasurer - oversees the financial operations of the community and issues online dues
					invoices
				</li>
				<li>
					Landscaping - helps interface with landscaping companies to maintain the common areas in
					the neighborhood
				</li>
			</ul>
		</FaqItem>
	</Section>

	<Section title="🌳 FAQ on Trees" class="flex flex-col gap-4">
		<FaqItem title="🌱 What trees may I plant?">
			You can plant new trees that do not grow taller than <strong>35 feet</strong>.
			<p class="mt-4">
				A typical 2 story home is 20-25 feet tall. If you planted a tree, and it's taller than your
				home it will likely need to be trimmed or removed.
			</p>
		</FaqItem>

		<FaqItem title="🌳 What happens if trees are blocking views?">
			Trees which impede protected views of other homes must be trimmed to the view-owners
			satisfaction. Enforcement of this rule is at the discretion of the board, but
			<strong>we are moving forward with establishing an official fine process</strong>
			for not complying.
			<p class="mt-4">More info will be available soon.</p>
		</FaqItem>

		<FaqItem title="🌲 What are legacy trees and how are they protected?">
			There are special rules about <em>legacy trees</em> that were left on the land before the
			division was created. These are typically very large, and there are very few left in the
			neighborhood. If you think you have a legacy tree and want to remove it please contact us at
			<Link href={`mailto:${contactEmail}`}>{contactEmail}</Link>.
		</FaqItem>
	</Section>
</Container>
