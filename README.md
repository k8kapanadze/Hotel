<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | მინიმალისტური ციფრული იდენტობა</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Noto+Sans+Georgian:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; }
    
    /* ფერების პალიტრა */
    :root {
      --matte-blue: #0a192f;
      --deep-black: #050505;
      --soft-gray: #f5f5f5;
      --border-gray: #e5e5e5;
    }

    body { background-color: white; color: var(--deep-black); }
    .bg-matte-blue { background-color: var(--matte-blue); }
    .text-matte-blue { color: var(--matte-blue); }
    
    /* აკორდეონის სტილი */
    .accordion-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .accordion-item.active .accordion-content {
      max-height: 300px;
    }
    .accordion-item.active .icon-plus {
      transform: rotate(45deg);
    }

    .minimal-card {
      border: 1px solid var(--border-gray);
      transition: all 0.3s ease;
    }
    .minimal-card:hover {
      border-color: var(--matte-blue);
      background-color: var(--soft-gray);
    }

    /* მუქი ლურჯი ფილტრი ფოტოებისთვის */
    .blue-overlay {
      background-color: var(--matte-blue);
      mix-blend-mode: multiply;
      opacity: 0.8;
    }
  </style>
</head>
<body class="h-full">

  <nav class="fixed top-0 w-full z-50 bg-white/90 backdrop-blur-md border-b border-gray-100">
    <div class="max-w-7xl mx-auto px-6 h-20 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <div class="w-8 h-8 bg-matte-blue flex items-center justify-center text-white font-bold text-sm">I</div>
        <span class="text-xl font-bold tracking-tighter text-matte-blue">IDENTISITE</span>
      </div>
      <div class="hidden md:flex space-x-8 text-sm font-medium uppercase tracking-widest">
        <a href="#services" class="hover:text-gray-500 transition">სერვისები</a>
        <a href="#process" class="hover:text-gray-500 transition">პროცესი</a>
        <a href="#contact" class="hover:text-gray-500 transition">კონტაქტი</a>
      </div>
    </div>
  </nav>

  <section class="pt-40 pb-20 px-6">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-6xl md:text-8xl font-bold tracking-tighter leading-none mb-10">
        DIGITAL<br><span class="text-gray-300">IDENTITY</span>
      </h1>
      <p class="max-w-xl text-lg text-gray-600 mb-12">
        მინიმალისტური მიდგომა, მაქსიმალური შედეგი. ჩვენ ვქმნით ციფრულ პროდუქტებს მათთვის, ვისაც სურს ხარისხი ზედმეტი დეტალების გარეშე.
      </p>
    </div>
  </section>

  <section id="services" class="py-24 bg-white px-6">
    <div class="max-w-7xl mx-auto grid md:grid-cols-2 gap-20">
      <div>
        <h2 class="text-4xl font-bold tracking-tight mb-8">სერვისები</h2>
        <div class="space-y-4">
          
          <div class="accordion-item border-b border-gray-200 cursor-pointer group" onclick="toggleAccordion(this)">
            <div class="py-6 flex justify-between items-center">
              <span class="text-xl font-medium uppercase tracking-wider">ვებ დეველოპმენტი</span>
              <span class="icon-plus transition-transform duration-300 text-2xl">+</span>
            </div>
            <div class="accordion-content">
              <p class="pb-6 text-gray-500">
                თანამედროვე, სწრაფი და მინიმალისტური ვებსაიტები, რომლებიც მორგებულია თქვენს ბიზნეს ამოცანებზე.
              </p>
            </div>
          </div>

          <div class="accordion-item border-b border-gray-200 cursor-pointer" onclick="toggleAccordion(this)">
            <div class="py-6 flex justify-between items-center">
              <span class="text-xl font-medium uppercase tracking-wider">UI/UX დიზაინი</span>
              <span class="icon-plus transition-transform duration-300 text-2xl">+</span>
            </div>
            <div class="accordion-content">
              <p class="pb-6 text-gray-500">
                ინტერფეისები, სადაც ყოველი პიქსელი გამართლებულია. აქცენტი მომხმარებლის გამოცდილებაზე.
              </p>
            </div>
          </div>

          <div class="accordion-item border-b border-gray-200 cursor-pointer" onclick="toggleAccordion(this)">
            <div class="py-6 flex justify-between items-center">
              <span class="text-xl font-medium uppercase tracking-wider">ბრენდინგი</span>
              <span class="icon-plus transition-transform duration-300 text-2xl">+</span>
            </div>
            <div class="accordion-content">
              <p class="pb-6 text-gray-500">
                ვიზუალური იდენტობის შექმნა, რომელიც თქვენს ბრენდს კონკურენტებისგან გამოარჩევს.
              </p>
            </div>
          </div>

        </div>
      </div>

      <div class="relative h-96 bg-matte-blue overflow-hidden group">
        <div class="absolute inset-0 blue-overlay"></div>
        <div class="absolute inset-0 flex items-center justify-center border border-white/10">
          <span class="text-white/20 text-9xl font-bold">ID</span>
        </div>
      </div>
    </div>
  </section>

  <section id="process" class="py-24 bg-gray-50 px-6">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-sm font-bold uppercase tracking-[0.3em] mb-16 text-gray-400">სამუშაო პროცესი</h2>
      <div class="grid md:grid-cols-4 gap-6">
        
        <div class="minimal-card p-10 bg-white">
          <span class="text-gray-300 text-sm font-bold mb-8 block">01</span>
          <h3 class="text-lg font-bold mb-4 uppercase">ანალიზი</h3>
          <p class="text-sm text-gray-500 leading-relaxed">თქვენი მოთხოვნების სიღრმისეული შესწავლა.</p>
        </div>

        <div class="minimal-card p-10 bg-white">
          <span class="text-gray-300 text-sm font-bold mb-8 block">02</span>
          <h3 class="text-lg font-bold mb-4 uppercase">დიზაინი</h3>
          <p class="text-sm text-gray-500 leading-relaxed">მინიმალისტური და სუფთა ვიზუალის შექმნა.</p>
        </div>

        <div class="minimal-card p-10 bg-white">
          <span class="text-gray-300 text-sm font-bold mb-8 block">03</span>
          <h3 class="text-lg font-bold mb-4 uppercase">კოდი</h3>
          <p class="text-sm text-gray-500 leading-relaxed">იდეის გადატანა მაღალი ხარისხის კოდში.</p>
        </div>

        <div class="minimal-card p-10 bg-white">
          <span class="text-gray-300 text-sm font-bold mb-8 block">04</span>
          <h3 class="text-lg font-bold mb-4 uppercase">შედეგი</h3>
          <p class="text-sm text-gray-500 leading-relaxed">პროექტის ჩაშვება და მხარდაჭერა.</p>
        </div>

      </div>
    </div>
  </section>

  <footer id="contact" class="bg-matte-blue text-white py-20 px-6">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-start">
      <div class="mb-12 md:mb-0">
        <h2 class="text-4xl font-bold mb-6 italic">დავიწყოთ?</h2>
        <p class="text-gray-400">info@identisite.ge</p>
      </div>
      <div class="w-full md:w-1/3">
        <button class="w-full border border-white/20 py-5 uppercase tracking-widest hover:bg-white hover:text-matte-blue transition-all duration-500">
          მოგვწერეთ
        </button>
      </div>
    </div>
    <div class="max-w-7xl mx-auto mt-20 pt-8 border-t border-white/5 text-[10px] uppercase tracking-widest text-gray-500">
      © 2026 IDENTISITE. ყველა უფლება დაცულია.
    </div>
  </footer>

  <script>
    function toggleAccordion(element) {
      const isActive = element.classList.contains('active');
      
      // ყველა სხვა აკორდეონის დახურვა
      document.querySelectorAll('.accordion-item').forEach(item => {
        item.classList.remove('active');
      });

      // მიმდინარე აკორდეონის გადართვა
      if (!isActive) {
        element.classList.add('active');
      }
    }
  </script>
</body>
</html>
