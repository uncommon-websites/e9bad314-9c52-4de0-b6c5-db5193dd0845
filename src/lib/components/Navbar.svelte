<script lang="ts">
  export let transparent = false;
</script>

<nav class="fixed top-0 left-0 right-0 z-50 flex items-center justify-between px-6 py-6 transition-colors duration-300 {transparent ? 'bg-transparent' : 'bg-novaxp-bg/80 backdrop-blur-md'}">
  <div class="flex items-center gap-2">
    <div class="text-xl font-bold text-white">NovaXp</div>
  </div>
  
  <div class="hidden md:block text-xs font-medium text-white/60 tracking-wide absolute left-1/2 transform -translate-x-1/2">
    2,400+ servers • 180,000+ members tracked
  </div>

  <div class="flex items-center gap-6 text-xs font-medium text-white/70">
    <a href="#features" class="hover:text-white transition-colors">Features</a>
    <a href="#pricing" class="hover:text-white transition-colors">Pricing</a>
    <a href="#add-bot" class="bg-[#5865F2] text-white px-4 py-2 rounded-md hover:bg-[#4752C4] transition-colors">Add to Discord</a>
  </div>
</nav>
