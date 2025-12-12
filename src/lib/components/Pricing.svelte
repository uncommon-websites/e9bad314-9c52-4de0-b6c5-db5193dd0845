<script>
  const plans = [
    {
      name: 'Starter',
      price: '$100',
      members: '0-50 members',
      features: [
        'XP tracking & leaderboards',
        'Basic rewards shop',
        'Discord slash commands',
        'Community analytics',
        'Email support'
      ]
    },
    {
      name: 'Growth',
      price: '$150',
      members: '50-250 members',
      popular: true,
      features: [
        'Everything in Starter',
        'Custom challenges',
        'Voting campaigns',
        'Advanced analytics',
        'Priority support',
        'Custom XP multipliers'
      ]
    },
    {
      name: 'Enterprise',
      price: '$250',
      members: '250-1000 members',
      features: [
        'Everything in Growth',
        'Unlimited challenges',
        'Cross-platform integration',
        'White-label options',
        'Dedicated support',
        'Custom feature requests'
      ]
    }
  ];
</script>

<section id="pricing" class="py-24 px-4 max-w-7xl mx-auto">
  <div class="text-center mb-16">
    <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Simple, one-time pricing</h2>
    <p class="text-gray-400 text-lg">No subscriptions. Pay once, use forever.</p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    {#each plans as plan}
      <div 
        class="bg-[#0A0A0A] rounded-xl border p-8 relative {plan.popular ? 'border-[#5865F2]' : 'border-white/5'}"
      >
        {#if plan.popular}
          <div class="absolute -top-4 left-1/2 transform -translate-x-1/2 bg-[#5865F2] text-white px-4 py-1 rounded-full text-xs font-bold">
            MOST POPULAR
          </div>
        {/if}
        
        <div class="mb-6">
          <h3 class="text-2xl font-bold text-white mb-2">{plan.name}</h3>
          <div class="text-gray-400 text-sm mb-4">{plan.members}</div>
          <div class="flex items-baseline gap-2">
            <span class="text-4xl font-bold text-white">{plan.price}</span>
            <span class="text-gray-500 text-sm">one-time</span>
          </div>
        </div>

        <ul class="space-y-3 mb-8">
          {#each plan.features as feature}
            <li class="flex items-start gap-3 text-sm">
              <svg class="w-5 h-5 text-[#5865F2] flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
              </svg>
              <span class="text-gray-300">{feature}</span>
            </li>
          {/each}
        </ul>

        <a 
          href="#add-bot" 
          class="block w-full text-center py-3 rounded-lg font-semibold transition-colors text-white {plan.popular ? 'bg-[#5865F2] hover:bg-[#4752C4]' : 'bg-white/5 hover:bg-white/10'}"
        >
          Get Started
        </a>
      </div>
    {/each}
  </div>

  <div class="text-center mt-12 text-gray-500 text-sm">
    All plans include lifetime updates and no hidden fees.
  </div>
</section>
