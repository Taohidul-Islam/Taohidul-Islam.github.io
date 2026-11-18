<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Taohidul Islam — Electronics Developer & Maker</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        cream: {
                            50: '#FDFBF7',
                            100: '#F5EBE0',
                            200: '#E3D5C8',
                            300: '#D5BDAF',
                        },
                        brown: {
                            700: '#8C6D53',
                            800: '#5C4033',
                            900: '#3E2723',
                            950: '#271815'
                        },
                        amber: {
                            accent: '#C67D5A',
                            light: '#E29578'
                        }
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                        mono: ['Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #FDFBF7;
            color: #3E2723;
        }
        .glass-card {
            background: rgba(245, 235, 224, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(213, 189, 175, 0.4);
        }
        .glass-nav {
            background: rgba(253, 251, 247, 0.85);
            backdrop-filter: blur(10px);
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #F5EBE0;
        }
        ::-webkit-scrollbar-thumb {
            background: #D5BDAF;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #C67D5A;
        }
    </style>
</head>
<body class="bg-cream-50 text-brown-900 selection:bg-amber-accent selection:text-white">

    <!-- Notification Toast (Replaces alert) -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-32 opacity-0 transition-all duration-300 bg-brown-900 text-cream-50 px-6 py-3 rounded-2xl shadow-2xl flex items-center space-x-3 border border-amber-accent/30">
        <i id="toast-icon" class="fa-solid fa-circle-check text-amber-accent text-xl"></i>
        <div>
            <h4 id="toast-title" class="font-bold text-sm">Success!</h4>
            <p id="toast-msg" class="text-xs text-cream-200">Message sent successfully.</p>
        </div>
    </div>

    <!-- Navigation Bar -->
    <nav class="fixed top-0 left-0 right-0 z-40 glass-nav border-b border-cream-200/60 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <a href="#hero" class="flex items-center space-x-3 group">
                <div class="w-10 h-10 rounded-xl bg-brown-900 text-cream-50 flex items-center justify-center font-bold text-lg shadow-md group-hover:bg-amber-accent transition-colors">
                    T
                </div>
                <div>
                    <span class="font-extrabold text-lg tracking-tight text-brown-900">Taohidul <span class="text-amber-accent">Islam</span></span>
                    <span class="block text-[10px] uppercase tracking-widest text-brown-700 font-semibold">Mirpur, Dhaka</span>
                </div>
            </a>

            <!-- Desktop Links -->
            <div class="hidden md:flex items-center space-x-8 font-medium text-sm text-brown-800">
                <a href="#about" class="hover:text-amber-accent transition-colors">About</a>
                <a href="#achievements" class="hover:text-amber-accent transition-colors flex items-center gap-1.5"><i class="fa-solid fa-trophy text-amber-accent"></i> Awards</a>
                <a href="#skills" class="hover:text-amber-accent transition-colors">Skills</a>
                <a href="#projects" class="hover:text-amber-accent transition-colors">Projects</a>
                <a href="#contact" class="hover:text-amber-accent transition-colors">Contact</a>
            </div>

            <!-- CTA / Sound Toggle -->
            <div class="hidden md:flex items-center space-x-4">
                <button onclick="toggleSound()" id="sound-btn" class="w-10 h-10 rounded-xl bg-cream-100 hover:bg-cream-200 text-brown-900 flex items-center justify-center transition-all shadow-sm" title="Toggle Ambient Lo-Fi Vibe">
                    <i class="fa-solid fa-volume-xmark" id="sound-icon"></i>
                </button>
                <a href="#contact" class="px-5 py-2.5 rounded-xl bg-brown-900 hover:bg-brown-800 text-cream-50 text-sm font-semibold shadow-lg hover:shadow-xl transition-all">
                    Let's Talk
                </a>
            </div>

            <!-- Mobile Menu Button -->
            <button onclick="toggleMobileMenu()" class="md:hidden p-2.5 rounded-xl bg-cream-100 text-brown-900 focus:outline-none">
                <i class="fa-solid fa-bars text-lg" id="menu-icon"></i>
            </button>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden glass-card border-b border-cream-200 px-6 py-5 space-y-4">
            <a href="#about" onclick="toggleMobileMenu()" class="block font-medium text-brown-800 hover:text-amber-accent">About</a>
            <a href="#achievements" onclick="toggleMobileMenu()" class="block font-medium text-brown-800 hover:text-amber-accent">Awards</a>
            <a href="#skills" onclick="toggleMobileMenu()" class="block font-medium text-brown-800 hover:text-amber-accent">Skills</a>
            <a href="#projects" onclick="toggleMobileMenu()" class="block font-medium text-brown-800 hover:text-amber-accent">Projects</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block font-medium text-brown-800 hover:text-amber-accent">Contact</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero" class="pt-32 pb-20 md:pt-40 md:py-32 relative overflow-hidden">
        <!-- Background decorative blobs -->
        <div class="absolute top-20 left-1/2 -translate-x-1/2 w-96 h-96 bg-amber-light/10 rounded-full blur-3xl pointer-events-none"></div>
        <div class="absolute bottom-10 right-10 w-72 h-72 bg-cream-200/50 rounded-full blur-2xl pointer-events-none"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                <!-- Text Column -->
                <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                    <div class="inline-flex items-center space-x-2 px-4 py-2 rounded-full bg-cream-200/70 border border-cream-300 text-brown-900 text-xs sm:text-sm font-semibold shadow-sm animate-bounce">
                        <span class="w-2.5 h-2.5 rounded-full bg-amber-accent"></span>
                        <span>National Champion (2026) • 16yo Electronics Dev</span>
                    </div>

                    <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold tracking-tight text-brown-900 leading-tight">
                        Hey! I'm <span class="text-amber-accent underline decoration-amber-light/50 decoration-wavy">Taohidul Islam</span> 👋
                    </h1>

                    <p class="text-base sm:text-lg text-brown-800 max-w-2xl mx-auto lg:mx-0 leading-relaxed font-normal">
                        16-year-old electronics developer, hardware maker, and 11th grader at <strong class="text-brown-900">SOS Hermann Gmeiner College Dhaka</strong>, based in Mirpur. I build custom ESP32 IoT systems, design PCBs in KiCad, and vibe-code with Claude.
                    </p>

                    <!-- CTAs -->
                    <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4 pt-4">
                        <a href="#projects" class="px-7 py-3.5 rounded-2xl bg-brown-900 hover:bg-brown-800 text-cream-50 font-bold text-sm shadow-xl hover:shadow-2xl transition-all transform hover:-translate-y-0.5 flex items-center gap-2">
                            <span>Explore My Work</span>
                            <i class="fa-solid fa-arrow-right text-xs"></i>
                        </a>
                        <a href="https://github.com/Taohidul-Islam" target="_blank" class="px-7 py-3.5 rounded-2xl bg-cream-100 hover:bg-cream-200 text-brown-900 font-bold text-sm border border-cream-300 shadow-sm transition-all flex items-center gap-2">
                            <i class="fa-brands fa-github text-lg"></i>
                            <span>GitHub Profile</span>
                        </a>
                    </div>

                    <!-- Quick Stats -->
                    <div class="grid grid-cols-3 gap-4 pt-8 border-t border-cream-200/80 max-w-lg mx-auto lg:mx-0">
                        <div class="text-center lg:text-left">
                            <h3 class="text-2xl sm:text-3xl font-extrabold text-brown-900">2x</h3>
                            <p class="text-xs text-brown-700 font-medium">National Wins</p>
                        </div>
                        <div class="text-center lg:text-left">
                            <h3 class="text-2xl sm:text-3xl font-extrabold text-brown-900">4th</h3>
                            <p class="text-xs text-brown-700 font-medium">Int'l Robotech</p>
                        </div>
                        <div class="text-center lg:text-left">
                            <h3 class="text-2xl sm:text-3xl font-extrabold text-brown-900">ESP32</h3>
                            <p class="text-xs text-brown-700 font-medium">Core Tech</p>
                        </div>
                    </div>
                </div>

                <!-- Image / Polaroid Column -->
                <div class="lg:col-span-5 flex justify-center">
                    <div class="relative group">
                        <!-- Polaroid Frame -->
                        <div class="w-72 sm:w-80 bg-white p-4 pb-8 rounded-2xl shadow-2xl transform rotate-2 group-hover:rotate-0 transition-transform duration-500 border border-cream-200">
                            <div class="relative overflow-hidden rounded-xl aspect-[4/5] bg-cream-100">
                                <img src="image_4ffc44.png" alt="Taohidul Islam" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/400x500/F5EBE0/3E2723?text=Taohidul+Islam'">
                                <div class="absolute inset-0 bg-gradient-to-t from-brown-900/40 via-transparent to-transparent opacity-60"></div>
                                <div class="absolute bottom-3 left-3 right-3 text-white">
                                    <span class="text-[10px] uppercase font-bold tracking-wider px-2 py-0.5 rounded bg-amber-accent/90">Mirpur, Dhaka</span>
                                </div>
                            </div>
                            <div class="pt-4 text-center">
                                <h3 class="font-extrabold text-brown-900 text-lg">Taohidul Islam</h3>
                                <p class="text-xs text-brown-700 font-mono mt-0.5">Hardware Maker & Developer</p>
                            </div>
                        </div>

                        <!-- Floating Badge -->
                        <div class="absolute -bottom-6 -left-6 glass-card px-4 py-3 rounded-2xl shadow-xl flex items-center space-x-3 border border-cream-300 animate-pulse">
                            <div class="w-10 h-10 rounded-xl bg-amber-accent/20 text-amber-accent flex items-center justify-center font-bold">
                                <i class="fa-solid fa-microchip text-lg"></i>
                            </div>
                            <div>
                                <h4 class="text-xs font-bold text-brown-900">KiCad & ESP32</h4>
                                <p class="text-[10px] text-brown-700">Custom PCB Design</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Me Section -->
    <section id="about" class="py-20 bg-cream-100/50 border-y border-cream-200/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto space-y-4 mb-16">
                <span class="text-xs uppercase font-extrabold tracking-widest text-amber-accent px-3 py-1 rounded-full bg-amber-accent/10">Get To Know Me</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-brown-900">Passionate Electronics Geek from Dhaka</h2>
                <p class="text-brown-800 text-sm sm:text-base">Building the future one circuit board at a time.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Card 1 -->
                <div class="glass-card p-8 rounded-3xl shadow-lg border border-cream-200/80 hover:shadow-xl transition-all group">
                    <div class="w-14 h-14 rounded-2xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-2xl font-bold mb-6 group-hover:bg-amber-accent group-hover:text-white transition-all">
                        <i class="fa-solid fa-school"></i>
                    </div>
                    <h3 class="text-xl font-bold text-brown-900 mb-3">Student & Life in Mirpur</h3>
                    <p class="text-sm text-brown-800 leading-relaxed">
                        I am 16 years old and currently studying in 11th Grade at <strong class="text-brown-900">SOS Hermann Gmeiner College Dhaka</strong>, located in Mirpur. Balancing rigorous academics with my absolute passion for electronics and hardware prototyping.
                    </p>
                </div>

                <!-- Card 2 -->
                <div class="glass-card p-8 rounded-3xl shadow-lg border border-cream-200/80 hover:shadow-xl transition-all group">
                    <div class="w-14 h-14 rounded-2xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-2xl font-bold mb-6 group-hover:bg-amber-accent group-hover:text-white transition-all">
                        <i class="fa-solid fa-microchip"></i>
                    </div>
                    <h3 class="text-xl font-bold text-brown-900 mb-3">Hardware & PCBs</h3>
                    <p class="text-sm text-brown-800 leading-relaxed">
                        My core expertise lies in ESP32 microcontrollers, schematic design, and custom PCB layout creation using <strong class="text-brown-900">KiCad</strong>. I love turning theoretical schematics into working physical prototypes.
                    </p>
                </div>

                <!-- Card 3 -->
                <div class="glass-card p-8 rounded-3xl shadow-lg border border-cream-200/80 hover:shadow-xl transition-all group">
                    <div class="w-14 h-14 rounded-2xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-2xl font-bold mb-6 group-hover:bg-amber-accent group-hover:text-white transition-all">
                        <i class="fa-solid fa-network-wired"></i>
                    </div>
                    <h3 class="text-xl font-bold text-brown-900 mb-3">Servers & Vibe-Coding</h3>
                    <p class="text-sm text-brown-800 leading-relaxed">
                        Beyond hardware, I manage home labs, configure SSH servers, handle network routing, design 3D models in OnShape, and accelerate development by vibe-coding alongside Claude.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Achievements & Trophies Section -->
    <section id="achievements" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto space-y-4 mb-16">
                <span class="text-xs uppercase font-extrabold tracking-widest text-amber-accent px-3 py-1 rounded-full bg-amber-accent/10">Competitions & Honors</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-brown-900">Awards & Recognition 🏆</h2>
                <p class="text-brown-800 text-sm sm:text-base">Real milestones from national tech fests and international robotics competitions.</p>
            </div>

            <!-- Featured Winner Showcase: IUT Techathon Nationals & Rover Summit 2026 -->
            <div class="glass-card rounded-3xl shadow-2xl p-6 sm:p-10 border border-cream-300 mb-10">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                    <div class="lg:col-span-6 space-y-6">
                        <div class="inline-flex items-center space-x-2 px-3.5 py-1.5 rounded-full bg-amber-accent text-white text-xs font-bold shadow">
                            <i class="fa-solid fa-trophy"></i>
                            <span>CHAMPION • National Win #1</span>
                        </div>
                        <h3 class="text-2xl sm:text-3xl font-extrabold text-brown-900">IUT Techathon Nationals & Rover Summit 2026</h3>
                        <p class="text-sm sm:text-base text-brown-800 leading-relaxed">
                            Crowned <strong>Champion (1st Place)</strong> in the <strong>Project Showcasing (Junior)</strong> segment representing <strong>Team Inferno</strong> from <strong class="text-brown-900">SOS Hermann Gmeiner College Dhaka</strong>. Awarded BDT 10,000/- prize money and the official championship crest.
                        </p>
                        <div class="flex flex-wrap gap-3 pt-2">
                            <span class="px-3 py-1.5 rounded-xl bg-cream-200 text-brown-900 text-xs font-semibold">📍 Islamic University of Technology (IUT)</span>
                            <span class="px-3 py-1.5 rounded-xl bg-cream-200 text-brown-900 text-xs font-semibold">🏆 BDT 10,000/- Prize</span>
                            <span class="px-3 py-1.5 rounded-xl bg-cream-200 text-brown-900 text-xs font-semibold">👥 Team Inferno</span>
                        </div>
                    </div>

                    <div class="lg:col-span-6 flex justify-center">
                        <div class="relative rounded-2xl overflow-hidden shadow-xl border-4 border-white bg-cream-200 max-w-lg w-full">
                            <img src="image_4fff63.png" alt="IUT Techathon Nationals & Rover Summit 2026 Champions" class="w-full h-auto object-cover hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/F5EBE0/3E2723?text=IUT+Techathon+2026+Champions'">
                            <div class="absolute bottom-0 inset-x-0 bg-gradient-to-t from-brown-900/90 to-transparent p-4 text-white">
                                <p class="text-xs font-bold">Team Inferno Award Ceremony — IUT Techathon Nationals & Rover Summit 2026</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Second National Win & International Placement -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- National Win #2: SMUCT CSIT Fest 2026 -->
                <div class="glass-card p-8 rounded-3xl shadow-lg border border-cream-200 flex flex-col justify-between hover:shadow-xl transition-all">
                    <div>
                        <div class="flex items-center justify-between mb-5">
                            <span class="px-3.5 py-1.5 rounded-full bg-amber-accent/20 text-amber-accent text-xs font-bold">National Win #2</span>
                            <div class="w-11 h-11 rounded-2xl bg-amber-accent/15 text-amber-accent flex items-center justify-center text-xl">
                                <i class="fa-solid fa-award"></i>
                            </div>
                        </div>
                        <h3 class="text-2xl font-extrabold text-brown-900 mb-3">SMUCT CSIT Fest 2026</h3>
                        <p class="text-sm text-brown-800 leading-relaxed mb-6">
                            Achieved a <strong>National Competition Win</strong> at <strong>SMUCT CSIT Fest 2026</strong>, showcasing custom hardware engineering, ESP32-based embedded design, and practical problem-solving against top student teams across the country.
                        </p>
                    </div>
                    <div class="pt-4 border-t border-cream-200 flex items-center justify-between text-xs text-brown-700 font-semibold">
                        <span>Shanto-Mariam University of Creative Technology</span>
                        <span class="text-amber-accent font-bold">2026</span>
                    </div>
                </div>

                <!-- International Achievement: 6th International Robotech Olympiad -->
                <div class="glass-card p-8 rounded-3xl shadow-lg border border-cream-200 flex flex-col justify-between hover:shadow-xl transition-all">
                    <div>
                        <div class="flex items-center justify-between mb-5">
                            <span class="px-3.5 py-1.5 rounded-full bg-brown-900 text-cream-50 text-xs font-bold">4th Place • International</span>
                            <div class="w-11 h-11 rounded-2xl bg-amber-accent/15 text-amber-accent flex items-center justify-center text-xl">
                                <i class="fa-solid fa-globe"></i>
                            </div>
                        </div>
                        <h3 class="text-2xl font-extrabold text-brown-900 mb-3">6th International Robotech Olympiad</h3>
                        <p class="text-sm text-brown-800 leading-relaxed mb-6">
                            Secured <strong>4th Place</strong> on the international stage at the <strong>6th International Robotech Olympiad</strong>, competing with robotics builders and electronics innovators in hardware prototyping and embedded systems.
                        </p>
                    </div>
                    <div class="pt-4 border-t border-cream-200 flex items-center justify-between text-xs text-brown-700 font-semibold">
                        <span>International Robotics & Tech Competition</span>
                        <span class="text-amber-accent font-bold">4th Place</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills & Tech Stack Section -->
    <section id="skills" class="py-20 bg-cream-100/50 border-y border-cream-200/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto space-y-4 mb-16">
                <span class="text-xs uppercase font-extrabold tracking-widest text-amber-accent px-3 py-1 rounded-full bg-amber-accent/10">Expertise</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-brown-900">Skills & Tech Stack</h2>
                <p class="text-brown-800 text-sm sm:text-base">The tools and technologies I use to bring ideas into reality.</p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Skill 1 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-microchip"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">ESP32 Development & IoT</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Firmware development, sensor integration, Wi-Fi/Bluetooth mesh networks, and real-time IoT automation.</p>
                    </div>
                </div>

                <!-- Skill 2 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-bolt"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">KiCad PCB Designing</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Schematic capture, multi-layer PCB layout design, footprint creation, and Gerber file generation for manufacturing.</p>
                    </div>
                </div>

                <!-- Skill 3 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-cube"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">CAD Design on OnShape</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Parametric 3D modeling for custom enclosures, robot chassis, brackets, and mechanical assemblies.</p>
                    </div>
                </div>

                <!-- Skill 4 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-wand-magic-sparkles"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">Vibe-Coding with Claude</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Leveraging LLMs and Claude AI to rapidly prototype software, web apps, scripts, and documentation.</p>
                    </div>
                </div>

                <!-- Skill 5 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-server"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">Network & Server Hosting</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Home lab management, local server hosting, routing, firewall setup, and containerized deployment.</p>
                    </div>
                </div>

                <!-- Skill 6 -->
                <div class="glass-card p-6 rounded-2xl shadow-sm hover:shadow-md transition-all border border-cream-200 flex items-start space-x-4">
                    <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center text-xl font-bold shrink-0">
                        <i class="fa-solid fa-terminal"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-brown-900 text-base mb-1">Operating SSH Servers</h3>
                        <p class="text-xs text-brown-700 leading-relaxed">Linux terminal administration, secure shell tunnels, remote server management, and automated bash scripting.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Showcase Section (Live GitHub Repositories) -->
    <section id="projects" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto space-y-4 mb-10">
                <span class="text-xs uppercase font-extrabold tracking-widest text-amber-accent px-3 py-1 rounded-full bg-amber-accent/10">Live from GitHub</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-brown-900">My Real Projects & Repositories</h2>
                <p class="text-brown-800 text-sm sm:text-base">Automatically synced with <a href="https://github.com/Taohidul-Islam" target="_blank" class="font-bold text-amber-accent underline">github.com/Taohidul-Islam</a> — zero fake placeholders.</p>
            </div>

            <!-- Controls Bar: Dynamic Language Filters & Refresh Button -->
            <div class="flex flex-col sm:flex-row items-center justify-between gap-4 mb-10">
                <!-- Dynamic Filter Buttons injected by JS -->
                <div id="repo-filters" class="flex flex-wrap items-center justify-center sm:justify-start gap-2">
                    <button onclick="filterRepos('ALL')" data-lang="ALL" class="filter-btn px-4 py-2 rounded-xl bg-brown-900 text-cream-50 text-xs font-bold shadow-sm transition-all">
                        All Repos
                    </button>
                </div>

                <!-- Refresh from GitHub Button -->
                <button onclick="fetchGitHubRepos(true)" id="refresh-repos-btn" class="px-4 py-2 rounded-xl bg-cream-200/80 hover:bg-cream-300 text-brown-900 text-xs font-bold border border-cream-300 shadow-sm transition-all flex items-center gap-2 shrink-0">
                    <i id="refresh-icon" class="fa-solid fa-rotate-right"></i>
                    <span>Refresh from GitHub</span>
                </button>
            </div>

            <!-- Loading Skeleton State -->
            <div id="projects-loading" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="glass-card rounded-3xl p-6 border border-cream-200 animate-pulse space-y-4">
                    <div class="flex justify-between">
                        <div class="h-5 w-20 bg-cream-300/70 rounded-full"></div>
                        <div class="h-5 w-12 bg-cream-300/70 rounded"></div>
                    </div>
                    <div class="h-6 w-3/4 bg-cream-300/80 rounded"></div>
                    <div class="space-y-2">
                        <div class="h-3 w-full bg-cream-300/60 rounded"></div>
                        <div class="h-3 w-5/6 bg-cream-300/60 rounded"></div>
                    </div>
                    <div class="pt-4 border-t border-cream-200 flex justify-between">
                        <div class="h-4 w-24 bg-cream-300/70 rounded"></div>
                        <div class="h-4 w-16 bg-cream-300/70 rounded"></div>
                    </div>
                </div>
                <div class="glass-card rounded-3xl p-6 border border-cream-200 animate-pulse space-y-4">
                    <div class="flex justify-between">
                        <div class="h-5 w-20 bg-cream-300/70 rounded-full"></div>
                        <div class="h-5 w-12 bg-cream-300/70 rounded"></div>
                    </div>
                    <div class="h-6 w-2/3 bg-cream-300/80 rounded"></div>
                    <div class="space-y-2">
                        <div class="h-3 w-full bg-cream-300/60 rounded"></div>
                        <div class="h-3 w-4/6 bg-cream-300/60 rounded"></div>
                    </div>
                    <div class="pt-4 border-t border-cream-200 flex justify-between">
                        <div class="h-4 w-24 bg-cream-300/70 rounded"></div>
                        <div class="h-4 w-16 bg-cream-300/70 rounded"></div>
                    </div>
                </div>
                <div class="glass-card rounded-3xl p-6 border border-cream-200 animate-pulse space-y-4">
                    <div class="flex justify-between">
                        <div class="h-5 w-20 bg-cream-300/70 rounded-full"></div>
                        <div class="h-5 w-12 bg-cream-300/70 rounded"></div>
                    </div>
                    <div class="h-6 w-3/4 bg-cream-300/80 rounded"></div>
                    <div class="space-y-2">
                        <div class="h-3 w-full bg-cream-300/60 rounded"></div>
                        <div class="h-3 w-5/6 bg-cream-300/60 rounded"></div>
                    </div>
                    <div class="pt-4 border-t border-cream-200 flex justify-between">
                        <div class="h-4 w-24 bg-cream-300/70 rounded"></div>
                        <div class="h-4 w-16 bg-cream-300/70 rounded"></div>
                    </div>
                </div>
            </div>

            <!-- Live Repositories Grid (Populated dynamically via GitHub API) -->
            <div id="projects-grid" class="hidden grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8"></div>

            <!-- Graceful Fallback / Empty / Rate-Limit State -->
            <div id="projects-fallback" class="hidden glass-card rounded-3xl p-10 text-center max-w-2xl mx-auto border border-cream-300 shadow-lg space-y-4">
                <div class="w-14 h-14 rounded-2xl bg-amber-accent/15 text-amber-accent flex items-center justify-center text-2xl mx-auto">
                    <i class="fa-brands fa-github"></i>
                </div>
                <h3 id="fallback-title" class="text-xl font-extrabold text-brown-900">Check Out My GitHub Directly</h3>
                <p id="fallback-desc" class="text-sm text-brown-800 leading-relaxed">
                    New public repositories will appear right here automatically as soon as they are pushed to GitHub.
                </p>
                <div class="pt-2">
                    <a href="https://github.com/Taohidul-Islam" target="_blank" class="inline-flex items-center gap-2 px-6 py-3 rounded-xl bg-brown-900 hover:bg-brown-800 text-cream-50 text-xs font-bold shadow-md transition-all">
                        <i class="fa-brands fa-github text-base"></i>
                        <span>Open github.com/Taohidul-Islam</span>
                    </a>
                </div>
            </div>

            <!-- GitHub Banner CTA -->
            <div class="mt-12 text-center">
                <a href="https://github.com/Taohidul-Islam" target="_blank" class="inline-flex items-center space-x-3 px-8 py-4 rounded-2xl bg-brown-900 hover:bg-brown-800 text-cream-50 font-bold text-sm shadow-xl transition-all">
                    <i class="fa-brands fa-github text-xl"></i>
                    <span>Follow @Taohidul-Islam on GitHub</span>
                </a>
            </div>
        </div>
    </section>

    <!-- Contact & Footer Section -->
    <section id="contact" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
                <!-- Info Column -->
                <div class="lg:col-span-5 space-y-6">
                    <span class="text-xs uppercase font-extrabold tracking-widest text-amber-accent px-3 py-1 rounded-full bg-amber-accent/10">Get in Touch</span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-brown-900">Let's Build Something Awesome Together!</h2>
                    <p class="text-brown-800 text-sm leading-relaxed">
                        Whether you want to collaborate on an ESP32 hardware project, discuss national competitions, or talk tech in Mirpur, Dhaka — my inbox is always open.
                    </p>

                    <div class="space-y-4 pt-4">
                        <a href="mailto:islamtaohidul26959@gmail.com" class="flex items-center space-x-4 p-4 rounded-2xl glass-card border border-cream-200 hover:border-amber-accent transition-colors group">
                            <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center font-bold text-lg group-hover:bg-amber-accent group-hover:text-white transition-all">
                                <i class="fa-solid fa-envelope"></i>
                            </div>
                            <div>
                                <span class="block text-xs font-semibold text-brown-700">Email Me</span>
                                <span class="text-sm font-bold text-brown-900">islamtaohidul26959@gmail.com</span>
                            </div>
                        </a>

                        <a href="tel:+8801601794808" class="flex items-center space-x-4 p-4 rounded-2xl glass-card border border-cream-200 hover:border-amber-accent transition-colors group">
                            <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center font-bold text-lg group-hover:bg-amber-accent group-hover:text-white transition-all">
                                <i class="fa-solid fa-phone"></i>
                            </div>
                            <div>
                                <span class="block text-xs font-semibold text-brown-700">Call / WhatsApp</span>
                                <span class="text-sm font-bold text-brown-900">+8801601794808</span>
                            </div>
                        </a>

                        <div class="flex items-center space-x-4 p-4 rounded-2xl glass-card border border-cream-200">
                            <div class="w-12 h-12 rounded-xl bg-amber-accent/10 text-amber-accent flex items-center justify-center font-bold text-lg">
                                <i class="fa-solid fa-location-dot"></i>
                            </div>
                            <div>
                                <span class="block text-xs font-semibold text-brown-700">Location</span>
                                <span class="text-sm font-bold text-brown-900">Mirpur, Dhaka, Bangladesh</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Form Column -->
                <div class="lg:col-span-7">
                    <div class="glass-card p-8 sm:p-10 rounded-3xl shadow-2xl border border-cream-300">
                        <h3 class="text-2xl font-bold text-brown-900 mb-6">Send Me a Message</h3>
                        <form onsubmit="handleContactSubmit(event)" class="space-y-6">
                            <div>
                                <label class="block text-xs font-bold text-brown-800 uppercase tracking-wider mb-2">Your Name</label>
                                <input type="text" id="contact-name" required placeholder="e.g. Sifat Ahmed" class="w-full px-4 py-3.5 rounded-xl bg-white/80 border border-cream-300 focus:outline-none focus:border-amber-accent text-sm text-brown-900 transition-colors">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-brown-800 uppercase tracking-wider mb-2">Your Email</label>
                                <input type="email" id="contact-email" required placeholder="e.g. sifat@example.com" class="w-full px-4 py-3.5 rounded-xl bg-white/80 border border-cream-300 focus:outline-none focus:border-amber-accent text-sm text-brown-900 transition-colors">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-brown-800 uppercase tracking-wider mb-2">Message</label>
                                <textarea id="contact-msg" rows="4" required placeholder="Let's build a project together..." class="w-full px-4 py-3.5 rounded-xl bg-white/80 border border-cream-300 focus:outline-none focus:border-amber-accent text-sm text-brown-900 transition-colors"></textarea>
                            </div>
                            <button type="submit" class="w-full py-4 rounded-xl bg-brown-900 hover:bg-brown-800 text-cream-50 font-bold text-sm shadow-xl hover:shadow-2xl transition-all flex items-center justify-center gap-2">
                                <span>Send Message</span>
                                <i class="fa-solid fa-paper-plane text-xs"></i>
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-brown-900 text-cream-50 py-12 border-t border-brown-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-6 text-center md:text-left">
            <div>
                <a href="#hero" class="text-lg font-extrabold tracking-tight text-cream-50">Taohidul <span class="text-amber-accent">Islam</span></a>
                <p class="text-xs text-cream-300 mt-1">16yo Electronics Developer & 11th Grader @ SOS Hermann Gmeiner College Dhaka.</p>
            </div>

            <div class="flex items-center space-x-6 text-xl">
                <a href="https://github.com/Taohidul-Islam" target="_blank" class="text-cream-300 hover:text-amber-accent transition-colors" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="mailto:islamtaohidul26959@gmail.com" class="text-cream-300 hover:text-amber-accent transition-colors" title="Email"><i class="fa-solid fa-envelope"></i></a>
                <a href="tel:+8801601794808" class="text-cream-300 hover:text-amber-accent transition-colors" title="Phone"><i class="fa-solid fa-phone"></i></a>
            </div>

            <div class="text-xs text-cream-300">
                &copy; 2026 Taohidul Islam. Built with passion in Mirpur, Dhaka.
            </div>
        </div>
    </footer>

    <!-- JavaScript for Interactivity, Terminal, Toast & Sound -->
    <script>
        // Mobile Menu Toggle
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            const icon = document.getElementById('menu-icon');
            menu.classList.toggle('hidden');
            if(menu.classList.contains('hidden')) {
                icon.className = "fa-solid fa-bars text-lg";
            } else {
                icon.className = "fa-solid fa-xmark text-lg";
            }
        }

        // Toast Notification System (Replaces alert)
        function showToast(title, message, isSuccess = true) {
            const toast = document.getElementById('toast');
            const titleEl = document.getElementById('toast-title');
            const msgEl = document.getElementById('toast-msg');
            const iconEl = document.getElementById('toast-icon');

            titleEl.textContent = title;
            msgEl.textContent = message;
            iconEl.className = isSuccess ? "fa-solid fa-circle-check text-amber-accent text-xl" : "fa-solid fa-triangle-exclamation text-yellow-400 text-xl";

            toast.classList.remove('translate-y-32', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-32', 'opacity-0');
            }, 4000);
        }

        // Contact Form Handler
        function handleContactSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('contact-name').value;
            showToast("Message Sent!", `Thanks ${name}! I'll get back to you soon.`);
            e.target.reset();
        }

        // Ambient Sound / Lo-fi Simulation toggle
        let soundActive = false;
        let audioCtx = null;
        let oscillator = null;

        function toggleSound() {
            soundActive = !soundActive;
            const btn = document.getElementById('sound-icon');
            if(soundActive) {
                btn.className = "fa-solid fa-volume-high text-amber-accent animate-pulse";
                showToast("Ambient Lo-Fi Vibe", "Ambient relaxing sound synthesis active.");
                try {
                    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                    oscillator = audioCtx.createOscillator();
                    const gainNode = audioCtx.createGain();
                    oscillator.type = 'sine';
                    oscillator.frequency.setValueAtTime(174.61, audioCtx.currentTime); // F3 note for cozy warm vibe
                    gainNode.gain.setValueAtTime(0.03, audioCtx.currentTime);
                    oscillator.connect(gainNode);
                    gainNode.connect(audioCtx.destination);
                    oscillator.start();
                } catch(e) {
                    console.log("Audio Context not supported or blocked");
                }
            } else {
                btn.className = "fa-solid fa-volume-xmark";
                showToast("Sound Off", "Ambient sound deactivated.");
                if(oscillator) {
                    oscillator.stop();
                    oscillator.disconnect();
                }
            }
        }

        function escapeHtml(text) {
            if (!text) return '';
            return String(text).replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
        }

        // =========================================================================
        // LIVE GITHUB REPOSITORY LOADER & CUSTOM HARDWARE PINNING CONFIGURATION
        // =========================================================================
        const GITHUB_USERNAME = 'Taohidul-Islam';

        // 1. Optional: Add exact repo names here (e.g. ['esp32-rover', 'kicad-board'])
        // to always float your favorite GitHub repos to the very top!
        const PINNED_REPOS = [];

        // 2. Optional: Add any non-GitHub hardware/PCB/CAD builds here later if you want
        // Example format:
        // {
        //     name: "Custom ESP32 Flight Controller",
        //     description: "4-layer KiCad PCB schematic and layout with onboard IMU.",
        //     language: "KiCad",
        //     html_url: "https://github.com/Taohidul-Islam",
        //     homepage: "",
        //     stargazers_count: 0,
        //     forks_count: 0,
        //     updated_at: "2026-11-18T00:00:00Z",
        //     isCustomHardware: true
        // }
        const CUSTOM_PROJECTS = [];

        let allFetchedRepos = [];
        let activeLanguageFilter = 'ALL';

        function formatRelativeDate(isoString) {
            if (!isoString) return 'Recently updated';
            const date = new Date(isoString);
            return date.toLocaleDateString('en-US', { month: 'short', day: 'numeric', year: 'numeric' });
        }

        function renderFilterButtons(repos) {
            const filterContainer = document.getElementById('repo-filters');
            const languages = new Set();
            repos.forEach(repo => {
                if (repo.language) languages.add(repo.language);
            });

            let buttonsHtml = `
                <button onclick="filterRepos('ALL')" data-lang="ALL" class="filter-btn px-4 py-2 rounded-xl ${activeLanguageFilter === 'ALL' ? 'bg-brown-900 text-cream-50' : 'bg-cream-200/70 text-brown-900 hover:bg-cream-300'} text-xs font-bold shadow-sm transition-all">
                    All (${repos.length})
                </button>
            `;

            languages.forEach(lang => {
                const count = repos.filter(r => r.language === lang).length;
                const isActive = activeLanguageFilter === lang;
                buttonsHtml += `
                    <button onclick="filterRepos('${escapeHtml(lang)}')" data-lang="${escapeHtml(lang)}" class="filter-btn px-4 py-2 rounded-xl ${isActive ? 'bg-brown-900 text-cream-50' : 'bg-cream-200/70 text-brown-900 hover:bg-cream-300'} text-xs font-bold shadow-sm transition-all">
                        ${escapeHtml(lang)} (${count})
                    </button>
                `;
            });

            filterContainer.innerHTML = buttonsHtml;
        }

        function filterRepos(lang) {
            activeLanguageFilter = lang;
            renderFilterButtons(allFetchedRepos);
            renderRepoCards();
        }

        function renderRepoCards() {
            const gridEl = document.getElementById('projects-grid');
            const fallbackEl = document.getElementById('projects-fallback');

            const filtered = activeLanguageFilter === 'ALL'
                ? allFetchedRepos
                : allFetchedRepos.filter(r => r.language === activeLanguageFilter);

            if (filtered.length === 0) {
                gridEl.classList.add('hidden');
                fallbackEl.classList.remove('hidden');
                return;
            }

            fallbackEl.classList.add('hidden');
            gridEl.classList.remove('hidden');

            gridEl.innerHTML = filtered.map(repo => {
                const isPinned = PINNED_REPOS.includes(repo.name) || repo.isCustomHardware;
                const badgeText = repo.language || 'Hardware / Repo';
                const description = repo.description
                    ? escapeHtml(repo.description)
                    : 'Public repository on GitHub — click below to inspect source code, schematics, or documentation.';
                const hasLiveDemo = repo.homepage && repo.homepage.trim().startsWith('http');

                return `
                    <div class="glass-card rounded-3xl overflow-hidden shadow-lg border border-cream-200 flex flex-col justify-between group hover:shadow-2xl transition-all">
                        <div class="p-6 space-y-4">
                            <div class="flex items-center justify-between gap-2">
                                <div class="flex items-center gap-2 flex-wrap">
                                    <span class="px-3 py-1 rounded-full bg-amber-accent/15 text-amber-accent text-xs font-bold">
                                        ${escapeHtml(badgeText)}
                                    </span>
                                    ${isPinned ? `<span class="px-2.5 py-0.5 rounded-full bg-brown-900 text-cream-50 text-[10px] font-bold"><i class="fa-solid fa-thumbtack mr-1"></i>Pinned</span>` : ''}
                                </div>
                                <div class="flex items-center space-x-3 text-xs font-semibold text-brown-700 shrink-0">
                                    <span title="Stars"><i class="fa-regular fa-star text-amber-accent"></i> ${repo.stargazers_count || 0}</span>
                                    <span title="Forks"><i class="fa-solid fa-code-fork text-amber-accent"></i> ${repo.forks_count || 0}</span>
                                </div>
                            </div>

                            <h3 class="text-xl font-bold text-brown-900 group-hover:text-amber-accent transition-colors break-words">
                                ${escapeHtml(repo.name)}
                            </h3>

                            <p class="text-sm text-brown-800 leading-relaxed line-clamp-3">
                                ${description}
                            </p>

                            <div class="pt-1 text-[11px] text-brown-700 font-mono">
                                <i class="fa-regular fa-clock mr-1"></i> Updated ${formatRelativeDate(repo.updated_at)}
                            </div>
                        </div>

                        <div class="px-6 py-4 bg-cream-200/50 border-t border-cream-200 flex items-center justify-between gap-3">
                            <a href="${escapeHtml(repo.html_url)}" target="_blank" rel="noopener noreferrer" class="text-xs font-bold text-brown-900 hover:text-amber-accent flex items-center gap-1.5 transition-colors">
                                <i class="fa-brands fa-github text-sm"></i>
                                <span>View on GitHub</span>
                            </a>
                            ${hasLiveDemo ? `
                                <a href="${escapeHtml(repo.homepage)}" target="_blank" rel="noopener noreferrer" class="px-3 py-1.5 rounded-lg bg-amber-accent text-white hover:bg-brown-900 text-[11px] font-bold flex items-center gap-1 transition-colors">
                                    <span>Live Demo</span>
                                    <i class="fa-solid fa-arrow-up-right-from-square text-[10px]"></i>
                                </a>
                            ` : `
                                <a href="${escapeHtml(repo.html_url)}" target="_blank" rel="noopener noreferrer" class="text-brown-700 hover:text-amber-accent transition-colors" title="Open Repository">
                                    <i class="fa-solid fa-arrow-up-right-from-square text-xs"></i>
                                </a>
                            `}
                        </div>
                    </div>
                `;
            }).join('');
        }

        async function fetchGitHubRepos(isManualRefresh = false) {
            const loadingEl = document.getElementById('projects-loading');
            const gridEl = document.getElementById('projects-grid');
            const fallbackEl = document.getElementById('projects-fallback');
            const fallbackTitle = document.getElementById('fallback-title');
            const fallbackDesc = document.getElementById('fallback-desc');
            const refreshIcon = document.getElementById('refresh-icon');

            loadingEl.classList.remove('hidden');
            gridEl.classList.add('hidden');
            fallbackEl.classList.add('hidden');
            if (refreshIcon) refreshIcon.classList.add('fa-spin');

            try {
                const response = await fetch(`https://api.github.com/users/${GITHUB_USERNAME}/repos?sort=updated&per_page=100`, {
                    headers: { 'Accept': 'application/vnd.github.v3+json' }
                });

                if (!response.ok) {
                    throw new Error(`GitHub API responded with status ${response.status}`);
                }

                const repos = await response.json();

                // Filter out forked repos if desired, or keep all public repos sorted by pinned status then updated date
                const combinedRepos = [...CUSTOM_PROJECTS, ...repos];

                combinedRepos.sort((a, b) => {
                    const aPinned = PINNED_REPOS.includes(a.name) || a.isCustomHardware ? 1 : 0;
                    const bPinned = PINNED_REPOS.includes(b.name) || b.isCustomHardware ? 1 : 0;
                    if (bPinned !== aPinned) return bPinned - aPinned;
                    return new Date(b.updated_at) - new Date(a.updated_at);
                });

                allFetchedRepos = combinedRepos;
                loadingEl.classList.add('hidden');

                if (allFetchedRepos.length === 0) {
                    fallbackTitle.textContent = "No Public Repositories Found Yet";
                    fallbackDesc.textContent = "Whenever you push a public repository to github.com/Taohidul-Islam, it will automatically show up right here!";
                    fallbackEl.classList.remove('hidden');
                } else {
                    renderFilterButtons(allFetchedRepos);
                    renderRepoCards();
                    if (isManualRefresh) {
                        showToast("GitHub Synced!", `Loaded ${allFetchedRepos.length} public repositor${allFetchedRepos.length === 1 ? 'y' : 'ies'}.`);
                    }
                }
            } catch (error) {
                console.error("GitHub fetch error:", error);
                loadingEl.classList.add('hidden');

                if (CUSTOM_PROJECTS.length > 0) {
                    allFetchedRepos = [...CUSTOM_PROJECTS];
                    renderFilterButtons(allFetchedRepos);
                    renderRepoCards();
                } else {
                    fallbackTitle.textContent = "Unable to Load GitHub Feed Right Now";
                    fallbackDesc.textContent = "GitHub's public API may be temporarily rate-limited or unreachable. You can browse all of Taohidul's repositories directly on GitHub:";
                    fallbackEl.classList.remove('hidden');
                }

                if (isManualRefresh) {
                    showToast("GitHub Sync Notice", "Could not reach GitHub API right now. Try again shortly.", false);
                }
            } finally {
                if (refreshIcon) refreshIcon.classList.remove('fa-spin');
            }
        }

        // Automatically fetch Taohidul's real repositories when the page loads
        document.addEventListener('DOMContentLoaded', () => {
            fetchGitHubRepos(false);
        });
    </script>
</body>
</html>
