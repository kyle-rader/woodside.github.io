<script lang="ts">
	import BusinessList from './business_list.svelte';

	let gardening = [
		{
			name: 'Garden Spot',
			website: 'https://www.garden-spot.com',
			mapUrl: 'https://maps.app.goo.gl/A3HLwq6wggDFyes69',
			distanceMiles: 1.5,
			note: ''
		},
		{
			name: 'My Garden',
			website: 'https://www.mygardennursery.com',
			mapUrl: 'https://maps.app.goo.gl/nzithbKu5FKKmxGUA',
			distanceMiles: 3.6,
			note: ''
		},
		{
			name: "Joe's Garden",
			website: 'https://www.joesgardens.com',
			mapUrl: 'https://maps.app.goo.gl/Fy3RrjD7pKCdHExd9',
			distanceMiles: 5.9,
			note: ''
		},
		{
			name: "Kent's Garden Center",
			website: 'https://kentsgardenandnursery.com',
			mapUrl: 'https://maps.app.goo.gl/2SidvnjecN4LsmwN6',
			distanceMiles: 10.6,
			note: ''
		}
	];

	let landscaping = [
		{
			name: 'Grow Source',
			website: 'http://growsource.com',
			mapUrl: 'https://maps.app.goo.gl/jL9S4sEcdUyAoYfB6',
			distanceMiles: 1.8,
			note: 'Landscaping supplies: Mulch, Soil, Bark, Gravel, etc.'
		},
		{
			name: 'Northstar Stone & Landscape Supply',
			website: 'http://www.northstarstone.net',
			mapUrl: 'https://maps.app.goo.gl/W1UWbCnN1XbqzCZR6',
			distanceMiles: 7.6,
			note: 'Landscaping supplies: Stone pavers, retaining blocks, Mulch, Soil, Bark, Gravel, etc.'
		}
	];

	let hardware = [
		{
			name: 'Builders Alliance',
			website: 'https://www.buildersalliance.com',
			mapUrl: 'https://maps.app.goo.gl/tDGq5c8V4fZnVcKx5',
			distanceMiles: 1.8,
			note: 'Building supplies: Lumber, Decking, Windows, Doors, Cabinets, Counter tops, etc.'
		},
		{
			name: 'Millwork Supply',
			website: 'https://www.bellinghammillwork.com',
			mapUrl: 'https://maps.app.goo.gl/oQBcdXbLWKNZmbAC6',
			distanceMiles: 1.8,
			note: 'Building supplies: Lumber, Decking, Windows, Doors, Cabinets, Counter tops, etc.'
		},
		{
			name: 'Lowes',
			website: 'https://www.lowes.com',
			mapUrl: 'https://maps.app.goo.gl/PbzpDYd4ooYwwM5x6',
			distanceMiles: 2.2,
			note: 'Closest general hardware store to the neighborhood.'
		},
		{
			name: 'Hardware Sales',
			icon: 'https://hardwaresales.net/wp-content/uploads/2024/08/hardware-store-logo.png',
			website: 'http://www.hardwaresales.net',
			mapUrl: 'https://maps.app.goo.gl/L2roF66NnPLdhHP28',
			distanceMiles: 3.2,
			note: 'Huge selection of tools and equipment. This is a lot of local contractors go to.'
		},
		{
			name: 'Home Depot',
			website: 'https://www.homedepot.com',
			mapUrl: 'https://maps.app.goo.gl/6mVTgQtmBoturn6J8',
			distanceMiles: 4.0,
			note: ''
		},
		{
			name: 'Ace Hardware',
			website: 'https://www.acehardware.com',
			mapUrl: 'https://maps.app.goo.gl/8acFPXL7ichtrfYv9',
			distanceMiles: 5.5,
			note: 'In Sehome Village.'
		}
	];
</script>

<h1 class="mb-2 text-2xl font-bold">📍 Local Businesses</h1>
<p class="mb-4 text-gray-500 dark:text-gray-300">
	These are some local businesses you may find useful while owning or living in a house!
	<br />
	(We are not affiliated with or paid by any of these businesses.)
</p>
<BusinessList title="🌳 Garden Nurseries" businesses={gardening} />
<BusinessList title="🪨 Landscaping Supplies" businesses={landscaping} />
<BusinessList title="🛠️ Hardware Stores" businesses={hardware} />
