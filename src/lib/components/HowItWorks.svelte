<script>
  const steps = [
    {
      number: "01",
      title: "Add NovaXp to Discord",
      description: "Click the 'Add to Discord' button and authorize NovaXp for your server. Takes less than 30 seconds.",
      icon: "🤖"
    },
    {
      number: "02",
      title: "Customize Your Settings",
      description: "Set up XP rates, rewards, and challenges that match your community's vibe. Or use our smart defaults.",
      icon: "⚙️"
    },
    {
      number: "03",
      title: "Watch Engagement Soar",
      description: "Members start earning XP automatically. Leaderboards update in real-time. Your community comes alive.",
      icon: "🚀"
    }
  ];
</script>

<section class="py-24 px-4 max-w-7xl mx-auto">
  <div class="text-center mb-16">
    <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Get started in minutes</h2>
    <p class="text-gray-400 text-lg">No technical knowledge required</p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-8 md:gap-12">
    {#each steps as step, i}
      <div class="relative">
        {#if i < steps.length - 1}
          <div class="hidden md:block absolute top-12 left-full w-full h-0.5 bg-gradient-to-r from-[#5865F2]/50 to-transparent -translate-x-1/2"></div>
        {/if}
        
        <div class="text-center">
          <div class="w-20 h-20 mx-auto mb-6 rounded-2xl bg-gradient-to-br from-[#5865F2] to-[#4752C4] flex items-center justify-center text-4xl">
            {step.icon}
          </div>
          
          <div class="text-[#5865F2] font-bold text-sm mb-3">{step.number}</div>
          <h3 class="text-xl font-bold text-white mb-3">{step.title}</h3>
          <p class="text-gray-400 text-sm leading-relaxed">{step.description}</p>
        </div>
      </div>
    {/each}
  </div>

  <div class="text-center mt-16">
    <a href="#add-bot" class="inline-block bg-[#5865F2] text-white px-8 py-3 rounded-full font-bold hover:bg-[#4752C4] transition-colors">
      Add to Discord Now
    </a>
  </div>
</section>
