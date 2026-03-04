<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Identity Engineering</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700;900&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', sans-serif; transition: background-color 0.4s ease, color 0.4s ease, border-color 0.4s ease; }
    html { scroll-behavior: smooth; }

    /* Scroll Progress Bar */
    #progress-bar {
      position: fixed; top: 0; left: 0; height: 3px; background: #001a33; z-index: 100; width: 0%;
    }

    /* Dark Mode Styling */
    .dark-mode { background-color: #050505 !important; color: #f1f5f9 !important; }
    .dark-mode #progress-bar { background: #38bdf8; }
    .dark-mode .accordion-item { border-color: rgba(255,255,255,0.05) !important; }
    .dark-mode .bg-soft { background-color: #0d0d0d !important; }
    .dark-mode .text-matte { color: #38bdf8 !important; }
    .dark-mode .calc-card { background: #111 !important; border-color: #222 !important; }

    /* Accordion Logic */
    .accordion-content {
      max-height: 0; overflow: hidden;
      transition: max-height 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .accordion-item.active .accordion-content { max-height: 1000px; padding-bottom: 4rem; }
    .accordion-item.active .plus-icon { transform: rotate(45deg); color: #001a33; }
    .dark-mode .accordion-item.active .plus-icon { color: #38bdf8; }

    /* Marquee Tech Stack */
    @keyframes scroll { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
    .tech-marquee { display: flex; width: 200%; animation: scroll 30s linear infinite; }
    
    /* Interactive Button */
    .btn-main {
      position: relative; overflow: hidden;
      border: 1px solid #001a33; padding: 14px 32px; border-radius: 100px;
      font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase;
    }
    .btn-main:hover { background: #001a33; color: white; }
    .dark-mode .btn-main { border-color: #38bdf8; color: #38bdf8; }
    .dark-mode .btn-main:hover { background: #38bdf8; color: #000; }
  </style>
</head>
<body class="bg-white text-[#111] antialiased">

  <div id="progress-bar"></div>

  <nav class="fixed top-0 w-full z-50 bg-white/80 backdrop-blur-md border-b border-gray-50 px-8 py-5">
    <div class="max-w-[1500px] mx-auto flex justify-between items-center">
      <a href="#" class="text-2xl font-black tracking-tighter uppercase text-matte">Identisite</a>
      
      <div class="flex items-center space-x-8">
        <button onclick="toggleDarkMode()" class="flex items-center space-x-2 group">
          <div class="w-10 h-5 bg-gray-200 dark:bg-gray-800 rounded-full relative p-1 transition-colors" id="toggle-bg">
            <div class="w-3 h-3 bg-white rounded-full absolute left-1 top-1 transition-transform" id="toggle-dot"></div>
          </div>
          <span class="text-[10px] font-bold uppercase tracking-widest opacity-50 group-hover:opacity-100">Night Mode</span>
        </button>
      </div>
    </div>
  </nav>

  <section class="min-h-screen flex items-center pt-20 px-8">
    <div class="max-w-[1500px] mx-auto grid lg:grid-cols-2 gap-16 w-full">
      <div class="space-y-8">
        <div class="flex items-center space-x-4">
            <div class="h-[1px] w-12 bg-gray-300"></div>
            <span class="text-[11px] font-bold uppercase tracking-[0.3em] text-gray-400">Digital Architecture Studio</span>
        </div>
        <h1 class="text-6xl md:text-8xl font-black tracking-tighter leading-none">
          შენი ბიზნესის <br> იდენტობა <span class="opacity-20 italic font-light">იწყება აქ</span>
        </h1>
        <p class="text-xl text-gray-400 max-w-xl leading-relaxed">
          წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
        </p>
        <div class="flex items-center space-x-6">
          <a href="#contact" class="btn-main">დავიწყოთ პროექტი</a>
          <a href="#portfolio" class="text-xs font-bold uppercase tracking-widest border-b border-black dark:border-white pb-1">შექმნილი პროექტები</a>
        </div>
      </div>
    </div>
  </section>

  <section class="py-24 px-8 bg-gray-50 bg-soft border-y border-gray-100">
    <div class="max-w-[1500px] mx-auto">
      <div class="mb-12">
        <h3 class="text-xs font-black uppercase tracking-[0.4em] text-matte mb-4">01 / Identify Your Needs</h3>
        <h2 class="text-4xl font-bold tracking-tighter">გააჟღერე იდეა</h2>
      </div>
      
      <div class="grid md:grid-cols-3 gap-6">
        <div onclick="selectService(this, 'UI/UX')" class="calc-card p-10 bg-white border border-gray-200 rounded-3xl cursor-pointer hover:border-matte transition group">
            <h4 class="text-xl font-bold mb-2">UI/UX დიზაინი</h4>
            <p class="text-sm text-gray-400">ვიზუალური იდენტობის შექმნა</p>
        </div>
        <div onclick="selectService(this, 'Web')" class="calc-card p-10 bg-white border border-gray-200 rounded-3xl cursor-pointer hover:border-matte transition">
            <h4 class="text-xl font-bold mb-2">Web Development</h4>
            <p class="text-sm text-gray-400">მაღალტექნოლოგიური კოდირება</p>
        </div>
        <div onclick="selectService(this, 'Branding')" class="calc-card p-10 bg-white border border-gray-200 rounded-3xl cursor-pointer hover:border-matte transition">
            <h4 class="text-xl font-bold mb-2">Branding</h4>
            <p class="text-sm text-gray-400">ბრენდის სრული სტრატეგია</p>
        </div>
      </div>
      
      <div class="mt-12 flex items-center justify-between p-8 border border-dashed border-gray-200 rounded-3xl">
        <p class="text-gray-400 font-medium">შერჩეული: <span id="selected-service" class="text-matte font-bold">---</span></p>
        <a href="#contact" class="text-xs font-black uppercase border-b-2 border-matte">მიიღე შეთავაზება →</a>
      </div>
    </div>
  </section>

  <section id="portfolio" class="py-10 px-8">
    <div class="max-w-[1500px] mx-auto">
      
      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer border-t border-gray-100 group">
          <div class="flex items-center space-x-12">
            <span class="text-[10px] font-black opacity-20 group-hover:opacity-100 transition">02</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">ჩვენ შესახებ</h2>
          </div>
          <div class="plus-icon text-4xl font-light transition-transform">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid lg:grid-cols-2 gap-16">
            <div class="space-y-6">
                <p class="text-2xl leading-relaxed">ჩვენი გუნდი აერთიანებს დიზაინერებსა და დეველოპერებს, რომელთა მიზანია ციფრული სტანდარტების შეცვლა.</p>
                <div class="flex space-x-12 pt-4">
                    <div><h5 class="text-3xl font-black">150+</h5><p class="text-[10px] text-gray-400 uppercase tracking-widest">პროექტი</p></div>
                    <div><h5 class="text-3xl font-black">20+</h5><p class="text-[10px] text-gray-400 uppercase tracking-widest">პარტნიორი</p></div>
                </div>
            </div>
          </div>
        </div>
      </div>

      <div id="contact" class="accordion-item" onclick="toggleAccordion(this)">
        <div class="py-12 flex justify-between items-center cursor-pointer border-t border-gray-100 group">
          <div class="flex items-center space-x-12">
            <span class="text-[10px] font-black opacity-20 group-hover:opacity-100 transition">03</span>
            <h2 class="text-3xl md:text-5xl font-bold tracking-tighter uppercase">კონტაქტი</h2>
          </div>
          <div class="plus-icon text-4xl font-light transition-transform">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid lg:grid-cols-2 gap-16">
            <div class="space-y-8">
                <h4 class="text-4xl font-bold">მოგვწერეთ. <br> ერთად დავიწყოთ.</h4>
                <div class="text-xl opacity-50">hello@identisite.ge</div>
            </div>
            <form class="space-y-4">
                <input type="text" placeholder="სახელი" class="w-full p-5 bg-gray-50 bg-soft rounded-2xl border-none outline-none focus:ring-1 ring-gray-200">
                <textarea placeholder="თქვენი იდეა" rows="4" class="w-full p-5 bg-gray-50 bg-soft rounded-2xl border-none outline-none focus:ring-1 ring-gray-200"></textarea>
                <button class="btn-main w-full">გაგზავნა</button>
            </form>
          </div>
        </div>
      </div>

    </div>
  </section>

  <div class="overflow-hidden border-y border-gray-100 py-10 opacity-30 grayscale hover:grayscale-0 transition-all">
    <div class="tech-marquee space-x-20">
      <span class="text-3xl font-black uppercase tracking-tighter">React</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Tailwind</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Node.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Figma</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Python</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Next.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter">React</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Tailwind</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Node.js</span>
      <span class="text-3xl font-black uppercase tracking-tighter">Figma</span>
    </div>
  </div>

  <footer class="py-12 px-8 text-center md:text-left">
    <div class="max-w-[1500px] mx-auto flex flex-col md:flex-row justify-between items-center text-[10px] font-bold uppercase tracking-[0.4em] opacity-40">
      <p>© 2026 IDENTISITE / Identity into Web</p>
      <div class="flex space-x-8 mt-4 md:mt-0">
        <a href="#">Instagram</a>
        <a href="#">LinkedIn</a>
      </div>
    </div>
  </footer>

  <script>
    // Scroll Progress
    window.onscroll = function() {
      let winScroll = document.body.scrollTop || document.documentElement.scrollTop;
      let height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
      let scrolled = (winScroll / height) * 100;
      document.getElementById("progress-bar").style.width = scrolled + "%";
    };

    // Dark Mode
    function toggleDarkMode() {
      const body = document.body;
      const dot = document.getElementById('toggle-dot');
      body.classList.toggle('dark-mode');
      
      if(body.classList.contains('dark-mode')) {
        dot.style.transform = "translateX(20px)";
      } else {
        dot.style.transform = "translateX(0px)";
      }
    }

    // Accordion
    function toggleAccordion(element) {
      const isActive = element.classList.contains('active');
      document.querySelectorAll('.accordion-item').forEach(item => item.classList.remove('active'));
      if(!isActive) element.classList.add('active');
    }

    // Calculator Logic
    function selectService(el, name) {
      document.querySelectorAll('.calc-card').forEach(c => c.style.borderColor = '');
      el.style.borderColor = '#001a33';
      document.getElementById('selected-service').innerText = name;
    }
  </script>

</body>
</html>
