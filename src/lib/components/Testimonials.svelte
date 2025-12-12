<script>
  const testimonials = [
    {
      quote: "NovaXp completely transformed our server. We went from 20% active members to over 70% in just two months. The leaderboard feature is addictive!",
      author: "Alex Chen",
      role: "Gaming Community Owner",
      server: "2,400 members",
      image: "/generated/image-a-diverse-group-of-young-people-excitedl-1765578359432-0.webp"
    },
    {
      quote: "The one-time payment model is a game-changer. No more monthly subscriptions eating into our budget. Setup took literally 2 minutes.",
      author: "Sarah Martinez",
      role: "NFT Community Manager",
      server: "850 members",
      image: "/generated/image-a-close-up-of-hands-holding-a-phone-show-1765578362867-1.webp"
    },
    {
      quote: "Our members love the XP shop. Being able to trade points for custom roles has created an economy within our community. Engagement is through the roof!",
      author: "James Wilson",
      role: "Educational Discord Owner",
      server: "1,200 members",
      image: "/generated/image-a-group-of-friends-celebrating-together--1765578366048-2.webp"
    }
  ];
</script>

<section class="py-24 px-4 max-w-7xl mx-auto">
  <div class="text-center mb-16">
    <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Loved by community builders</h2>
    <p class="text-gray-400 text-lg">Join thousands of Discord servers using NovaXp</p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    {#each testimonials as testimonial}
      <div class="bg-[#0A0A0A] rounded-xl border border-white/5 p-6 flex flex-col">
        <div class="flex-1 mb-6">
          <p class="text-gray-300 text-sm leading-relaxed mb-6">"{testimonial.quote}"</p>
        </div>
        
        <div class="flex items-center gap-4">
          <div class="w-12 h-12 rounded-full bg-gradient-to-br from-[#5865F2] to-[#4752C4] flex items-center justify-center flex-shrink-0">
            <span class="text-white font-bold text-lg">{testimonial.author.charAt(0)}</span>
          </div>
          <div>
            <div class="text-white font-semibold text-sm">{testimonial.author}</div>
            <div class="text-gray-500 text-xs">{testimonial.role}</div>
            <div class="text-[#5865F2] text-xs mt-1">{testimonial.server}</div>
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>
