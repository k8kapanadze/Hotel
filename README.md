<!doctype html>
<html lang="ka" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>IDENTISITE | საიტების დამზადება, ვებსაიტების გაკეთება</title>
  <meta name="description" content="IDENTISITE — პრემიუმ ვებ სააგენტო. თქვენი ბრენდის ციფრული იდენტობა."/>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700&family=Outfit:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            'navy-dark':   '#0f172a',
            'navy-darker': '#020617',
            'blue-deep':   '#1e3a8a',
            'blue-primary':'#3b82f6',
            'blue-light':  '#60a5fa',
            'gray-text':   '#64748b',
            'gray-light':  '#94a3b8',
            'gray-lighter':'#e2e8f0',
          },
          fontFamily: {
            sans: ['"Noto Sans Georgian"', '"Outfit"', 'system-ui', 'sans-serif'],
          },
        }
      }
    }
  </script>
  <style>
    body { font-feature-settings: "liga" 1, "calt" 1; }
    .gradient-text {
      background: linear-gradient(90deg, #3b82f6, #60a5fa);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .card-hover {
      transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
    }
    .card-hover:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 40px -12px rgba(59,130,246,0.18);
    }
    #theme-toggle svg.sun { display: block; }
    #theme-toggle svg.moon { display: none; }
    .dark #theme-toggle svg.sun { display: none; }
    .dark #theme-toggle svg.moon { display: block; }
    .reveal-text {
      opacity: 0;
      transform: translateY(20px);
      transition: all 1.2s cubic-bezier(0.215, 0.61, 0.355, 1);
    }
    .reveal-text.visible {
      opacity: 1;
      transform: translateY(0);
    }
    .subtext {
      opacity: 0;
      transition: opacity 1.8s ease-out 0.6s;
    }
    .subtext.visible {
      opacity: 0.9;
    }
  </style>
