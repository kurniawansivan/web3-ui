<script lang="ts">
  import { Copy, Check } from 'lucide-svelte';

  let isCopied = false;
  const address = '0x71C...9A21';

  function copyAddress(){
    navigator.clipboard.writeText(address);
    isCopied = true;
    setTimeout(() => { isCopied = false; }, 2000);
  }
</script>

<div class="flex flex-col items-center w-full max-w-sm rounded-2xl bg-gray-800 p-6 shadow-lg border border-gray-700">
  
  <img 
    src="https://api.dicebear.com/9.x/adventurer/svg?seed=Jocelyn" 
    alt="User Avatar" 
    class="mb-4 h-24 w-24 rounded-full border-4 border-gray-700 shadow-sm bg-gray-600"
  />

  <h2 class="text-xl font-bold text-white">
    Ivan Kurniawan Sentosa
  </h2>

  <p class="text-sm font-medium text-gray-400 mb-6">
    @backend_wizard
  </p>

  <button 
    on:click={copyAddress}
    class="group flex items-center gap-2 rounded-full bg-gray-900 px-4 py-2 text-sm font-medium text-gray-300 transition-colors hover:bg-gray-700 hover:text-white"
    >
    
    <span>{address}</span>
    
    {#if isCopied}
      <Check size={16} class="text-green-400"/>
    {:else}
      <Copy size={16}/>
    {/if}

  </button>

</div>