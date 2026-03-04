<!doctype html>
<html lang="ka" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>IDENTISITE | Premium Minimalism</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Noto+Sans+Georgian:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Noto Sans Georgian', 'Inter', sans-serif; }
    html { scroll-behavior: smooth; }
    
    body { background-color: #ffffff; color: #121212; }

    /* Matte Colors */
    .bg-matte-dark { background-color: #121212; }
    .bg-matte-navy { background-color: #001a33; }
    .bg-matte-gray { background-color: #f8f8f8; }
    .border-matte { border-color: #eeeeee; }

    /* Minimalist Elements */
    .nav-link { 
        font-size: 13px; 
        letter-spacing: 0.05em; 
        transition: all 0.3s ease; 
    }
    .nav-link:hover { color: #666; }

    .card-minimal {
      background: #ffffff;
      border-bottom: 1px solid #eee;
      transition: all 0.4s ease;
    }
    .card-minimal:hover {
      background: #fdfdfd;
      padding-left: 20px;
      border-bottom-color: #121212;
    }

    .btn-outline {
      border: 1.5px solid #121212;
      transition: all 0.3s ease;
    }
    .btn-outline:hover {
      background: #121212;
      color: #ffffff;
    }

    .process-step {
      border-left: 1px solid #eee;
      padding-left: 2rem;
      position: relative;
    }
    .process-step::before {
      content: '';
      position: absolute;
      left: -1px;
      top: 0;
      width: 1px;
      height: 0;
      background: #121212;
      transition: height 0.5s ease;
    }
    .process-step:hover::before { height: 100%; }
  </style>
 </head>
 <body class="h-full">

  <nav class="fixed top-0 w-full z-50 bg-white/80 backdrop-blur-md border-b border-matte">
    <div class="max-w-[1400px] mx-auto px-8 h-24 flex justify-between items-center">
      <a href="#" class="text-xl font-semibold tracking-tighter">IDENTISITE<span class="text-gray-300">.</span></a>
      
      <div class="hidden lg:flex items-center space-x-12">
        <a href="#home" class="nav-link font-medium uppercase">მთავარი</a>
        <a href="#about" class="nav-link font-medium uppercase">ჩვენ შესახებ</a>
        <a href="#services" class="nav-link font-medium uppercase">სერვისები</a>
        <a href="#portfolio" class="nav-link font-medium uppercase">პორტფოლიო</a>
        <a href="#process" class="nav-link font-medium uppercase">პროცესი</a>
        <a href="#blog" class="nav-link font-medium uppercase">ბლოგი</a>
        <a href="#contact" class="nav-link font-medium uppercase">კონტაქტი</a>
      </div>

      <div class="flex items-center space-x-6">
        <button class="text-xs font-bold border-b border-black">GE</button>
        <a href="#contact" class="bg-matte-dark text-white text-xs font-bold px-6 py-3 rounded-full hover:opacity-80 transition">დავიწყოთ</a>
      </div>
    </div>
  </nav>

  <section id="home" class="pt-60 pb-40 px-8">
    <div class="max-w-[1400px] mx-auto">
      <h1 class="text-7xl lg:text-[100px] font-medium tracking-tighter leading-[0.9] mb-12 italic">
        Identity <br> <span class="not-italic text-gray-300">— into Web.</span>
      </h1>
      <div class="flex flex-col md:flex-row justify-between items-end">
        <p class="text-2xl text-gray-400 max-w-xl font-light">
          ჩვენ ვქმნით ციფრულ გარემოს, სადაც თქვენი ბრენდის იდენტობა საუბრობს სიმარტივით და დახვეწილობით.
        </p>
        <div class="mt-8 md:mt-0 flex space-x-4">
            <div class="text-right">
                <span class="block text-4xl font-light">150+</span>
                <span class="text-[10px] uppercase tracking-widest text-gray-400 font-bold">Projects</span>
            </div>
            <div class="w-[1px] h-12 bg-gray-200"></div>
            <div class="text-right">
                <span class="block text-4xl font-light">05+</span>
                <span class="text-[10px] uppercase tracking-widest text-gray-400 font-bold">Years</span>
            </div>
        </div>
      </div>
    </div>
  </section>

  <section id="services" class="py-32 bg-matte-gray px-8">
    <div class="max-w-[1400px] mx-auto">
      <span class="text-[11px] font-bold uppercase tracking-[0.3em] text-gray-400 mb-12 block">01 / სერვისები</span>
      <div class="grid lg:grid-cols-2 gap-20">
        <div>
            <h2 class="text-5xl font-light tracking-tight mb-8">რას ვაკეთებთ <br>თქვენთვის</h2>
            <p class="text-gray-500 mb-12">სრული ციფრული ციკლი იდეიდან რეალიზაციამდე.</p>
            <a href="#contact" class="btn-outline px-10 py-4 inline-block text-xs font-bold uppercase">ყველა სერვისი</a>
        </div>
        <div class="space-y-2">
            <div class="card-minimal p-8 flex justify-between items-center group">
                <span class="text-2xl font-light">UX/UI დიზაინი</span>
                <span class="text-gray-300 group-hover:text-black transition">→</span>
            </div>
            <div class="card-minimal p-8 flex justify-between items-center group">
                <span class="text-2xl font-light">E-commerce სისტემები</span>
                <span class="text-gray-300 group-hover:text-black transition">→</span>
            </div>
            <div class="card-minimal p-8 flex justify-between items-center group">
                <span class="text-2xl font-light">კორპორატიული საიტები</span>
                <span class="text-gray-300 group-hover:text-black transition">→</span>
            </div>
            <div class="card-minimal p-8 flex justify-between items-center group">
                <span class="text-2xl font-light">ბრენდინგი & სტრატეგია</span>
                <span class="text-gray-300 group-hover:text-black transition">→</span>
            </div>
        </div>
      </div>
    </div>
  </section>

  <section id="process" class="py-32 px-8">
    <div class="max-w-[1400px] mx-auto">
      <span class="text-[11px] font-bold uppercase tracking-[0.3em] text-gray-400 mb-20 block">02 / პროცესი</span>
      <div class="grid md:grid-cols-4 gap-12">
        <div class="process-step">
            <span class="text-[10px] font-bold text-gray-300 block mb-4 uppercase">Step 01</span>
            <h3 class="text-xl font-bold mb-4 uppercase tracking-tighter">კვლევა</h3>
            <p class="text-sm text-gray-500 font-light">ბიზნესის ანალიზი და მიზნების განსაზღვრა.</p>
        </div>
        <div class="process-step">
            <span class="text-[10px] font-bold text-gray-300 block mb-4 uppercase">Step 02</span>
            <h3 class="text-xl font-bold mb-4 uppercase tracking-tighter">დიზაინი</h3>
            <p class="text-sm text-gray-500 font-light">ვიზუალური იდენტობის და სტრუქტურის შექმნა.</p>
        </div>
        <div class="process-step">
            <span class="text-[10px] font-bold text-gray-300 block mb-4 uppercase">Step 03</span>
            <h3 class="text-xl font-bold mb-4 uppercase tracking-tighter">დეველოპმენტი</h3>
            <p class="text-sm text-gray-500 font-light">იდეის ქცევა ფუნქციურ ციფრულ პროდუქტად.</p>
        </div>
        <div class="process-step">
            <span class="text-[10px] font-bold text-gray-300 block mb-4 uppercase">Step 04</span>
            <h3 class="text-xl font-bold mb-4 uppercase tracking-tighter">გაშვება</h3>
            <p class="text-sm text-gray-500 font-light">ტესტირება და პროექტის საბოლოო ლაივ რეჟიმი.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="py-40 bg-matte-dark text-white px-8">
    <div class="max-w-[1400px] mx-auto text-center">
      <h2 class="text-5xl lg:text-8xl font-light mb-12 tracking-tighter">გაქვთ იდეა? <br> <span class="text-gray-500 italic">მოდით, დავიწყოთ.</span></h2>
      <a href="mailto:hello@identisite.ge" class="text-2xl lg:text-4xl border-b border-gray-700 pb-2 hover:border-white transition">hello@identisite.ge</a>
      
      <div class="grid md:grid-cols-3 gap-8 mt-32 text-left opacity-40 text-[10px] font-bold uppercase tracking-[0.2em]">
        <div>თბილისი, საქართველო</div>
        <div class="md:text-center">+995 555 00 00 00</div>
        <div class="md:text-right">Social: IG, FB, LI</div>
      </div>
    </div>
  </section>

  <footer class="py-12 border-t border-matte px-8">
    <div class="max-w-[1400px] mx-auto flex justify-between items-center text-[10px] font-bold uppercase tracking-widest text-gray-400">
      <p>© 2026 IDENTISITE.</p>
      <p>CREATED WITH FOCUS ON IDENTITY.</p>
    </div>
  </footer>

 </body>
</html>
