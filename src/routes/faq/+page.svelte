<script lang="ts">
	import { contactEmail } from '$lib';
	import Link from '$lib/components/link.svelte';
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import FaqItem from './faq_item.svelte';
</script>

<Container>
	<Section title="❓ FAQ" class="flex flex-col gap-4">
		<FaqItem title="🗑️ Trash & ♻️ Recycling Schedule">
			You can find your schedule on
			<Link href="https://ssc-inc.com/collection-schedule/"
				>the <abbr title="Sanitation Service Company">SSC</abbr> website here</Link
			>.
		</FaqItem>
	</Section>

	<Section title="🌳 Tree Rules" class="flex flex-col gap-4">
		<FaqItem title="🌱 Planting new Trees">
			Trees must not be <em>planted</em> if they can grow taller than <strong>35 feet</strong>.
			<p class="mt-4">
				A typical 2 story home is 20-25 feet tall. If you planted a tree, and it's taller than your
				home it will likely need to be trimmed or removed.
			</p>
		</FaqItem>

		<FaqItem title="🪚 Trees Blocking Views">
			Trees which impede protected views of other homes must be trimmed to the view-owners
			satisfaction. Enforcement of this rule is at the discretion of the board, but
			<strong>we are moving forward with establishing an official fine process</strong>
			for not complying.
			<p class="mt-4">More info will be available soon.</p>
		</FaqItem>

		<FaqItem title="🌲 Legacy Trees">
			There are special rules about <em>legacy trees</em> that were left on the land before the
			division was created. These are typically very large, and there are very few left in the
			neighborhood. If you think you have a legacy tree and want to remove it please contact us at
			<Link href={`mailto:${contactEmail}`}>{contactEmail}</Link>.
		</FaqItem>
	</Section>
</Container>
