<!doctype html>
<html lang="ka" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IDENTISITE | იდენტობა იწყება აქ</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body { 
            font-family: 'Noto Sans Georgian', sans-serif; 
            background-color: #ffffff; /* თეთრი ბექგრაუნდი */
            color: #000000; /* შავი ტექსტი */
        }
        
        /* მინიმალისტური Card სტილი */
        .minimal-card {
            background-color: #ffffff;
            border: 1px solid #e5e7eb; /* ღია ნაცრისფერი ჩარჩო */
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        /* ნაზი ჩამოშლის ანიმაცია */
        .collapsible-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out, padding 0.5s ease-out;
            padding: 0 1.5rem; /* ჰორიზონტალური პადინგი */
        }

        .collapsible-card.active .collapsible-content {
            max-height: 1000px; /* საკმარისი სიმაღლე */
            padding: 1.5rem; /* ვერტიკალური პადინგი გაშლისას */
            border-top: 1px solid #e5e7eb;
        }

        /* მუქი ლურჯი (მატოვი) */
        .matte-blue-bg { background-color: #1a2a44; }
        .matte-blue-text { color: #1a2a44; }
        
        /* ღილაკის სტილი */
        .btn-matte {
            background-color: #1a2a44;
            color: #ffffff;
            transition: background-color 0.3s ease;
        }
        .btn-matte:hover {
            background-color: #000000;
        }

        /* ისრის როტაცია */
        .arrow-icon {
            transition: transform 0.3s ease;
        }
        .collapsible-card.active .arrow-icon {
            transform: rotate(180deg);
        }
    </style>
</head>
<body class="h-full">

    <div class="max-w-7xl mx-auto p-4 md:p-6 lg:p-8">
        
        <header class="minimal-card mb-6 p-4 flex justify-between items-center shadow-sm">
            <a href="#" class="text-2xl font-bold text-black flex items-center gap-2">
                <div class="w-8 h-8 matte-blue-bg rounded-lg flex items-center justify-center text-white font-bold">I</div>
                IDENTISITE
            </a>
            <nav class="hidden md:flex gap-6">
                <a href="#home" class="font-medium text-gray-700 hover:text-black">მთავარი</a>
                <a href="#portfolio" class="font-medium text-gray-700 hover:text-black">პორტფოლიო</a>
                <a href="#contact" class="font-medium text-gray-700 hover:text-black">კონტაქტი</a>
            </nav>
            <button class="md:hidden p-2 text-gray-600">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            </button>
        </header>

        <div class="minimal-card mb-6 shadow-sm">
            <img src="https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?q=80&w=1600&auto=format&fit=crop" alt="Office Collaboration" class="w-full h-80 object-crop">
        </div>

        <div class="minimal-card mb-6 shadow-sm p-6 md:p-8">
            <div class="max-w-4xl">
                <h1 class="text-4xl md:text-5xl font-bold text-black mb-6 leading-tight">
                    შენი ბიზნესის <br>
                    <span class="matte-blue-text">იდენტობა იწყება აქ</span>
                </h1>
                
                <p class="text-xl text-gray-700 mb-10 leading-relaxed border-l-4 border-black pl-6">
                    წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
                </p>

                <div class="flex flex-wrap gap-4">
                    <a href="#contact" class="btn-matte px-8 py-3 rounded-xl font-semibold hover:scale-105 transition-transform">
                        შეკვეთა
                    </a>
                    
                    <a href="#portfolio" class="border-2 border-black text-black px-8 py-3 rounded-xl font-semibold hover:bg-black hover:text-white transition-all hover:scale-105">
                        შექმნილი პროექტები
                    </a>
                </div>
            </div>
        </div>

        <div class="space-y-4">

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">2. ჩვენ შესახებ</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <p>IDENTISITE არის პრემიუმ ვებ სააგენტო, რომელიც ბიზნესებს ეხმარება ციფრულ სამყაროში გამორჩეული და დასამახსოვრებელი იდენტობის შექმნაში.</p>
                </div>
            </div>

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">3. სერვისები</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <ul class="list-disc pl-5 space-y-1">
                        <li>კორპორატიული ვებსაიტები</li>
                        <li>E-commerce მაღაზიები</li>
                        <li>UI/UX დიზაინი</li>
                        <li>SEO ოპტიმიზაცია</li>
                    </ul>
                </div>
            </div>

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">4. პორტფოლიო</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
                        <div class="aspect-square bg-gray-100 rounded-lg flex items-center justify-center text-gray-500">Project A</div>
                        <div class="aspect-square bg-gray-100 rounded-lg flex items-center justify-center text-gray-500">Project B</div>
                        <div class="aspect-square bg-gray-100 rounded-lg flex items-center justify-center text-gray-500">Project C</div>
                    </div>
                </div>
            </div>

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">5. პროცესი</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <p>ჩვენი სამუშაო პროცესი მოიცავს: კვლევას, დიზაინს, დეველოპმენტს და ტესტირებას.</p>
                </div>
            </div>

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">6. ბლოგი</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <p>სიახლეები და სტატიები ციფრული მარკეტინგის და ვებ დიზაინის შესახებ.</p>
                </div>
            </div>

            <div class="minimal-card collapsible-card shadow-sm">
                <button class="w-full p-5 flex justify-between items-center text-left" onclick="toggleCard(this)">
                    <span class="text-lg font-semibold text-black">7. კონტაქტი</span>
                    <svg class="w-5 h-5 text-gray-500 arrow-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                </button>
                <div class="collapsible-content text-gray-700 leading-relaxed">
                    <p>დაგვიკავშირდით პროექტის დასაწყებად: info@identisite.ge</p>
                </div>
            </div>

        </div>

    </div>

    <script>
        function toggleCard(button) {
            const card = button.closest('.collapsible-card');
            
            // დახუროს სხვა გაშლილი ქარდები (სურვილისამებრ)
            // document.querySelectorAll('.collapsible-card').forEach(c => {
            //     if (c !== card) c.classList.remove('active');
            // });

            card.classList.toggle('active');
        }
    </script>
</body>
</html>
