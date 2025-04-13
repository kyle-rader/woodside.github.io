<script lang="ts">
	import { contactEmail } from '$lib';
	let name = '';
	let email = '';
	let address = '';
	let isValidEmail = false;

	function validateEmail(email: string) {
		const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
		isValidEmail = emailRegex.test(email);
	}

	function handleSubmit() {
		if (!isValidEmail || !name || !address) {
			alert('Please fill in all fields correctly');
			return;
		}

		const subject = `Woodside - Invoice Request for ${name}`;
		const body = `Name: ${name}\nEmail: ${email}\nAddress:\n${address}`;
		const mailtoLink = `mailto:${contactEmail}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;

		window.location.href = mailtoLink;
	}
</script>

<div class="">
	<h2 class="mb-4 text-xl font-semibold">Request an Invoice</h2>
	<form on:submit|preventDefault={handleSubmit} class="space-y-4">
		<div>
			<label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300"
				>Name</label
			>
			<input
				type="text"
				id="name"
				bind:value={name}
				required
				class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 dark:bg-zinc-800 dark:text-gray-300"
			/>
		</div>

		<div>
			<label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300"
				>Email</label
			>
			<input
				type="email"
				id="email"
				bind:value={email}
				on:input={(e) => validateEmail(e.currentTarget.value)}
				required
				class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 dark:bg-zinc-800 dark:text-gray-300"
			/>
			{#if email && !isValidEmail}
				<p class="mt-1 text-sm text-red-600">Please enter a valid email address</p>
			{/if}
		</div>

		<div>
			<label for="address" class="block text-sm font-medium text-gray-700 dark:text-gray-300"
				>Mailing Address</label
			>
			<textarea
				id="address"
				bind:value={address}
				required
				rows="3"
				class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 dark:bg-zinc-800 dark:text-gray-300"
			></textarea>
		</div>

		<button
			type="submit"
			class="flex w-full justify-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-sm font-medium text-white shadow-sm hover:bg-indigo-700 focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:outline-none dark:bg-indigo-400 dark:hover:bg-indigo-500"
		>
			Send Invoice Request Email
		</button>
	</form>
</div>
