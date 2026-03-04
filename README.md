<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Modern Identity</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Noto+Sans+Georgian:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; transition: background-color 0.4s ease, color 0.4s ease; }
    html { scroll-behavior: smooth; }
    
    /* Grains Overlay */
    .noise::before {
      content: "";
      position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: url('https://grainy-gradients.vercel.app/noise.svg');
      opacity: 0.03; pointer-events: none; z-index: 9999;
    }

    /* Grains Overlap with Glow */
    .glow-blob {
      position: absolute; filter: blur(120px); z-index: 0; opacity: 0.2;
    }

    /* Glass Cards */
    .glass-card {
      background: rgba(30, 41, 59, 0.7);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    /* Glow Elements */
    .gradient-text {
      background: linear-gradient(135deg, #38bdf8 0%, #818cf8 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .btn-main {
      background: linear-gradient(135deg, #38bdf8 0%, #818cf8 100%);
      color: #000; font-weight: 700; border-radius: 100px;
      transition: all 0.3s ease;
    }
    .btn-main:hover { transform: translateY(-3px); box-shadow: 0 10px 30px #38bdf850; }

    /* Theme Switcher Toggle */
    .theme-switch {
      width: 50px; height: 26px; background: rgba(255,255,255,0.1);
      border-radius: 50px; position: relative; cursor: pointer;
    }
    .theme-switch .dot {
      width: 20px; height: 20px; background: white;
      border-radius: 50%; position: absolute; top: 3px; left: 3px; transition: 0.3s;
    }

    /* Dark Mode Utility */
    .dark-mode { background-color: #050505 !important; color: #f1f5f9 !important; }
    .dark-mode .noise::before { opacity: 0.05; }
    .dark-mode .theme-switch { background: #38bdf8; }
    .dark-mode .theme-switch .dot { left: 27px; background: #000; }
    .dark-mode .glass-card { background: rgba(13, 13, 13, 0.8); }

    /* Marquee Tech Stack */
    @keyframes scroll { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
    .tech-marquee { display: flex; width: 200%; animation: scroll 30s linear infinite; }
    
    /* Calculator Interaction */
    .calc-card:hover { border-color: #38bdf8; transform: translateY(-5px); }
  </style>
</head>
<body class="bg-[#0f172a] text-slate-200 antialiased noise">

  <nav class="fixed top-0 w-full z-50 dark-glass border-b border-white/5 px-8 py-5">
    <div class="max-w-7xl mx-auto flex justify-between items-center h-20">
      <a href="#" class="flex items-center space-x-3">
        <div class="w-10 h-10 btn-main flex items-center justify-center font-bold text-black">I</div>
        <span class="text-xl font-bold tracking-tighter text-white">IDENTISITE</span>
      </a>
      
      <div class="flex items-center space-x-8">
        <div class="theme-switch" onclick="toggleDarkMode()">
          <div class="dot"></div>
        </div>
        <span class="text-xs font-bold opacity-30">GE / EN</span>
      </div>
    </div>
  </nav>

  <section id="home" class="relative pt-32 pb-20 overflow-hidden min-h-screen flex items-center">
    <div class="glow-blob w-[500px] h-[500px] bg-sky-600 top-20 -left-24"></div>
    <div class="glow-blob w-[400px] h-[400px] bg-indigo-600 bottom-0 -right-24"></div>

    <div class="max-w-7xl mx-auto px-6 grid lg:grid-cols-2 gap-16 items-center z-10 relative">
      <div>
        <div class="inline-block px-4 py-1 rounded-full bg-sky-500/10 border border-sky-500/20 text-sky-400 text-xs font-bold mb-6">PREMIUM WEB SYSTEMS</div>
        <h1 class="text-5xl lg:text-7xl font-bold text-white leading-[1.1] mb-8">
          შენი ბიზნესის <br>
          <span class="gradient-text">იდენტობა</span> იწყება აქ
        </h1>
        <p class="text-lg text-slate-400 mb-10 max-w-lg leading-relaxed">
          წაშალეთ ზღვარი იდეასა და რეალობას შორის. ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს და შედეგზე ორიენტირებულს ხდის.
        </p>
        <div class="flex flex-wrap gap-4">
          <a href="#contact" class="btn-main px-8 py-4 font-bold text-black text-sm uppercase tracking-widest">დავიწყოთ პროექტი</a>
          <a href="#portfolio" class="px-8 py-4 rounded-full border border-white/10 hover:bg-white/5 font-bold text-sm text-white transition">შექმნილი პროექტები</a>
        </div>
      </div>
      
      <div class="relative h-[450px] hidden lg:block">
         <div class="absolute top-10 left-10 dark-glass p-8 rounded-2xl w-72 shadow-2xl">
            <div class="text-[120px] font-bold text-sky-400">98%</div>
            <div class="text-slate-400 text-xs uppercase tracking-widest">კმაყოფილი კლიენტი</div>
         </div>
      </div>
    </div>
  </section>

  <section id="services" class="py-24 bg-[#0b1120] px-6">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl font-bold text-white mb-4">გააჟღერე იდეა</h2>
        <div class="w-12 h-1 bg-sky-500 mx-auto rounded-full"></div>
      </div>

      <div class="grid md:grid-cols-3 gap-8 mb-12">
        <div onclick="selectService(this, 'UX/UI')" class="glass-card calc-card p-10 rounded-3xl cursor-pointer transition flex flex-col items-center">
          <div class="w-16 h-16 bg-sky-500 rounded-2xl mb-8 flex items-center justify-center font-bold text-black text-2xl">01</div>
          <h3 class="text-xl font-bold text-white mb-2">UX/UI</h3>
          <p class="text-slate-400 text-sm opacity-50">ინტერფეისის დიზაინი</p>
        </div>
        <div onclick="selectService(this, 'Web')" class="glass-card calc-card p-10 rounded-3xl cursor-pointer transition flex flex-col items-center">
            <div class="w-16 h-16 bg-indigo-500 rounded-2xl mb-8 flex items-center justify-center font-bold text-black text-2xl">02</div>
            <h3 class="text-xl font-bold text-white mb-2">Web Dev</h3>
            <p class="text-slate-400 text-sm opacity-50">საიტების დამზადება</p>
        </div>
        <div onclick="selectService(this, 'Branding')" class="glass-card calc-card p-10 rounded-3xl cursor-pointer transition flex flex-col items-center">
            <div class="w-16 h-16 bg-sky-500 rounded-2xl mb-8 flex items-center justify-center font-bold text-black text-2xl">03</div>
            <h3 class="text-xl font-bold text-white mb-2">Branding</h3>
            <p class="text-slate-400 text-sm opacity-50">ბრენდის სტრატეგია</p>
        </div>
      </div>

      <div class="max-w-3xl mx-auto p-10 glass-card rounded-3xl text-center">
          <p class="text-slate-400 mb-2">შერჩეული: <span id="selected-service" class="gradient-text font-bold">---</span></p>
          <a href="#contact" class="btn-main px-8 py-3 inline-block font-bold">მიიღე შეთავაზება</a>
      </div>
    </div>
  </section>

  <section id="portfolio" class="py-24 relative bg-[#0f172a] px-6">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl font-bold text-white">პორტფოლიო</h2>
      </div>

      <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
        <div class="aspect-video glass-card rounded-2xl flex items-center justify-center text-slate-500">Work 01</div>
        <div class="aspect-video glass-card rounded-2xl flex items-center justify-center text-slate-500">Work 02</div>
        <div class="aspect-video glass-card rounded-2xl flex items-center justify-center text-slate-500">Work 03</div>
        <div class="aspect-video glass-card rounded-2xl flex items-center justify-center text-slate-500">Work 04</div>
      </div>
    </div>
  </section>

  <div class="overflow-hidden border-y border-white/5 py-10 opacity-30 grayscale hover:grayscale-0 transition-all bg-[#0b1120]">
    <div class="tech-marquee space-x-20">
      <span class="text-3xl font-black uppercase tracking-tighter text-white">React</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Tailwind</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Node.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Figma</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Python</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Next.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">React</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Tailwind</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Node.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter text-white">Figma</span>
    </div>
  </div>

  <section id="contact" class="py-24 px-6 relative bg-[#0b1120]">
    <div class="max-w-4xl mx-auto glass-card p-12 rounded-3xl relative">
      <h2 class="text-4xl font-bold text-center text-white mb-12">დავიწყოთ პროექტი</h2>
      <form class="space-y-6">
        <div class="grid md:grid-cols-2 gap-6">
            <input type="text" placeholder="თქვენი სახელი" class="w-full p-5 bg-white/5 rounded-xl border border-white/10 outline-none text-white focus:border-sky-500">
            <input type="email" placeholder="ელ-ფოსტა" class="w-full p-5 bg-white/5 rounded-xl border border-white/10 outline-none text-white focus:border-sky-500">
        </div>
        <textarea placeholder="თქვენი შეტყობინება" rows="5" class="w-full p-5 bg-white/5 rounded-xl border border-white/10 outline-none text-white focus:border-sky-500"></textarea>
        <button class="w-full btn-main p-5 rounded-xl text-lg hover:shadow-2xl">გაგზავნა</button>
      </form>
    </div>
  </section>

  <footer class="py-12 border-t border-white/5 bg-[#0f172a]">
    <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center opacity-60 text-sm">
      <p>© 2026 IDENTISITE. ყველა უფლება დაცულია.</p>
      <div class="flex space-x-6 mt-4 md:mt-0 font-bold text-white">
        <a href="#" class="hover:text-sky-400 transition">Facebook</a>
        <a href="#" class="hover:text-sky-400 transition">Instagram</a>
      </div>
    </div>
  </footer>

  <script>
    // Dark Mode Toggle
    function toggleDarkMode() {
      document.body.classList.toggle('dark-mode');
    }

    // Calculator Select
    function selectService(el, name) {
      document.getElementById('selected-service').innerText = name;
    }
  </script>

</body>
</html>
