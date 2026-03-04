<!doctype html>
<html lang="ka" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="IDENTISITE - იდენტობა რომელიც საიტად იქცევა. მინიმალისტური პრემიუმ დიზაინი.">
  <title>IDENTISITE | Minimalist Identity</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Noto+Sans+Georgian:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; }
    html { scroll-behavior: smooth; }
    
    body {
      background-color: #ffffff;
      color: #1a1a1a;
    }

    /* Tegeta Style Matte Colors */
    .bg-matte-navy { background-color: #001a33; } /* მუქი ლურჯი მატოვი */
    .text-matte-navy { color: #001a33; }
    .bg-matte-grey { background-color: #f5f5f7; }
    
    /* Artmedia Style Cards */
    .soft-card {
      background: #ffffff;
      border-radius: 24px;
      border: 1px solid #e5e7eb;
      transition: all 0.3s ease;
    }
    .soft-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.05);
      border-color: #001a33;
    }

    .nav-link {
      position: relative;
      color: #4b5563;
      transition: color 0.3s ease;
    }
    .nav-link:hover { color: #001a33; }
    
    .btn-matte {
      background-color: #001a33;
      color: #ffffff;
      transition: all 0.3s ease;
      border-radius: 12px;
    }
    .btn-matte:hover {
      background-color: #000000;
      transform: translateY(-1px);
    }

    .section-num {
      font-size: 14px;
      font-weight: 600;
      color: #9ca3af;
      margin-right: 12px;
    }
  </style>
 </head>
 <body class="h-full overflow-auto">

  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/90 backdrop-blur-md border-b border-gray-100">
    <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center">
      <div class="flex items-center space-x-8">
        <a href="#home" class="flex items-center space-x-2">
          <div class="w-8 h-8 bg-matte-navy rounded flex items-center justify-center text-white font-bold">I</div>
          <span class="text-xl font-bold tracking-tight text-matte-navy">IDENTISITE</span>
        </a>
      </div>
      
      <div class="hidden lg:flex items-center space-x-10">
        <a href="#home" class="nav-link text-sm font-semibold uppercase tracking-wider">მთავარი</a>
        <a href="#about" class="nav-link text-sm font-semibold uppercase tracking-wider">ჩვენ შესახებ</a>
        <a href="#services" class="nav-link text-sm font-semibold uppercase tracking-wider">სერვისები</a>
        <a href="#contact" class="nav-link text-sm font-semibold uppercase tracking-wider">კონტაქტი</a>
      </div>

      <div class="flex items-center space-x-6">
        <span class="text-xs font-bold text-gray-400 cursor-pointer hover:text-matte-navy">GE / EN</span>
        <a href="#contact" class="btn-matte px-6 py-2.5 text-sm font-bold shadow-sm">დავიწყოთ</a>
      </div>
    </div>
  </nav>

  <section id="home" class="pt-40 pb-20 px-6">
    <div class="max-w-7xl mx-auto">
      <div class="flex items-center mb-6">
        <span class="section-num">01</span>
        <div class="h-[1px] w-12 bg-gray-200"></div>
        <span class="ml-4 text-xs font-bold uppercase tracking-[0.2em] text-gray-400">იდენტობა რომელიც საიტად იქცევა</span>
      </div>
      
      <div class="grid lg:grid-cols-2 gap-12 items-end">
        <div>
          <h1 class="text-5xl lg:text-7xl font-bold text-matte-navy leading-[1.1] mb-8">
            ციფრული <br>ტრანსფორმაცია <br><span class="text-gray-300">იწყება აქ.</span>
          </h1>
          <p class="text-xl text-gray-500 max-w-lg mb-10 leading-relaxed">
            ვქმნით მინიმალისტურ და ფუნქციურ ციფრულ პროდუქტებს, რომლებიც თქვენს ბიზნესს ახალ სიმაღლეზე აიყვანს.
          </p>
          <div class="flex space-x-4">
            <button class="btn-matte px-10 py-4 font-bold">პროექტის დაწყება</button>
            <button class="px-10 py-4 border border-gray-200 rounded-xl font-bold hover:bg-gray-50 transition">პორტფოლიო</button>
          </div>
        </div>
        
        <div class="grid grid-cols-2 gap-4">
          <div class="bg-matte-grey p-8 rounded-[32px]">
            <div class="text-4xl font-bold text-matte-navy mb-2">150+</div>
            <div class="text-sm font-medium text-gray-400 uppercase">დასრულებული პროექტი</div>
          </div>
          <div class="bg-matte-navy p-8 rounded-[32px] text-white">
            <div class="text-4xl font-bold mb-2">98%</div>
            <div class="text-sm font-medium opacity-60 uppercase">კმაყოფილი კლიენტი</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="services" class="py-24 bg-white px-6">
    <div class="max-w-7xl mx-auto">
      <div class="mb-16">
        <div class="flex items-center mb-4">
          <span class="section-num">02</span>
          <span class="text-xs font-bold uppercase tracking-widest text-gray-400">რას ვაკეთებთ</span>
        </div>
        <h2 class="text-4xl font-bold text-matte-navy">სერვისები</h2>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div class="soft-card p-10 group">
          <div class="w-16 h-16 bg-matte-grey rounded-2xl flex items-center justify-center mb-8 group-hover:bg-matte-navy transition-colors duration-500">
            <svg class="w-8 h-8 text-matte-navy group-hover:text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-matte-navy mb-4">UX/UI დიზაინი</h3>
          <p class="text-gray-500 leading-relaxed mb-8">
            თანამედროვე სტანდარტების შესაბამისი დიზაინი, რომელიც მორგებულია მომხმარებლის გამოცდილებაზე.
          </p>
          <a href="#" class="flex items-center font-bold text-matte-navy group-hover:translate-x-2 transition-transform">
            გაიგე მეტი <span class="ml-2">→</span>
          </a>
        </div>

        <div class="soft-card p-10 group border-matte-navy">
          <div class="w-16 h-16 bg-matte-grey rounded-2xl flex items-center justify-center mb-8 group-hover:bg-matte-navy transition-colors duration-500">
            <svg class="w-8 h-8 text-matte-navy group-hover:text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z" />
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-matte-navy mb-4">E-commerce</h3>
          <p class="text-gray-500 leading-relaxed mb-8">
            სრულფასოვანი ონლაინ მაღაზიები, რომლებიც ორიენტირებულია გაყიდვების ზრდასა და სიმარტივეზე.
          </p>
          <a href="#" class="flex items-center font-bold text-matte-navy group-hover:translate-x-2 transition-transform">
            გაიგე მეტი <span class="ml-2">→</span>
          </a>
        </div>

        <div class="soft-card p-10 group">
          <div class="w-16 h-16 bg-matte-grey rounded-2xl flex items-center justify-center mb-8 group-hover:bg-matte-navy transition-colors duration-500">
            <svg class="w-8 h-8 text-matte-navy group-hover:text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-matte-navy mb-4">ბრენდინგი</h3>
          <p class="text-gray-500 leading-relaxed mb-8">
            თქვენი ბრენდის ვიზუალური ნარატივი, რომელიც ზუსტად გადმოსცემს კომპანიის ღირებულებებს.
          </p>
          <a href="#" class="flex items-center font-bold text-matte-navy group-hover:translate-x-2 transition-transform">
            გაიგე მეტი <span class="ml-2">→</span>
          </a>
        </div>
      </div>
    </div>
  </section>

  <footer class="bg-matte-grey py-12 px-6">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center">
      <div class="text-sm font-medium text-gray-400 mb-4 md:mb-0">
        © 2026 IDENTISITE. ყველა უფლება დაცულია.
      </div>
      <div class="flex space-x-8">
        <a href="#" class="text-xs font-bold uppercase tracking-tighter hover:text-matte-navy">Facebook</a>
        <a href="#" class="text-xs font-bold uppercase tracking-tighter hover:text-matte-navy">Instagram</a>
        <a href="#" class="text-xs font-bold uppercase tracking-tighter hover:text-matte-navy">LinkedIn</a>
      </div>
    </div>
  </footer>

 </body>
</html>
