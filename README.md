<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | საიტების დამზადება, ვებსაიტების გაკეთება, საიტების ფასები</title>
  <meta name="description" content="IDENTISITE - საიტების დამზადება და ვებსაიტების გაკეთება ბიზნესებისთვის.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700&family=Outfit:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <style>
    :root {
      --blue-900: #0A1628;
      --blue-950: #050C1A;
      --blue-800: #0D1B3E;
      --blue-700: #1E3A8A;
      --electric: #3B82F6;
      --electric-light: #60A5FA;
      --electric-pale: #93C5FD;
      --navy: #070D1F;
    }
    * { font-family: 'Noto Sans Georgian', 'Outfit', sans-serif; }
    html { scroll-behavior: smooth; }
    body { background: #050A18; color: #E2E8F0; }

    .gradient-text {
      background: linear-gradient(135deg, #60A5FA 0%, #3B82F6 50%, #93C5FD 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .glass-card {
      background: rgba(7, 15, 41, 0.8);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(59, 130, 246, 0.2);
    }
    .hover-lift {
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .hover-lift:hover {
      transform: translateY(-8px);
      box-shadow: 0 25px 50px -12px rgba(59, 130, 246, 0.25);
    }
    .nav-link { position: relative; }
    .nav-link::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0;
      width: 0; height: 2px;
      background: linear-gradient(90deg, #3B82F6, #60A5FA);
      transition: width 0.3s ease;
    }
    .nav-link:hover::after { width: 100%; }

    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-20px); }
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes scaleIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }
    .animate-float { animation: float 6s ease-in-out infinite; }
    .animate-fade-in-up { animation: fadeInUp 0.8s ease-out forwards; }
    .stagger-1 { animation-delay: 0.1s; }
    .stagger-2 { animation-delay: 0.2s; }
    .stagger-3 { animation-delay: 0.3s; }
    .stagger-4 { animation-delay: 0.4s; }

    .blob {
      position: absolute;
      border-radius: 50%;
      filter: blur(80px);
      opacity: 0.4;
    }

    /* Glow effects */
    .glow-blue {
      box-shadow: 0 0 30px rgba(59,130,246,0.3), 0 0 60px rgba(59,130,246,0.1);
    }
    .btn-primary {
      background: linear-gradient(135deg, #2563EB, #1D4ED8);
      transition: all 0.3s ease;
    }
    .btn-primary:hover {
      background: linear-gradient(135deg, #3B82F6, #2563EB);
      box-shadow: 0 0 30px rgba(59,130,246,0.5);
      transform: scale(1.03);
    }

    /* Card with blue border glow */
    .card-dark {
      background: linear-gradient(135deg, rgba(13,27,62,0.8), rgba(7,13,31,0.9));
      border: 1px solid rgba(59,130,246,0.2);
      transition: all 0.3s ease;
    }
    .card-dark:hover {
      border-color: rgba(59,130,246,0.5);
      box-shadow: 0 0 20px rgba(59,130,246,0.1);
    }

    /* Section dividers */
    .section-dark { background: #060C1E; }
    .section-navy { background: #070D1F; }
    .section-deep { background: #050A18; }

    /* Input dark */
    input, textarea {
      background: #070D1F !important;
      border-color: rgba(30,58,138,0.6) !important;
      color: #E2E8F0 !important;
    }
    input::placeholder, textarea::placeholder { color: #334155 !important; }
    input:focus, textarea:focus {
      border-color: #3B82F6 !important;
      outline: none;
      box-shadow: 0 0 0 2px rgba(59,130,246,0.2);
    }

    /* Noise texture overlay for hero */
    .noise-overlay::before {
      content: '';
      position: absolute;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
    }

    .grid-line-bg {
      background-image: linear-gradient(rgba(59,130,246,0.05) 1px, transparent 1px),
                        linear-gradient(90deg, rgba(59,130,246,0.05) 1px, transparent 1px);
      background-size: 50px 50px;
    }

    /* Stats counter */
    .stat-card {
      background: rgba(13,27,62,0.6);
      border: 1px solid rgba(59,130,246,0.2);
      border-radius: 1rem;
      padding: 1rem 1.5rem;
    }

    /* Tag badge */
    .tag-badge {
      background: rgba(30,58,138,0.4);
      color: #93C5FD;
      border: 1px solid rgba(59,130,246,0.3);
      border-radius: 9999px;
      padding: 0.25rem 1rem;
      font-size: 0.875rem;
      font-weight: 500;
    }
  </style>
</head>
<body class="h-full overflow-auto">
<div class="w-full min-h-full">

  <!-- Navigation -->
  <nav id="navbar" class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 bg-[#070D1F]/95 backdrop-blur-xl border-b border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-20">
        <a href="#home" class="flex items-center space-x-2">
          <div class="w-11 h-11 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center glow-blue">
            <span class="text-white font-bold text-xl">I</span>
          </div>
          <span class="text-2xl font-bold text-white tracking-tight">IDENTISITE</span>
        </a>
        <div class="hidden lg:flex items-center space-x-8">
          <a href="#home" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">მთავარი</a>
          <a href="#about" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">ჩვენ შესახებ</a>
          <a href="#services" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">სერვისები</a>
          <a href="#portfolio" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">პორტფოლიო</a>
          <a href="#process" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">პროცესი</a>
          <a href="#blog" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">ბლოგი</a>
          <a href="#contact" class="nav-link text-[#94A3B8] hover:text-[#60A5FA] transition-colors font-medium">კონტაქტი</a>
        </div>
        <div class="flex items-center space-x-4">
          <button id="langSwitch" class="px-3 py-1.5 text-sm font-medium text-[#94A3B8] hover:text-[#60A5FA] border border-[#1E3A8A]/50 rounded-lg hover:border-[#3B82F6] transition-all">EN</button>
          <a href="#contact" class="hidden sm:inline-flex px-6 py-3 btn-primary text-white font-semibold rounded-xl">დავიწყოთ</a>
          <button id="mobileMenuBtn" class="lg:hidden p-2 text-[#94A3B8] hover:text-[#60A5FA]">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
          </button>
        </div>
      </div>
      <div id="mobileMenu" class="lg:hidden hidden pb-4">
        <div class="flex flex-col space-y-3">
          <a href="#home" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">მთავარი</a>
          <a href="#about" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">ჩვენ შესახებ</a>
          <a href="#services" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">სერვისები</a>
          <a href="#portfolio" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">პორტფოლიო</a>
          <a href="#process" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">პროცესი</a>
          <a href="#blog" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">ბლოგი</a>
          <a href="#contact" class="text-[#94A3B8] hover:text-[#60A5FA] py-2 font-medium">კონტაქტი</a>
        </div>
      </div>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden pt-20 section-deep grid-line-bg noise-overlay">
    <div class="blob w-96 h-96 bg-[#1D4ED8] top-20 -left-48 animate-float"></div>
    <div class="blob w-80 h-80 bg-[#2563EB] bottom-20 -right-40 animate-float" style="animation-delay: -3s;"></div>
    <div class="blob w-64 h-64 bg-[#1E40AF] top-1/2 left-1/3 animate-float" style="animation-delay: -1.5s;"></div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 relative z-10">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <div class="text-center lg:text-left">
          <div class="inline-flex items-center px-4 py-2 tag-badge mb-6 animate-fade-in-up">
            <span class="w-2 h-2 bg-[#3B82F6] rounded-full mr-2 animate-pulse"></span>
            პრემიუმ ვებ სააგენტო
          </div>
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white leading-tight mb-6 animate-fade-in-up stagger-1">
            შენი ბიზნესის<br>
            <span class="gradient-text">იდენტობა იწყება აქ</span>
          </h1>
          <p class="text-xl text-[#94A3B8] mb-8 max-w-xl animate-fade-in-up stagger-2">
            იდენტობა რომელიც საიტად იქცევა - ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს გამოარჩევს და შედეგს მოგიტანთ.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start animate-fade-in-up stagger-3">
            <a href="#contact" class="px-8 py-4 btn-primary text-white font-semibold rounded-xl text-center">დავიწყოთ პროექტი</a>
            <a href="#portfolio" class="px-8 py-4 bg-transparent text-[#E2E8F0] font-semibold rounded-xl border-2 border-[#1E3A8A] hover:border-[#3B82F6] hover:text-white transition-all duration-300 text-center">ვნახოთ ნამუშევრები</a>
          </div>
          <div class="grid grid-cols-3 gap-6 mt-12 animate-fade-in-up stagger-4">
            <div class="stat-card text-center lg:text-left">
              <div class="text-3xl font-bold gradient-text">150+</div>
              <div class="text-[#64748B] text-sm">პროექტი</div>
            </div>
            <div class="stat-card text-center lg:text-left">
              <div class="text-3xl font-bold gradient-text">98%</div>
              <div class="text-[#64748B] text-sm">კმაყოფილება</div>
            </div>
            <div class="stat-card text-center lg:text-left">
              <div class="text-3xl font-bold gradient-text">5+</div>
              <div class="text-[#64748B] text-sm">წლიანი გამოცდილება</div>
            </div>
          </div>
        </div>
        <!-- Hero Visual -->
        <div class="relative hidden lg:block">
          <div class="relative w-full h-96">
            <div class="absolute top-0 left-10 w-64 h-40 glass-card rounded-2xl p-4 animate-float shadow-xl">
              <div class="flex items-center space-x-3 mb-3">
                <div class="w-10 h-10 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-lg flex items-center justify-center">
                  <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                </div>
                <span class="font-semibold text-white">პროექტი დასრულდა</span>
              </div>
              <div class="h-2 bg-[#1E3A8A]/50 rounded-full overflow-hidden">
                <div class="h-full w-full bg-gradient-to-r from-[#3B82F6] to-[#60A5FA] rounded-full"></div>
              </div>
            </div>
            <div class="absolute top-20 right-0 w-56 h-48 glass-card rounded-2xl p-4 animate-float shadow-xl" style="animation-delay:-2s;">
              <div class="text-center">
                <div class="w-16 h-16 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl mx-auto mb-3 flex items-center justify-center">
                  <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
                </div>
                <div class="text-2xl font-bold text-white">2,847</div>
                <div class="text-[#64748B] text-sm">ვიზიტორი დღეს</div>
              </div>
            </div>
            <div class="absolute bottom-0 left-20 w-72 h-44 glass-card rounded-2xl p-4 animate-float shadow-xl" style="animation-delay:-4s;">
              <div class="flex items-center justify-between mb-4">
                <span class="font-semibold text-white">კონვერსია</span>
                <span class="text-[#3B82F6] font-medium">+24%</span>
              </div>
              <div class="flex items-end space-x-2 h-20">
                <div class="flex-1 bg-[#1E3A8A] rounded-t" style="height:40%"></div>
                <div class="flex-1 bg-[#1E3A8A] rounded-t" style="height:55%"></div>
                <div class="flex-1 bg-[#1E3A8A] rounded-t" style="height:45%"></div>
                <div class="flex-1 bg-[#3B82F6] rounded-t" style="height:70%"></div>
                <div class="flex-1 bg-[#3B82F6] rounded-t" style="height:85%"></div>
                <div class="flex-1 bg-[#60A5FA] rounded-t" style="height:100%"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-[#1E3A8A]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/></svg>
    </div>
  </section>

  <!-- Trusted -->
  <section class="py-16 bg-[#060C1E] border-y border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <p class="text-center text-[#475569] mb-8">ჩვენ გვენდობიან</p>
      <div class="flex flex-wrap justify-center items-center gap-12 opacity-40">
        <div class="text-2xl font-bold text-[#3B82F6]">TechCorp</div>
        <div class="text-2xl font-bold text-[#3B82F6]">StartupX</div>
        <div class="text-2xl font-bold text-[#3B82F6]">DigitalHub</div>
        <div class="text-2xl font-bold text-[#3B82F6]">InnovateLab</div>
        <div class="text-2xl font-bold text-[#3B82F6]">FutureTech</div>
      </div>
    </div>
  </section>

  <!-- About -->
  <section id="about" class="py-24 section-deep">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">ჩვენ შესახებ</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">ბრენდის იდენტობას ციფრულ გამოცდილებად ვაქცევთ</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">IDENTISITE არის პრემიუმ ვებ სააგენტო, რომელიც ბიზნესებს ეხმარება ციფრულ სამყაროში გამორჩეული იდენტობის შექმნაში.</p>
      </div>
      <div class="grid lg:grid-cols-2 gap-16 items-center mb-20">
        <div>
          <h3 class="text-2xl font-bold text-white mb-6">ჩვენი ისტორია</h3>
          <p class="text-[#94A3B8] mb-6">2019 წელს დაარსებული IDENTISITE წამოვიდა ერთი მარტივი იდეით - ყოველ ბიზნესს აქვს უნიკალური იდენტობა, რომელიც იმსახურებს გამორჩეულ ციფრულ წარმოჩენას. დღეს ჩვენ 150-ზე მეტი წარმატებული პროექტი გვაქვს.</p>
          <div class="grid sm:grid-cols-2 gap-6">
            <div class="card-dark p-6 rounded-2xl">
              <div class="w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center mb-4">
                <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
              </div>
              <h4 class="font-semibold text-white mb-2">მისია</h4>
              <p class="text-[#64748B] text-sm">ბიზნესის უნიკალური იდენტობის გარდასახვა მაღალტექნოლოგიურ ციფრულ აქტივად.</p>
            </div>
            <div class="card-dark p-6 rounded-2xl">
              <div class="w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center mb-4">
                <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"/></svg>
              </div>
              <h4 class="font-semibold text-white mb-2">ხედვა</h4>
              <p class="text-[#64748B] text-sm">ციფრული არქიტექტურის ახალი სტანდარტის დამკვიდრება რეგიონში.</p>
            </div>
          </div>
        </div>
        <div class="relative">
          <div class="bg-gradient-to-br from-[#1D4ED8] to-[#1E3A8A] rounded-3xl p-8 text-white glow-blue">
            <h4 class="text-xl font-semibold mb-6">ჩვენი ფილოსოფია</h4>
            <ul class="space-y-4">
              <li class="flex items-start space-x-3"><svg class="w-6 h-6 flex-shrink-0 mt-0.5 text-[#93C5FD]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg><span>ინდივიდუალური მიდგომა ყოველ პროექტზე</span></li>
              <li class="flex items-start space-x-3"><svg class="w-6 h-6 flex-shrink-0 mt-0.5 text-[#93C5FD]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg><span>ხარისხი კომპრომისის გარეშე</span></li>
              <li class="flex items-start space-x-3"><svg class="w-6 h-6 flex-shrink-0 mt-0.5 text-[#93C5FD]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg><span>გამჭვირვალე კომუნიკაცია</span></li>
              <li class="flex items-start space-x-3"><svg class="w-6 h-6 flex-shrink-0 mt-0.5 text-[#93C5FD]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg><span>შედეგზე ორიენტირებული მუშაობა</span></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Services -->
  <section id="services" class="py-24 section-navy">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">სერვისები</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">რას გთავაზობთ</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">სრული სპექტრი ციფრული გადაწყვეტილებები თქვენი ბიზნესის ზრდისთვის</p>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Service cards -->
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">კორპორატიული ვებსაიტები</h3>
          <p class="text-[#64748B] mb-4">პროფესიონალური ვებსაიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>უნიკალური დიზაინი</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>SEO ოპტიმიზაცია</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">E-commerce მაღაზიები</h3>
          <p class="text-[#64748B] mb-4">სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემებით.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>გადახდის ინტეგრაცია</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>ადმინ პანელი</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">Landing Page დიზაინი</h3>
          <p class="text-[#64748B] mb-4">კონვერსიაზე ორიენტირებული სადესანტო გვერდები.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>A/B ტესტირება</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>სწრაფი ჩატვირთვა</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 5a1 1 0 011-1h14a1 1 0 011 1v2a1 1 0 01-1 1H5a1 1 0 01-1-1V5zM4 13a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H5a1 1 0 01-1-1v-6zM16 13a1 1 0 011-1h2a1 1 0 011 1v6a1 1 0 01-1 1h-2a1 1 0 01-1-1v-6z"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">UI/UX დიზაინი</h3>
          <p class="text-[#64748B] mb-4">მომხმარებელზე ორიენტირებული ინტერფეისების დიზაინი.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>Wireframing</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>პროტოტიპირება</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">ვებსაიტის რედიზაინი</h3>
          <p class="text-[#64748B] mb-4">განაახლეთ თქვენი ვებსაიტი თანამედროვე სტანდარტებით.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>მონაცემების მიგრაცია</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>პერფორმანსის გაუმჯობესება</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
        <div class="group card-dark p-8 rounded-3xl hover-lift">
          <div class="w-14 h-14 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-3">SEO ოპტიმიზაცია</h3>
          <p class="text-[#64748B] mb-4">გაზარდეთ ხილვადობა საძიებო სისტემებში.</p>
          <ul class="text-sm text-[#475569] space-y-2 mb-6">
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>საკვანძო სიტყვების კვლევა</span></li>
            <li class="flex items-center space-x-2"><svg class="w-4 h-4 text-[#3B82F6]" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/></svg><span>ტექნიკური SEO</span></li>
          </ul>
          <a href="#contact" class="inline-flex items-center text-[#3B82F6] font-medium hover:text-[#60A5FA]">შეკვეთა <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
        </div>
      </div>
    </div>
  </section>

  <!-- Why Us -->
  <section class="py-24 section-deep">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">რატომ ჩვენ</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">რატომ IDENTISITE?</h2>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div class="text-center p-6 card-dark rounded-2xl">
          <div class="w-16 h-16 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mx-auto mb-4">
            <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"/></svg>
          </div>
          <h3 class="font-bold text-white mb-2">პრემიუმ ხარისხი</h3>
          <p class="text-[#64748B] text-sm">ყოველ დეტალზე ზრუნვა</p>
        </div>
        <div class="text-center p-6 card-dark rounded-2xl">
          <div class="w-16 h-16 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mx-auto mb-4">
            <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
          </div>
          <h3 class="font-bold text-white mb-2">დროული მიწოდება</h3>
          <p class="text-[#64748B] text-sm">პროექტები ვადაში</p>
        </div>
        <div class="text-center p-6 card-dark rounded-2xl">
          <div class="w-16 h-16 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mx-auto mb-4">
            <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/></svg>
          </div>
          <h3 class="font-bold text-white mb-2">გამოცდილი გუნდი</h3>
          <p class="text-[#64748B] text-sm">5+ წლის გამოცდილება</p>
        </div>
        <div class="text-center p-6 card-dark rounded-2xl">
          <div class="w-16 h-16 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-2xl flex items-center justify-center mx-auto mb-4">
            <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z"/></svg>
          </div>
          <h3 class="font-bold text-white mb-2">მხარდაჭერა 24/7</h3>
          <p class="text-[#64748B] text-sm">მუდმივი ტექნიკური მხარდაჭერა</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Portfolio -->
  <section id="portfolio" class="py-24 section-navy">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">პორტფოლიო</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">ჩვენი ნამუშევრები</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">გაეცანით ჩვენს წარმატებულ პროექტებს</p>
      </div>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#1D4ED8] to-[#1E3A8A] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">TechCorp Website</h3>
            <p class="text-white/80 text-sm mb-3">კორპორატიული ვებსაიტი</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">React</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Tailwind</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Node.js</span></div>
          </div>
        </div>
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">StyleShop E-commerce</h3>
            <p class="text-white/80 text-sm mb-3">ონლაინ მაღაზია</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Next.js</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Stripe</span></div>
          </div>
        </div>
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#1E3A8A] to-[#1D4ED8] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">FoodDelivery App</h3>
            <p class="text-white/80 text-sm mb-3">მობილური აპლიკაცია</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">React Native</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Firebase</span></div>
          </div>
        </div>
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#1D4ED8] to-[#1E3A8A] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">HealthCare Portal</h3>
            <p class="text-white/80 text-sm mb-3">სამედიცინო პლატფორმა</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Vue.js</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Laravel</span></div>
          </div>
        </div>
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#2563EB] to-[#1E3A8A] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">EduLearn Platform</h3>
            <p class="text-white/80 text-sm mb-3">სასწავლო პლატფორმა</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">Next.js</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">MongoDB</span></div>
          </div>
        </div>
        <div class="group relative overflow-hidden rounded-3xl bg-gradient-to-br from-[#1E3A8A] to-[#2563EB] aspect-[4/3] hover-lift cursor-pointer" onclick="location.href='#contact'">
          <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute inset-0 flex flex-col justify-end p-6 text-white translate-y-8 group-hover:translate-y-0 transition-transform duration-300">
            <h3 class="text-xl font-bold mb-2">RealEstate Pro</h3>
            <p class="text-white/80 text-sm mb-3">უძრავი ქონების პორტალი</p>
            <div class="flex flex-wrap gap-2"><span class="px-2 py-1 bg-white/20 rounded-full text-xs">React</span><span class="px-2 py-1 bg-white/20 rounded-full text-xs">GraphQL</span></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Process -->
  <section id="process" class="py-24 section-deep">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">პროცესი</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">როგორ ვმუშაობთ</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">გამჭვირვალე და ეფექტური პროცესი</p>
      </div>
      <div class="relative">
        <div class="hidden lg:block absolute left-1/2 top-0 bottom-0 w-px bg-gradient-to-b from-[#3B82F6] to-[#1D4ED8] transform -translate-x-1/2"></div>
        <div class="space-y-12 lg:space-y-0">
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center lg:pb-20">
            <div class="lg:text-right lg:pr-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">1</div>
              <h3 class="text-xl font-bold text-white mb-3">კონსულტაცია</h3>
              <p class="text-[#94A3B8]">უფასო კონსულტაცია, სადაც ვისმენთ თქვენს მოთხოვნებს და ვადებს.</p>
            </div>
            <div class="hidden lg:flex items-center justify-start pl-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">1</div>
            </div>
          </div>
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center lg:pb-20">
            <div class="hidden lg:flex items-center justify-end pr-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">2</div>
            </div>
            <div class="lg:pl-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">2</div>
              <h3 class="text-xl font-bold text-white mb-3">კვლევა და სტრატეგია</h3>
              <p class="text-[#94A3B8]">ბაზრის ანალიზი და სტრატეგიის შემუშავება.</p>
            </div>
          </div>
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center lg:pb-20">
            <div class="lg:text-right lg:pr-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">3</div>
              <h3 class="text-xl font-bold text-white mb-3">დიზაინი</h3>
              <p class="text-[#94A3B8]">უნიკალური დიზაინი Wireframe და Mockup-ით.</p>
            </div>
            <div class="hidden lg:flex items-center justify-start pl-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">3</div>
            </div>
          </div>
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center lg:pb-20">
            <div class="hidden lg:flex items-center justify-end pr-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">4</div>
            </div>
            <div class="lg:pl-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">4</div>
              <h3 class="text-xl font-bold text-white mb-3">განვითარება</h3>
              <p class="text-[#94A3B8]">თანამედროვე ტექნოლოგიებით ვებსაიტის აწყობა.</p>
            </div>
          </div>
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center lg:pb-20">
            <div class="lg:text-right lg:pr-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">5</div>
              <h3 class="text-xl font-bold text-white mb-3">ტესტირება</h3>
              <p class="text-[#94A3B8]">საფუძვლიანი ტესტირება ყველა მოწყობილობაზე.</p>
            </div>
            <div class="hidden lg:flex items-center justify-start pl-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">5</div>
            </div>
          </div>
          <div class="relative lg:grid lg:grid-cols-2 lg:gap-16 items-center">
            <div class="hidden lg:flex items-center justify-end pr-16">
              <div class="absolute left-1/2 transform -translate-x-1/2 w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full flex items-center justify-center font-bold text-lg z-10">6</div>
            </div>
            <div class="lg:pl-16">
              <div class="inline-flex items-center justify-center w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] text-white rounded-full font-bold text-lg mb-4 lg:hidden">6</div>
              <h3 class="text-xl font-bold text-white mb-3">გაშვება და მხარდაჭერა</h3>
              <p class="text-[#94A3B8]">ვებსაიტის გაშვება და უწყვეტი ტექნიკური მხარდაჭერა.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Testimonials -->
  <section class="py-24 section-navy">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">შეფასებები</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">რას ამბობენ კლიენტები</h2>
      </div>
      <div class="grid md:grid-cols-3 gap-8">
        <div class="card-dark p-8 rounded-3xl">
          <div class="flex text-[#3B82F6] mb-4">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
          </div>
          <p class="text-[#94A3B8] mb-6">"IDENTISITE-მა ჩვენი ხედვა რეალობად აქცია. პროფესიონალური მიდგომა და შესანიშნავი შედეგი."</p>
          <div class="flex items-center">
            <div class="w-12 h-12 bg-gradient-to-br from-[#1D4ED8] to-[#3B82F6] rounded-full flex items-center justify-center text-white font-bold">ლ.გ</div>
            <div class="ml-4"><div class="font-semibold text-white">ლაშა გოგიშვილი</div><div class="text-sm text-[#475569]">CEO, TechCorp</div></div>
          </div>
        </div>
        <div class="card-dark p-8 rounded-3xl">
          <div class="flex text-[#3B82F6] mb-4">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
          </div>
          <p class="text-[#94A3B8] mb-6">"ონლაინ მაღაზიის გახსნის შემდეგ გაყიდვები 300%-ით გაიზარდა!"</p>
          <div class="flex items-center">
            <div class="w-12 h-12 bg-gradient-to-br from-[#1D4ED8] to-[#3B82F6] rounded-full flex items-center justify-center text-white font-bold">ა.ჩ</div>
            <div class="ml-4"><div class="font-semibold text-white">ანა ჩხეიძე</div><div class="text-sm text-[#475569]">Founder, StyleShop</div></div>
          </div>
        </div>
        <div class="card-dark p-8 rounded-3xl">
          <div class="flex text-[#3B82F6] mb-4">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/></svg>
          </div>
          <p class="text-[#94A3B8] mb-6">"კომუნიკაცია იყო გამჭვირვალე, ხარისხი - უმაღლესი."</p>
          <div class="flex items-center">
            <div class="w-12 h-12 bg-gradient-to-br from-[#1D4ED8] to-[#3B82F6] rounded-full flex items-center justify-center text-white font-bold">გ.ბ</div>
            <div class="ml-4"><div class="font-semibold text-white">გიორგი ბუაჩიძე</div><div class="text-sm text-[#475569]">Marketing Director, InnovateLab</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Blog -->
  <section id="blog" class="py-24 section-deep">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">ბლოგი</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">სიახლეები და სტატიები</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">სასარგებლო ინფორმაცია ვებსაიტების შესახებ</p>
      </div>
      <div class="grid md:grid-cols-3 gap-8">
        <article class="group card-dark rounded-3xl overflow-hidden hover-lift">
          <div class="aspect-video bg-gradient-to-br from-[#1D4ED8] to-[#1E3A8A]"></div>
          <div class="p-6">
            <div class="flex items-center space-x-4 text-sm text-[#475569] mb-3"><span>15 იანვარი, 2026</span><span>•</span><span>5 წუთი</span></div>
            <h3 class="text-lg font-bold text-white mb-2 group-hover:text-[#60A5FA] transition-colors">2026 წლის ვებ დიზაინის ტრენდები</h3>
            <p class="text-[#64748B] text-sm mb-4">რა ტენდენციები განსაზღვრავს ვებ დიზაინის მომავალს...</p>
            <a href="#blog-post-1" class="inline-flex items-center text-[#3B82F6] font-medium text-sm hover:text-[#60A5FA]">წაიკითხე მეტი <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
          </div>
        </article>
        <article class="group card-dark rounded-3xl overflow-hidden hover-lift">
          <div class="aspect-video bg-gradient-to-br from-[#2563EB] to-[#1D4ED8]"></div>
          <div class="p-6">
            <div class="flex items-center space-x-4 text-sm text-[#475569] mb-3"><span>10 იანვარი, 2026</span><span>•</span><span>7 წუთი</span></div>
            <h3 class="text-lg font-bold text-white mb-2 group-hover:text-[#60A5FA] transition-colors">SEO ოპტიმიზაციის საფუძვლები</h3>
            <p class="text-[#64748B] text-sm mb-4">როგორ გააუმჯობესოთ პოზიციები Google-ში...</p>
            <a href="#blog-post-2" class="inline-flex items-center text-[#3B82F6] font-medium text-sm hover:text-[#60A5FA]">წაიკითხე მეტი <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
          </div>
        </article>
        <article class="group card-dark rounded-3xl overflow-hidden hover-lift">
          <div class="aspect-video bg-gradient-to-br from-[#1E3A8A] to-[#2563EB]"></div>
          <div class="p-6">
            <div class="flex items-center space-x-4 text-sm text-[#475569] mb-3"><span>5 იანვარი, 2026</span><span>•</span><span>6 წუთი</span></div>
            <h3 class="text-lg font-bold text-white mb-2 group-hover:text-[#60A5FA] transition-colors">E-commerce წარმატების საიდუმლო</h3>
            <p class="text-[#64748B] text-sm mb-4">რა ფაქტორები განსაზღვრავს ონლაინ მაღაზიის წარმატებას...</p>
            <a href="#blog-post-3" class="inline-flex items-center text-[#3B82F6] font-medium text-sm hover:text-[#60A5FA]">წაიკითხე მეტი <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg></a>
          </div>
        </article>
      </div>
    </div>
  </section>

  <!-- Blog Details -->
  <section class="py-16 bg-[#060C1E] border-t border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-6">
      <article id="blog-post-1" class="p-6 rounded-2xl border border-[#1E3A8A]/30 bg-[#0D1B3E]/60">
        <h3 class="text-2xl font-bold text-white mb-3">2026 წლის ვებ დიზაინის ტრენდები</h3>
        <p class="text-[#94A3B8]">მთავარი აქცენტი კეთდება მკაფიო მესიჯინგზე, მაღალი კონტრასტის CTA-ებზე და ნდობის ელემენტებზე.</p>
        <a href="#blog" class="inline-flex mt-4 text-[#3B82F6] font-semibold hover:text-[#60A5FA]">ბლოგში დაბრუნება</a>
      </article>
      <article id="blog-post-2" class="p-6 rounded-2xl border border-[#1E3A8A]/30 bg-[#0D1B3E]/60">
        <h3 class="text-2xl font-bold text-white mb-3">SEO ოპტიმიზაციის საფუძვლები</h3>
        <p class="text-[#94A3B8]">SEO იწყება სწორი საკვანძო ფრაზებით, semantic HTML-ით და mobile-first გამოცდილებით.</p>
        <a href="#blog" class="inline-flex mt-4 text-[#3B82F6] font-semibold hover:text-[#60A5FA]">ბლოგში დაბრუნება</a>
      </article>
      <article id="blog-post-3" class="p-6 rounded-2xl border border-[#1E3A8A]/30 bg-[#0D1B3E]/60">
        <h3 class="text-2xl font-bold text-white mb-3">E-commerce წარმატების საიდუმლო</h3>
        <p class="text-[#94A3B8]">პროდუქტის გვერდი, checkout-ის სისწრაფე და სოციალური მტკიცებულება განსაზღვრავს შედეგს.</p>
        <a href="#blog" class="inline-flex mt-4 text-[#3B82F6] font-semibold hover:text-[#60A5FA]">ბლოგში დაბრუნება</a>
      </article>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-24 section-navy">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="tag-badge mb-4 inline-block">კონტაქტი</span>
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">დავიწყოთ თანამშრომლობა</h2>
        <p class="text-xl text-[#94A3B8] max-w-3xl mx-auto">გაგვიზიარეთ თქვენი იდეა</p>
      </div>
      <div class="grid lg:grid-cols-2 gap-16">
        <div class="card-dark p-8 rounded-3xl">
          <form id="contactForm" class="space-y-6">
            <div class="grid sm:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-sm font-medium text-[#93C5FD] mb-2">სახელი *</label>
                <input type="text" id="name" name="name" required class="w-full px-4 py-3 rounded-xl" placeholder="თქვენი სახელი">
              </div>
              <div>
                <label for="email" class="block text-sm font-medium text-[#93C5FD] mb-2">ელფოსტა *</label>
                <input type="email" id="email" name="email" required class="w-full px-4 py-3 rounded-xl" placeholder="your@email.com">
              </div>
            </div>
            <div>
              <label for="company" class="block text-sm font-medium text-[#93C5FD] mb-2">კომპანია</label>
              <input type="text" id="company" name="company" class="w-full px-4 py-3 rounded-xl" placeholder="კომპანიის სახელი">
            </div>
            <div>
              <label for="project" class="block text-sm font-medium text-[#93C5FD] mb-2">პროექტის აღწერა *</label>
              <textarea id="project" name="project" rows="4" required class="w-full px-4 py-3 rounded-xl resize-none" placeholder="მოგვიყევით პროექტის შესახებ..."></textarea>
            </div>
            <button type="submit" id="submitBtn" class="w-full px-8 py-4 btn-primary text-white font-semibold rounded-xl">გაგზავნა</button>
            <div id="formMessage" class="hidden text-center p-4 rounded-xl"></div>
          </form>
        </div>
        <div class="space-y-8">
          <div class="card-dark p-6 rounded-2xl flex items-start space-x-4">
            <div class="w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center flex-shrink-0">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
            </div>
            <div><h4 class="font-semibold text-white mb-1">ელფოსტა</h4><p class="text-[#94A3B8]">info@identisite.ge</p></div>
          </div>
          <div class="card-dark p-6 rounded-2xl flex items-start space-x-4">
            <div class="w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center flex-shrink-0">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
            </div>
            <div><h4 class="font-semibold text-white mb-1">ტელეფონი</h4><p class="text-[#94A3B8]">+995 555 123 456</p></div>
          </div>
          <div class="card-dark p-6 rounded-2xl flex items-start space-x-4">
            <div class="w-12 h-12 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center flex-shrink-0">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            </div>
            <div><h4 class="font-semibold text-white mb-1">მისამართი</h4><p class="text-[#94A3B8]">თბილისი, საქართველო</p></div>
          </div>
          <div class="flex space-x-4">
            <a href="https://x.com" target="_blank" rel="noopener noreferrer" class="w-12 h-12 card-dark rounded-xl flex items-center justify-center text-[#64748B] hover:text-[#3B82F6] transition-all">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
            </a>
            <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" class="w-12 h-12 card-dark rounded-xl flex items-center justify-center text-[#64748B] hover:text-[#3B82F6] transition-all">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
            </a>
            <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="w-12 h-12 card-dark rounded-xl flex items-center justify-center text-[#64748B] hover:text-[#3B82F6] transition-all">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            </a>
            <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" class="w-12 h-12 card-dark rounded-xl flex items-center justify-center text-[#64748B] hover:text-[#3B82F6] transition-all">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M22.675 0h-21.35c-.732 0-1.325.593-1.325 1.325v21.351c0 .731.593 1.324 1.325 1.324h11.495v-9.294h-3.128v-3.622h3.128v-2.671c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.463.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.313h3.587l-.467 3.622h-3.12v9.293h6.116c.73 0 1.323-.593 1.323-1.325v-21.35c0-.732-.593-1.325-1.325-1.325z"/></svg>
            </a>
          </div>
        </div>
      </div>
      <!-- FAQ -->
      <div class="mt-24">
        <h3 class="text-2xl font-bold text-white text-center mb-12">ხშირად დასმული კითხვები</h3>
        <div class="max-w-3xl mx-auto space-y-4">
          <div class="card-dark rounded-2xl overflow-hidden">
            <button class="w-full px-6 py-4 text-left flex justify-between items-center hover:bg-[#1E3A8A]/20 transition-colors" onclick="toggleFaq(this)">
              <span class="font-semibold text-white">რა ღირს ვებსაიტის შექმნა?</span>
              <svg class="w-5 h-5 text-[#3B82F6] transform transition-transform faq-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
            </button>
            <div class="faq-answer hidden px-6 pb-4"><p class="text-[#94A3B8]">Landing Page: 500₾-დან, E-commerce: 3000₾-დან. დაგვიკავშირდით კონსულტაციისთვის.</p></div>
          </div>
          <div class="card-dark rounded-2xl overflow-hidden">
            <button class="w-full px-6 py-4 text-left flex justify-between items-center hover:bg-[#1E3A8A]/20 transition-colors" onclick="toggleFaq(this)">
              <span class="font-semibold text-white">რამდენ ხანში დამზადდება ვებსაიტი?</span>
              <svg class="w-5 h-5 text-[#3B82F6] transform transition-transform faq-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
            </button>
            <div class="faq-answer hidden px-6 pb-4"><p class="text-[#94A3B8]">Landing Page: 1-2 კვირა, კორპორატიული: 3-4 კვირა, E-commerce: 4-8 კვირა.</p></div>
          </div>
          <div class="card-dark rounded-2xl overflow-hidden">
            <button class="w-full px-6 py-4 text-left flex justify-between items-center hover:bg-[#1E3A8A]/20 transition-colors" onclick="toggleFaq(this)">
              <span class="font-semibold text-white">გთავაზობთ ტექნიკურ მხარდაჭერას?</span>
              <svg class="w-5 h-5 text-[#3B82F6] transform transition-transform faq-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
            </button>
            <div class="faq-answer hidden px-6 pb-4"><p class="text-[#94A3B8]">დიახ! 24/7. პირველი 3 თვე უფასოა, შემდეგ 50₾/თვიდან.</p></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Privacy & Terms -->
  <section id="privacy-policy" class="py-14 bg-[#060C1E] border-t border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h3 class="text-2xl font-bold text-white mb-4">კონფიდენციალურობა</h3>
      <p class="text-[#94A3B8]">თქვენი მოწოდებული საკონტაქტო ინფორმაცია გამოიყენება მხოლოდ კომუნიკაციისთვის. მონაცემები არ გადაეცემა მესამე მხარეს.</p>
    </div>
  </section>
  <section id="terms-conditions" class="py-14 bg-[#050A18] border-t border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h3 class="text-2xl font-bold text-white mb-4">პირობები</h3>
      <p class="text-[#94A3B8]">თანამშრომლობა იწყება მოთხოვნის დაზუსტებით და ვადების შეთანხმებით.</p>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-[#020710] text-white py-16 border-t border-[#1A2744]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-4 gap-12 mb-12">
        <div>
          <a href="#home" class="flex items-center space-x-2 mb-6">
            <div class="w-11 h-11 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center"><span class="text-white font-bold text-xl">I</span></div>
            <span class="text-2xl font-bold">IDENTISITE</span>
          </a>
          <p class="text-[#475569] text-sm">იდენტობა რომელიც საიტად იქცევა</p>
        </div>
        <div>
          <h4 class="font-semibold mb-4 text-white">სერვისები</h4>
          <ul class="space-y-2 text-[#475569] text-sm">
            <li><a href="#services" class="hover:text-[#3B82F6] transition-colors">კორპორატიული საიტები</a></li>
            <li><a href="#services" class="hover:text-[#3B82F6] transition-colors">E-commerce</a></li>
            <li><a href="#services" class="hover:text-[#3B82F6] transition-colors">UI/UX დიზაინი</a></li>
            <li><a href="#services" class="hover:text-[#3B82F6] transition-colors">SEO ოპტიმიზაცია</a></li>
          </ul>
        </div>
        <div>
          <h4 class="font-semibold mb-4 text-white">კომპანია</h4>
          <ul class="space-y-2 text-[#475569] text-sm">
            <li><a href="#about" class="hover:text-[#3B82F6] transition-colors">ჩვენ შესახებ</a></li>
            <li><a href="#portfolio" class="hover:text-[#3B82F6] transition-colors">პორტფოლიო</a></li>
            <li><a href="#blog" class="hover:text-[#3B82F6] transition-colors">ბლოგი</a></li>
            <li><a href="#contact" class="hover:text-[#3B82F6] transition-colors">კონტაქტი</a></li>
          </ul>
        </div>
        <div>
          <h4 class="font-semibold mb-4 text-white">კონტაქტი</h4>
          <ul class="space-y-2 text-[#475569] text-sm">
            <li>info@identisite.ge</li>
            <li>+995 555 123 456</li>
            <li>თბილისი, საქართველო</li>
          </ul>
        </div>
      </div>
      <div class="border-t border-[#1A2744] pt-8 flex flex-col md:flex-row justify-between items-center">
        <p class="text-[#475569] text-sm">© 2026 IDENTISITE. ყველა უფლება დაცულია.</p>
        <div class="flex space-x-6 mt-4 md:mt-0">
          <a href="#privacy-policy" class="text-[#475569] hover:text-[#3B82F6] text-sm transition-colors">კონფიდენციალურობა</a>
          <a href="#terms-conditions" class="text-[#475569] hover:text-[#3B82F6] text-sm transition-colors">პირობები</a>
        </div>
      </div>
    </div>
  </footer>
</div>

<script>
  // Mobile menu
  document.getElementById('mobileMenuBtn').addEventListener('click', () => {
    document.getElementById('mobileMenu').classList.toggle('hidden');
  });
  document.querySelectorAll('#mobileMenu a').forEach(l => l.addEventListener('click', () => {
    document.getElementById('mobileMenu').classList.add('hidden');
  }));

  // Language switcher (toggle)
  let currentLang = 'ka';
  document.getElementById('langSwitch').addEventListener('click', () => {
    currentLang = currentLang === 'ka' ? 'en' : 'ka';
    document.getElementById('langSwitch').textContent = currentLang === 'ka' ? 'EN' : 'GE';
  });

  // FAQ toggle
  function toggleFaq(button) {
    const answer = button.nextElementSibling;
    const icon = button.querySelector('.faq-icon');
    answer.classList.toggle('hidden');
    icon.classList.toggle('rotate-180');
  }

  // Contact form
  document.getElementById('contactForm').addEventListener('submit', async (e) => {
    e.preventDefault();
    const btn = document.getElementById('submitBtn');
    const msg = document.getElementById('formMessage');
    btn.disabled = true;
    btn.textContent = 'იგზავნება...';
    await new Promise(r => setTimeout(r, 1000));
    msg.className = 'text-center p-4 rounded-xl bg-[#1E3A8A]/40 text-[#93C5FD] border border-[#3B82F6]/30';
    msg.textContent = 'მადლობა! შეტყობინება მიღებულია. დაგიკავშირდებით მალე.';
    msg.classList.remove('hidden');
    e.target.reset();
    btn.disabled = false;
    btn.textContent = 'გაგზავნა';
    setTimeout(() => msg.classList.add('hidden'), 5000);
  });

  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const t = document.querySelector(a.getAttribute('href'));
      if (t) t.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });

  // Navbar scroll shadow
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').classList.toggle('shadow-lg', window.pageYOffset > 100);
  });
</script>
</body>
</html>