</head>
<body class="bg-white text-navy-dark antialiased">

  <!-- Navigation -->
  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-lighter transition-all">
    <div class="max-w-7xl mx-auto px-6 lg:px-8">
      <div class="flex justify-between items-center h-20">
        <a href="#" class="flex items-center gap-3">
          <div class="w-10 h-10 bg-blue-deep rounded-xl flex items-center justify-center text-white font-bold text-xl shadow-md">I</div>
          <span class="text-2xl font-bold tracking-tight">IDENTISITE</span>
        </a>

        <div class="hidden lg:flex items-center gap-10">
          <a href="#home"     class="font-medium text-gray-text hover:text-blue-primary transition-colors">მთავარი</a>
          <a href="#services" class="font-medium text-gray-text hover:text-blue-primary transition-colors">სერვისები</a>
          <a href="#portfolio"class="font-medium text-gray-text hover:text-blue-primary transition-colors">პორტფოლიო</a>
          <a href="#contact"  class="font-medium text-gray-text hover:text-blue-primary transition-colors">კონტაქტი</a>
        </div>

        <div class="flex items-center gap-5">
          <button id="theme-toggle" class="p-2 rounded-lg hover:bg-gray-lighter/40 transition-colors" aria-label="შეცვალე თემა">
            <svg class="sun w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"/></svg>
            <svg class="moon w-5 h-5 hidden" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"/></svg>
          </button>
          <a href="#contact" class="px-6 py-3 bg-blue-primary text-white font-semibold rounded-xl hover:bg-blue-deep transition-all shadow-md hover:shadow-lg">დავიწყოთ</a>
        </div>
      </div>
    </div>
  </nav>

  <!-- Hero -->
  <section id="home" class="min-h-screen flex items-center pt-24 pb-20 bg-white">
    <div class="max-w-7xl mx-auto px-6 lg:px-8 w-full">
      <div class="max-w-4xl">
        <h1 class="text-5xl sm:text-6xl lg:text-7xl font-extrabold leading-tight tracking-tight">
          <span class="reveal-text block">შენი ბიზნესის</span>
          <span class="reveal-text block gradient-text">იდენტობა იწყება აქ</span>
        </h1>

        <p class="subtext mt-8 text-xl sm:text-2xl text-gray-text max-w-3xl leading-relaxed">
          წაშალეთ ზღვარი იდეასა და რეალობას შორის.<br>
          ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
        </p>

        <div class="mt-12 flex flex-wrap gap-5">
          <a href="#contact" class="px-8 py-4 bg-blue-primary text-white font-semibold rounded-xl hover:bg-blue-deep transition-all shadow-lg hover:shadow-xl text-lg">დავიწყოთ პროექტი</a>
          <a href="#portfolio" class="px-8 py-4 border-2 border-blue-deep text-blue-deep font-semibold rounded-xl hover:bg-blue-deep hover:text-white transition-all text-lg">ნამუშევრები</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Services -->
  <section id="services" class="py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-4xl sm:text-5xl font-bold">რას ვაკეთებთ</h2>
        <p class="mt-5 text-xl text-gray-text">სრული ციკლის ციფრული გადაწყვეტები თანამედროვე ბიზნესებისთვის</p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="card-hover bg-white p-8 rounded-2xl border border-gray-lighter shadow-sm">
          <div class="w-14 h-14 bg-blue-deep rounded-xl flex items-center justify-center text-white mb-6 text-2xl font-bold">01</div>
          <h3 class="text-2xl font-bold mb-4">კორპორატიული საიტები</h3>
          <p class="text-gray-text">უნიკალური დიზაინი • SEO მზად • სწრაფი ჩატვირთვა</p>
        </div>

        <div class="card-hover bg-white p-8 rounded-2xl border border-gray-lighter shadow-sm">
          <div class="w-14 h-14 bg-blue-deep rounded-xl flex items-center justify-center text-white mb-6 text-2xl font-bold">02</div>
          <h3 class="text-2xl font-bold mb-4">ონლაინ მაღაზიები</h3>
          <p class="text-gray-text">გადახდის სისტემები • ადმინ პანელი • მობილური ადაპტაცია</p>
        </div>

        <div class="card-hover bg-white p-8 rounded-2xl border border-gray-lighter shadow-sm">
          <div class="w-14 h-14 bg-blue-deep rounded-xl flex items-center justify-center text-white mb-6 text-2xl font-bold">03</div>
          <h3 class="text-2xl font-bold mb-4">Landing Page</h3>
          <p class="text-gray-text">მაღალი კონვერსია • A/B ტესტირება • სწრაფი შედეგი</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-24 bg-white">
    <div class="max-w-5xl mx-auto px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-5xl font-bold">დავიწყოთ თანამშრომლობა</h2>
        <p class="mt-5 text-xl text-gray-text">მოგვწერეთ — უფასო კონსულტაცია 24 საათის განმავლობაში</p>
      </div>

      <form class="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto">
        <input type="text" placeholder="სახელი" required class="w-full px-6 py-4 rounded-xl border border-gray-lighter focus:border-blue-primary outline-none transition-all">
        <input type="email" placeholder="ელ.ფოსტა" required class="w-full px-6 py-4 rounded-xl border border-gray-lighter focus:border-blue-primary outline-none transition-all">
        <textarea placeholder="პროექტის აღწერა" rows="5" required class="md:col-span-2 w-full px-6 py-4 rounded-xl border border-gray-lighter focus:border-blue-primary outline-none transition-all resize-none"></textarea>
        <button type="submit" class="md:col-span-2 bg-blue-primary text-white font-semibold py-5 rounded-xl hover:bg-blue-deep transition-all shadow-lg text-lg">გაგზავნა</button>
      </form>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-navy-darker text-gray-lighter py-16">
    <div class="max-w-7xl mx-auto px-6 lg:px-8 text-center">
      <p class="text-lg">© 2026 IDENTISITE — თქვენი ციფრული იდენტობის პარტნიორი</p>
    </div>
  </footer>

  <script>
    // Theme toggle
    const toggle = document.getElementById('theme-toggle');
    toggle.addEventListener('click', () => {
      document.documentElement.classList.toggle('dark');
      localStorage.theme = document.documentElement.classList.contains('dark') ? 'dark' : 'light';
    });

    // Respect system preference or saved choice
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      document.documentElement.classList.add('dark');
    }

    // Reveal animation on load
    window.addEventListener('load', () => {
      document.querySelectorAll('.reveal-text').forEach((el,i) => {
        setTimeout(() => el.classList.add('visible'), 200 + i*300);
      });
      setTimeout(() => document.querySelector('.subtext').classList.add('visible'), 1200);
    });
  </script>
</body>
</html>
