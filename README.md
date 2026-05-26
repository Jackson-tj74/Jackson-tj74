<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Jackson Tuyikunde — Full Stack Developer</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://code.iconify.design/3/3.1.0/iconify.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet" />
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            cream: '#FDFCF8',
            savor: '#F3EFE0',
            stone: {
              50: '#fafaf9', 100: '#f5f5f4', 200: '#e7e5e4', 300: '#d6d3d1',
              400: '#a8a29e', 500: '#78716c', 600: '#57534e', 700: '#44403c',
              800: '#292524', 900: '#1c1917', 950: '#0c0a09'
            }
          },
          borderRadius: { '4xl': '2rem' },
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            serif: ['Playfair Display', 'serif'],
          }
        }
      }
    }
  </script>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Inter', sans-serif; background: #0c0a09; color: #f5f5f4; overflow-x: hidden; }

    /* Scrollbar */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #1c1917; }
    ::-webkit-scrollbar-thumb { background: #78716c; border-radius: 3px; }

    /* Animations */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeInLeft {
      from { opacity: 0; transform: translateX(-30px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes fadeInRight {
      from { opacity: 0; transform: translateX(30px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes scaleIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-15px); }
    }
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 20px rgba(243,239,224,0.1); }
      50% { box-shadow: 0 0 40px rgba(243,239,224,0.2); }
    }
    @keyframes gradient-shift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }
    @keyframes blink {
      0%, 100% { border-color: #F3EFE0; }
      50% { border-color: transparent; }
    }
    @keyframes spin-slow {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    @keyframes progress-fill {
      from { width: 0%; }
    }
    @keyframes orbit {
      from { transform: rotate(0deg) translateX(120px) rotate(0deg); }
      to { transform: rotate(360deg) translateX(120px) rotate(-360deg); }
    }

    .animate-fade-in-up { animation: fadeInUp 1s cubic-bezier(0.16,1,0.3,1) forwards; }
    .animate-fade-in-left { animation: fadeInLeft 1s cubic-bezier(0.16,1,0.3,1) forwards; }
    .animate-fade-in-right { animation: fadeInRight 1s cubic-bezier(0.16,1,0.3,1) forwards; }
    .animate-scale-in { animation: scaleIn 0.8s cubic-bezier(0.16,1,0.3,1) forwards; }
    .animate-float { animation: float 6s ease-in-out infinite; }
    .animate-pulse-glow { animation: pulse-glow 3s ease-in-out infinite; }
    .animate-spin-slow { animation: spin-slow 20s linear infinite; }

    .reveal {
      opacity: 0; filter: blur(8px); transform: translateY(24px);
      transition: all 1.2s cubic-bezier(0.16,1,0.3,1);
    }
    .reveal.active { opacity: 1; filter: blur(0); transform: translateY(0); }
    .delay-100 { transition-delay: 100ms; }
    .delay-200 { transition-delay: 200ms; }
    .delay-300 { transition-delay: 300ms; }
    .delay-400 { transition-delay: 400ms; }
    .delay-500 { transition-delay: 500ms; }

    /* Typing effect */
    .typing-container { display: inline-flex; align-items: center; }
    .typing-text {
      overflow: hidden; white-space: nowrap;
      border-right: 3px solid #F3EFE0;
      animation: typing 3s steps(40,end) forwards, blink 0.75s step-end infinite;
      width: 0;
    }

    /* Gradient text */
    .gradient-text {
      background: linear-gradient(135deg, #F3EFE0, #d6d3d1, #F3EFE0);
      background-size: 200% 200%;
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: gradient-shift 4s ease infinite;
    }

    /* Glass card */
    .glass-card {
      background: rgba(28,25,23,0.6);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(243,239,224,0.1);
      transition: all 500ms cubic-bezier(0.16,1,0.3,1);
    }
    .glass-card:hover {
      background: rgba(28,25,23,0.8);
      border-color: rgba(243,239,224,0.25);
      transform: translateY(-4px);
      box-shadow: 0 25px 50px -12px rgba(0,0,0,0.4);
    }

    /* Skill bar */
    .skill-bar { background: rgba(243,239,224,0.1); border-radius: 999px; overflow: hidden; height: 8px; }
    .skill-fill {
      height: 100%; border-radius: 999px;
      background: linear-gradient(90deg, #F3EFE0, #d6d3d1);
      animation: progress-fill 1.5s cubic-bezier(0.16,1,0.3,1) forwards;
    }

    /* Orbit animation for hero decoration */
    .orbit-dot {
      animation: orbit 8s linear infinite;
    }
    .orbit-dot-2 {
      animation: orbit 12s linear infinite reverse;
    }
    .orbit-dot-3 {
      animation: orbit 16s linear infinite;
      animation-delay: -4s;
    }

    /* Grid background pattern */
    .grid-pattern {
      background-image:
        linear-gradient(rgba(243,239,224,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(243,239,224,0.03) 1px, transparent 1px);
      background-size: 60px 60px;
    }

    /* Noise texture overlay */
    .noise-overlay::before {
      content: ''; position: absolute; inset: 0; z-index: 1; pointer-events: none;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      opacity: 0.4;
    }

    /* Section divider */
    .section-divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(243,239,224,0.2), transparent);
    }

    /* Tech icon hover */
    .tech-icon {
      transition: all 300ms cubic-bezier(0.16,1,0.3,1);
    }
    .tech-icon:hover {
      transform: scale(1.15) translateY(-4px);
      box-shadow: 0 12px 24px rgba(0,0,0,0.3);
    }

    /* Link hover underline */
    .hover-underline { position: relative; }
    .hover-underline::after {
      content: ''; position: absolute; bottom: -2px; left: 0;
      width: 0; height: 1px; background: #F3EFE0;
      transition: width 300ms ease;
    }
    .hover-underline:hover::after { width: 100%; }

    /* Avatar ring */
    .avatar-ring {
      background: conic-gradient(from 0deg, #F3EFE0, #78716c, #F3EFE0);
      animation: spin-slow 8s linear infinite;
    }

    /* Stats card counter */
    .stat-number {
      font-variant-numeric: tabular-nums;
    }

    /* Toast notification */
    .toast {
      position: fixed; bottom: 2rem; left: 50%; transform: translateX(-50%) translateY(100px);
      background: rgba(28,25,23,0.95); backdrop-filter: blur(12px);
      border: 1px solid rgba(243,239,224,0.2); border-radius: 1rem;
      padding: 1rem 1.5rem; z-index: 100;
      transition: transform 500ms cubic-bezier(0.16,1,0.3,1);
      pointer-events: none;
    }
    .toast.show { transform: translateX(-50%) translateY(0); }
  </style>
</head>
<body class="grid-pattern">

  <!-- Toast Notification -->
  <div id="toast" class="toast flex items-center gap-3">
    <span class="iconify text-savor" data-icon="mdi:check-circle" data-width="20"></span>
    <span id="toast-msg" class="text-sm text-stone-200">Copied to clipboard!</span>
  </div>

  <!-- ===== NAVIGATION ===== -->
  <nav class="fixed top-0 left-0 right-0 z-50 h-20 flex items-center px-6 backdrop-blur-xl bg-stone-950/70 border-b border-stone-800/50">
    <div class="max-w-6xl mx-auto w-full flex items-center justify-between">
      <a href="#hero" class="flex items-center gap-2">
        <div class="w-8 h-8 rounded-lg bg-savor flex items-center justify-center">
          <span class="text-stone-900 font-bold text-sm">JT</span>
        </div>
        <span class="font-semibold text-cream tracking-tight">Jackson.dev</span>
      </a>
      <div class="hidden md:flex items-center gap-8">
        <a href="#about" class="text-sm text-stone-400 hover:text-cream transition-colors hover-underline">About</a>
        <a href="#skills" class="text-sm text-stone-400 hover:text-cream transition-colors hover-underline">Skills</a>
        <a href="#projects" class="text-sm text-stone-400 hover:text-cream transition-colors hover-underline">Projects</a>
        <a href="#certificates" class="text-sm text-stone-400 hover:text-cream transition-colors hover-underline">Certificates</a>
        <a href="#contact" class="text-sm font-bold uppercase tracking-wide bg-cream text-stone-900 px-5 py-2.5 rounded-full hover:scale-105 transition-transform duration-150">Contact</a>
      </div>
      <!-- Mobile menu button -->
      <button id="mobile-menu-btn" class="md:hidden text-cream p-2" aria-label="Menu">
        <span class="iconify" data-icon="mdi:menu" data-width="24"></span>
      </button>
    </div>
  </nav>

  <!-- Mobile menu -->
  <div id="mobile-menu" class="fixed inset-0 z-40 bg-stone-950/95 backdrop-blur-xl flex flex-col items-center justify-center gap-8 hidden">
    <a href="#about" class="text-2xl text-cream font-light mobile-link">About</a>
    <a href="#skills" class="text-2xl text-cream font-light mobile-link">Skills</a>
    <a href="#projects" class="text-2xl text-cream font-light mobile-link">Projects</a>
    <a href="#certificates" class="text-2xl text-cream font-light mobile-link">Certificates</a>
    <a href="#contact" class="text-2xl text-cream font-light mobile-link">Contact</a>
    <button id="mobile-menu-close" class="absolute top-6 right-6 text-cream p-2">
      <span class="iconify" data-icon="mdi:close" data-width="28"></span>
    </button>
  </div>

  <!-- ===== HERO SECTION ===== -->
  <section id="hero" class="relative min-h-screen flex items-center justify-center px-6 noise-overlay overflow-hidden">
    <!-- Background decoration -->
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-savor/5 rounded-full blur-3xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-stone-700/20 rounded-full blur-3xl"></div>
    </div>

    <!-- Orbiting dots -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-0 h-0 pointer-events-none">
      <div class="orbit-dot absolute w-2 h-2 bg-savor/30 rounded-full"></div>
      <div class="orbit-dot-2 absolute w-1.5 h-1.5 bg-stone-500/40 rounded-full"></div>
      <div class="orbit-dot-3 absolute w-1 h-1 bg-savor/20 rounded-full"></div>
    </div>

    <div class="relative z-10 text-center max-w-4xl mx-auto">
      <!-- Avatar -->
      <div class="animate-scale-in mb-8 flex justify-center" style="animation-delay: 0.2s; opacity: 0;">
        <div class="avatar-ring p-[3px] rounded-full">
          <div class="w-28 h-28 md:w-36 md:h-36 rounded-full bg-stone-900 flex items-center justify-center overflow-hidden border-4 border-stone-950">
            <img src="https://picsum.photos/seed/jackson-dev-rw/300/300.jpg" alt="Jackson Tuyikunde" class="w-full h-full object-cover" />
          </div>
        </div>
      </div>

      <!-- Greeting -->
      <div class="animate-fade-in-up mb-4" style="animation-delay: 0.4s; opacity: 0;">
        <span class="inline-flex items-center gap-2 text-xs font-bold uppercase tracking-[0.3em] text-stone-500 bg-stone-900/60 px-4 py-2 rounded-full border border-stone-800/50">
          <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></span>
          Available for work
        </span>
      </div>

      <!-- Name -->
      <h1 class="animate-fade-in-up font-serif text-5xl md:text-7xl lg:text-8xl font-medium tracking-tighter leading-[0.85] mb-6" style="animation-delay: 0.6s; opacity: 0;">
        <span class="text-cream">Jackson</span><br/>
        <span class="gradient-text">Tuyikunde</span>
      </h1>

      <!-- Typing subtitle -->
      <div class="animate-fade-in-up mb-8 h-8 flex justify-center" style="animation-delay: 0.8s; opacity: 0;">
        <div class="typing-container">
          <span class="typing-text text-lg md:text-xl font-light text-stone-400">Full Stack Developer · Rwanda 🇷🇼</span>
        </div>
      </div>

      <!-- Description -->
      <p class="animate-fade-in-up text-stone-500 text-lg md:text-xl font-light leading-relaxed max-w-2xl mx-auto mb-10" style="animation-delay: 1s; opacity: 0;">
        Crafting modern web experiences with React, Node.js & clean design. Turning ideas into elegant, performant digital products.
      </p>

      <!-- CTA Buttons -->
      <div class="animate-fade-in-up flex flex-col sm:flex-row items-center justify-center gap-4" style="animation-delay: 1.2s; opacity: 0;">
        <a href="#projects" class="group flex items-center gap-2 bg-cream text-stone-900 font-bold text-sm uppercase tracking-wide px-8 py-4 rounded-full hover:scale-105 transition-transform duration-150">
          View My Work
          <span class="iconify group-hover:translate-x-1 transition-transform" data-icon="mdi:arrow-right" data-width="18"></span>
        </a>
        <a href="#contact" class="flex items-center gap-2 border border-stone-700 text-cream font-bold text-sm uppercase tracking-wide px-8 py-4 rounded-full hover:bg-stone-800/50 hover:border-stone-600 transition-all duration-300">
          <span class="iconify" data-icon="mdi:email-outline" data-width="18"></span>
          Get in Touch
        </a>
      </div>

      <!-- Social links -->
      <div class="animate-fade-in-up flex items-center justify-center gap-5 mt-10" style="animation-delay: 1.4s; opacity: 0;">
        <a href="https://github.com/Jackson-tj74" target="_blank" rel="noopener" class="w-11 h-11 rounded-full border border-stone-700 flex items-center justify-center text-stone-400 hover:text-cream hover:border-savor/50 hover:bg-savor/5 transition-all duration-300" aria-label="GitHub">
          <span class="iconify" data-icon="mdi:github" data-width="20"></span>
        </a>
        <a href="https://tjdevsphere.netlify.app" target="_blank" rel="noopener" class="w-11 h-11 rounded-full border border-stone-700 flex items-center justify-center text-stone-400 hover:text-cream hover:border-savor/50 hover:bg-savor/5 transition-all duration-300" aria-label="Portfolio">
          <span class="iconify" data-icon="mdi:web" data-width="20"></span>
        </a>
        <a href="mailto:tuyikundejackson74@gmail.com" class="w-11 h-11 rounded-full border border-stone-700 flex items-center justify-center text-stone-400 hover:text-cream hover:border-savor/50 hover:bg-savor/5 transition-all duration-300" aria-label="Email">
          <span class="iconify" data-icon="mdi:email" data-width="20"></span>
        </a>
        <a href="#" class="w-11 h-11 rounded-full border border-stone-700 flex items-center justify-center text-stone-400 hover:text-cream hover:border-savor/50 hover:bg-savor/5 transition-all duration-300" aria-label="LinkedIn">
          <span class="iconify" data-icon="mdi:linkedin" data-width="20"></span>
        </a>
        <a href="#" class="w-11 h-11 rounded-full border border-stone-700 flex items-center justify-center text-stone-400 hover:text-cream hover:border-savor/50 hover:bg-savor/5 transition-all duration-300" aria-label="Twitter/X">
          <span class="iconify" data-icon="mdi:twitter" data-width="20"></span>
        </a>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-fade-in-up" style="animation-delay: 2s; opacity: 0;">
      <div class="w-6 h-10 rounded-full border-2 border-stone-700 flex justify-center pt-2">
        <div class="w-1 h-2 bg-savor/60 rounded-full animate-bounce"></div>
      </div>
    </div>
  </section>

  <!-- ===== GITHUB STATS BAR ===== -->
  <section class="relative z-10 py-8 px-6 border-y border-stone-800/50 bg-stone-950/80 backdrop-blur-md">
    <div class="max-w-5xl mx-auto grid grid-cols-2 md:grid-cols-4 gap-6 md:gap-8">
      <div class="text-center reveal">
        <div class="stat-number text-3xl md:text-4xl font-serif text-cream font-medium" data-target="15">0</div>
        <div class="text-xs uppercase tracking-[0.2em] text-stone-500 mt-1">Projects</div>
      </div>
      <div class="text-center reveal delay-100">
        <div class="stat-number text-3xl md:text-4xl font-serif text-cream font-medium" data-target="10">0</div>
        <div class="text-xs uppercase tracking-[0.2em] text-stone-500 mt-1">Technologies</div>
      </div>
      <div class="text-center reveal delay-200">
        <div class="stat-number text-3xl md:text-4xl font-serif text-cream font-medium" data-target="5">0</div>
        <div class="text-xs uppercase tracking-[0.2em] text-stone-500 mt-1">Certificates</div>
      </div>
      <div class="text-center reveal delay-300">
        <div class="stat-number text-3xl md:text-4xl font-serif text-cream font-medium" data-target="2">0</div>
        <div class="text-xs uppercase tracking-[0.2em] text-stone-500 mt-1">Languages</div>
      </div>
    </div>
  </section>

  <!-- ===== ABOUT SECTION ===== -->
  <section id="about" class="relative py-32 px-6 noise-overlay">
    <div class="max-w-6xl mx-auto">
      <div class="flex flex-col lg:flex-row gap-16 lg:gap-20 items-center">
        <!-- Image -->
        <div class="lg:w-2/5 reveal">
          <div class="relative">
            <div class="absolute -inset-4 bg-gradient-to-br from-savor/10 to-stone-800/20 rounded-3xl blur-2xl"></div>
            <div class="relative rounded-2xl overflow-hidden aspect-[4/5] animate-pulse-glow">
              <img src="https://picsum.photos/seed/dev-workspace-rwanda/600/750.jpg" alt="Working" class="w-full h-full object-cover" />
              <div class="absolute inset-0 bg-gradient-to-t from-stone-950/60 via-transparent to-transparent"></div>
              <div class="absolute bottom-6 left-6 right-6">
                <div class="glass-card rounded-xl px-4 py-3 flex items-center gap-3">
                  <div class="w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
                  <span class="text-sm text-stone-300">Based in Rwanda 🇷🇼</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Content -->
        <div class="lg:w-3/5">
          <div class="reveal">
            <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">About Me</span>
            <h2 class="font-serif text-4xl md:text-5xl font-medium tracking-tighter leading-[0.9] text-cream mb-8">
              Building the web,<br/><em class="text-stone-400">one pixel at a time</em>
            </h2>
          </div>
          <div class="space-y-5 reveal delay-100">
            <p class="text-lg text-stone-400 font-light leading-relaxed">
              I'm <strong class="text-cream font-medium">Jackson Tuyikunde</strong>, a passionate Full Stack Developer from <strong class="text-cream font-medium">Rwanda</strong>. I specialize in building modern, responsive web applications using the MERN stack and modern frontend tools.
            </p>
            <p class="text-lg text-stone-400 font-light leading-relaxed">
              My journey began at <strong class="text-cream font-medium">Alight Coding School</strong>, where I earned my Full-Stack Development certificate. Since then, I've been building real-world solutions — from smart management systems to community service platforms.
            </p>
            <p class="text-lg text-stone-400 font-light leading-relaxed">
              When I'm not coding, I'm exploring new design trends in Figma, contributing to open-source projects, or learning new technologies to stay ahead of the curve.
            </p>
          </div>

          <!-- Quick info grid -->
          <div class="grid grid-cols-2 gap-4 mt-10 reveal delay-200">
            <div class="glass-card rounded-xl p-4">
              <span class="iconify text-savor/60 mb-2" data-icon="mdi:map-marker-outline" data-width="20"></span>
              <div class="text-xs text-stone-500 uppercase tracking-wider">Location</div>
              <div class="text-sm text-cream font-medium mt-1">Rwanda</div>
            </div>
            <div class="glass-card rounded-xl p-4">
              <span class="iconify text-savor/60 mb-2" data-icon="mdi:school-outline" data-width="20"></span>
              <div class="text-xs text-stone-500 uppercase tracking-wider">Education</div>
              <div class="text-sm text-cream font-medium mt-1">Alight Coding School</div>
            </div>
            <div class="glass-card rounded-xl p-4">
              <span class="iconify text-savor/60 mb-2" data-icon="mdi:briefcase-outline" data-width="20"></span>
              <div class="text-xs text-stone-500 uppercase tracking-wider">Focus</div>
              <div class="text-sm text-cream font-medium mt-1">Full Stack Dev</div>
            </div>
            <div class="glass-card rounded-xl p-4">
              <span class="iconify text-savor/60 mb-2" data-icon="mdi:translate" data-width="20"></span>
              <div class="text-xs text-stone-500 uppercase tracking-wider">Languages</div>
              <div class="text-sm text-cream font-medium mt-1">Kinyarwanda, English</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== SKILLS SECTION ===== -->
  <section id="skills" class="relative py-32 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-20 reveal">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">Tech Stack</span>
        <h2 class="font-serif text-4xl md:text-5xl font-medium tracking-tighter text-cream">
          Skills & <em class="text-stone-400">Technologies</em>
        </h2>
      </div>

      <!-- Skill Categories -->
      <div class="grid md:grid-cols-3 gap-6 mb-16">
        <!-- Frontend -->
        <div class="glass-card rounded-3xl p-8 reveal delay-100">
          <div class="w-12 h-12 rounded-2xl bg-savor/10 flex items-center justify-center mb-6">
            <span class="iconify text-savor" data-icon="mdi:palette-outline" data-width="24"></span>
          </div>
          <h3 class="font-serif text-xl font-medium text-cream mb-2">Frontend</h3>
          <p class="text-sm text-stone-500 mb-6">Building beautiful, responsive interfaces</p>
          <div class="space-y-4">
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">React.js</span><span class="text-stone-500">90%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 90%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">TypeScript</span><span class="text-stone-500">75%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 75%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Tailwind CSS</span><span class="text-stone-500">95%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 95%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">JavaScript</span><span class="text-stone-500">92%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 92%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">React Native</span><span class="text-stone-500">70%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 70%;"></div></div>
            </div>
          </div>
        </div>

        <!-- Backend -->
        <div class="glass-card rounded-3xl p-8 reveal delay-200">
          <div class="w-12 h-12 rounded-2xl bg-savor/10 flex items-center justify-center mb-6">
            <span class="iconify text-savor" data-icon="mdi:server-outline" data-width="24"></span>
          </div>
          <h3 class="font-serif text-xl font-medium text-cream mb-2">Backend</h3>
          <p class="text-sm text-stone-500 mb-6">Robust APIs and server-side logic</p>
          <div class="space-y-4">
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Node.js</span><span class="text-stone-500">85%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 85%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">MongoDB</span><span class="text-stone-500">80%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 80%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">REST APIs</span><span class="text-stone-500">88%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 88%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Authentication</span><span class="text-stone-500">78%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 78%;"></div></div>
            </div>
          </div>
        </div>

        <!-- Tools & Design -->
        <div class="glass-card rounded-3xl p-8 reveal delay-300">
          <div class="w-12 h-12 rounded-2xl bg-savor/10 flex items-center justify-center mb-6">
            <span class="iconify text-savor" data-icon="mdi:tools" data-width="24"></span>
          </div>
          <h3 class="font-serif text-xl font-medium text-cream mb-2">Tools & Design</h3>
          <p class="text-sm text-stone-500 mb-6">Streamlined workflow & pixel-perfect design</p>
          <div class="space-y-4">
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Figma</span><span class="text-stone-500">88%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 88%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Git & GitHub</span><span class="text-stone-500">90%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 90%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">VS Code</span><span class="text-stone-500">95%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 95%;"></div></div>
            </div>
            <div>
              <div class="flex justify-between text-sm mb-1.5"><span class="text-stone-300">Vercel / Netlify</span><span class="text-stone-500">92%</span></div>
              <div class="skill-bar"><div class="skill-fill" style="width: 92%;"></div></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Tech icons row -->
      <div class="reveal delay-200">
        <div class="flex flex-wrap items-center justify-center gap-4 md:gap-6">
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="React.js">
            <span class="iconify text-[#61DAFB]" data-icon="logos:react" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="JavaScript">
            <span class="iconify text-[#F7DF1E]" data-icon="logos:javascript" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="TypeScript">
            <span class="iconify text-[#3178C6]" data-icon="logos:typescript-icon" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="Node.js">
            <span class="iconify text-[#339933]" data-icon="logos:nodejs-icon" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="MongoDB">
            <span class="iconify text-[#47A248]" data-icon="logos:mongodb-icon" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="Tailwind CSS">
            <span class="iconify text-[#06B6D4]" data-icon="logos:tailwindcss-icon" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="Figma">
            <span class="iconify text-[#F24E1E]" data-icon="logos:figma" data-width="28"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="Git">
            <span class="iconify text-[#F05032]" data-icon="logos:git-icon" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="React Native">
            <span class="iconify text-[#61DAFB]" data-icon="logos:react" data-width="32"></span>
          </div>
          <div class="tech-icon w-16 h-16 rounded-2xl bg-stone-900/80 border border-stone-800/50 flex items-center justify-center cursor-default" title="VS Code">
            <span class="iconify text-[#007ACC]" data-icon="logos:visual-studio-code" data-width="32"></span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== PROJECTS SECTION ===== -->
  <section id="projects" class="relative py-32 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-20 reveal">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">Portfolio</span>
        <h2 class="font-serif text-4xl md:text-5xl font-medium tracking-tighter text-cream">
          Featured <em class="text-stone-400">Projects</em>
        </h2>
      </div>

      <div class="grid md:grid-cols-2 gap-8">
        <!-- Project 1 - IngendoSmart (Featured) -->
        <div class="md:col-span-2 reveal">
          <div class="glass-card rounded-3xl overflow-hidden group">
            <div class="flex flex-col lg:flex-row">
              <div class="lg:w-1/2 aspect-video lg:aspect-auto relative overflow-hidden">
                <img src="https://picsum.photos/seed/smart-dashboard-app/800/500.jpg" alt="IngendoSmart" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
                <div class="absolute top-4 left-4">
                  <span class="bg-savor text-stone-900 text-xs font-bold uppercase tracking-wider px-3 py-1.5 rounded-full">Featured</span>
                </div>
              </div>
              <div class="lg:w-1/2 p-8 lg:p-12 flex flex-col justify-center">
                <div class="flex items-center gap-2 mb-4">
                  <span class="iconify text-savor/60" data-icon="mdi:rocket-launch-outline" data-width="18"></span>
                  <span class="text-xs font-bold uppercase tracking-[0.2em] text-stone-500">Currently Working On</span>
                </div>
                <h3 class="font-serif text-2xl md:text-3xl font-medium text-cream mb-4">IngendoSmart</h3>
                <p class="text-stone-400 font-light leading-relaxed mb-6">
                  A smart management system designed to streamline operations with modern web technologies. Built with React.js, Node.js, and MongoDB for a seamless full-stack experience.
                </p>
                <div class="flex flex-wrap gap-2 mb-8">
                  <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">React.js</span>
                  <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">Node.js</span>
                  <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">MongoDB</span>
                  <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">Tailwind CSS</span>
                </div>
                <div class="flex items-center gap-4">
                  <a href="https://github.com/Jackson-tj74/IngendoSmart" target="_blank" rel="noopener" class="flex items-center gap-2 text-sm font-bold uppercase tracking-wide text-cream hover:text-savor transition-colors hover-underline">
                    <span class="iconify" data-icon="mdi:github" data-width="18"></span>
                    View Code
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Project 2 - Community Services -->
        <div class="reveal delay-100">
          <div class="glass-card rounded-3xl overflow-hidden group h-full flex flex-col">
            <div class="aspect-video relative overflow-hidden">
              <img src="https://picsum.photos/seed/community-services-platform/600/400.jpg" alt="Community Services" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-stone-950/80 via-transparent to-transparent"></div>
            </div>
            <div class="p-8 flex flex-col flex-1">
              <div class="flex items-center gap-2 mb-3">
                <span class="iconify text-green-400/70" data-icon="mdi:handshake-outline" data-width="16"></span>
                <span class="text-xs font-bold uppercase tracking-[0.2em] text-stone-500">Open to Collaboration</span>
              </div>
              <h3 class="font-serif text-xl font-medium text-cream mb-3">Community Services Nyabiheke</h3>
              <p class="text-stone-400 font-light text-sm leading-relaxed mb-6 flex-1">
                A community-focused platform for the Nyabiheke Cohort 4, enabling local service coordination and community engagement.
              </p>
              <div class="flex flex-wrap gap-2 mb-6">
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">HTML/CSS</span>
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">JavaScript</span>
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">Netlify</span>
              </div>
              <a href="https://community-services-nyabiheke-cohort4.netlify.app/" target="_blank" rel="noopener" class="flex items-center gap-2 text-sm font-bold uppercase tracking-wide text-cream hover:text-savor transition-colors hover-underline">
                <span class="iconify" data-icon="mdi:open-in-new" data-width="16"></span>
                Live Demo
              </a>
            </div>
          </div>
        </div>

        <!-- Project 3 - Portfolio -->
        <div class="reveal delay-200">
          <div class="glass-card rounded-3xl overflow-hidden group h-full flex flex-col">
            <div class="aspect-video relative overflow-hidden">
              <img src="https://picsum.photos/seed/portfolio-website-dev/600/400.jpg" alt="TJ Dev Sphere" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-stone-950/80 via-transparent to-transparent"></div>
            </div>
            <div class="p-8 flex flex-col flex-1">
              <div class="flex items-center gap-2 mb-3">
                <span class="iconify text-blue-400/70" data-icon="mdi:web" data-width="16"></span>
                <span class="text-xs font-bold uppercase tracking-[0.2em] text-stone-500">Portfolio Site</span>
              </div>
              <h3 class="font-serif text-xl font-medium text-cream mb-3">TJ Dev Sphere</h3>
              <p class="text-stone-400 font-light text-sm leading-relaxed mb-6 flex-1">
                My personal portfolio website showcasing hosted projects, skills, and professional journey as a full-stack developer.
              </p>
              <div class="flex flex-wrap gap-2 mb-6">
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">React</span>
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">Tailwind</span>
                <span class="text-xs bg-stone-800/80 text-stone-300 px-3 py-1 rounded-full">Netlify</span>
              </div>
              <a href="https://tjdevsphere.netlify.app" target="_blank" rel="noopener" class="flex items-center gap-2 text-sm font-bold uppercase tracking-wide text-cream hover:text-savor transition-colors hover-underline">
                <span class="iconify" data-icon="mdi:open-in-new" data-width="16"></span>
                Live Demo
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- More projects link -->
      <div class="text-center mt-12 reveal delay-300">
        <a href="https://github.com/Jackson-tj74" target="_blank" rel="noopener" class="inline-flex items-center gap-2 text-sm font-bold uppercase tracking-wide text-stone-400 hover:text-savor transition-colors hover-underline">
          View All Projects on GitHub
          <span class="iconify" data-icon="mdi:arrow-right" data-width="18"></span>
        </a>
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== GITHUB STATS SECTION ===== -->
  <section class="relative py-24 px-6">
    <div class="max-w-4xl mx-auto reveal">
      <div class="text-center mb-12">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">GitHub Activity</span>
        <h2 class="font-serif text-3xl md:text-4xl font-medium tracking-tighter text-cream">
          My GitHub <em class="text-stone-400">Stats</em>
        </h2>
      </div>
      <div class="flex flex-col items-center gap-6">
        <img src="https://github-readme-stats.vercel.app/api?username=Jackson-tj74&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0c0a09&title_color=F3EFE0&icon_color=F3EFE0&text_color=a8a29e" alt="GitHub Stats" class="w-full max-w-lg rounded-2xl" />
        <img src="https://github-readme-streak-stats.herokuapp.com?user=Jackson-tj74&theme=tokyonight&hide_border=true&background=0c0a09&ring=F3EFE0&fire=F3EFE0&currStreakLabel=F3EFE0&sideLabels=a8a29e&dates=78716c" alt="GitHub Streak" class="w-full max-w-lg rounded-2xl" />
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Jackson-tj74&layout=compact&theme=tokyonight&hide_border=true&bg_color=0c0a09&title_color=F3EFE0&text_color=a8a29e" alt="Top Languages" class="w-full max-w-lg rounded-2xl" />
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== CERTIFICATES SECTION ===== -->
  <section id="certificates" class="relative py-32 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-20 reveal">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">Achievements</span>
        <h2 class="font-serif text-4xl md:text-5xl font-medium tracking-tighter text-cream">
          Certificates & <em class="text-stone-400">Awards</em>
        </h2>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Certificate 1 -->
        <div class="glass-card rounded-3xl p-8 reveal delay-100 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-savor/20 to-savor/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-savor" data-icon="mdi:code-braces" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Full-Stack Development</h3>
          <p class="text-sm text-stone-500 mb-4">Alight Coding School</p>
          <div class="flex items-center gap-2">
            <span class="iconify text-green-400/70" data-icon="mdi:check-decagram" data-width="16"></span>
            <span class="text-xs text-stone-400">Professional Certificate</span>
          </div>
        </div>

        <!-- Certificate 2 -->
        <div class="glass-card rounded-3xl p-8 reveal delay-200 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-blue-400/20 to-blue-400/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-blue-400" data-icon="mdi:school" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">High School Diploma</h3>
          <p class="text-sm text-stone-500 mb-4">MCE — Rwanda</p>
          <div class="flex items-center gap-2">
            <span class="iconify text-green-400/70" data-icon="mdi:check-decagram" data-width="16"></span>
            <span class="text-xs text-stone-400">Academic Certificate</span>
          </div>
        </div>

        <!-- Certificate 3 -->
        <div class="glass-card rounded-3xl p-8 reveal delay-300 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-green-400/20 to-green-400/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-green-400" data-icon="mdi:translate" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Duolingo International</h3>
          <p class="text-sm text-stone-500 mb-4">Duolingo Platform</p>
          <div class="flex items-center gap-2">
            <span class="iconify text-green-400/70" data-icon="mdi:check-decagram" data-width="16"></span>
            <span class="text-xs text-stone-400">International Certificate</span>
          </div>
        </div>

        <!-- Certificate 4 -->
        <div class="glass-card rounded-3xl p-8 reveal delay-100 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-yellow-400/20 to-yellow-400/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-yellow-400" data-icon="mdi:certificate-outline" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">IELTS Academic</h3>
          <p class="text-sm text-stone-500 mb-4">Certified English Communications</p>
          <div class="flex items-center gap-2">
            <span class="iconify text-green-400/70" data-icon="mdi:check-decagram" data-width="16"></span>
            <span class="text-xs text-stone-400">International Certificate</span>
          </div>
        </div>

        <!-- Certificate 5 -->
        <div class="glass-card rounded-3xl p-8 reveal delay-200 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-purple-400/20 to-purple-400/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-purple-400" data-icon="mdi:lightbulb-on-outline" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Entrepreneurship Challenge</h3>
          <p class="text-sm text-stone-500 mb-4">Innovation Program</p>
          <div class="flex items-center gap-2">
            <span class="iconify text-green-400/70" data-icon="mdi:check-decagram" data-width="16"></span>
            <span class="text-xs text-stone-400">Innovator Award</span>
          </div>
        </div>

        <!-- Languages card -->
        <div class="glass-card rounded-3xl p-8 reveal delay-300 group">
          <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-rose-400/20 to-rose-400/5 flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
            <span class="iconify text-rose-400" data-icon="mdi:account-voice" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-4">Languages</h3>
          <div class="space-y-3">
            <div class="flex items-center justify-between">
              <span class="text-sm text-stone-300">Kinyarwanda</span>
              <span class="text-xs bg-green-400/10 text-green-400 px-2 py-0.5 rounded-full">Native</span>
            </div>
            <div class="flex items-center justify-between">
              <span class="text-sm text-stone-300">English</span>
              <span class="text-xs bg-blue-400/10 text-blue-400 px-2 py-0.5 rounded-full">Fluent (IELTS)</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== WHAT I BRING SECTION ===== -->
  <section class="relative py-32 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-20 reveal">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">Why Work With Me</span>
        <h2 class="font-serif text-4xl md:text-5xl font-medium tracking-tighter text-cream">
          What I <em class="text-stone-400">Bring</em>
        </h2>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div class="glass-card rounded-3xl p-8 text-center reveal delay-100">
          <div class="w-16 h-16 rounded-full bg-savor/10 flex items-center justify-center mx-auto mb-5">
            <span class="iconify text-savor" data-icon="mdi:lightning-bolt" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Fast Delivery</h3>
          <p class="text-sm text-stone-500 font-light">Quick turnaround without compromising quality</p>
        </div>
        <div class="glass-card rounded-3xl p-8 text-center reveal delay-200">
          <div class="w-16 h-16 rounded-full bg-savor/10 flex items-center justify-center mx-auto mb-5">
            <span class="iconify text-savor" data-icon="mdi:eye-outline" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Clean Design</h3>
          <p class="text-sm text-stone-500 font-light">Pixel-perfect UI with attention to detail</p>
        </div>
        <div class="glass-card rounded-3xl p-8 text-center reveal delay-300">
          <div class="w-16 h-16 rounded-full bg-savor/10 flex items-center justify-center mx-auto mb-5">
            <span class="iconify text-savor" data-icon="mdi:cellphone-link" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Responsive</h3>
          <p class="text-sm text-stone-500 font-light">Looks great on every device and screen size</p>
        </div>
        <div class="glass-card rounded-3xl p-8 text-center reveal delay-400">
          <div class="w-16 h-16 rounded-full bg-savor/10 flex items-center justify-center mx-auto mb-5">
            <span class="iconify text-savor" data-icon="mdi:message-text-outline" data-width="28"></span>
          </div>
          <h3 class="font-serif text-lg font-medium text-cream mb-2">Great Comms</h3>
          <p class="text-sm text-stone-500 font-light">Clear, timely communication throughout</p>
        </div>
      </div>
    </div>
  </section>

  <div class="section-divider max-w-6xl mx-auto"></div>

  <!-- ===== CONTACT SECTION ===== -->
  <section id="contact" class="relative py-32 px-6 noise-overlay">
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute bottom-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-savor/5 rounded-full blur-3xl"></div>
    </div>

    <div class="relative z-10 max-w-3xl mx-auto text-center">
      <div class="reveal">
        <span class="text-xs font-bold uppercase tracking-[0.3em] text-savor/70 mb-4 block">Get in Touch</span>
        <h2 class="font-serif text-4xl md:text-6xl font-medium tracking-tighter text-cream mb-6">
          Let's Build<br/><em class="text-stone-400">Something Great</em>
        </h2>
        <p class="text-lg text-stone-400 font-light leading-relaxed mb-12 max-w-xl mx-auto">
          I'm always open to discussing new projects, creative ideas, or opportunities to be part of your vision.
        </p>
      </div>

      <!-- Contact cards -->
      <div class="grid sm:grid-cols-2 gap-6 mb-12">
        <button onclick="copyEmail()" class="glass-card rounded-2xl p-6 text-left cursor-pointer group reveal delay-100">
          <span class="iconify text-savor/60 mb-3 group-hover:scale-110 transition-transform" data-icon="mdi:email-outline" data-width="24"></span>
          <div class="text-xs text-stone-500 uppercase tracking-wider mb-1">Email</div>
          <div class="text-sm text-cream font-medium break-all">tuyikundejackson74@gmail.com</div>
          <div class="text-xs text-stone-600 mt-2 group-hover:text-savor transition-colors">Click to copy</div>
        </button>

        <a href="https://github.com/Jackson-tj74" target="_blank" rel="noopener" class="glass-card rounded-2xl p-6 text-left group reveal delay-200">
          <span class="iconify text-savor/60 mb-3 group-hover:scale-110 transition-transform" data-icon="mdi:github" data-width="24"></span>
          <div class="text-xs text-stone-500 uppercase tracking-wider mb-1">GitHub</div>
          <div class="text-sm text-cream font-medium">@Jackson-tj74</div>
          <div class="text-xs text-stone-600 mt-2 group-hover:text-savor transition-colors">View profile →</div>
        </a>

        <a href="https://tjdevsphere.netlify.app" target="_blank" rel="noopener" class="glass-card rounded-2xl p-6 text-left group reveal delay-300">
          <span class="iconify text-savor/60 mb-3 group-hover:scale-110 transition-transform" data-icon="mdi:web" data-width="24"></span>
          <div class="text-xs text-stone-500 uppercase tracking-wider mb-1">Portfolio</div>
          <div class="text-sm text-cream font-medium">tjdevsphere.netlify.app</div>
          <div class="text-xs text-stone-600 mt-2 group-hover:text-savor transition-colors">Visit site →</div>
        </a>

        <a href="https://community-services-nyabiheke-cohort4.netlify.app/" target="_blank" rel="noopener" class="glass-card rounded-2xl p-6 text-left group reveal delay-400">
          <span class="iconify text-savor/60 mb-3 group-hover:scale-110 transition-transform" data-icon="mdi:handshake-outline" data-width="24"></span>
          <div class="text-xs text-stone-500 uppercase tracking-wider mb-1">Collaborate</div>
          <div class="text-sm text-cream font-medium">Community Services</div>
          <div class="text-xs text-stone-600 mt-2 group-hover:text-savor transition-colors">View project →</div>
        </a>
      </div>

      <!-- CTA Button -->
      <div class="reveal delay-300">
        <a href="mailto:tuyikundejackson74@gmail.com" class="inline-flex items-center gap-3 bg-cream text-stone-900 font-bold text-sm uppercase tracking-wide px-10 py-5 rounded-full hover:scale-105 transition-transform duration-150 shadow-lg shadow-savor/10">
          <span class="iconify" data-icon="mdi:send" data-width="18"></span>
          Send Me an Email
        </a>
      </div>
    </div>
  </section>

  <!-- ===== FOOTER ===== -->
  <footer class="border-t border-stone-800/50 py-12 px-6">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
      <div class="flex items-center gap-3">
        <div class="w-8 h-8 rounded-lg bg-savor flex items-center justify-center">
          <span class="text-stone-900 font-bold text-sm">JT</span>
        </div>
        <span class="text-sm text-stone-500">© 2025 Jackson Tuyikunde. All rights reserved.</span>
      </div>
      <div class="flex items-center gap-5">
        <a href="https://github.com/Jackson-tj74" target="_blank" rel="noopener" class="text-stone-500 hover:text-cream transition-colors" aria-label="GitHub">
          <span class="iconify" data-icon="mdi:github" data-width="20"></span>
        </a>
        <a href="mailto:tuyikundejackson74@gmail.com" class="text-stone-500 hover:text-cream transition-colors" aria-label="Email">
          <span class="iconify" data-icon="mdi:email" data-width="20"></span>
        </a>
        <a href="https://tjdevsphere.netlify.app" target="_blank" rel="noopener" class="text-stone-500 hover:text-cream transition-colors" aria-label="Portfolio">
          <span class="iconify" data-icon="mdi:web" data-width="20"></span>
        </a>
      </div>
      <div class="text-xs text-stone-600 flex items-center gap-1.5">
        Built with <span class="iconify text-red-400/70" data-icon="mdi:heart" data-width="12"></span> in Rwanda
      </div>
    </div>
  </footer>

  <!-- ===== JAVASCRIPT ===== -->
  <script>
    // ---- Scroll Reveal ----
    const revealElements = document.querySelectorAll('.reveal');
    const revealObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('active');
        }
      });
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
    revealElements.forEach(el => revealObserver.observe(el));

    // ---- Counter Animation ----
    const statNumbers = document.querySelectorAll('.stat-number[data-target]');
    const counterObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const el = entry.target;
          const target = parseInt(el.dataset.target);
          let current = 0;
          const increment = target / 40;
          const timer = setInterval(() => {
            current += increment;
            if (current >= target) {
              current = target;
              clearInterval(timer);
            }
            el.textContent = Math.floor(current) + '+';
          }, 40);
          counterObserver.unobserve(el);
        }
      });
    }, { threshold: 0.5 });
    statNumbers.forEach(el => counterObserver.observe(el));

    // ---- Skill bar animation on scroll ----
    const skillFills = document.querySelectorAll('.skill-fill');
    const skillObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.animationPlayState = 'running';
          skillObserver.unobserve(entry.target);
        }
      });
    }, { threshold: 0.3 });
    skillFills.forEach(el => {
      el.style.animationPlayState = 'paused';
      skillObserver.observe(el);
    });

    // ---- Smooth scroll ----
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
        // Close mobile menu if open
        document.getElementById('mobile-menu').classList.add('hidden');
      });
    });

    // ---- Mobile menu ----
    const mobileBtn = document.getElementById('mobile-menu-btn');
    const mobileMenu = document.getElementById('mobile-menu');
    const mobileClose = document.getElementById('mobile-menu-close');

    mobileBtn.addEventListener('click', () => mobileMenu.classList.remove('hidden'));
    mobileClose.addEventListener('click', () => mobileMenu.classList.add('hidden'));
    document.querySelectorAll('.mobile-link').forEach(link => {
      link.addEventListener('click', () => mobileMenu.classList.add('hidden'));
    });

    // ---- Navbar background on scroll ----
    const nav = document.querySelector('nav');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 80) {
        nav.style.background = 'rgba(12,10,9,0.9)';
      } else {
        nav.style.background = 'rgba(12,10,9,0.7)';
      }
    });

    // ---- Copy email ----
    function copyEmail() {
      navigator.clipboard.writeText('tuyikundejackson74@gmail.com').then(() => {
        showToast('Email copied to clipboard!');
      }).catch(() => {
        // Fallback
        const ta = document.createElement('textarea');
        ta.value = 'tuyikundejackson74@gmail.com';
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        document.body.removeChild(ta);
        showToast('Email copied to clipboard!');
      });
    }

    function showToast(msg) {
      const toast = document.getElementById('toast');
      const toastMsg = document.getElementById('toast-msg');
      toastMsg.textContent = msg;
      toast.classList.add('show');
      setTimeout(() => toast.classList.remove('show'), 2500);
    }

    // ---- Active nav link highlight ----
    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('nav a[href^="#"]');
    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop - 120;
        if (window.scrollY >= sectionTop) {
          current = section.getAttribute('id');
        }
      });
      navLinks.forEach(link => {
        link.classList.remove('text-cream');
        link.classList.add('text-stone-400');
        if (link.getAttribute('href') === '#' + current) {
          link.classList.add('text-cream');
          link.classList.remove('text-stone-400');
        }
      });
    });
  </script>
</body>
</html>
