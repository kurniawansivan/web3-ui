<script lang="ts">
	import { Copy, Check } from 'lucide-svelte';

	let isCopied = false;
	const address = '0x71C...9A21';

	function copyAddress() {
		navigator.clipboard.writeText(address);
		isCopied = true;
		setTimeout(() => {
			isCopied = false;
		}, 2000);
	}
</script>

<div class="group relative w-full max-w-sm">
	<div
		class="absolute -inset-1 rounded-2xl bg-gradient-to-r from-pink-600 via-purple-600 to-blue-600 opacity-25 blur transition duration-500 group-hover:opacity-100"
	></div>
	<div
		class="relative flex flex-col items-center rounded-2xl border border-gray-800 bg-gray-900 p-6 shadow-xl"
	>
		<img
			src="https://api.dicebear.com/9.x/adventurer/svg?seed=Jocelyn"
			alt="User Avatar"
			class="mb-4 h-24 w-24 rounded-full border-4 border-gray-700 bg-gray-600 shadow-sm"
		/>

		<h2 class="text-xl font-bold text-white">Ivan Kurniawan Sentosa</h2>

		<p class="mb-6 text-sm font-medium text-gray-400">@backend_wizard</p>

		<div class="mb-6 grid w-full grid-cols-3 gap-2 border-b border-t border-gray-800 py-4">
			<div class="flex flex-col items-center">
				<span class="text-lg font-bold text-white">#85</span>
				<span class="text-xs uppercase tracking-wider text-gray-500">Rank</span>
			</div>

			<div class="flex flex-col items-center border-l border-gray-800">
				<span class="text-lg font-bold text-pink-500">12.5</span>
				<span class="text-xs uppercase tracking-wider text-gray-500">ETH</span>
			</div>

			<div class="flex flex-col items-center border-l border-gray-800">
				<span class="text-lg font-bold text-blue-400">42</span>
				<span class="text-xs uppercase tracking-wider text-gray-500">NFTs</span>
			</div>
		</div>

		<button
			on:click={copyAddress}
			class="group flex items-center gap-2 rounded-full bg-gray-900 px-4 py-2 text-sm font-medium text-gray-300 transition-colors hover:bg-gray-700 hover:text-white"
		>
			<span>{address}</span>

			{#if isCopied}
				<Check size={16} class="text-green-400" />
			{:else}
				<Copy size={16} />
			{/if}
		</button>
	</div>
</div>
