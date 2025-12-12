<script>
  import { onMount } from 'svelte';
  
  let animatedBars = [0, 0, 0, 0, 0, 0, 0];
  const targetHeights = [60, 75, 45, 90, 65, 80, 70];
  
  onMount(() => {
    const interval = setInterval(() => {
      animatedBars = animatedBars.map((val, i) => {
        const target = targetHeights[i];
        if (val < target) return Math.min(val + 5, target);
        if (val > target) return Math.max(val - 5, target);
        return val;
      });
    }, 50);
    
    return () => clearInterval(interval);
  });
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-lg">
    <div class="bg-[#2B2D31] rounded-xl p-6 border border-white/5">
      <div class="flex items-center justify-between mb-6">
        <div>
          <div class="text-white font-semibold text-lg">Engagement Analytics</div>
          <div class="text-gray-400 text-sm">Last 7 days</div>
        </div>
        <div class="bg-[#5865F2]/20 px-3 py-1 rounded">
          <span class="text-[#5865F2] font-bold text-sm">+24%</span>
        </div>
      </div>
      
      <div class="flex items-end justify-between gap-2 h-32">
        {#each animatedBars as height, i}
          <div class="flex-1 flex flex-col items-center gap-2">
            <div class="w-full bg-[#1a1a1a] rounded-t-lg relative overflow-hidden" style="height: {height}%">
              <div class="absolute inset-0 bg-gradient-to-t from-[#5865F2] to-[#4752C4]"></div>
            </div>
            <div class="text-gray-500 text-xs">{['M', 'T', 'W', 'T', 'F', 'S', 'S'][i]}</div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>
