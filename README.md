<!doctype html>
<html lang="ka" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IDENTISITE | იდენტობა იწყება აქ</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        body { 
            font-family: 'Noto Sans Georgian', sans-serif; 
            background-color: #ffffff;
            color: #000000;
        }
        /* ლურჯი გრადიენტი სვეტებისთვის */
        .sidebar-gradient {
            background: linear-gradient(180deg, #001f3f 0%, #003366 50%, #004080 100%);
        }
        .matte-blue { background-color: #1a2a44; }
        .btn-matte {
            background-color: #1a2a44;
            transition: all 0.3s ease;
        }
        .btn-matte:hover {
            background-color: #000000;
            transform: translateY(-2px);
        }
        .nav-item {
            border-bottom: 1px solid rgba(255,255,255,0.1);
            transition: background 0.3s;
        }
        .nav-item:hover {
            background: rgba(255,255,255,0.1);
        }
    </style>
</head>
<body class="h-full">

    <div class="flex flex-col md:flex-row min-h-screen">
        
        <aside class="w-full md:w-64 sidebar-gradient text-white flex flex-col">
            <div class="p-6 text-2xl font-bold border-b border-white/10">
                IDENTISITE
            </div>
            <nav class="flex-grow">
                <a href="#home" class="block p-4 nav-item font-medium">მთავარი</a>
                <a href="#about" class="block p-4 nav-item font-medium">ჩვენ შესახებ</a>
                <a href="#services" class="block p-4 nav-item font-medium">სერვისები</a>
                <a href="#portfolio" class="block p-4 nav-item font-medium">პორტფოლიო</a>
                <a href="#process" class="block p-4 nav-item font-medium">პროცესი</a>
                <a href="#blog" class="block p-4 nav-item font-medium">ბლოგი</a>
                <a href="#contact" class="block p-4 nav-item font-medium">კონტაქტი</a>
            </nav>
        </aside>

        <main class="flex-grow bg-white">
            
            <section id="home" class="min-h-screen flex flex-col justify-center px-8 md:px-20 py-12">
                <div class="max-w-4xl">
                    <h1 class="text-5xl md:text-7xl font-bold text-black mb-6 leading-tight">
                        შენი ბიზნესის <br>
                        <span class="text-[#1a2a44]">იდენტობა იწყება აქ</span>
                    </h1>
                    
                    <p class="text-xl md:text-2xl text-gray-700 mb-10 leading-relaxed border-l-4 border-black pl-6">
                        წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
                    </p>

                    <div class="flex flex-wrap gap-4">
                        <a href="#contact" class="btn-matte text-white px-10 py-4 rounded-lg font-bold text-lg shadow-lg">
                            შეკვეთა
                        </a>
                        
                        <a href="#portfolio" class="border-2 border-black text-black px-10 py-4 rounded-lg font-bold text-lg hover:bg-black hover:text-white transition-all">
                            შექმნილი პროექტები
                        </a>
                    </div>
                </div>
            </section>

            <section id="portfolio" class="py-20 px-8 bg-gray-50">
                <h2 class="text-3xl font-bold mb-12 uppercase tracking-widest">პორტფოლიო</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <div class="aspect-video bg-black rounded-lg flex items-center justify-center text-white">Project 01</div>
                    <div class="aspect-video bg-[#1a2a44] rounded-lg flex items-center justify-center text-white">Project 02</div>
                </div>
            </section>

        </main>
    </div>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
