<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Premium UI</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', sans-serif; transition: background-color 0.5s ease, color 0.5s ease; }
    html { scroll-behavior: smooth; }

    /* Custom Scrollbar */
    ::-webkit-scrollbar { width: 5px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: #001a33; border-radius: 10px; }

    /* Accordion Logic */
    .accordion-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.6s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.4s ease;
      opacity: 0;
    }
    .accordion-item.active .accordion-content {
      max-height: 1200px;
      opacity: 1;
      padding-top: 2rem;
      padding-bottom: 4rem;
    }
    .accordion-item.active .plus-icon { transform: rotate(45deg); }
    
    /* Dark Mode Utility */
    .dark-mode { background-color: #050505 !important; color: #f8fafc !important; }
    .dark-mode .accordion-item { border-color: rgba(255,255,255,0.1) !important; }
    .dark-mode .bg-gray-50 { background-color: #0d0d0d !important; }
    .dark-mode .text-matte-navy { color: #38bdf8 !important; }
    .dark-mode .border-matte { border-color: #38bdf8 !important; }
    .dark-mode .btn-primary { background: #38bdf8; color: #000; }
    .dark-mode nav { background: rgba(5, 5, 5, 0.8) !important; border-bottom: 1px solid rgba(255,255,255,0.05); }

    .plus-icon { transition: transform 0.4s ease; }
    .accordion-item { border-top: 1px solid #eee; }
  </style>
</head>
<body class="bg-[#fcfcfc] text-[#0a0a0a] antialiased">

  <nav class="fixed top-0 w-full z-50 bg-white/80 backdrop-blur-xl px-8 py-5 border-b border-gray-100 transition-all">
    <div class="max-w-[1400px] mx-auto flex justify-between items-center">
      <a href="#" class="text-2xl font-black tracking-tighter text-matte-navy uppercase">Identisite</a>
      
      <div class="flex items-center space-x-8">
        <button onclick="toggleDarkMode()" class="p-2 rounded-full hover:bg-gray-100 transition dark:hover:bg-white/10" id="theme-toggle">
          <svg id="sun-icon" class="w-5 h-5 hidden" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364-6.364l-.707.707M6.343 17.657l-.707.707M16.95 16.95l.707.707M7.05 7.05l.707.707M12 8a4 4 0 100 8 4 4 0 000-8z"></path></svg>
          <svg id="moon-icon" class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path></svg>
        </button>
        <span class="text-xs font-bold opacity-30">GE / EN</span>
      </div>
    </div>
  </nav>

  <section class="min-h-screen flex items-center pt-20 px-8">
    <div class="max-w-[1400px] mx-auto grid lg:grid-cols-12 gap-12 items-center w-full">
      <div class="lg:col-span-8 space-y-10">
        <div>
          <h2 class="text-matte-navy font-bold uppercase tracking-[0.4em] text-xs mb-4">Identity starts here</h2>
          <h1 class="text-6xl md:text-8xl font-extrabold tracking-tighter leading-none mb-6">
            შენი ბიზნესის <br> იდენტობა <span class="text-gray-300 italic">იწყება აქ</span>
          </h1>
          <p class="text-xl md:text-2xl text-gray-500 max-w-2xl leading-relaxed">
            წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
          </p>
        </div>
        
        <div class="flex flex-wrap gap-5">
          <a href="#contact" class="bg-[#001a33] text-white px-10 py-5 rounded-full font-bold text-sm uppercase tracking-widest hover:scale-105 transition btn-primary">დავიწყოთ პროექტი</a>
          <a href="#portfolio" class="border border-gray-200 px-10 py-5 rounded-full font-bold text-sm uppercase tracking-widest hover:bg-gray-50 transition">შექმნილი პროექტები</a>
        </div>
      </div>
    </div>
  </section>

  <section id="portfolio" class="pb-40 px-8">
    <div class="max-w-[1400px] mx-auto">
      
      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-14 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-12">
            <span class="text-sm font-black text-gray-200 group-hover:text-matte-navy transition">01</span>
            <h2 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase group-hover:translate-x-4 transition-transform">ჩვენ შესახებ</h2>
          </div>
          <div class="plus-icon text-5xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid lg:grid-cols-2 gap-20">
            <p class="text-2xl leading-relaxed text-gray-500">
              IDENTISITE არის ადგილი, სადაც კოდი და კრეატივი ერთმანეთს ხვდება. ჩვენ არ ვაკეთებთ უბრალოდ საიტებს, ჩვენ ვქმნით თქვენი ბიზნესის ციფრულ ხერხემალს.
            </p>
            <div class="grid grid-cols-2 gap-6">
                <div class="bg-gray-50 p-10 rounded-[30px]">
                    <span class="block text-4xl font-black mb-2">150+</span>
                    <span class="text-xs uppercase font-bold text-gray-400">წარმატებული ქეისი</span>
                </div>
                <div class="bg-gray-50 p-10 rounded-[30px]">
                    <span class="block text-4xl font-black mb-2">100%</span>
                    <span class="text-xs uppercase font-bold text-gray-400">ხარისხის გარანტია</span>
                </div>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-14 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-12">
            <span class="text-sm font-black text-gray-200 group-hover:text-matte-navy transition">02</span>
            <h2 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase group-hover:translate-x-4 transition-transform">სერვისები</h2>
          </div>
          <div class="plus-icon text-5xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-3 gap-8">
            <div class="p-10 bg-gray-50 rounded-[40px] hover:bg-matte-navy hover:text-white transition group/card">
                <h3 class="text-2xl font-bold mb-4">UX/UI დიზაინი</h3>
                <p class="opacity-60 text-sm">თანამედროვე და ინტუიციური დიზაინი ნებისმიერი მოწყობილობისთვის.</p>
            </div>
            <div class="p-10 bg-gray-50 rounded-[40px] hover:bg-matte-navy hover:text-white transition">
                <h3 class="text-2xl font-bold mb-4">E-commerce</h3>
                <p class="opacity-60 text-sm">ონლაინ გაყიდვების სისტემები, რომლებიც რეალურ შედეგს გაძლევთ.</p>
            </div>
            <div class="p-10 bg-gray-50 rounded-[40px] hover:bg-matte-navy hover:text-white transition">
                <h3 class="text-2xl font-bold mb-4">ბრენდინგი</h3>
                <p class="opacity-60 text-sm">თქვენი ბრენდის ვიზუალური იდენტობის შექმნა და განვითარება.</p>
            </div>
          </div>
        </div>
      </div>

      <div id="contact" class="accordion-item border-b" onclick="toggleAccordion(this)">
        <div class="py-14 flex justify-between items-center cursor-pointer group">
          <div class="flex items-center space-x-12">
            <span class="text-sm font-black text-gray-200 group-hover:text-matte-navy transition">03</span>
            <h2 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase group-hover:translate-x-4 transition-transform">კონტაქტი</h2>
          </div>
          <div class="plus-icon text-5xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="max-w-3xl">
            <h4 class="text-5xl font-bold mb-10">დავიწყოთ <br> ახალი პროექტი.</h4>
            <form class="space-y-6">
                <div class="grid md:grid-cols-2 gap-6">
                    <input type="text" placeholder="თქვენი სახელი" class="w-full p-6 bg-gray-50 rounded-2xl outline-none focus:ring-2 ring-matte-navy/10 border-none">
                    <input type="email" placeholder="ელ-ფოსტა" class="w-full p-6 bg-gray-50 rounded-2xl outline-none focus:ring-2 ring-matte-navy/10 border-none">
                </div>
                <textarea placeholder="პროექტის აღწერა" rows="4" class="w-full p-6 bg-gray-50 rounded-2xl outline-none focus:ring-2 ring-matte-navy/10 border-none"></textarea>
                <button class="bg-[#001a33] text-white px-12 py-6 rounded-full font-bold uppercase tracking-widest btn-primary">გაგზავნა</button>
            </form>
          </div>
        </div>
      </div>

    </div>
  </section>

  <footer class="py-12 px-8 border-t border-gray-100 opacity-40">
    <div class="max-w-[1400px] mx-auto flex flex-col md:flex-row justify-between items-center">
      <p class="text-xs font-bold uppercase tracking-widest">© 2026 IDENTISITE / All rights reserved</p>
      <div class="flex space-x-8 text-xs font-bold uppercase tracking-widest mt-4 md:mt-0">
        <a href="#" class="hover:text-matte-navy">Facebook</a>
        <a href="#" class="hover:text-matte-navy">Instagram</a>
      </div>
    </div>
  </footer>

  <script>
    // Accordion Logic
    function toggleAccordion(element) {
      const isActive = element.classList.contains('active');
      
      // Close all other items
      document.querySelectorAll('.accordion-item').forEach(item => {
        item.classList.remove('active');
      });

      // Toggle current item
      if (!isActive) {
        element.classList.add('active');
      }
    }

    // Dark Mode Logic
    function toggleDarkMode() {
      const body = document.body;
      const moonIcon = document.getElementById('moon-icon');
      const sunIcon = document.getElementById('sun-icon');
      
      body.classList.toggle('dark-mode');
      
      if (body.classList.contains('dark-mode')) {
        moonIcon.classList.add('hidden');
        sunIcon.classList.remove('hidden');
      } else {
        moonIcon.classList.remove('hidden');
        sunIcon.classList.add('hidden');
      }
    }
  </script>

</body>
</html>
