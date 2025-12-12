<script>
  import { onMount } from 'svelte';
  
  let activeChallenge = 0;
  
  onMount(() => {
    const interval = setInterval(() => {
      activeChallenge = (activeChallenge + 1) % 3;
    }, 3000);
    
    return () => clearInterval(interval);
  });
  
  const challenges = [
    { title: 'Daily Streak', progress: 75, total: 100, reward: 50 },
    { title: 'Social Butterfly', progress: 45, total: 50, reward: 100 },
    { title: 'Voice Champion', progress: 30, total: 60, reward: 150 }
  ];
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-md space-y-3">
    {#each challenges as challenge, i}
      <div 
        class="bg-[#2B2D31] rounded-lg p-4 border transition-all duration-500"
        style="border-color: {activeChallenge === i ? '#5865F2' : 'rgba(255, 255, 255, 0.05)'}; opacity: {activeChallenge === i ? 1 : 0.6};"
      >
        <div class="flex items-center justify-between mb-3">
          <div class="text-white font-medium text-sm">{challenge.title}</div>
          <div class="flex items-center gap-1 bg-[#5865F2]/20 px-2 py-1 rounded">
            <span class="text-[#5865F2] font-bold text-xs">+{challenge.reward}</span>
            <span class="text-[#5865F2] text-xs">XP</span>
          </div>
        </div>
        <div class="relative h-2 bg-[#1a1a1a] rounded-full overflow-hidden mb-2">
          <div 
            class="absolute inset-y-0 left-0 bg-gradient-to-r from-[#5865F2] to-[#4752C4] transition-all duration-500"
            style="width: {(challenge.progress / challenge.total) * 100}%"
          ></div>
        </div>
        <div class="text-gray-400 text-xs">{challenge.progress} / {challenge.total}</div>
      </div>
    {/each}
  </div>
</div>
