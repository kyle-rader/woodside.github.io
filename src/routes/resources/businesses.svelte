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

<BusinessList title="🌳 Garden Nurseries" businesses={gardening} />
<BusinessList title="🛠️ Hardware Stores" businesses={hardware} />
