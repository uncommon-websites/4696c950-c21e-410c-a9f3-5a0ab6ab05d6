<script lang="ts">
	import { onMount } from 'svelte';

    // Partner data - Law firms, certifiers, and notified bodies
    const partners = [
        { name: 'TÜV SÜD', src: '' },
        { name: 'DEKRA', src: '' },
        { name: 'Clifford Chance', src: '' },
        { name: 'Latham & Watkins', src: '' },
        { name: 'BSI', src: '' },
        { name: 'Allen & Overy', src: '' },
        { name: 'Freshfields', src: '' },
        { name: 'DLA Piper', src: '' },
        { name: 'SGS', src: '' },
        { name: 'Eurofins', src: '' },
        { name: 'Linklaters', src: '' },
        { name: 'Bird & Bird', src: '' },
        { name: 'White & Case', src: '' },
        { name: 'Baker McKenzie', src: '' },
        { name: 'Osborne Clarke', src: '' },
        { name: 'Hogan Lovells', src: '' },
        { name: 'Intertek', src: '' },
        { name: 'Applus+', src: '' },
        { name: 'Bureau Veritas', src: '' },
        { name: 'Taylor Wessing', src: '' },
        { name: 'CMS', src: '' },
    ];

    const articles = [
        {
            tag: 'Compliance',
            title: 'The AIA Compliance Roadmap',
            desc: 'A step-by-step guide for high-risk AI providers to meet 2026 deadlines.',
            img: '/generated/image-a-close-up-of-a-high-quality-printed-doc-1768668460004-2.webp',
            bg: 'bg-primary-50'
        },
        {
            tag: 'Regulation',
            title: 'Annex IV Deep Dive',
            desc: 'Everything you need to include in your technical documentation for CE-marking.',
            img: 'https://placehold.co/300x200/D4C5A3/1a1a1a?text=Annex+IV',
            bg: 'bg-gray-100'
        },
        {
            tag: 'Standards',
            title: 'ISO/IEC 42001 & the AI Act',
            desc: 'How to align your AI Management System with European legal requirements.',
            img: 'https://placehold.co/300x200/E8E8E3/1a1a1a?text=ISO+42001',
            bg: 'bg-primary-100'
        },
        {
            tag: 'Strategy',
            title: 'GPAI Provider Obligations',
            desc: 'The specific requirements for General Purpose AI models under the new rules.',
            img: 'https://placehold.co/300x200/F0E6D2/1a1a1a?text=GPAI',
            bg: 'bg-gray-200'
        }
    ];

    const testimonials = [
        {
            quote: "AIA Conformity provides the structured legal logic we need to bridge the gap between engineering and compliance.",
            author: "Dr. Elena Vance",
            role: "Head of AI Compliance",
            company: "European Tech Group",
            img: "/generated/image-a-professional-woman-in-her-40s-legal-or-1768668457667-1.webp"
        }
    ];
</script>

