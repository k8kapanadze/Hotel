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
      --soft-gray: #f8f8f8;
      --border-color: #eeeeee;
    }

    .bg-matte-blue { background-color: var(--matte-blue); }
    .text-matte-blue { color: var(--matte-blue); }
    .border-matte { border-color: var(--border-color); }

    /* აკორდეონის ლოგიკა */
    .accordion-content {
      max-height: 0;
      transition: max-height 0.5s cubic-bezier(0, 1, 0, 1);
      overflow: hidden;
    }
    .accordion-item.active .accordion-content {
      max-height: 1000px;
      transition: max-height 1s ease-in-out;
    }
    .accordion-item.active .plus-icon { transform: rotate(45deg); }

    /* მინიმალისტური ბარათები */
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
      filter: grayscale(100%) brightness(0.5) sepia(100%) hue-rotate(190deg) saturate(300%);
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .animate-up { animation: fadeInUp 0.6s ease-out forwards; }
  </style>
</head>
<body class="bg-white text-[#050505]">

  <nav id="navbar" class="fixed top-0 w-full z-50 bg-white/90 backdrop-blur-md border-b border-matte">
    <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center">
      <a href="#home" class="flex items-center space-x-3">
        <div class="w-10 h-10 bg-matte-blue flex items-center justify-center text-white font-bold italic">I</div>
        <span class="text-xl font-bold tracking-tighter text-matte-blue">IDENTISITE</span>
      </a>
      
      <div class="hidden lg:flex items-center space-x-10 text-[11px] uppercase tracking-[0.2em] font-bold">
        <a href="#home" class="hover:text-gray-400 transition" data-lang="ka">მთავარი</a>
        <a href="#services" class="hover:text-gray-400 transition" data-lang="ka">სერვისები</a>
        <a href="#process" class="hover:text-gray-400 transition" data-lang="ka">პროცესი</a>
        <a href="#contact" class="hover:text-gray-400 transition" data-lang="ka">კონტაქტი</a>
      </div>

      <div class="flex items-center space-x-6">
        <button id="langSwitch" class="text-[10px] font-bold border border-matte px-3 py-1 hover:bg-matte-blue hover:text-white transition">EN</button>
        <button id="mobileMenuBtn" class="lg:hidden">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M4 8h16M4 16h16" stroke-width="2"/></svg>
        </button>
      </div>
    </div>
  </nav>

  <div id="mobileMenu" class="fixed inset-0 bg-white z-[60] hidden flex-col items-center justify-center space-y-8 text-2xl uppercase tracking-widest font-bold">
    <button onclick="toggleMenu()" class="absolute top-8 right-8 text-4xl">&times;</button>
    <a href="#home" onclick="toggleMenu()">მთავარი</a>
    <a href="#services" onclick="toggleMenu()">სერვისები</a>
    <a href="#process" onclick="toggleMenu()">პროცესი</a>
    <a href="#contact" onclick="toggleMenu()">კონტაქტი</a>
  </div>

  <section id="home" class="pt-48 pb-32 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="inline-block bg-matte-blue text-white text-[10px] font-bold px-4 py-1 mb-8 uppercase tracking-widest animate-up">
        Premium Web Studio
      </div>
      <h1 class="text-6xl md:text-9xl font-bold tracking-tighter leading-[0.85] mb-12 animate-up" style="animation-delay: 0.1s;">
        IDENTITY<br><span class="text-gray-200">INTO CODE.</span>
      </h1>
      
      <div class="grid lg:grid-cols-2 gap-12 items-end">
        <p class="text-xl text-gray-500 max-w-lg animate-up" style="animation-delay: 0.2s;" data-lang="ka">
          ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს გამოარჩევს. მინიმალისტური დიზაინი, მაქსიმალური ფუნქციონალით.
        </p>
        
        <div class="flex space-x-12 border-t border-matte pt-8 animate-up" style="animation-delay: 0.3s;">
          <div>
            <div class="text-3xl font-bold text-matte-blue">150+</div>
            <div class="text-[10px] uppercase tracking-widest text-gray-400" data-lang="ka">პროექტი</div>
          </div>
          <div>
            <div class="text-3xl font-bold text-matte-blue">98%</div>
            <div class="text-[10px] uppercase tracking-widest text-gray-400" data-lang="ka">კმაყოფილება</div>
          </div>
          <div>
            <div class="text-3xl font-bold text-matte-blue">5+</div>
            <div class="text-[10px] uppercase tracking-widest text-gray-400" data-lang="ka">წელი</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="px-6 mb-32">
    <div class="max-w-7xl mx-auto h-[500px] bg-matte-blue relative overflow-hidden">
      <img src="https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&q=80" alt="Studio" class="absolute inset-0 w-full h-full object-cover blue-filter opacity-50">
      <div class="absolute inset-0 flex items-center justify-center border border-white/5">
        <div class="text-white/10 text-[20vw] font-bold select-none italic">IDENTISITE</div>
      </div>
    </div>
  </section>

  <section id="services" class="py-24 px-6 border-t border-matte">
    <div class="max-w-7xl mx-auto grid lg:grid-cols-12 gap-16">
      <div class="lg:col-span-4">
        <h2 class="text-xs font-bold uppercase tracking-[0.4em] text-gray-400 mb-4" data-lang="ka">სერვისები</h2>
        <h3 class="text-4xl font-bold tracking-tighter" data-lang="ka">რას ვაკეთებთ</h3>
      </div>
      <div class="lg:col-span-8 space-y-2">
        
        <div class="accordion-item border-b border-matte cursor-pointer group" onclick="toggleAcc(this)">
          <div class="py-8 flex justify-between items-center group-hover:px-4 transition-all">
            <span class="text-2xl font-bold tracking-tight uppercase">Corporate Websites</span>
            <span class="plus-icon text-3xl transition-transform duration-500">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-8 text-gray-500 max-w-xl" data-lang="ka">
              უნიკალური კორპორატიული საიტები, რომლებიც ორიენტირებულია ბრენდის პრესტიჟზე და კონვერსიაზე.
            </p>
          </div>
        </div>

        <div class="accordion-item border-b border-matte cursor-pointer group" onclick="toggleAcc(this)">
          <div class="py-8 flex justify-between items-center group-hover:px-4 transition-all">
            <span class="text-2xl font-bold tracking-tight uppercase">E-commerce solutions</span>
            <span class="plus-icon text-3xl transition-transform duration-500">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-8 text-gray-500 max-w-xl" data-lang="ka">
              სრულფასოვანი ონლაინ მაღაზიები თანამედროვე გადახდის სისტემებით.
            </p>
          </div>
        </div>

        <div class="accordion-item border-b border-matte cursor-pointer group" onclick="toggleAcc(this)">
          <div class="py-8 flex justify-between items-center group-hover:px-4 transition-all">
            <span class="text-2xl font-bold tracking-tight uppercase">UI/UX Design</span>
            <span class="plus-icon text-3xl transition-transform duration-500">+</span>
          </div>
          <div class="accordion-content">
            <p class="pb-8 text-gray-500 max-w-xl" data-lang="ka">
              ინტუიციური და სუფთა დიზაინი საუკეთესო მომხმარებლის გამოცდილებისთვის.
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>

  <section id="process" class="py-32 bg-white px-6">
    <div class="max-w-7xl mx-auto">
      <div class="grid md:grid-cols-4 gap-px bg-gray-100 border border-gray-100">
        
        <div class="minimal-card p-12 bg-white">
          <span class="text-[10px] font-bold text-gray-300 mb-12 block">01 / ANALYZE</span>
          <h4 class="text-xl font-bold mb-4 italic">კვლევა</h4>
          <p class="text-sm text-gray-400 leading-relaxed" data-lang="ka">ბიზნეს მიზნების და აუდიტორიის დეტალური შესწავლა.</p>
        </div>

        <div class="minimal-card p-12 bg-white">
          <span class="text-[10px] font-bold text-gray-300 mb-12 block">02 / DESIGN</span>
          <h4 class="text-xl font-bold mb-4 italic">დიზაინი</h4>
          <p class="text-sm text-gray-400 leading-relaxed" data-lang="ka">ვიზუალური კონცეფციის და პროტოტიპის შექმნა.</p>
        </div>

        <div class="minimal-card p-12 bg-white">
          <span class="text-[10px] font-bold text-gray-300 mb-12 block">03 / BUILD</span>
          <h4 class="text-xl font-bold mb-4 italic">კოდი</h4>
          <p class="text-sm text-gray-400 leading-relaxed" data-lang="ka">მაღალი ხარისხის კოდი და ფუნქციური გამართვა.</p>
        </div>

        <div class="minimal-card p-12 bg-white">
          <span class="text-[10px] font-bold text-gray-300 mb-12 block">04 / LIVE</span>
          <h4 class="text-xl font-bold mb-4 italic">გაშვება</h4>
          <p class="text-sm text-gray-400 leading-relaxed" data-lang="ka">ტესტირება და პროექტის საბოლოო ჩაშვება.</p>
        </div>

      </div>
    </div>
  </section>

  <footer id="contact" class="bg-matte-blue text-white pt-32 pb-12 px-6 overflow-hidden relative">
    <div class="max-w-7xl mx-auto relative z-10">
      <div class="grid lg:grid-cols-2 gap-20">
        <div>
          <h2 class="text-6xl md:text-8xl font-bold tracking-tighter mb-12 italic">LET'S<br>TALK.</h2>
          <div class="space-y-4 text-gray-400 uppercase tracking-widest text-sm font-bold">
            <p>hello@identisite.ge</p>
            <p>+995 5XX XX XX XX</p>
          </div>
        </div>
        
        <form class="space-y-6">
          <input type="text" placeholder="თქვენი სახელი" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none">
          <input type="email" placeholder="ელ-ფოსტა" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none">
          <textarea placeholder="პროექტის შესახებ" rows="4" class="w-full bg-transparent border-b border-white/10 py-4 focus:border-white transition outline-none"></textarea>
          <button class="px-12 py-5 border border-white text-[10px] font-bold uppercase tracking-[0.3em] hover:bg-white hover:text-matte-blue transition-all duration-500">
            გაგზავნა
          </button>
        </form>
      </div>

      <div class="mt-40 pt-8 border-t border-white/5 flex flex-col md:flex-row justify-between text-[10px] uppercase tracking-widest text-gray-500">
        <p>© 2026 IDENTISITE. ALL RIGHTS RESERVED.</p>
        <div class="flex space-x-8 mt-4 md:mt-0">
          <a href="#" class="hover:text-white transition">Instagram</a>
          <a href="#" class="hover:text-white transition">Behance</a>
          <a href="#" class="hover:text-white transition">LinkedIn</a>
        </div>
      </div>
    </div>
  </footer>

  <script>
    // აკორდეონის ფუნქცია
    function toggleAcc(element) {
      const items = document.querySelectorAll('.accordion-item');
      const isActive = element.classList.contains('active');
      
      items.forEach(item => item.classList.remove('active'));
      if (!isActive) {
        element.classList.add('active');
      }
    }

    // მობილური მენიუ
    function toggleMenu() {
      const menu = document.getElementById('mobileMenu');
      menu.classList.toggle('hidden');
      menu.classList.toggle('flex');
    }
    document.getElementById('mobileMenuBtn').addEventListener('click', toggleMenu);

    // ნავიგაციის სქროლი
    window.addEventListener('scroll', () => {
      const nav = document.getElementById('navbar');
      if (window.scrollY > 50) {
        nav.classList.add('py-2');
      } else {
        nav.classList.remove('py-2');
      }
    });

    // ენის შეცვლის იმიტაცია
    const langBtn = document.getElementById('langSwitch');
    langBtn.addEventListener('click', () => {
      langBtn.innerText = langBtn.innerText === 'EN' ? 'KA' : 'EN';
    });
  </script>
</body>
</html>
