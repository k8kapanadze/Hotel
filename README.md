<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Modern Identity</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Noto+Sans+Georgian:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; }
    html { scroll-behavior: smooth; }
    
    /* ახალი ფერების პალიტრა */
    :root {
      --brand-bg: #0f172a;
      --brand-accent: #38bdf8;
      --brand-gradient: linear-gradient(135deg, #38bdf8 0%, #818cf8 100%);
    }

    .dark-glass {
      background: rgba(30, 41, 59, 0.7);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .gradient-text {
      background: var(--brand-gradient);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .btn-primary {
      background: var(--brand-gradient);
      box-shadow: 0 4px 20px -5px rgba(56, 189, 248, 0.5);
      transition: all 0.3s ease;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 25px -5px rgba(56, 189, 248, 0.6);
    }

    .service-card {
      background: #1e293b;
      border: 1px solid rgba(255, 255, 255, 0.05);
      transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    .service-card:hover {
      border-color: #38bdf8;
      transform: scale(1.02);
      box-shadow: 0 0 30px rgba(56, 189, 248, 0.1);
    }

    @keyframes pulse-glow {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 0.6; }
    }
    .glow-blob {
      position: absolute;
      filter: blur(120px);
      z-index: 0;
      animation: pulse-glow 8s infinite;
    }
  </style>
</head>
<body class="bg-[#0f172a] text-slate-200">

  <nav class="fixed top-0 w-full z-50 dark-glass border-b border-white/5">
    <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center">
      <a href="#" class="flex items-center space-x-3">
        <div class="w-10 h-10 btn-primary rounded-lg flex items-center justify-center font-bold text-white">I</div>
        <span class="text-xl font-bold tracking-tighter text-white">IDENTISITE</span>
      </a>
      
      <div class="flex items-center space-x-4">
        <button class="text-xs border border-white/10 px-3 py-1 rounded hover:bg-white/5 transition">EN</button>
        <a href="#contact" class="btn-primary px-5 py-2 rounded-full text-sm font-bold text-white">დავიწყოთ</a>
      </div>
    </div>
  </nav>

  <section id="home" class="relative pt-32 pb-20 overflow-hidden">
    <div class="glow-blob w-[500px] h-[500px] bg-sky-600/20 -top-48 -left-24"></div>
    <div class="glow-blob w-[400px] h-[400px] bg-indigo-600/20 bottom-0 -right-24"></div>

    <div class="max-w-7xl mx-auto px-6 relative z-10">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <div>
          <div class="inline-block px-4 py-1 rounded-full bg-sky-500/10 border border-sky-500/20 text-sky-400 text-xs font-bold mb-6">
            PREMIUM DIGITAL AGENCY
          </div>
          <h1 class="text-5xl lg:text-7xl font-bold text-white leading-[1.1] mb-8">
            შენი ბიზნესის <br>
            <span class="gradient-text">იდენტობა</span> იწყება აქ
          </h1>
          <p class="text-lg text-slate-400 mb-10 max-w-lg leading-relaxed">
            იდენტობა რომელიც საიტად იქცევა — ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს გამოარჩევს.
          </p>
          <div class="flex flex-wrap gap-4">
            <button class="btn-primary px-8 py-4 rounded-xl font-bold text-white text-sm">დავიწყოთ პროექტი</button>
            <button class="px-8 py-4 rounded-xl border border-white/10 hover:bg-white/5 font-bold text-sm transition">ნამუშევრები</button>
          </div>
        </div>

        <div class="relative h-[450px] hidden lg:block">
           <div class="absolute top-10 left-10 dark-glass p-6 rounded-2xl w-64 shadow-2xl border-t border-white/20">
              <div class="text-sky-400 font-bold text-3xl mb-1">98%</div>
              <div class="text-slate-400 text-xs uppercase tracking-widest">კმაყოფილი კლიენტი</div>
           </div>
           <div class="absolute bottom-10 right-10 dark-glass p-6 rounded-2xl w-64 shadow-2xl border-l border-white/20">
              <div class="flex items-center space-x-4 mb-4">
                <div class="w-10 h-10 rounded-full bg-green-500/20 flex items-center justify-center">
                  <div class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></div>
                </div>
                <div class="text-sm font-medium">პროექტი აქტიურია</div>
              </div>
              <div class="h-1.5 w-full bg-white/10 rounded-full overflow-hidden">
                <div class="h-full bg-sky-500 w-3/4"></div>
              </div>
           </div>
        </div>
      </div>
    </div>
  </section>

  <section id="services" class="py-24 relative bg-[#0b1120]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center mb-20">
        <h2 class="text-3xl font-bold text-white mb-4">რას გთავაზობთ</h2>
        <div class="h-1 w-20 btn-primary mx-auto rounded-full"></div>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div class="service-card p-8 rounded-3xl group">
          <div class="w-12 h-12 rounded-2xl bg-sky-500/10 flex items-center justify-center mb-6 group-hover:bg-sky-500 transition-colors">
            <svg class="w-6 h-6 text-sky-400 group-hover:text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"></path></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-4">კორპორატიული საიტები</h3>
          <p class="text-slate-400 text-sm leading-relaxed mb-6">პროფესიონალური ვებსაიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს.</p>
          <a href="#" class="text-sky-400 text-sm font-bold flex items-center hover:underline">
            დეტალურად <span class="ml-2">→</span>
          </a>
        </div>

        <div class="service-card p-8 rounded-3xl border-sky-500/30 bg-gradient-to-b from-slate-800 to-[#1e293b]">
          <div class="w-12 h-12 rounded-2xl bg-sky-500 flex items-center justify-center mb-6">
            <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-4">E-commerce</h3>
          <p class="text-slate-400 text-sm leading-relaxed mb-6">სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემების ინტეგრაციით.</p>
          <a href="#" class="text-sky-400 text-sm font-bold flex items-center hover:underline">
            დეტალურად <span class="ml-2">→</span>
          </a>
        </div>

        <div class="service-card p-8 rounded-3xl group">
          <div class="w-12 h-12 rounded-2xl bg-indigo-500/10 flex items-center justify-center mb-6 group-hover:bg-indigo-500 transition-colors">
            <svg class="w-6 h-6 text-indigo-400 group-hover:text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-width="2" d="M4 5a1 1 0 011-1h14a1 1 0 011 1v2a1 1 0 01-1 1H5a1 1 0 01-1-1V5z"></path></svg>
          </div>
          <h3 class="text-xl font-bold text-white mb-4">UI/UX დიზაინი</h3>
          <p class="text-slate-400 text-sm leading-relaxed mb-6">მომხმარებელზე ორიენტირებული ინტერფეისები საუკეთესო გამოცდილებისთვის.</p>
          <a href="#" class="text-sky-400 text-sm font-bold flex items-center hover:underline">
            დეტალურად <span class="ml-2">→</span>
          </a>
        </div>
      </div>
    </div>
  </section>

  <footer class="py-12 border-t border-white/5 bg-[#0f172a]">
    <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center opacity-60 text-sm">
      <p>© 2026 IDENTISITE. ყველა უფლება დაცულია.</p>
      <div class="flex space-x-6 mt-4 md:mt-0">
        <a href="#" class="hover:text-white transition">Facebook</a>
        <a href="#" class="hover:text-white transition">Instagram</a>
        <a href="#" class="hover:text-white transition">LinkedIn</a>
      </div>
    </div>
  </footer>

 </body>
</html>
