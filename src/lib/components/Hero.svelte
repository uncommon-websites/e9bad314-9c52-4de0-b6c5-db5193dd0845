<script>
    import Navbar from './Navbar.svelte';
</script>

<section class="relative min-h-screen flex flex-col items-center pt-32 overflow-hidden bg-[#050505]">
    <!-- Gradient overlay to fade to black at bottom -->
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,_var(--tw-gradient-stops))] from-[#5865F2]/20 via-[#1a202c] to-[#050505] pointer-events-none opacity-80"></div>
    
    <Navbar transparent={true} />
    
    <div class="text-center z-10 px-4 max-w-4xl mx-auto mt-10">
        <div class="mb-6 text-white/80 text-sm font-medium tracking-wide">Transform your Discord community</div>
        <h1 class="text-5xl md:text-7xl font-medium text-white tracking-tight mb-8 leading-[1.1]">
            Turn lurkers into<br />
            active members.
        </h1>
        
        <div class="flex items-center justify-center gap-6 mb-20">
            <a href="#add-bot" class="bg-[#5865F2] text-white px-6 py-3 rounded-full font-semibold hover:bg-[#4752C4] transition-colors">Add to Discord</a>
            <span class="text-white/70 text-sm font-medium">One-click installation.</span>
        </div>
    </div>

    <!-- Hero Image Placeholder / Mockup -->
    <div class="relative w-full max-w-7xl mx-auto perspective-2000 z-10">
        <div class="transform rotate-x-20 rotate-y-minus-10 rotate-z-10 scale-90 translate-y-20 origin-top">
            <!-- Discord-style Leaderboard Interface -->
            <div class="bg-[#2B2D31] rounded-xl shadow-2xl overflow-hidden border border-white/10 relative">
                <!-- Header -->
                <div class="h-14 bg-[#313338] border-b border-black/20 flex items-center px-6 gap-4">
                    <div class="text-white font-semibold text-sm flex items-center gap-2">
                        <svg class="w-5 h-5 text-[#5865F2]" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5zm0 18c-3.31 0-6-2.69-6-6s2.69-6 6-6 6 2.69 6 6-2.69 6-6 6zm-1-9h2v2h-2v-2zm0 4h2v2h-2v-2z"/>
                        </svg>
                        # leaderboard
                    </div>
                    <div class="flex-1"></div>
                    <div class="text-xs text-gray-400">🏆 Top Members</div>
                </div>
                
                <!-- Leaderboard List -->
                <div class="bg-[#2B2D31] p-6">
                    {#each Array(10) as _, i}
                        <div class="flex items-center gap-4 px-4 py-3 rounded-lg hover:bg-[#35373C] group transition-colors mb-2">
                            <div class="w-8 text-center font-bold text-gray-500 text-sm">#{i + 1}</div>
                            <div class="w-10 h-10 rounded-full bg-gradient-to-br from-[#5865F2] to-[#4752C4] flex-shrink-0 flex items-center justify-center text-white font-semibold text-sm">
                                {String.fromCharCode(65 + i)}
                            </div>
                            <div class="flex-1">
                                <div class="h-3 bg-[#35373C] rounded w-32 mb-1"></div>
                                <div class="h-2 bg-[#35373C]/50 rounded w-20"></div>
                            </div>
                            <div class="flex items-center gap-2">
                                <div class="text-[#5865F2] font-bold text-sm">{(1000 - i * 50).toLocaleString()}</div>
                                <div class="text-gray-500 text-xs">XP</div>
                            </div>
                            <div class="w-6 h-6 rounded bg-[#5865F2]/20 flex items-center justify-center">
                                <span class="text-[#5865F2] text-xs">⚡</span>
                            </div>
                        </div>
                    {/each}
                </div>
                
                <!-- Fade out at bottom of card -->
                <div class="absolute bottom-0 left-0 right-0 h-32 bg-gradient-to-t from-[#050505] to-transparent"></div>
            </div>
        </div>
    </div>
</section>

<style>
    .perspective-2000 {
        perspective: 2000px;
    }
    .rotate-x-20 {
        transform: rotateX(20deg) rotateY(-10deg) rotateZ(5deg);
    }
</style>
