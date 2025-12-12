<script lang="ts">
	import Hero from "$lib/components/Hero.svelte";
	import FeatureSection from "$lib/components/FeatureSection.svelte";
	import HowItWorks from "$lib/components/HowItWorks.svelte";
	import Testimonials from "$lib/components/Testimonials.svelte";
	import Pricing from "$lib/components/Pricing.svelte";
	import Footer from "$lib/components/Footer.svelte";
	
	import Leaderboard from "$lib/components/visuals/Leaderboard.svelte";
	import XPTracking from "$lib/components/visuals/XPTracking.svelte";
	import RewardsShop from "$lib/components/visuals/RewardsShop.svelte";
	import Challenges from "$lib/components/visuals/Challenges.svelte";
	import Analytics from "$lib/components/visuals/Analytics.svelte";
	import Commands from "$lib/components/visuals/Commands.svelte";
</script>

<main class="bg-novaxp-bg min-h-screen text-white selection:bg-white/20">
	<Hero />
	
	<div class="mt-20 md:mt-40">
        <!-- Stats Section -->
        <div class="px-4 max-w-6xl mx-auto mb-32">
             <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
                 <div class="bg-[#0A0A0A] rounded-xl border border-white/5 p-8">
                     <div class="text-4xl md:text-5xl font-bold text-white mb-2">2,400+</div>
                     <div class="text-gray-400">Active Discord Servers</div>
                 </div>
                 <div class="bg-[#0A0A0A] rounded-xl border border-white/5 p-8">
                     <div class="text-4xl md:text-5xl font-bold text-white mb-2">180K+</div>
                     <div class="text-gray-400">Members Tracked</div>
                 </div>
                 <div class="bg-[#0A0A0A] rounded-xl border border-white/5 p-8">
                     <div class="text-4xl md:text-5xl font-bold text-white mb-2">12M+</div>
                     <div class="text-gray-400">XP Points Distributed</div>
                 </div>
             </div>
             <div class="text-center mt-10 text-gray-500 text-sm flex flex-col items-center gap-2">
                 <span class="transform rotate-90">›</span>
                 See what makes NovaXp different.
             </div>
        </div>

		<FeatureSection 
			label="REAL-TIME LEADERBOARDS"
			title="Drive competition."
			description="Public leaderboards showcase top members, creating healthy competition and motivating participation across your entire community."
		>
			<Leaderboard />
		</FeatureSection>

		<FeatureSection 
			label="AUTOMATIC XP TRACKING"
			title="Reward every action."
			description="Automatically track messages, reactions, voice activity, and more. Members earn XP for everything they do in your server."
		>
			<XPTracking />
		</FeatureSection>

		<FeatureSection 
			label="CUSTOM CHALLENGES"
			title="Keep members engaged."
			description="Create daily streaks, special events, and custom challenges. Integrate with Twitter, YouTube, and other platforms for cross-platform engagement."
		>
			<Challenges />
		</FeatureSection>

		<FeatureSection 
			label="REWARDS SHOP"
			title="Let members spend their XP."
			description="Create a custom shop where members exchange XP for roles, perks, or exclusive rewards. Fully customizable to match your community."
		>
			<RewardsShop />
		</FeatureSection>

		<FeatureSection 
			label="ADVANCED ANALYTICS"
			title="Track engagement trends."
			description="Understand your community with detailed analytics. See who's active, when they're online, and what drives engagement."
		>
			<Analytics />
		</FeatureSection>

		<FeatureSection 
			label="SLASH COMMANDS"
			title="Simple and intuitive."
			description="Easy-to-use Discord slash commands make it simple for members to check their XP, view leaderboards, and browse rewards."
		>
			<Commands />
		</FeatureSection>

		<FeatureSection 
			label="VOTING CAMPAIGNS"
			title="Run community events."
			description="Create voting campaigns with prize pools. Automated winner selection makes running contests and giveaways effortless."
		>
			<Analytics />
		</FeatureSection>

		<FeatureSection 
			label="ONE-CLICK SETUP"
			title="Get started in seconds."
			description="No complex configuration needed. Add NovaXp to your Discord server with one click and start gamifying your community immediately."
		>
			<Commands />
		</FeatureSection>
	</div>

	<HowItWorks />

	<Testimonials />

	<Pricing />

	<Footer />
</main>

