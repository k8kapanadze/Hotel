<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Modern Identity Systems</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Noto+Sans+Georgian:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Inter', 'Noto Sans Georgian', sans-serif; cursor: none; }
    html { scroll-behavior: smooth; }
    body { background-color: #ffffff; color: #000000; overflow-x: hidden; }

    /* Custom Cursor */
    #cursor {
      width: 12px; height: 12px; background: #000; border-radius: 50%;
      position: fixed; pointer-events: none; z-index: 9999;
      transition: transform 0.2s ease;
    }

    /* Minimal Lines & Transitions */
    .line-grow {
      height: 1px; width: 0; background: #000;
      transition: width 0.8s cubic-bezier(0.65, 0, 0.35, 1);
    }
    .section-visible .line-grow { width: 100%; }

    .nav-item { font-size: 11px; letter-spacing: 0.2em; font-weight: 600; text-transform: uppercase; }
    
    .hover-reveal {
      position: relative; overflow: hidden;
    }
    .hover-reveal::after {
      content: ''; position: absolute; bottom: 0; left: 0; width: 100%; height: 100%;
      background: #000; transform: translateY(100%); transition: transform 0.4s ease;
      z-index: -1;
    }
    .hover-reveal:hover::after { transform: translateY(0); }
    .hover-reveal:hover { color: #fff; }

    /* Stats floating */
    .stat-blur { backdrop-filter: blur(10px); background: rgba(255,255,255,0.1); border: 1px solid #eee; }

    @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
    .reveal { animation: fadeIn 1s forwards; }
  </style>
</head>
<body class="antialiased">

  <div id="cursor" class="hidden md:block"></div>

  <header class="fixed top-0 w-full z-50 mix-blend-difference py-10 px-8 md:px-16 flex justify-between items-center">
    <a href="#" class="text-xl font-bold tracking-tighter text-white">IDENTISITE.</a>
    <nav class="hidden lg:flex space-x-10 text-white">
      <a href="#home" class="nav-item opacity-60 hover:opacity-100 transition">მთავარი</a>
      <a href="#about" class="nav-item opacity-60 hover:opacity-100 transition">ჩვენ შესახებ</a>
      <a href="#services" class="nav-item opacity-60 hover:opacity-100 transition">სერვისები</a>
      <a href="#portfolio" class="nav-item opacity-60 hover:opacity-100 transition">პორტფოლიო</a>
      <a href="#process" class="nav-item opacity-60 hover:opacity-100 transition">პროცესი</a>
      <a href="#blog" class="nav-item opacity-60 hover:opacity-100 transition">ბლოგი</a>
      <a href="#contact" class="nav-item opacity-60 hover:opacity-100 transition">კონტაქტი</a>
    </nav>
    <div class="text-white nav-item">GE / EN</div>
  </header>

  <section id="home" class="min-h-screen flex flex-col justify-center px-8 md:px-16 relative">
    <div class="max-w-6xl">
      <span class="text-xs uppercase tracking-[0.5em] text-gray-400 mb-8 block reveal">Digital Boutique Agency</span>
      <h1 class="text-6xl md:text-[120px] font-medium leading-[0.85] tracking-tighter mb-12 reveal" style="animation-delay: 0.2s;">
        WE TURN <br> IDENTITY <br> <span class="italic text-gray-200">INTO ART.</span>
      </h1>
      <div class="flex flex-col md:flex-row md:items-center space-y-6 md:space-y-0 md:space-x-12 reveal" style="animation-delay: 0.4s;">
        <p class="text-lg max-w-sm text-gray-500 leading-snug">
          იდენტობა რომელიც საიტად იქცევა. მინიმალისტური ესთეტიკა, მაქსიმალური შედეგი.
        </p>
        <a href="#contact" class="inline-block border border-black px-10 py-5 nav-item hover:bg-black hover:text-white transition-all">
          დავიწყოთ პროექტი
        </a>
      </div>
    </div>

    <div class="absolute right-0 top-0 h-full w-1/3 border-l border-gray-50 -z-10 hidden md:block"></div>
  </section>

  <section id="services" class="py-32 px-8 md:px-16 bg-gray-50">
    <div class="max-w-7xl mx-auto">
      <div class="flex justify-between items-end mb-20">
        <h2 class="text-4xl md:text-6xl font-light tracking-tight">Capabilities</h2>
        <span class="nav-item text-gray-400">01 — Services</span>
      </div>

      <div class="space-y-0 border-t border-gray-200">
        <div class="group py-12 border-b border-gray-200 flex flex-col md:flex-row justify-between md:items-center hover:px-6 transition-all duration-500 cursor-pointer bg-white">
          <div>
            <span class="text-xs text-gray-400 mr-8">01</span>
            <h3 class="text-3xl md:text-5xl font-light group-hover:italic transition-all">UX/UI დიზაინი</h3>
          </div>
          <p class="text-gray-400 max-w-xs text-sm mt-4 md:mt-0">უნიკალური ვიზუალური ენა თქვენი ბრენდისთვის.</p>
        </div>

        <div class="group py-12 border-b border-gray-200 flex flex-col md:flex-row justify-between md:items-center hover:px-6 transition-all duration-500 cursor-pointer bg-white">
          <div>
            <span class="text-xs text-gray-400 mr-8">02</span>
            <h3 class="text-3xl md:text-5xl font-light group-hover:italic transition-all">E-commerce</h3>
          </div>
          <p class="text-gray-400 max-w-xs text-sm mt-4 md:mt-0">გაყიდვებზე ორიენტირებული დახვეწილი პლატფორმები.</p>
        </div>

        <div class="group py-12 border-b border-gray-200 flex flex-col md:flex-row justify-between md:items-center hover:px-6 transition-all duration-500 cursor-pointer bg-white">
          <div>
            <span class="text-xs text-gray-400 mr-8">03</span>
            <h3 class="text-3xl md:text-5xl font-light group-hover:italic transition-all">Branding</h3>
          </div>
          <p class="text-gray-400 max-w-xs text-sm mt-4 md:mt-0">იდენტობის შექმნა, რომელიც დროს უძლებს.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="process" class="py-32 px-8 md:px-16 overflow-hidden">
    <div class="max-w-7xl mx-auto">
      <span class="nav-item text-gray-400 block mb-20">02 — The Method</span>
      <div class="grid md:grid-cols-4 gap-12">
        <div>
          <h4 class="text-sm font-bold uppercase mb-6 tracking-widest">01 / კვლევა</h4>
          <p class="text-gray-500 text-sm leading-relaxed">ვიწყებთ თქვენი ბიზნესის დნმ-ის შესწავლით.</p>
        </div>
        <div>
          <h4 class="text-sm font-bold uppercase mb-6 tracking-widest">02 / სტრატეგია</h4>
          <p class="text-gray-500 text-sm leading-relaxed">ვქმნით გზამკვლევს ციფრული წარმატებისთვის.</p>
        </div>
        <div>
          <h4 class="text-sm font-bold uppercase mb-6 tracking-widest">03 / დიზაინი</h4>
          <p class="text-gray-500 text-sm leading-relaxed">ვიზუალიზაცია, სადაც ყოველი პიქსელი მნიშვნელოვანია.</p>
        </div>
        <div>
          <h4 class="text-sm font-bold uppercase mb-6 tracking-widest">04 / გაშვება</h4>
          <p class="text-gray-500 text-sm leading-relaxed">პროექტის დასრულება და მუდმივი მხარდაჭერა.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="py-40 px-8 md:px-16 bg-black text-white">
    <div class="max-w-7xl mx-auto text-center">
      <h2 class="text-5xl md:text-[12vw] font-bold leading-none tracking-tighter mb-20">LET'S TALK.</h2>
      <div class="grid md:grid-cols-2 gap-20 text-left">
        <div>
          <span class="nav-item text-gray-500 block mb-8">Contact Information</span>
          <a href="mailto:hello@identisite.ge" class="text-2xl md:text-4xl hover:text-gray-400 transition">hello@identisite.ge</a>
          <p class="mt-4 text-xl">+995 555 00 00 00</p>
        </div>
        <div class="flex flex-col justify-end items-start md:items-end">
          <span class="nav-item text-gray-500 block mb-8">Social Systems</span>
          <div class="flex space-x-6">
            <a href="#" class="hover-reveal px-4 py-2 border border-white/20 rounded-full">INSTAGRAM</a>
            <a href="#" class="hover-reveal px-4 py-2 border border-white/20 rounded-full">LINKEDIN</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer class="py-12 px-8 md:px-16 border-t border-gray-100 flex justify-between items-center text-[10px] tracking-[0.3em] font-bold uppercase text-gray-400">
    <div>© 2026 IDENTISITE. ALL RIGHTS RESERVED.</div>
    <div>MADE FOR THOSE WHO VALUE IDENTITY.</div>
  </footer>

  <script>
    // Custom Cursor Movement
    const cursor = document.getElementById('cursor');
    document.addEventListener('mousemove', e => {
      cursor.style.left = e.clientX + 'px';
      cursor.style.top = e.clientY + 'px';
    });

    // Simple interaction effect
    document.querySelectorAll('a, button, .group').forEach(el => {
      el.addEventListener('mouseenter', () => cursor.style.transform = 'scale(4)');
      el.addEventListener('mouseleave', () => cursor.style.transform = 'scale(1)');
    });
  </script>
</body>
</html>
