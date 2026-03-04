<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Minimalist Accordion UI</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', sans-serif; transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1); }
    html { scroll-behavior: smooth; }
    body { background-color: #ffffff; color: #111111; }

    /* Matte Navy & Grey Shades */
    .bg-matte-navy { background-color: #001a33; }
    .text-matte-navy { color: #001a33; }
    .bg-soft-grey { background-color: #f5f5f7; }

    /* Accordion Logic */
    .accordion-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.5s ease-out, padding 0.5s ease;
    }
    .accordion-item.active .accordion-content {
      max-height: 1000px;
      padding-bottom: 3rem;
    }
    .accordion-item.active .plus-icon {
      transform: rotate(45deg);
    }
    
    .accordion-row {
      border-bottom: 1px solid #e5e7eb;
      cursor: pointer;
    }
    .accordion-row:hover {
      background-color: #fafafa;
    }

    .nav-link { font-size: 11px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; }
  </style>
</head>
<body class="antialiased">

  <nav class="fixed top-0 w-full z-50 bg-white/90 backdrop-blur-md border-b border-gray-100 px-8 py-6">
    <div class="max-w-[1600px] mx-auto flex justify-between items-center">
      <a href="#" class="text-xl font-bold tracking-tighter text-matte-navy">IDENTISITE</a>
      <div class="hidden lg:flex space-x-10">
        <a href="#" class="nav-link text-gray-400 hover:text-matte-navy">Menu</a>
        <a href="#" class="nav-link text-gray-400">GE / EN</a>
      </div>
    </div>
  </nav>

  <section class="pt-48 pb-20 px-8">
    <div class="max-w-[1600px] mx-auto">
      <h1 class="text-6xl md:text-8xl font-bold tracking-tighter text-matte-navy mb-10">
        იდენტობა <br> საიტად.
      </h1>
      <p class="text-xl text-gray-400 max-w-lg">
        მინიმალისტური სისტემები ბიზნესის ციფრული ტრანსფორმაციისთვის.
      </p>
    </div>
  </section>

  <section class="px-8 pb-40">
    <div class="max-w-[1600px] mx-auto border-t border-gray-200">
      
      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">01</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">ჩვენ შესახებ</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid lg:grid-cols-2 gap-10 pt-10">
            <p class="text-xl text-gray-500 leading-relaxed">
              2019 წლიდან IDENTISITE ქმნის პრემიუმ ვებ პროდუქტებს. ჩვენი ფილოსოფია მარტივია: ყოველი ბრენდი უნიკალურია და მას სჭირდება ინდივიდუალური ციფრული ენა.
            </p>
            <div class="bg-soft-grey p-10 rounded-3xl">
              <h4 class="font-bold text-matte-navy mb-4">ჩვენი მისია</h4>
              <p class="text-gray-500">ბიზნესის უნიკალური იდენტობის გარდასახვა მაღალტექნოლოგიურ ციფრულ აქტივად.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">02</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">სერვისები</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-3 gap-6 pt-10">
            <div class="p-8 border border-gray-100 rounded-3xl hover:bg-matte-navy hover:text-white group">
              <h3 class="text-xl font-bold mb-4">UX/UI დიზაინი</h3>
              <p class="text-sm opacity-60">თანამედროვე ინტერფეისები მომხმარებლის საუკეთესო გამოცდილებისთვის.</p>
            </div>
            <div class="p-8 border border-gray-100 rounded-3xl hover:bg-matte-navy hover:text-white">
              <h3 class="text-xl font-bold mb-4">E-commerce</h3>
              <p class="text-sm opacity-60">სრულფასოვანი ონლაინ მაღაზიები და გადახდის სისტემები.</p>
            </div>
            <div class="p-8 border border-gray-100 rounded-3xl hover:bg-matte-navy hover:text-white">
              <h3 class="text-xl font-bold mb-4">ბრენდინგი</h3>
              <p class="text-sm opacity-60">ვიზუალური სტრატეგია, რომელიც გამოგარჩევთ ბაზარზე.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">03</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">პორტფოლიო</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid grid-cols-2 md:grid-cols-4 gap-4 pt-10">
            <div class="aspect-video bg-soft-grey rounded-2xl flex items-center justify-center text-gray-300">Project 01</div>
            <div class="aspect-video bg-soft-grey rounded-2xl flex items-center justify-center text-gray-300">Project 02</div>
            <div class="aspect-video bg-soft-grey rounded-2xl flex items-center justify-center text-gray-300">Project 03</div>
            <div class="aspect-video bg-soft-grey rounded-2xl flex items-center justify-center text-gray-300">Project 04</div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">04</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">პროცესი</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-4 gap-8 pt-10">
            <div><h5 class="font-bold text-matte-navy mb-2">01. კვლევა</h5><p class="text-sm text-gray-400">ანალიზი და მიზნების დასახვა.</p></div>
            <div><h5 class="font-bold text-matte-navy mb-2">02. დიზაინი</h5><p class="text-sm text-gray-400">ვიზუალური სტრუქტურის შექმნა.</p></div>
            <div><h5 class="font-bold text-matte-navy mb-2">03. კოდი</h5><p class="text-sm text-gray-400">იდეის ქცევა რეალურ საიტად.</p></div>
            <div><h5 class="font-bold text-matte-navy mb-2">04. ლაივი</h5><p class="text-sm text-gray-400">პროექტის ჩაშვება და მხარდაჭერა.</p></div>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">05</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">ბლოგი</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="pt-10 space-y-4">
            <a href="#" class="block p-6 hover:bg-soft-grey rounded-2xl">
              <span class="text-xs text-gray-400">24 მაისი, 2024</span>
              <h4 class="text-xl font-bold">თანამედროვე ვებ-დიზაინის ტრენდები</h4>
            </a>
          </div>
        </div>
      </div>

      <div class="accordion-item" onclick="toggleAccordion(this)">
        <div class="accordion-row py-10 flex justify-between items-center group border-b-0">
          <div class="flex items-center space-x-12">
            <span class="text-xs font-bold text-gray-300">06</span>
            <h2 class="text-3xl md:text-5xl font-medium group-hover:pl-4 transition-all">კონტაქტი</h2>
          </div>
          <div class="plus-icon text-3xl font-light">+</div>
        </div>
        <div class="accordion-content">
          <div class="grid md:grid-cols-2 gap-10 pt-10">
            <div>
              <h4 class="text-4xl font-bold mb-6">მოგვწერეთ.</h4>
              <p class="text-gray-400 mb-8">მზად ვართ ახალი გამოწვევებისთვის.</p>
              <a href="mailto:hello@identisite.ge" class="text-2xl border-b border-black pb-2">hello@identisite.ge</a>
            </div>
            <form class="space-y-4">
              <input type="text" placeholder="სახელი" class="w-full p-4 bg-soft-grey rounded-xl border-none outline-none">
              <textarea placeholder="შეტყობინება" class="w-full p-4 bg-soft-grey rounded-xl border-none outline-none h-32"></textarea>
              <button class="bg-matte-navy text-white px-10 py-4 rounded-xl font-bold w-full md:w-auto">გაგზავნა</button>
            </form>
          </div>
        </div>
      </div>

    </div>
  </section>

  <footer class="p-8 border-t border-gray-100">
    <div class="max-w-[1600px] mx-auto flex justify-between items-center">
      <p class="text-xs font-bold text-gray-300 uppercase tracking-widest">© 2026 IDENTISITE</p>
      <div class="flex space-x-6 text-xs font-bold uppercase tracking-widest">
        <a href="#" class="hover:text-matte-navy">Instagram</a>
        <a href="#" class="hover:text-matte-navy">Facebook</a>
      </div>
    </div>
  </footer>

  <script>
    function toggleAccordion(element) {
      // Close other items if you want only one open at a time
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
