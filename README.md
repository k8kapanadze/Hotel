<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Premium Identity</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', sans-serif; }
    html { scroll-behavior: smooth; }
    body { background-color: #fcfcfc; color: #0a0a0a; overflow-x: hidden; }

    /* Colors & Effects */
    .bg-matte-navy { background-color: #001a33; }
    .text-matte-navy { color: #001a33; }
    .border-matte { border-color: #001a33; }
    
    /* Premium Hover Lift */
    .hover-lift { transition: transform 0.3s ease, box-shadow 0.3s ease; }
    .hover-lift:hover { transform: translateY(-5px); }

    /* Accordion Custom Style */
    .accordion-item { border-top: 1px solid #e5e7eb; transition: all 0.5s ease; }
    .accordion-content { 
      max-height: 0; 
      overflow: hidden; 
      transition: max-height 0.6s cubic-bezier(0.4, 0, 0.2, 1); 
    }
    .accordion-item.active { background-color: #ffffff; }
    .accordion-item.active .accordion-content { max-height: 1200px; padding-bottom: 4rem; }
    .accordion-item.active .plus-icon { transform: rotate(135deg); color: #001a33; }
    
    /* Button Styles */
    .btn-primary {
      background: #001a33;
      color: white;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    .btn-primary:hover { background: #000; box-shadow: 0 10px 20px rgba(0,26,51,0.2); }
    
    .btn-secondary {
      border: 1px solid #001a33;
      color: #001a33;
      transition: all 0.3s ease;
    }
    .btn-secondary:hover { background: #f8f9fa; }

    /* Decorative Typography */
    .bg-text {
      position: absolute;
      font-size: 20vw;
      font-weight: 900;
      color: #f0f0f0;
      z-index: -1;
      line-height: 1;
      user-select: none;
    }
  </style>
</head>
<body class="antialiased">

  <header class="fixed top-0 w-full z-50 bg-white/80 backdrop-blur-md px-8 py-6 border-b border-gray-100">
    <div class="max-w-[1400px] mx-auto flex justify-between items-center">
      <a href="#" class="text-2xl font-black tracking-tighter text-matte-navy uppercase">Identisite</a>
      <div class="hidden md:flex space-x-12 items-center">
        <nav class="flex space-x-8 text-[11px] font-bold uppercase tracking-widest text-gray-400">
            <a href="#about" class="hover:text-matte-navy transition">About</a>
            <a href="#services" class="hover:text-matte-navy transition">Services</a>
            <a href="#contact" class="hover:text-matte-navy transition">Contact</a>
        </nav>
        <span class="text-xs font-bold text-matte-navy">GE / EN</span>
      </div>
    </div>
  </header>

  <section class="min-h-screen flex items-center relative pt-20 px-8">
    <div class="bg-text top-40 -right-20">IDEAS</div>
    <div class="max-w-[1400px] mx-auto grid lg:grid-cols-2 gap-12 items-center w-full">
      <div class="space-y-8">
        <div class="inline-block px-4 py-1 border border-matte text-[10px] font-bold uppercase tracking-[0.3em] text-matte-navy">Premium Digital Agency</div>
        <h1 class="text-5xl md:text-7xl font-extrabold tracking-tighter leading-[1.1] text-matte-navy">
          შენი ბიზნესის <br> იდენტობა <span class="text-gray-300 italic font-light">იწყება აქ</span>
        </h1>
        <p class="text-lg md:text-xl text-gray-500 leading-relaxed max-w-xl">
          წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
        </p>
        <div class="flex flex-wrap gap-4 pt-4">
          <a href="#contact" class="btn-primary px-10 py-5 rounded-full font-bold text-sm uppercase tracking-widest">დავიწყოთ პროექტი</a>
          <a href="#portfolio" class="btn-secondary px-10 py-5 rounded-full font-bold text-sm uppercase tracking-widest">შექმნილი პროექტები</a>
        </div>
      </div>
      <div class="hidden lg:block relative">
        <div class="w-full aspect-square bg-matte-navy rounded-[60px] relative overflow-hidden flex items-center justify-center group">
            <div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/asfalt-dark.png')] opacity-20"></div>
            <div class="text-white text-center z-10">
                <div class="text-[120px] font-black leading-none opacity-10 group-hover:opacity-20 transition">ID</div>
                <p class="text-xs uppercase tracking-[0.5em] font-light">Digital Architecture</p>
            </div>
            <div class="absolute -bottom-20 -left-20 w-64 h-64 border border-white/10 rounded-full"></div>
            <div class="absolute -top-10 -right-10 w-40 h-40 bg-white/5 rounded-full blur-3xl"></div>
        </div>
      </div>
    </div>
  </section>

  <section id="portfolio" class="pb-40 px-8">
    <div class="max-w-[1400px] mx-auto">
      
      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-10">
            <span class="text-xs font-black text-gray-200 group-hover:text-matte-navy transition">01</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">ჩვენ შესახებ</h2>
          </div>
          <span class="plus-icon text-4xl font-light transition-transform">+</span>
        </div>
        <div class="accordion-content">
          <div class="grid lg:grid-cols-2 gap-16 items-start pt-8">
            <div class="space-y-6">
                <p class="text-2xl text-matte-navy font-medium leading-snug">
                    IDENTISITE არ არის მხოლოდ სააგენტო, ეს არის ციფრული ლაბორატორია.
                </p>
                <p class="text-gray-500 leading-relaxed">
                    2019 წლიდან ჩვენი გუნდი ეხმარება ბიზნესებს იპოვონ საკუთარი ხმა ინტერნეტ სივრცეში. ჩვენი მიზანია შევქმნათ პროდუქტი, რომელიც დროს უძლებს.
                </p>
            </div>
            <div class="grid grid-cols-2 gap-4">
                <div class="bg-gray-50 p-8 rounded-3xl">
                    <span class="block text-3xl font-bold text-matte-navy mb-2">150+</span>
                    <span class="text-[10px] uppercase font-bold text-gray-400 tracking-widest">პროექტი</span>
                </div>
                <div class="bg-gray-50 p-8 rounded-3xl">
                    <span class="block text-3xl font-bold text-matte-navy mb-2">5+</span>
                    <span class="text-[10px] uppercase font-bold text-gray-400 tracking-widest">წელი</span>
                </div>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-10">
            <span class="text-xs font-black text-gray-200 group-hover:text-matte-navy transition">02</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">სერვისები</h2>
          </div>
          <span class="plus-icon text-4xl font-light transition-transform">+</span>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-3 gap-6 pt-8">
            <div class="p-10 border border-gray-100 rounded-[40px] hover:bg-matte-navy hover:text-white transition-all group/card">
                <h3 class="text-2xl font-bold mb-4">UX/UI Design</h3>
                <p class="text-sm opacity-60 mb-8">ინტუიციური და ესთეტიურად სრულყოფილი ინტერფეისები.</p>
                <div class="w-12 h-12 rounded-full border border-current flex items-center justify-center">→</div>
            </div>
            <div class="p-10 border border-gray-100 rounded-[40px] bg-matte-navy text-white hover-lift cursor-pointer">
                <h3 class="text-2xl font-bold mb-4">E-commerce</h3>
                <p class="text-sm opacity-60 mb-8">გაყიდვებზე და კონვერსიაზე ორიენტირებული პლატფორმები.</p>
                <div class="w-12 h-12 rounded-full border border-white/30 flex items-center justify-center">→</div>
            </div>
            <div class="p-10 border border-gray-100 rounded-[40px] hover:bg-matte-navy hover:text-white transition-all group/card">
                <h3 class="text-2xl font-bold mb-4">Branding</h3>
                <p class="text-sm opacity-60 mb-8">ლოგოდან სრულ ვიზუალურ სტრატეგიამდე.</p>
                <div class="w-12 h-12 rounded-full border border-current flex items-center justify-center">→</div>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-10">
            <span class="text-xs font-black text-gray-200 group-hover:text-matte-navy transition">03</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">პორტფოლიო</h2>
          </div>
          <span class="plus-icon text-4xl font-light transition-transform">+</span>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-2 gap-8 pt-8">
            <div class="group/item cursor-pointer">
                <div class="aspect-video bg-gray-100 rounded-[30px] overflow-hidden mb-4">
                    <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&q=80" class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700" alt="Work">
                </div>
                <h4 class="text-xl font-bold">Digital Identity Case 01</h4>
                <p class="text-xs text-gray-400 uppercase tracking-widest mt-1">Web Design / Development</p>
            </div>
            <div class="group/item cursor-pointer">
                <div class="aspect-video bg-gray-100 rounded-[30px] overflow-hidden mb-4">
                    <img src="https://images.unsplash.com/photo-1522542550221-31fd19575a2d?auto=format&fit=crop&q=80" class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700" alt="Work">
                </div>
                <h4 class="text-xl font-bold">E-commerce Platform 02</h4>
                <p class="text-xs text-gray-400 uppercase tracking-widest mt-1">Development / UX Research</p>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-10">
            <span class="text-xs font-black text-gray-200 group-hover:text-matte-navy transition">04</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">პროცესი</h2>
          </div>
          <span class="plus-icon text-4xl font-light transition-transform">+</span>
        </div>
        <div class="accordion-content pt-8">
            <div class="flex flex-col md:flex-row justify-between space-y-8 md:space-y-0 md:space-x-12">
                <div class="flex-1 border-t border-gray-100 pt-6">
                    <span class="text-[10px] font-black text-matte-navy">01/DISCOVER</span>
                    <h5 class="font-bold my-2">კვლევა</h5>
                    <p class="text-xs text-gray-400">ბიზნესის ანალიზი</p>
                </div>
                <div class="flex-1 border-t border-gray-100 pt-6">
                    <span class="text-[10px] font-black text-matte-navy">02/DESIGN</span>
                    <h5 class="font-bold my-2">დიზაინი</h5>
                    <p class="text-xs text-gray-400">ვიზუალიზაცია</p>
                </div>
                <div class="flex-1 border-t border-gray-100 pt-6">
                    <span class="text-[10px] font-black text-matte-navy">03/BUILD</span>
                    <h5 class="font-bold my-2">კოდი</h5>
                    <p class="text-xs text-gray-400">პროგრამირება</p>
                </div>
                <div class="flex-1 border-t border-gray-100 pt-6">
                    <span class="text-[10px] font-black text-matte-navy">04/LIVE</span>
                    <h5 class="font-bold my-2">ლაივი</h5>
                    <p class="text-xs text-gray-400">ჩაშვება</p>
                </div>
            </div>
        </div>
      </div>

      <div id="contact" class="accordion-item border-b" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-10">
            <span class="text-xs font-black text-gray-200 group-hover:text-matte-navy transition">05</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">კონტაქტი</h2>
          </div>
          <span class="plus-icon text-4xl font-light transition-transform">+</span>
        </div>
        <div class="accordion-content pt-8">
          <div class="grid lg:grid-cols-2 gap-20 items-center">
            <div>
                <h3 class="text-4xl font-bold mb-6">მოდით, <br> ვისაუბროთ.</h3>
                <div class="space-y-4">
                    <a href="mailto:hello@identisite.ge" class="block text-2xl font-light hover:text-matte-navy transition">hello@identisite.ge</a>
                    <p class="text-gray-400">+995 555 00 00 00</p>
                </div>
            </div>
            <form class="space-y-4">
                <input type="text" placeholder="სახელი" class="w-full p-5 bg-gray-50 rounded-2xl border-none outline-none focus:ring-1 ring-matte-navy">
                <textarea placeholder="პროექტის შესახებ" rows="4" class="w-full p-5 bg-gray-50 rounded-2xl border-none outline-none focus:ring-1 ring-matte-navy"></textarea>
                <button class="btn-primary px-12 py-5 rounded-full w-full font-bold uppercase tracking-widest text-xs">გაგზავნა</button>
            </form>
          </div>
        </div>
      </div>

    </div>
  </section>

  <footer class="py-12 px-8 border-t border-gray-50">
    <div class="max-w-[1400px] mx-auto flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
      <p class="text-[10px] font-bold text-gray-300 uppercase tracking-[0.3em]">© 2026 IDENTISITE / Identity into Web</p>
      <div class="flex space-x-8 text-[10px] font-bold uppercase tracking-widest">
        <a href="#" class="hover:text-matte-navy transition">Facebook</a>
        <a href="#" class="hover:text-matte-navy transition">Instagram</a>
        <a href="#" class="hover:text-matte-navy transition">LinkedIn</a>
      </div>
    </div>
  </footer>

  <script>
    function toggleAccordion(element) {
      // If you want only one open at a time, uncomment below:
      /*
      document.querySelectorAll('.accordion-item').forEach(item => {
        if (item !== element) item.classList.remove('active');
      });
      */
      element.classList.toggle('active');
    }
  </script>
</body>
</html>
