<script>
  import { slide } from 'svelte/transition';
  
  let openIndex = -1;
  
  const faqs = [
    {
      question: "How does the one-time payment work?",
      answer: "Unlike other Discord bots with monthly subscriptions, NovaXp uses a one-time payment model. Pay once based on your server size, and use NovaXp forever with all future updates included. No hidden fees, no recurring charges."
    },
    {
      question: "Can I upgrade my plan later?",
      answer: "Yes! If your community grows, you can easily upgrade to a higher tier. You'll only pay the difference between your current plan and the new one."
    },
    {
      question: "How long does setup take?",
      answer: "Most servers are up and running in under 2 minutes. Just click 'Add to Discord', authorize the bot, and you're done. You can customize settings later, but NovaXp works great with default settings."
    },
    {
      question: "What happens if my server grows beyond my plan's limit?",
      answer: "NovaXp will continue working, but you'll get a notification to upgrade. You have 30 days to upgrade before any features are limited. We never abruptly cut off service."
    },
    {
      question: "Do you offer refunds?",
      answer: "Yes! We offer a 30-day money-back guarantee. If NovaXp doesn't work for your community, just contact support for a full refund, no questions asked."
    },
    {
      question: "Can I customize the XP rates and rewards?",
      answer: "Absolutely! You have full control over XP rates for different activities, custom challenges, reward shop items, and more. Make NovaXp work exactly how you want."
    }
  ];
  
  function toggle(index) {
    openIndex = openIndex === index ? -1 : index;
  }
</script>

<section class="py-24 px-4 max-w-4xl mx-auto">
  <div class="text-center mb-16">
    <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Frequently asked questions</h2>
    <p class="text-gray-400 text-lg">Everything you need to know about NovaXp</p>
  </div>

  <div class="space-y-4">
    {#each faqs as faq, i}
      <div class="bg-[#0A0A0A] rounded-xl border border-white/5 overflow-hidden">
        <button
          class="w-full px-6 py-5 flex items-center justify-between text-left hover:bg-white/5 transition-colors"
          on:click={() => toggle(i)}
        >
          <span class="text-white font-semibold pr-8">{faq.question}</span>
          <svg 
            class="w-5 h-5 text-[#5865F2] flex-shrink-0 transition-transform duration-300"
            class:rotate-180={openIndex === i}
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
          </svg>
        </button>
        
        {#if openIndex === i}
          <div transition:slide={{ duration: 300 }} class="px-6 pb-5">
            <p class="text-gray-400 text-sm leading-relaxed">{faq.answer}</p>
          </div>
        {/if}
      </div>
    {/each}
  </div>

  <div class="text-center mt-12">
    <p class="text-gray-400 mb-4">Still have questions?</p>
    <a href="#" class="text-[#5865F2] hover:text-[#4752C4] font-semibold transition-colors">
      Contact our support team →
    </a>
  </div>
</section>
