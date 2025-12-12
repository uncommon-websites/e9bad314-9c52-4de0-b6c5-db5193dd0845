<script>
  import { onMount } from 'svelte';
  
  let highlighted = 0;
  
  onMount(() => {
    const interval = setInterval(() => {
      highlighted = (highlighted + 1) % 5;
    }, 2000);
    
    return () => clearInterval(interval);
  });
</script>

<div class="w-full h-full flex items-center justify-center p-8">
  <div class="w-full max-w-md space-y-2">
    {#each Array(5) as _, i}
      <div 
        class="flex items-center gap-4 px-4 py-3 rounded-lg transition-all duration-500"
        style="background-color: {highlighted === i ? 'rgba(88, 101, 242, 0.15)' : 'rgba(255, 255, 255, 0.03)'}; border: 1px solid {highlighted === i ? 'rgba(88, 101, 242, 0.3)' : 'rgba(255, 255, 255, 0.05)'};"
      >
        <div class="w-8 text-center font-bold text-gray-500 text-sm">#{i + 1}</div>
        <div 
          class="w-10 h-10 rounded-full flex-shrink-0 flex items-center justify-center text-white font-semibold text-sm transition-all duration-500"
          style="background: linear-gradient(135deg, {highlighted === i ? '#5865F2' : '#35373C'}, {highlighted === i ? '#4752C4' : '#2B2D31'});"
        >
          {String.fromCharCode(65 + i)}
        </div>
        <div class="flex-1">
          <div class="h-3 bg-white/5 rounded w-32 mb-1"></div>
          <div class="h-2 bg-white/5 rounded w-20"></div>
        </div>
        <div class="flex items-center gap-2">
          <div 
            class="font-bold text-sm transition-colors duration-500"
            style="color: {highlighted === i ? '#5865F2' : '#888'};"
          >
            {(1000 - i * 150).toLocaleString()}
          </div>
          <div class="text-gray-500 text-xs">XP</div>
        </div>
      </div>
    {/each}
  </div>
</div>
