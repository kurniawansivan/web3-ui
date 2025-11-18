<script lang="ts">
  import { Copy } from 'lucide-svelte';
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

  <button class="group flex items-center gap-2 rounded-full bg-gray-900 px-4 py-2 text-sm font-medium text-gray-300 transition-colors hover:bg-gray-700 hover:text-white">
    
    <span>0x71C...9A21</span>
    
    <Copy size={16} />

  </button>

</div>