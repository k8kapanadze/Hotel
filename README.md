<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | PREMIUM DIGITAL IDENTITY</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Noto+Sans+Georgian:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; scroll-behavior: smooth; }
    
    :root {
      --matte-blue: #0a192f;
      --deep-black: #050505;
      --soft-gray: #f9f9f9;
      --border-color: #e2e2e2;
    }

    .bg-matte-blue { background-color: var(--matte-blue); }
    .text-matte-blue { color: var(--matte-blue); }
    .border-matte { border-color: var(--border-color); }

    /* აკორდეონის ლოგიკა */
    .accordion-content {
      max-height: 0;
      transition: all 0.5s cubic-bezier(0, 1, 0, 1);
      overflow: hidden;
    }
    .accordion-item.active .accordion-content {
      max-height: 500px;
      transition: all 0.8s ease-in-out;
    }
    .accordion-item.active .plus-icon { transform: rotate(45deg); }

    /* მინიმალისტური კარდები */
    .minimal-card {
      border: 1px solid var(--border-color);
      transition: all 0.3s ease;
    }
    .minimal-card:hover {
      background-color: var(--soft-gray);
      border-color: var(--matte-blue);
    }

    /* ლურჯი ფილტრი ფოტოებისთვის */
    .blue-filter {
      filter: grayscale(100%) brightness(0.4) sepia(100%) hue-rotate(195deg) saturate(400%);
    }

    .nav-link { position: relative; }
    .nav-link::after {
      content: ''; position: absolute; bottom: -2px; left: 0; width: 0; height: 1px;
      background: var(--matte-blue); transition: width 0.3s;
    }
    .nav-link:hover::after { width: 100%; }
  </style>
