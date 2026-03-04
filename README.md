<!doctype html>
<html lang="ka" class="h-full">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IDENTISITE | კრეატიული ვებ დიზაინი</title>
  <meta name="description" content="IDENTISITE - კრეატიული და განსხვავებული ვებ დიზაინი, რომელიც ხაზს უსვამს თქვენს ბრენდს." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700&family=Outfit:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    :root {
      --blue-900: #0A1628;
      --blue-950: #050C1A;
      --blue-800: #0D1B3E;
      --blue-700: #1E3A8A;
      --electric: #3B82F6;
      --electric-light: #60A5FA;
      --electric-pale: #93C5FD;
      --navy: #070D1F;
    }
    * { font-family: 'Noto Sans Georgian', 'Outfit', sans-serif; }
    html { scroll-behavior: smooth; }
    body { background: #fff; color: #1F2937; transition: background 0.3s, color 0.3s; }

    /* Light and Dark Mode */
    body.dark { background: #050A18; color: #E2E8F0; }

    /* Fonts and Text Effects */
    .gradient-text {
      background: linear-gradient(135deg, #60A5FA, #3B82F6, #93C5FD);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    /* Buttons and Cards */
    .btn-toggle {
      transition: background 0.3s, transform 0.3s;
    }
    /* Dark Mode toggle button style */
    .dark-mode-btn {
      background: #1E3A8A;
      color: #fff;
    }
  </style>
</head>
<body class="h-full overflow-auto">

<!-- Floating Dark Mode Toggle Button -->
<div class="fixed top-4 right-4 z-50">
  <button id="darkModeToggle" class="px-4 py-2 bg-blue-700 text-white rounded-lg shadow-lg hover:bg-blue-800 transition">ღამის რეჟიმი</button>
</div>

<!-- მოკლე ნავიგაცია -->
<nav class="fixed top-0 left-0 right-0 z-40 bg-white dark:bg-[#070D1F] border-b border-gray-200 dark:border-gray-700 transition-colors duration-300">
  <div class="max-w-7xl mx-auto px-4 flex justify-between items-center h-16">
    <div class="flex items-center space-x-2">
      <div class="w-10 h-10 bg-gradient-to-br from-[#2563EB] to-[#1D4ED8] rounded-xl flex items-center justify-center text-white font-bold">I</div>
      <span class="text-xl font-bold text-gray-800 dark:text-gray-200">IDENTISITE</span>
    </div>
    <div class="hidden md:flex space-x-8 text-gray-600 dark:text-gray-300">
      <a href="#home" class="hover:text-blue-500 transition">მთავარი</a>
      <a href="#about" class="hover:text-blue-500 transition">ჩვენ შესახებ</a>
      <a href="#services" class="hover:text-blue-500 transition">სერვისები</a>
      <a href="#portfolio" class="hover:text-blue-500 transition">პორტფოლიო</a>
      <a href="#contact" class="hover:text-blue-500 transition">კონტაქტი</a>
    </div>
  </div>
</nav>

<!-- მთავარი სექცია -->
<section id="home" class="min-h-screen flex items-center justify-center px-4 bg-white dark:bg-[#050A18] transition-colors duration-300 pt-20 relative overflow-hidden">

  <!-- კრეატიული გრაფიკა და ბლობები -->
  <div class="absolute inset-0">
    <div class="w-96 h-96 bg-[#1D4ED8] rounded-full absolute top-20 -left-48 opacity-70 animate-bounce"></div>
    <div class="w-80 h-80 bg-[#2563EB] rounded-full absolute bottom-20 -right-40 opacity-70 animate-bounce" style="animation-delay: -3s;"></div>
    <div class="w-64 h-64 bg-[#1E40AF] rounded-full absolute top-1/2 left-1/3 opacity-70 animate-bounce" style="animation-delay: -1.5s;"></div>
  </div>

  <!-- შინაარსი -->
  <div class="max-w-7xl mx-auto flex flex-col lg:flex-row items-center justify-between z-10 relative">
    <div class="text-center lg:text-left mb-8 lg:mb-0">
      <div class="inline-flex items-center px-4 py-2 mb-6 bg-gradient-to-r from-[#2563EB] to-[#3B82F6] text-white rounded-full font-semibold text-sm shadow-lg">
        <span class="w-2 h-2 bg-white rounded-full mr-2 animate-pulse"></span> პრემიუმ ვებ სააგენტო
      </div>
      <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold mb-4">
        შენი ბიზნესის<br>
        <span class="gradient-text">იდენტობა იწყება აქ</span>
      </h1>
      <p class="text-gray-600 dark:text-gray-400 mb-6 text-lg max-w-xl mx-auto lg:mx-0">
        იდენტობა რომელიც საიტად იქცევა - ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს გამოარჩევს და შედეგს მოგიტანთ.
      </p>
      <div class="flex justify-center lg:justify-start space-x-4">
        <a href="#contact" class="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded-xl text-white font-semibold transition">დავიწყოთ პროექტი</a>
        <a href="#portfolio" class="px-6 py-3 border-2 border-gray-300 dark:border-gray-600 rounded-xl text-gray-800 dark:text-gray-200 hover:border-blue-500 hover:text-blue-500 transition">ნამუშევრები</a>
      </div>
    </div>
    <!-- სურათი ან ვიზუალური ელემენტი -->
    <div class="hidden lg:block relative w-96 h-96">
      <div class="absolute inset-0 bg-gradient-to-br from-[#1D4ED8] to-[#2563EB] rounded-3xl p-4 shadow-lg transform hover:scale-105 transition-transform cursor-pointer" onclick="location.href='#contact'">
        <div class="w-full h-full bg-white rounded-lg"></div>
      </div>
    </div>
  </div>
</section>

<!-- სხვა სექციები (ჩვენ შესახებ, სერვისები, პორტფოლიო, კონტაქტი) - ამ სექციებს შეგიძლიათ დაამატოთ იგივე სტილში, როგორც ზემოთ, სქემის მიხედვით -->

<!-- სკრიპტი ღამის რეჟიმის და ფუნქციებისათვის -->
<script>
  // ღამის რეჟიმის აქცენტი
  const toggleBtn = document.getElementById('darkModeToggle');
  toggleBtn.addEventListener('click', () => {
    document.body.classList.toggle('dark');
    toggleBtn.textContent = document.body.classList.contains('dark') ? 'საღამო რეჟიმი' : 'ღამის რეჟიმი';
  });
</script>

</body>
</html>
