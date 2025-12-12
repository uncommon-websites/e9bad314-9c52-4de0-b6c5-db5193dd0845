<script>
  import { onMount } from 'svelte';
  
  let currentCommand = 0;
  
  const commands = [
    { cmd: '/leaderboard', desc: 'View top members' },
    { cmd: '/xp', desc: 'Check your XP' },
    { cmd: '/rewards', desc: 'Browse rewards shop' },
    { cmd: '/challenges', desc: 'View active challenges' }
  ];
  
  onMount(() => {
    const interval = setInterval(() => {
      currentCommand = (currentCommand + 1) % commands.length;
    }, 2500);
    
    return () => clearInterval(interval);
  });
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-md">
    <div class="bg-[#2B2D31] rounded-xl p-6 border border-white/5">
      <div class="space-y-3">
        {#each commands as command, i}
          <div 
            class="flex items-center gap-3 p-3 rounded-lg transition-all duration-500"
            style="background-color: {currentCommand === i ? 'rgba(88, 101, 242, 0.15)' : 'transparent'}; border: 1px solid {currentCommand === i ? 'rgba(88, 101, 242, 0.3)' : 'transparent'};"
          >
            <div class="w-8 h-8 rounded-lg bg-[#5865F2]/20 flex items-center justify-center flex-shrink-0">
              <span class="text-[#5865F2] font-bold text-sm">/</span>
            </div>
            <div class="flex-1">
              <div 
                class="font-mono font-semibold text-sm mb-1 transition-colors duration-500"
                style="color: {currentCommand === i ? '#5865F2' : '#fff'};"
              >
                {command.cmd}
              </div>
              <div class="text-gray-400 text-xs">{command.desc}</div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>