<div class="min-h-screen bg-white text-gray-900 font-sans selection:bg-primary-100">
    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-white/90 backdrop-blur-sm border-b border-gray-100">
        <div class="max-w-[1600px] mx-auto px-6 py-6 flex justify-between items-center">
            <div class="flex items-center gap-3">
                <svg width="32" height="32" viewBox="0 0 96 96" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M32.9111 0C27.4958 0 22.3024 2.14748 18.4732 5.97001L-0.00390625 24.415V32.8579C-0.00390625 38.8228 2.56275 44.1892 6.65372 47.9167C2.56275 51.6441 -0.00390625 57.0105 -0.00390625 62.9754V71.4184L18.4732 89.8634C22.3024 93.686 27.4958 95.8333 32.9111 95.8333C38.8864 95.8333 44.2622 93.2712 47.9961 89.1873C51.73 93.2712 57.1058 95.8333 63.0811 95.8333C68.4964 95.8333 73.6898 93.686 77.519 89.8634L95.9961 71.4184V62.9754C95.9961 57.0105 93.4295 51.6441 89.3385 47.9167C93.4295 44.1892 95.9961 38.8228 95.9961 32.8579V24.415L77.519 5.97001C73.6898 2.14748 68.4964 0 63.0811 0C57.1058 0 51.73 2.5622 47.9961 6.64607C44.2622 2.5622 38.8864 0 32.9111 0ZM61.8172 47.9167C61.5871 47.707 61.3612 47.4916 61.1399 47.2708L47.9961 34.1497L34.8523 47.2708C34.631 47.4916 34.4051 47.707 34.175 47.9167C34.4051 48.1263 34.631 48.3417 34.8523 48.5626L47.9961 61.6836L61.1399 48.5626C61.3612 48.3417 61.5871 48.1263 61.8172 47.9167ZM53.3294 71.4184V75.4505C53.3294 80.8268 57.6955 85.1853 63.0811 85.1853C65.6673 85.1853 68.1477 84.1596 69.9765 82.334L85.3295 67.0076V62.9754C85.3295 57.5992 80.9635 53.2407 75.5779 53.2407C72.9916 53.2407 70.5112 54.2663 68.6824 56.092L53.3294 71.4184ZM42.6628 71.4184L27.3098 56.092C25.481 54.2663 23.0007 53.2407 20.4144 53.2407C15.0287 53.2407 10.6628 57.5992 10.6628 62.9754V67.0076L26.0157 82.334C27.8445 84.1596 30.3249 85.1853 32.9111 85.1853C38.2967 85.1853 42.6628 80.8268 42.6628 75.4505V71.4184ZM42.6628 20.3828V24.415L27.3098 39.7414C25.481 41.567 23.0007 42.5926 20.4144 42.5926C15.0287 42.5926 10.6628 38.2341 10.6628 32.8579V28.8257L26.0157 13.4994C27.8445 11.6738 30.3249 10.6482 32.9111 10.6482C38.2967 10.6482 42.6628 15.0065 42.6628 20.3828ZM68.6824 39.7414L53.3294 24.415V20.3828C53.3294 15.0065 57.6955 10.6482 63.0811 10.6482C65.6673 10.6482 68.1477 11.6738 69.9765 13.4994L85.3295 28.8257V32.8579C85.3295 38.2341 80.9635 42.5926 75.5779 42.5926C72.9916 42.5926 70.5112 41.567 68.6824 39.7414Z" fill="currentColor"/>
                </svg>
                <a href="/" class="text-sm font-bold tracking-tight uppercase">
                    AIA Conformity
                </a>
            </div>
            <div class="flex items-center gap-8">
                <nav class="hidden md:flex items-center gap-6 text-xs font-medium uppercase tracking-wider text-gray-500">
                    <a href="#" class="hover:text-primary-600 transition-colors">Platform</a>
                    <a href="#" class="hover:text-primary-600 transition-colors">AIA Guide</a>
                    <a href="#" class="hover:text-primary-600 transition-colors">Partners</a>
                </nav>
                <a href="#" class="bg-primary-900 text-white px-5 py-2.5 text-xs font-medium rounded-sm hover:bg-primary-800 transition-colors">
                    Request a Demo
                </a>
            </div>
        </div>
    </header>

    <main class="pt-32 pb-20">
        <div class="max-w-[1600px] mx-auto px-6 grid grid-cols-12 gap-8">
            <!-- Sidebar Navigation -->
            <div class="col-span-2 hidden lg:block sticky top-32 h-fit">
                <nav class="flex flex-col space-y-4 text-[10px] text-gray-400 font-bold uppercase tracking-widest">
                    <a href="#" class="text-primary-600">Overview</a>
                    <a href="#" class="hover:text-gray-900 transition-colors">Inventory</a>
                    <a href="#" class="hover:text-gray-900 transition-colors">Legal Logic</a>
                    <a href="#" class="hover:text-gray-900 transition-colors">Documentation</a>
                    <a href="#" class="hover:text-gray-900 transition-colors">Risk Register</a>
                </nav>
            </div>

            <!-- Main Content Area -->
            <div class="col-span-12 lg:col-span-10 space-y-32">
                
                <!-- Hero Section -->
                <section class="relative">
                    <div class="relative w-full h-[650px] overflow-hidden rounded-sm">
                        <img src="/generated/image-a-clean-minimalist-high-tech-office-in-b-1768668454859-0.webp" alt="Modern office" class="absolute inset-0 w-full h-full object-cover" />
                        <div class="absolute inset-0 bg-white/40"></div>
                        
                        <div class="absolute inset-0 flex flex-col items-center justify-center p-12 text-center">
                            <h1 class="text-5xl md:text-7xl font-light text-gray-950 mb-8 max-w-4xl leading-[1.1] tracking-tight">
                                AI compliance you <br><span class="italic font-serif">can prove.</span>
                            </h1>
                            <p class="text-lg text-gray-700 mb-12 max-w-xl leading-relaxed">
                                Deliver provable AIA conformity via automated inventory, legal logic, and documentation workflows.
                            </p>

                            <!-- Logos Card -->
                            <div class="bg-white/95 backdrop-blur-md p-8 rounded-sm shadow-xl max-w-5xl w-full border border-gray-100">
                                <p class="text-[10px] text-gray-400 mb-8 uppercase tracking-[0.2em] font-bold">
                                    Working with leading legal partners, certifiers, and notified bodies
                                </p>
                                <div class="grid grid-cols-3 md:grid-cols-7 gap-y-10 gap-x-4 items-center justify-items-center opacity-70 grayscale">
                                    {#each partners as partner}
                                        <div class="h-4 flex items-center justify-center">
                                            <span class="text-[9px] font-black text-gray-900 tracking-tighter uppercase whitespace-nowrap">{partner.name}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Features Section -->
                <section>
                    <div class="flex justify-between items-baseline mb-24 border-b border-gray-100 pb-4">
                        <h2 class="text-4xl font-light text-gray-900 max-w-2xl leading-tight">
                            Compliance is now a product, <br><span class="text-primary-600">not a guessing game.</span>
                        </h2>
                        <span class="text-[10px] text-gray-400 uppercase tracking-[0.3em] font-bold">The Platform</span>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-20">
                        <div class="space-y-16">
                            <div class="group">
                                <div class="flex gap-6 items-start">
                                    <div class="w-10 h-10 rounded-full border border-primary-200 flex items-center justify-center text-primary-600 font-bold shrink-0">01</div>
                                    <div>
                                        <h3 class="text-xl font-medium mb-4">Automated AI Inventory</h3>
                                        <p class="text-gray-500 leading-relaxed text-sm">
                                            Instantly detect, classify, and track AI systems—from prototypes to production—across products and teams. Maintain a single source of truth for all your AI assets.
                                        </p>
                                    </div>
                                </div>
                            </div>
                            <div class="group">
                                <div class="flex gap-6 items-start">
                                    <div class="w-10 h-10 rounded-full border border-primary-200 flex items-center justify-center text-primary-600 font-bold shrink-0">02</div>
                                    <div>
                                        <h3 class="text-xl font-medium mb-4">Real-time Legal Mapping</h3>
                                        <p class="text-gray-500 leading-relaxed text-sm">
                                            Our compliance engine links your systems to the right obligations using official AIA definitions and thresholds. No more manual cross-referencing of complex legal texts.
                                        </p>
                                    </div>
                                </div>
                            </div>
                            <div class="group">
                                <div class="flex gap-6 items-start">
                                    <div class="w-10 h-10 rounded-full border border-primary-200 flex items-center justify-center text-primary-600 font-bold shrink-0">03</div>
                                    <div>
                                        <h3 class="text-xl font-medium mb-4">Annex IV Documentation</h3>
                                        <p class="text-gray-500 leading-relaxed text-sm">
                                            Generate full technical files using guided templates that align with official EU formats. Ready for CE-marking and regulatory audits out of the box.
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="bg-gray-50 rounded-sm p-12 flex flex-col justify-center border border-gray-100 relative overflow-hidden">
                            <div class="absolute top-0 right-0 w-64 h-64 bg-primary-50 rounded-full -mr-32 -mt-32 opacity-50"></div>
                            <div class="relative z-10">
                                <div class="text-xs font-bold text-primary-600 uppercase tracking-widest mb-6">ISO 42001 Aligned</div>
                                <h3 class="text-2xl font-light mb-6 leading-tight">Built for speed. <br>Designed for certainty.</h3>
                                <p class="text-gray-600 text-sm leading-relaxed mb-8">
                                    Log risks, responsibilities, and vendors with workflows designed to prepare you for formal AI management certification without duplicating effort.
                                </p>
                                <div class="space-y-4">
                                    <div class="flex items-center gap-3 text-xs font-medium text-gray-700">
                                        <svg class="w-4 h-4 text-primary-600" fill="currentColor" viewBox="0 0 20 20"><path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"/></svg>
                                        Declaration of Conformity Generator
                                    </div>
                                    <div class="flex items-center gap-3 text-xs font-medium text-gray-700">
                                        <svg class="w-4 h-4 text-primary-600" fill="currentColor" viewBox="0 0 20 20"><path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"/></svg>
                                        ISO-style Risk Register
                                    </div>
                                    <div class="flex items-center gap-3 text-xs font-medium text-gray-700">
                                        <svg class="w-4 h-4 text-primary-600" fill="currentColor" viewBox="0 0 20 20"><path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"/></svg>
                                        Vendor Management Modules
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Strategic Section -->
                <section class="bg-gray-950 text-white rounded-sm p-20 relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-1/2 h-full opacity-10">
                         <svg class="w-full h-full" viewBox="0 0 100 100" preserveAspectRatio="none">
                            <path d="M0 0 L100 0 L100 100 Z" fill="currentColor" />
                        </svg>
                    </div>
                    <div class="relative z-10 grid grid-cols-1 md:grid-cols-2 gap-20 items-center">
                        <div>
                            <span class="text-primary-400 text-[10px] font-bold uppercase tracking-[0.3em] mb-8 block">Market Strategy</span>
                            <h2 class="text-4xl font-light mb-8 leading-tight">
                                Your edge in the <br><span class="italic">compliance race.</span>
                            </h2>
                            <p class="text-gray-400 text-sm leading-relaxed mb-10 max-w-md">
                                GPUs are fast, but audits aren't. General purpose and high-risk AI providers face early deadlines and real liability. AIA Conformity helps you move faster—with evidence that stands up to regulators.
                            </p>
                            <div class="flex gap-4">
                                <button class="bg-primary-600 text-white px-8 py-3 text-xs font-bold uppercase tracking-widest rounded-sm hover:bg-primary-500 transition-colors">
                                    Join Waitlist
                                </button>
                                <button class="border border-white/20 text-white px-8 py-3 text-xs font-bold uppercase tracking-widest rounded-sm hover:bg-white/10 transition-colors">
                                    View Roadmap
                                </button>
                            </div>
                        </div>
                        <div class="grid grid-cols-2 gap-6">
                            <div class="bg-white/5 backdrop-blur-sm p-8 border border-white/10 rounded-sm">
                                <div class="text-3xl font-light text-primary-400 mb-2">2026</div>
                                <div class="text-[10px] uppercase font-bold tracking-wider text-gray-500">Compliance Milestone</div>
                            </div>
                            <div class="bg-white/5 backdrop-blur-sm p-8 b                 </div>
                                <div class="md:w-2/3 p-16 flex flex-col justify-center">
                                    <div class="text-primary-600 mb-8">
                                        <svg class="w-12 h-12 opacity-20" fill="currentColor" viewBox="0 0 32 32"><path d="M10 8v8H6v2h4v4H4v-4h2v-2H2V8h8zm14 0v8h-4v2h4v4h-6v-4h2v-2h-4V8h8z"/></svg>
                                    </div>
                                    <blockquote class="text-2xl font-light leading-relaxed mb-10 text-gray-800">
                                        "{testimonial.quote}"
                                    </blockquote>
                                    <div>
                                        <div class="font-bold text-gray-900 uppercase tracking-widest text-sm">{testimonial.author}</div>
                                        <div class="text-xs text-gray-500 mt-1">{testimonial.role} — {testimonial.company}</div>
                                    </div>
                                </div>
                            </div>
                        {/each}
                    </div>
                </section>

                <!-- Articles -->
                <section>
                    <div class="flex justify-between items-baseline mb-16 border-b border-gray-100 pb-4">
                        <h2 class="text-3xl font-light text-gray-900">
                            Compliance Intelligence
                        </h2>
                        <span class="text-[10px] text-gray-400 uppercase tracking-[0.3em] font-bold">Resources</span>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                        {#each articles as article}
                            <div class="group cursor-pointer">
                                <div class="relative aspect-[4/5] mb-6 overflow-hidden {article.bg} rounded-sm">
                                    <img src={article.img} alt={article.title} class="w-full h-full object-cover grayscale group-hover:scale-105 transition-transform duration-700 opacity-80" />
                                    <span class="absolute top-4 left-4 text-[9px] font-bold uppercase tracking-widest bg-white px-2 py-1 shadow-sm">{article.tag}</span>
                                </div>
                                <h3 class="text-lg font-medium mb-3 leading-tight group-hover:text-primary-600 transition-colors">
                                    {article.title}
                                </h3>
                                <p class="text-xs text-gray-500 mb-4 leading-relaxed">
                                    {article.desc}
                                </p>
                                <a href="#" class="text-[10px] font-bold uppercase tracking-widest text-primary-600 border-b border-primary-600 pb-1">Read Analysis</a>
                            </div>
                        {/each}
                    </div>
                </section>

                <!-- Final CTA -->
                <section class="border-t border-gray-100 pt-32 pb-16 text-center">
                    <h2 class="text-4xl md:text-5xl font-light mb-8">Ready for the AI Act?</h2>
                    <p class="text-gray-500 mb-12 max-w-xl mx-auto leading-relaxed">
                        Join our waitlist for early access, legal-grade documentation templates, and exclusive partner offers from European assessors and certifiers.
                    </p>
                    <div class="flex flex-col md:flex-row gap-4 justify-center items-center">
                        <input type="email" placeholder="Enter your work email" class="px-6 py-3 border border-gray-200 rounded-sm w-full md:w-80 text-sm focus:outline-none focus:border-primary-600" />
                        <button class="bg-primary-900 text-white px-10 py-3 text-xs font-bold uppercase tracking-widest rounded-sm hover:bg-primary-800 transition-colors w-full md:w-auto">
                            Join Waitlist
                        </button>
                    </div>
                </section>

            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-white pt-32 pb-12 border-t border-gray-100 relative overflow-hidden">
        <div class="absolute left-0 bottom-0 text-[15vw] font-black text-gray-50 leading-none select-none pointer-events-none -mb-8 -ml-8 uppercase tracking-tighter">
            Conformity
        </div>

        <div class="max-w-[1600px] mx-auto px-6 relative z-10">
            <div class="grid grid-cols-1 md:grid-cols-12 gap-16 mb-24">
                <div class="md:col-span-4">
                    <div class="flex items-center gap-3 mb-8">
                        <svg width="24" height="24" viewBox="0 0 96 96" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M32.9111 0C27.4958 0 22.3024 2.14748 18.4732 5.97001L-0.00390625 24.415V32.8579C-0.00390625 38.8228 2.56275 44.1892 6.65372 47.9167C2.56275 51.6441 -0.00390625 57.0105 -0.00390625 62.9754V71.4184L18.4732 89.8634C22.3024 93.686 27.4958 95.8333 32.9111 95.8333C38.8864 95.8333 44.2622 93.2712 47.9961 89.1873C51.73 93.2712 57.1058 95.8333 63.0811 95.8333C68.4964 95.8333 73.6898 93.686 77.519 89.8634L95.9961 71.4184V62.9754C95.9961 57.0105 93.4295 51.6441 89.3385 47.9167C93.4295 44.1892 95.9961 38.8228 95.9961 32.8579V24.415L77.519 5.97001C73.6898 2.14748 68.4964 0 63.0811 0C57.1058 0 51.73 2.5622 47.9961 6.64607C44.2622 2.5622 38.8864 0 32.9111 0ZM61.8172 47.9167C61.5871 47.707 61.3612 47.4916 61.1399 47.2708L47.9961 34.1497L34.8523 47.2708C34.631 47.4916 34.4051 47.707 34.175 47.9167C34.4051 48.1263 34.631 48.3417 34.8523 48.5626L47.9961 61.6836L61.1399 48.5626C61.3612 48.3417 61.5871 48.1263 61.8172 47.9167ZM53.3294 71.4184V75.4505C53.3294 80.8268 57.6955 85.1853 63.0811 85.1853C65.6673 85.1853 68.1477 84.1596 69.9765 82.334L85.3295 67.0076V62.9754C85.3295 57.5992 80.9635 53.2407 75.5779 53.2407C72.9916 53.2407 70.5112 54.2663 68.6824 56.092L53.3294 71.4184ZM42.6628 71.4184L27.3098 56.092C25.481 54.2663 23.0007 53.2407 20.4144 53.2407C15.0287 53.2407 10.6628 57.5992 10.6628 62.9754V67.0076L26.0157 82.334C27.8445 84.1596 30.3249 85.1853 32.9111 85.1853C38.2967 85.1853 42.6628 80.8268 42.6628 75.4505V71.4184ZM42.6628 20.3828V24.415L27.3098 39.7414C25.481 41.567 23.0007 42.5926 20.4144 42.5926C15.0287 42.5926 10.6628 38.2341 10.6628 32.8579V28.8257L26.0157 13.4994C27.8445 11.6738 30.3249 10.6482 32.9111 10.6482C38.2967 10.6482 42.6628 15.0065 42.6628 20.3828ZM68.6824 39.7414L53.3294 24.415V20.3828C53.3294 15.0065 57.6955 10.6482 63.0811 10.6482C65.6673 10.6482 68.1477 11.6738 69.9765 13.4994L85.3295 28.8257V32.8579C85.3295 38.2341 80.9635 42.5926 75.5779 42.5926C72.9916 42.5926 70.5112 41.567 68.6824 39.7414Z" fill="currentColor"/>
                        </svg>
                        <div class="text-xs font-bold tracking-tight uppercase">AIA Conformity</div>
                    </div>
                    <p class="text-sm text-gray-500 leading-relaxed max-w-xs">
                        The EU-focused RegTech platform dedicated to provable AI Act conformity and ISO 42001 alignment.
                    </p>
                </div>
                
                <div class="md:col-span-8 grid grid-cols-2 md:grid-cols-4 gap-8">
                    <div>
                        <h4 class="text-[10px] font-bold uppercase tracking-widest text-gray-900 mb-6">Platform</h4>
                        <ul class="text-xs text-gray-500 space-y-4">
                            <li><a href="#" class="hover:text-primary-600">Inventory</a></li>
                            <li><a href="#" class="hover:text-primary-600">Legal Logic</a></li>
                            <li><a href="#" class="hover:text-primary-600">Documentation</a></li>
                            <li><a href="#" class="hover:text-primary-600">Integrations</a></li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="text-[10px] font-bold uppercase tracking-widest text-gray-900 mb-6">Resources</h4>
                        <ul class="text-xs text-gray-500 space-y-4">
                            <li><a href="#" class="hover:text-primary-600">AIA Guide</a></li>
                            <li><a href="#" class="hover:text-primary-600">Annex IV Templates</a></li>
                            <li><a href="#" class="hover:text-primary-600">Risk Register</a></li>
                            <li><a href="#" class="hover:text-primary-600">API Docs</a></li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="text-[10px] font-bold uppercase tracking-widest text-gray-900 mb-6">Company</h4>
                        <ul class="text-xs text-gray-500 space-y-4">
                            <li><a href="#" class="hover:text-primary-600">About Us</a></li>
                            <li><a href="#" class="hover:text-primary-600">Partners</a></li>
                            <li><a href="#" class="hover:text-primary-600">Contact</a></li>
                            <li><a href="#" class="hover:text-primary-600">Careers</a></li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="text-[10px] font-bold uppercase tracking-widest text-gray-900 mb-6">Legal</h4>
                        <ul class="text-xs text-gray-500 space-y-4">
                            <li><a href="#" class="hover:text-primary-600">Privacy</a></li>
                            <li><a href="#" class="hover:text-primary-600">Terms</a></li>
                            <li><a href="#" class="hover:text-primary-600">Compliance</a></li>
                        </ul>
                    </div>
                </div>
            </div>

            <div class="flex flex-col md:flex-row justify-between items-center pt-12 border-t border-gray-100 gap-8">
                <div class="text-[10px] text-gray-400 font-medium uppercase tracking-widest">
                    © 2025 AIA Conformity. All rights reserved.
                </div>
                <div class="flex gap-8">
                    <a href="#" class="text-gray-400 hover:text-primary-600 transition-colors">
                        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                    </a>
                    <a href="#" class="text-gray-400 hover:text-primary-600 transition-colors">
                        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.761 0 5-2.239 5-5v-14c0-2.761-2.239-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                    </a>
                </div>
            </div>
        </div>
    </footer>
</div>

<style>
    /* Custom scrollbar hide for clean look */
    ::-webkit-scrollbar {
        width: 0px;
        background: transparent;
    }
    
    :global(html) {
        scroll-behavior: smooth;
    }
</style>

