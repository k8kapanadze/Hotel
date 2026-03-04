<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Minimalist Design</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Noto+Sans+Georgian:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; }
    
    /* Minimalist Card Style */
    .m-card {
      background: #ffffff;
      border: 1px solid #f1f5f9;
      border-radius: 24px;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .m-card:hover {
      border-color: #3C7EFC;
      box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.05);
      transform: translateY(-4px);
    }

    .bento-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .pill-button {
      border-radius: 9999px;
      transition: all 0.3s ease;
    }

    .gradient-subtle {
      background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
    }
  </style>
</head>

<body class="bg-[#FBFBFE] text-slate-900">

  <nav class="fixed top-6 left-0 right-0 z-50 px-4">
    <div class="max-w-5xl mx-auto m-card bg-white/70 backdrop-blur-md px-6 py-3 flex justify-between items-center border border-white/20 shadow-sm">
      <a href="#" class="text-xl font-bold tracking-tight text-[#3C7EFC]">IDENTISITE</a>
      <div class="hidden md:flex space-x-8 text-sm font-medium text-slate-500">
        <a href="#services" class="hover:text-[#3C7EFC]">სერვისები</a>
        <a href="#portfolio" class="hover:text-[#3C7EFC]">პორტფოლიო</a>
        <a href="#contact" class="hover:text-[#3C7EFC]">კონტაქტი</a>
      </div>
      <button class="bg-slate-900 text-white px-5 py-2 pill-button text-sm font-medium hover:bg-[#3C7EFC]">დავიწყოთ</button>
    </div>
  </nav>

  <section class="pt-40 pb-20 px-4">
    <div class="max-w-7xl mx-auto text-center">
      <span class="bg-blue-50 text-[#3C7EFC] px-4 py-1.5 rounded-full text-xs font-bold tracking-widest uppercase">Premium Web Agency</span>
      <h1 class="text-5xl md:text-7xl font-bold mt-8 mb-6 tracking-tight">შენი ბიზნესის <br/><span class="text-slate-400">იდენტობა იწყება აქ</span></h1>
      <p class="text-slate-500 max-w-2xl mx-auto text-lg mb-10">ჩვენ ვქმნით მინიმალისტურ, სწრაფ და შედეგზე ორიენტირებულ ციფრულ პროდუქტებს.</p>
    </div>
  </section>

  <section id="services" class="max-w-7xl mx-auto px-4 py-20">
    <div class="mb-12">
      <h2 class="text-3xl font-bold">ჩვენი სერვისები</h2>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="m-card p-10 md:col-span-2 gradient-subtle flex flex-col justify-between">
        <div>
          <div class="w-12 h-12 bg-blue-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-6 h-6 text-[#3C7EFC]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"></path></svg>
          </div>
          <h3 class="text-2xl font-bold mb-4">კორპორატიული საიტები</h3>
          <p class="text-slate-500 max-w-md text-lg">პროფესიონალური პლატფორმები, რომლებიც თქვენს ბიზნესს საერთაშორისო სტანდარტების დონეზე წარმოაჩენს.</p>
        </div>
        <div class="mt-10 flex space-x-2">
          <span class="px-3 py-1 bg-white border border-slate-100 rounded-lg text-xs font-medium text-slate-500 uppercase">Custom Design</span>
          <span class="px-3 py-1 bg-white border border-slate-100 rounded-lg text-xs font-medium text-slate-500 uppercase">SEO Ready</span>
        </div>
      </div>

      <div class="m-card p-10 flex flex-col justify-between">
        <div>
          <div class="w-12 h-12 bg-purple-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
          </div>
          <h3 class="text-xl font-bold mb-3">E-commerce</h3>
          <p class="text-slate-500 text-sm">ონლაინ მაღაზიები გამართული გადახდის სისტემებით.</p>
        </div>
        <a href="#" class="text-[#3C7EFC] font-semibold text-sm flex items-center group">
          შეკვეთა 
          <svg class="w-4 h-4 ml-2 group-hover:translate-x-2 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path></svg>
        </a>
      </div>

      <div class="m-card p-10 flex flex-col justify-between">
        <div>
          <div class="w-12 h-12 bg-orange-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-6 h-6 text-orange-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M4 13a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H5a1 1 0 01-1-1v-6z"></path></svg>
          </div>
          <h3 class="text-xl font-bold mb-3">UI/UX დიზაინი</h3>
          <p class="text-slate-500 text-sm">თანამედროვე ინტერფეისი საუკეთესო გამოცდილებისთვის.</p>
        </div>
        <a href="#" class="text-slate-400 font-semibold text-sm">იხილეთ მეტი</a>
      </div>

      <div class="m-card p-10 md:col-span-2 flex flex-col md:flex-row items-center justify-between">
        <div>
          <h3 class="text-2xl font-bold mb-2">გაქვთ პროექტი?</h3>
          <p class="text-slate-500">მოდით, ერთად ვაქციოთ თქვენი იდეა რეალობად.</p>
        </div>
        <button class="mt-6 md:mt-0 bg-[#3C7EFC] text-white px-8 py-3 pill-button font-bold hover:shadow-lg hover:shadow-blue-200">კონსულტაცია</button>
      </div>
    </div>
  </section>

</body>
</html>