</head>
<body class="bg-white text-[#050505]">

  <nav id="navbar" class="fixed top-0 w-full z-50 bg-white/95 backdrop-blur-sm border-b border-matte">
    <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center">
      <a href="#home" class="flex items-center space-x-3">
        <div class="w-10 h-10 bg-matte-blue flex items-center justify-center text-white font-bold italic">I</div>
        <span class="text-xl font-bold tracking-tighter text-matte-blue uppercase">IDENTISITE</span>
      </a>
      
      <div class="hidden lg:flex items-center space-x-8 text-[11px] uppercase tracking-widest font-bold">
        <a href="#home" class="nav-link" data-lang="ka">მთავარი</a>
        <a href="#about" class="nav-link" data-lang="ka">ჩვენ შესახებ</a>
        <a href="#services" class="nav-link" data-lang="ka">სერვისები</a>
        <a href="#portfolio" class="nav-link" data-lang="ka">პორტფოლიო</a>
        <a href="#process" class="nav-link" data-lang="ka">პროცესი</a>
        <a href="#blog" class="nav-link" data-lang="ka">ბლოგი</a>
        <a href="#contact" class="nav-link" data-lang="ka">კონტაქტი</a>
      </div>

      <div class="flex items-center space-x-6">
        <button id="langSwitch" class="text-[10px] font-bold border border-matte px-3 py-1 hover:bg-matte-blue hover:text-white transition">EN</button>
        <button id="mobileMenuBtn" class="lg:hidden">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M4 8h16M4 16h16" stroke-width="2"/></svg>
        </button>
      </div>
    </div>
  </nav>

  <section id="home" class="pt-48 pb-32 px-6">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-6xl md:text-[120px] font-bold tracking-tighter leading-[0.85] mb-12">
        IDENTITY<br><span class="text-gray-200 uppercase">is Digital.</span>
      </h1>
      <div class="grid lg:grid-cols-2 gap-12 items-end">
        <p class="text-xl text-gray-500 max-w-lg" data-lang="ka">
          იდენტობა, რომელიც საიტად იქცევა. ჩვენ ვქმნით პრემიუმ ციფრულ გამოცდილებას თქვენი ბიზნესის წარმატებისთვის.
        </p>
        <div class="flex space-x-12 border-t border-matte pt-8">
          <div><div class="text-3xl font-bold text-matte-blue">150+</div><div class="text-[10px] uppercase text-gray-400">პროექტი</div></div>
          <div><div class="text-3xl font-bold text-matte-blue">98%</div><div class="text-[10px] uppercase text-gray-400">კმაყოფილება</div></div>
          <div><div class="text-3xl font-bold text-matte-blue">5+</div><div class="text-[10px] uppercase text-gray-400">წელი</div></div>
        </div>
      </div>
    </div>
  </section>

  <section id="about" class="py-24 px-6 bg-matte-blue text-white overflow-hidden relative">
    <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-16 items-center">
      <div>
        <h2 class="text-sm font-bold uppercase tracking-[0.4em] text-gray-400 mb-6">ჩვენ შესახებ</h2>
        <h3 class="text-4xl font-bold mb-8 leading-tight">ბრენდის იდენტობას ციფრულ გამოცდილებად ვაქცევთ</h3>
        <p class="text-gray-400 mb-8">IDENTISITE არის პრემიუმ ვებ სააგენტო, რომელიც ბიზნესებს ეხმარება ციფრულ სამყაროში გამორჩეული იდენტობის შექმნაში.</p>
        <div class="grid grid-cols-2 gap-8">
          <div class="border-l border-white/10 pl-6">
            <h4 class="font-bold mb-2 uppercase text-sm">მისია</h4>
            <p class="text-xs text-gray-500">ბიზნესების გაძლიერება ინოვაციებით.</p>
          </div>
          <div class="border-l border-white/10 pl-6">
            <h4 class="font-bold mb-2 uppercase text-sm">ხედვა</h4>
            <p class="text-xs text-gray-500">წამყვანი ციფრული პარტნიორი რეგიონში.</p>
          </div>
        </div>
      </div>
      <div class="relative h-[400px] border border-white/5 bg-white/5">
        <div class="absolute inset-0 flex items-center justify-center text-8xl font-black text-white/5 italic">ABOUT</div>
      </div>
    </div>
  </section>

  <section id="services" class="py-24 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="mb-16">
        <h2 class="text-sm font-bold uppercase tracking-[0.4em] text-gray-400 mb-4">სერვისები</h2>
        <h3 class="text-4xl font-bold">რას გთავაზობთ</h3>
      </div>
      <div class="space-y-0 border-t border-matte">
        <div class="accordion-item border-b border-matte cursor-pointer" onclick="toggleAcc(this)">
          <div class="py-10 flex justify-between items-center group">
            <span class="text-2xl font-bold uppercase italic tracking-tighter transition-all group-hover:pl-4">01. Corporate Websites</span>
            <span class="plus-icon text-3xl transition-transform">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-10 text-gray-500 max-w-2xl">პროფესიონალური ვებსაიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს და კლიენტებს მოიზიდავს.</p>
          </div>
        </div>
        <div class="accordion-item border-b border-matte cursor-pointer" onclick="toggleAcc(this)">
          <div class="py-10 flex justify-between items-center group">
            <span class="text-2xl font-bold uppercase italic tracking-tighter transition-all group-hover:pl-4">02. E-commerce Shops</span>
            <span class="plus-icon text-3xl transition-transform">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-10 text-gray-500 max-w-2xl">სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემებით და მარაგის მართვით.</p>
          </div>
        </div>
        <div class="accordion-item border-b border-matte cursor-pointer" onclick="toggleAcc(this)">
          <div class="py-10 flex justify-between items-center group">
            <span class="text-2xl font-bold uppercase italic tracking-tighter transition-all group-hover:pl-4">03. UI/UX Design</span>
            <span class="plus-icon text-3xl transition-transform">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-10 text-gray-500 max-w-2xl">მომხმარებელზე ორიენტირებული ინტერფეისების დიზაინი საუკეთესო გამოცდილებისთვის.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="portfolio" class="py-24 bg-gray-50 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="flex justify-between items-end mb-16">
        <h2 class="text-4xl font-bold tracking-tighter uppercase">Portfolio</h2>
        <a href="#" class="text-[10px] font-bold uppercase tracking-widest border-b border-matte pb-1 hover:text-gray-400 transition">View All</a>
      </div>
      <div class="grid md:grid-cols-2 gap-8">
        <div class="group cursor-pointer">
          <div class="h-[400px] bg-matte-blue mb-6 overflow-hidden">
            <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&q=80" class="w-full h-full object-cover blue-filter opacity-60 group-hover:scale-105 transition duration-700">
          </div>
          <h4 class="text-lg font-bold uppercase">Digital Platform X</h4>
          <p class="text-xs text-gray-400 uppercase tracking-widest">Web Development / UI Design</p>
        </div>
        <div class="group cursor-pointer">
          <div class="h-[400px] bg-matte-blue mb-6 overflow-hidden">
            <img src="https://images.unsplash.com/photo-1522542550221-31fd19575a2d?auto=format&fit=crop&q=80" class="w-full h-full object-cover blue-filter opacity-60 group-hover:scale-105 transition duration-700">
          </div>
          <h4 class="text-lg font-bold uppercase">Fashion E-store</h4>
          <p class="text-xs text-gray-400 uppercase tracking-widest">E-commerce / Branding</p>
        </div>
      </div>
    </div>
  </section>

  <section id="process" class="py-24 px-6 border-y border-matte">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-sm font-bold uppercase tracking-[0.4em] text-gray-400 mb-16 text-center">პროცესი</h2>
      <div class="grid md:grid-cols-4 gap-px bg-gray-200 border border-gray-200">
        <div class="minimal-card p-12 bg-white"><span class="text-xs font-bold text-gray-300 block mb-8">01.</span><h4 class="font-bold uppercase mb-4 italic">კვლევა</h4><p class="text-xs text-gray-400">ბიზნესის მიზნების შესწავლა.</p></div>
        <div class="minimal-card p-12 bg-white"><span class="text-xs font-bold text-gray-300 block mb-8">02.</span><h4 class="font-bold uppercase mb-4 italic">დიზაინი</h4><p class="text-xs text-gray-400">ვიზუალური იდენტობის შექმნა.</p></div>
        <div class="minimal-card p-12 bg-white"><span class="text-xs font-bold text-gray-300 block mb-8">03.</span><h4 class="font-bold uppercase mb-4 italic">კოდი</h4><p class="text-xs text-gray-400">იდეის გადატანა კოდში.</p></div>
        <div class="minimal-card p-12 bg-white"><span class="text-xs font-bold text-gray-300 block mb-8">04.</span><h4 class="font-bold uppercase mb-4 italic">შედეგი</h4><p class="text-xs text-gray-400">პროექტის ჩაშვება.</p></div>
      </div>
    </div>
  </section>

  <section id="blog" class="py-24 px-6">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-sm font-bold uppercase tracking-[0.4em] text-gray-400 mb-16">ბლოგი</h2>
      <div class="grid md:grid-cols-3 gap-12">
        <div class="border-b border-matte pb-8 group cursor-pointer">
          <p class="text-[10px] text-gray-400 mb-4 uppercase">24 Mar, 2026</p>
          <h4 class="text-xl font-bold uppercase mb-4 group-hover:text-gray-500 transition">მინიმალისტური დიზაინის ძალა</h4>
          <p class="text-sm text-gray-400">რატომ არის ნაკლები მეტი თანამედროვე ვებში...</p>
        </div>
        <div class="border-b border-matte pb-8 group cursor-pointer">
          <p class="text-[10px] text-gray-400 mb-4 uppercase">18 Mar, 2026</p>
          <h4 class="text-xl font-bold uppercase mb-4 group-hover:text-gray-500 transition">SEO-ს მნიშვნელობა 2026-ში</h4>
          <p class="text-sm text-gray-400">როგორ მოვხვდეთ ძიების პირველ გვერდზე...</p>
        </div>
        <div class="border-b border-matte pb-8 group cursor-pointer">
          <p class="text-[10px] text-gray-400 mb-4 uppercase">12 Mar, 2026</p>
          <h4 class="text-xl font-bold uppercase mb-4 group-hover:text-gray-500 transition">E-commerce ტენდენციები</h4>
          <p class="text-sm text-gray-400">რა ელის ონლაინ გაყიდვების ბაზარს...</p>
        </div>
      </div>
    </div>
  </section>

  <footer id="contact" class="bg-matte-blue text-white pt-32 pb-12 px-6 overflow-hidden">
    <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-20">
      <div>
        <h2 class="text-7xl font-bold tracking-tighter mb-12 italic uppercase">Let's Create<br>History.</h2>
        <div class="space-y-4 text-gray-500 uppercase tracking-widest text-xs font-bold">
          <p>hello@identisite.ge</p>
          <p>Tbilisi, Georgia</p>
        </div>
      </div>
      <form class="space-y-8">
        <input type="text" placeholder="სახელი" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none text-sm">
        <input type="email" placeholder="ელ-ფოსტა" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none text-sm">
        <textarea placeholder="მესიჯი" rows="3" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none text-sm"></textarea>
        <button class="w-full border border-white py-5 text-[10px] font-bold uppercase tracking-[0.4em] hover:bg-white hover:text-matte-blue transition-all duration-500">გაგზავნა</button>
      </form>
    </div>
    <div class="max-w-7xl mx-auto mt-40 pt-8 border-t border-white/5 flex flex-col md:flex-row justify-between text-[10px] uppercase tracking-[0.2em] text-gray-600">
      <p>© 2026 IDENTISITE. PREMIUM DIGITAL AGENCY.</p>
      <div class="flex space-x-8 mt-4 md:mt-0 italic font-bold">
        <a href="#" class="hover:text-white transition">Instagram</a>
        <a href="#" class="hover:text-white transition">Behance</a>
      </div>
    </div>
  </footer>

  <script>
    function toggleAcc(element) {
      const items = document.querySelectorAll('.accordion-item');
      const isActive = element.classList.contains('active');
      items.forEach(item => item.classList.remove('active'));
      if (!isActive) element.classList.add('active');
    }

    const mobileBtn = document.getElementById('mobileMenuBtn');
    mobileBtn.addEventListener('click', () => {
      // მობილური მენიუს ლოგიკა
      alert('მენიუ აქტიურია');
    });
  </script>
</body>
</html>
