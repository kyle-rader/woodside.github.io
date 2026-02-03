<script lang="ts">
	import { contactEmail } from '$lib';
	import Link from '$lib/components/link.svelte';
	import Container from '$lib/layout/container.svelte';
	import Section from '$lib/layout/section.svelte';
	import FaqItem from './faq_item.svelte';

	const effectiveDate = new Date('2026-01-05');
	const today = new Date();
	today.setHours(0, 0, 0, 0);
	effectiveDate.setHours(0, 0, 0, 0);
	const isEffective = today >= effectiveDate;
</script>

<Container>
	<Section title="❓ Frequently Asked Questions" class="flex flex-col gap-4" id="faq">
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

			<p class="mt-4">
				You can contact the board at <Link href={`mailto:${contactEmail}`}>{contactEmail}</Link>.
			</p>
		</FaqItem>

		<FaqItem title="🏠 Selling Your Home - What documents do prospective buyers need?">
			<p class="mb-4">
				When selling your home, prospective buyers will typically request various HOA documents
				including:
			</p>
			<ul class="mb-4 list-disc pl-4">
				<li>HOA bylaws and covenants</li>
				<li>Financial statements and budgets</li>
				<li>Meeting minutes</li>
			</ul>
			<p>
				All the documents requested by prospective buyers can be downloaded from our
				<Link href="/resources#documents">Documents section on the resources page</Link>.
			</p>
		</FaqItem>
	</Section>

	<Section title="🌳 FAQ on Trees" class="flex flex-col gap-4" id="trees">
		<FaqItem title="🌱 What trees may I plant?">
			You can plant new trees that do not grow taller than <strong>35 feet</strong>.
			<p class="mt-4">
				A typical 2 story home is 20-25 feet tall. If you planted a tree, and it's taller than your
				home it will likely need to be trimmed or removed.
			</p>
		</FaqItem>

		<FaqItem title="🌳 What happens if trees are blocking views?">
			Trees which impede protected views of other homes must be trimmed to the view-owners
			satisfaction. The board has established an official fine process for violations. See the
			<Link href="/faq#fines">Fines section</Link> for details on the enforcement timeline and fine schedule.
		</FaqItem>

		<FaqItem title="🌲 What are legacy trees and how are they protected?">
			There are special rules about <em>legacy trees</em> that were left on the land before the
			division was created. These are typically very large, and there are very few left in the
			neighborhood. If you think you have a legacy tree and want to remove it please contact us at
			<Link href={`mailto:${contactEmail}`}>{contactEmail}</Link>.
		</FaqItem>
	</Section>

	<Section title="💰 FAQ on Fines" class="flex flex-col gap-4" id="fines">
		{#if isEffective}
			<div class="mb-4 rounded-md border-2 border-green-500 bg-green-50 p-4 dark:bg-green-900/20">
				<p class="font-semibold text-green-800 dark:text-green-200">
					✓ Fine schedule is now in effect as of February 5, 2026
				</p>
			</div>
		{:else}
			<div
				class="mb-4 rounded-md border-2 border-yellow-500 bg-yellow-50 p-4 dark:bg-yellow-900/20"
			>
				<p class="font-semibold text-yellow-800 dark:text-yellow-200">
					⚠️ This fine schedule is not in effect yet. It will be effective as of February 5, 2026.
				</p>
			</div>
		{/if}

		<FaqItem title="⏱️ What is the enforcement timeline for fines issued by the board?">
			<p class="mb-4">
				The board follows a structured enforcement process to ensure homeowners have fair notice and
				opportunity to correct violations:
			</p>

			<div class="mb-4">
				<h4 class="mb-2 font-semibold">Enforcement Timeline:</h4>
				<ol class="list-decimal space-y-3 pl-6">
					<li>
						<strong>Step 1 – Courtesy Notice</strong>
						<p class="mt-1">
							An informal written notice describing the issue and requesting voluntary correction.
							No fines are imposed at this stage.
						</p>
					</li>
					<li>
						<strong>Step 2 – Formal Notice of Violation</strong>
						<p class="mt-1">
							If the issue is not corrected, a written Notice of Violation will be sent identifying
							the covenant involved, the corrective action required, the compliance deadline, and
							hearing rights.
						</p>
						<p class="mt-1">
							For tree, vegetation, and view-related issues, the standard compliance period is
							forty-five (45) days.
						</p>
					</li>
					<li>
						<strong>Step 3 – Hearing Opportunity</strong>
						<p class="mt-1">
							Owners may request a hearing within fourteen (14) days of the Notice of Violation.
							Owners may present information, propose a plan, or request additional time. The Board
							will issue a written decision.
						</p>
					</li>
					<li>
						<strong>Step 4 – Fine Schedule Applies</strong>
						<p class="mt-1">
							If the violation remains after the compliance period and hearing process:
						</p>
						<ul class="mt-1 list-disc space-y-1 pl-4">
							<li><strong>First violation:</strong> $50</li>
							<li><strong>Second violation:</strong> $150</li>
							<li><strong>Continuing violation:</strong> $100 per week until corrected</li>
						</ul>
						<p class="mt-1">Fines are not retroactive and are imposed only after due process.</p>
					</li>
					<li>
						<strong>Step 5 – Continued Non-Compliance</strong>
						<p class="mt-1">
							If a violation continues, the Association may pursue additional remedies available
							under the Governing Documents and Washington law, including seeking court-ordered
							compliance.
						</p>
					</li>
				</ol>
			</div>

			<p class="mt-4">
				If you have questions about a violation notice or would like to request a hearing, please
				contact the board at <Link href={`mailto:${contactEmail}`}>{contactEmail}</Link>.
			</p>
		</FaqItem>
	</Section>
</Container>
