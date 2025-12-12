<script>
  import { onMount } from 'svelte';
  
  let selectedIndex = 0;
  
  onMount(() => {
    const interval = setInterval(() => {
      selectedIndex = (selectedIndex + 1) % 3;
    }, 2500);
    
    return () => clearInterval(interval);
  });
  
  const rewards = [
    { icon: '👑', name: 'VIP Role', cost: 500 },
    { icon: '🎨', name: 'Custom Color', cost: 300 },
    { icon: '🎁', name: 'Special Perk', cost: 750 }
  ];
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-md">
    <div class="grid grid-cols-3 gap-4">
      {#each rewards as reward, i}
        <div 
          class="bg-[#2B2D31] rounded-xl p-4 border transition-all duration-500 cursor-pointer"
          style="border-color: {selectedIndex === i ? '#5865F2' : 'rgba(255, 255, 255, 0.05)'}; transform: scale({selectedIndex === i ? 1.05 : 1});"
        >
          <div class="text-4xl mb-3 text-center">{reward.icon}</div>
          <div class="text-white text-sm font-medium text-center mb-2">{reward.name}</div>
          <div class="flex items-center justify-center gap-1">
            <span class="text-[#5865F2] font-bold text-sm">{reward.cost}</span>
            <span class="text-gray-500 text-xs">XP</span>
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>
