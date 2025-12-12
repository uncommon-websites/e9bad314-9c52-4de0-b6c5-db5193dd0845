<script>
  import { onMount } from 'svelte';
  
  let progress = 0;
  
  onMount(() => {
    const interval = setInterval(() => {
      progress = (progress + 1) % 101;
    }, 50);
    
    return () => clearInterval(interval);
  });
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-lg">
    <div class="bg-[#2B2D31] rounded-xl p-6 border border-white/5">
      <div class="flex items-center gap-4 mb-6">
        <div class="w-16 h-16 rounded-full bg-gradient-to-br from-[#5865F2] to-[#4752C4] flex items-center justify-center">
          <span class="text-white text-2xl font-bold">⚡</span>
        </div>
        <div>
          <div class="text-white font-semibold text-lg">Level 12</div>
          <div class="text-gray-400 text-sm">2,450 / 3,000 XP</div>
        </div>
      </div>
      
      <div class="relative h-3 bg-[#1a1a1a] rounded-full overflow-hidden mb-4">
        <div 
          class="absolute inset-y-0 left-0 bg-gradient-to-r from-[#5865F2] to-[#4752C4] transition-all duration-100 ease-linear"
          style="width: {progress}%"
        ></div>
      </div>
      
      <div class="grid grid-cols-3 gap-4 text-center">
        <div class="bg-[#1a1a1a] rounded-lg p-3">
          <div class="text-[#5865F2] font-bold text-xl">247</div>
          <div class="text-gray-500 text-xs">Messages</div>
        </div>
        <div class="bg-[#1a1a1a] rounded-lg p-3">
          <div class="text-[#5865F2] font-bold text-xl">12</div>
          <div class="text-gray-500 text-xs">Reactions</div>
        </div>
        <div class="bg-[#1a1a1a] rounded-lg p-3">
          <div class="text-[#5865F2] font-bold text-xl">3h</div>
          <div class="text-gray-500 text-xs">Voice</div>
        </div>
      </div>
    </div>
  </div>
</div>
