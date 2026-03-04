<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Identisite | Premium Web Architecture</title>
    <style>
        :root {
            --primary: #2563eb;
            --dark: #0f172a;
            --gray: #64748b;
            --line-color: rgba(0, 0, 0, 0.05); /* ბადის ხაზების ფერი */
        }

        * { margin: 0; padding: 0; box-sizing: border-box; cursor: none; } /* კურსორს ვმალავთ სტანდარტულს */

        body {
            background-color: #ffffff;
            font-family: 'Inter', -apple-system, sans-serif;
            color: var(--dark);
            overflow-x: hidden;
            /* Blueprint Grid Lines */
            background-image: 
                linear-gradient(var(--line-color) 1px, transparent 1px),
                linear-gradient(90deg, var(--line-color) 1px, transparent 1px);
            background-size: 100px 100px; /* ბადის ზომა */
        }

        /* --- CUSTOM CURSOR --- */
        #cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            background: var(--primary);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            mix-blend-mode: difference;
            transition: transform 0.1s ease;
        }

        /* --- HERO SECTION (REFINED LEFT SIDE) --- */
        .hero {
            display: flex;
            min-height: 100vh;
            align-items: center;
            padding: 0 8%;
            border-bottom: 1px solid var(--line-color);
        }

        .hero-left {
            flex: 1.2;
            padding-right: 50px;
        }

        .hero-tag {
            font-size: 11px;
            letter-spacing: 5px;
            text-transform: uppercase;
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 25px;
            display: block;
        }

        .hero-left h1 {
            font-size: clamp(45px, 5.5vw, 80px);
            line-height: 1;
            font-weight: 400; /* თხელი ბაზა */
            letter-spacing: -2px;
            margin-bottom: 35px;
        }

        .hero-left h1 b {
            font-weight: 800; /* სქელი აქცენტი */
            display: block;
        }

        .hero-description {
            font-size: 16px;
            line-height: 2;
            letter-spacing: 2.5px; /* გაშლილი ტექსტი */
            color: var(--gray);
            text-transform: uppercase;
            max-width: 550px;
            margin-bottom: 50px;
            border-left: 2px solid var(--primary);
            padding-left: 25px;
        }

        .btn-group {
            display: flex;
            gap: 40px;
        }

        .btn-link {
            text-decoration: none;
            color: var(--dark);
            font-size: 13px;
            font-weight: 600;
            letter-spacing: 2px;
            text-transform: uppercase;
            padding-bottom: 8px;
            border-bottom: 1px solid var(--dark);
            transition: 0.3s;
        }

        .btn-link:hover { color: var(--primary); border-color: var(--primary); padding-left: 10px; }

        /* --- MARQUEE (TECH STACK) --- */
        .marquee {
            padding: 40px 0;
            background: #fff;
            border-bottom: 1px solid var(--line-color);
            overflow: hidden;
            display: flex;
        }

        .marquee-content {
            display: flex;
            animation: scroll 20s linear infinite;
            white-space: nowrap;
        }

        .marquee-content span {
            font-size: 14px;
            font-weight: 800;
            letter-spacing: 5px;
            margin: 0 60px;
            text-transform: uppercase;
            color: rgba(0,0,0,0.2);
        }

        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* --- STACKING CARDS (SERVICES) --- */
        .services-container {
            padding: 100px 8%;
        }

        .stacking-card {
            position: sticky;
            top: 100px;
            background: white;
            border: 1px solid var(--line-color);
            border-radius: 32px;
            padding: 60px;
            height: 450px;
            margin-bottom: 100px;
            box-shadow: 0 -20px 40px rgba(0,0,0,0.02);
            display: flex;
            align-items: center;
            transition: transform 0.5s;
        }

        .card-content { flex: 1; }
        .card-content h3 { font-size: 32px; margin-bottom: 20px; }
        .card-image { flex: 1; text-align: right; font-size: 120px; opacity: 0.1; }

        /* --- მობილური --- */
        @media (max-width: 992px) {
            .hero { flex-direction: column; text-align: center; padding-top: 100px; }
            .hero-description { border-left: none; padding-left: 0; margin: 0 auto 40px; }
            .btn-group { justify-content: center; }
            .stacking-card { height: auto; padding: 40px; }
        }
    </style>
</head>
<body>

    <div id="cursor"></div>

    <section class="hero">
        <div class="hero-left">
            <span class="hero-tag">Digital Studio</span>
            <h1>შენი ბიზნესის <br> <b>იდენტობა</b> იწყება აქ</h1>
            <p class="hero-description">
                წაშალეთ ზღვარი იდეასა და რეალობას შორის. ვქმნით ციფრულ გამოცდილებას, რომელიც ბრენდს ხილვადს ხდის.
            </p>
            <div class="btn-group">
                <a href="#" class="btn-link">დავიწყოთ პროექტი</a>
                <a href="#" class="btn-link" style="opacity: 0.5;">პორტფოლიო</a>
            </div>
        </div>
        
        <div style="flex: 1; text-align: right;">
            <img src="https://via.placeholder.com/500x500/f3f4f6/000000?text=GRAPHIC+ELEMENT" alt="UI" style="max-width: 100%; border-radius: 40px;">
        </div>
    </section>

    <div class="marquee">
        <div class="marquee-content">
            <span>WEB ARCHITECTURE</span>
            <span>UI/UX DESIGN</span>
            <span>E-COMMERCE</span>
            <span>SEO OPTIMIZATION</span>
            <span>BRANDING</span>
            <span>WEB ARCHITECTURE</span>
            <span>UI/UX DESIGN</span>
            <span>E-COMMERCE</span>
            <span>SEO OPTIMIZATION</span>
            <span>BRANDING</span>
        </div>
    </div>

    <section class="services-container">
        <div class="stacking-card">
            <div class="card-content">
                <h3>01. კორპორატიული საიტები</h3>
                <p>პროფესიონალური საიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს.</p>
            </div>
            <div class="card-image">🌐</div>
        </div>

        <div class="stacking-card" style="margin-top: -50px;">
            <div class="card-content">
                <h3>02. E-commerce მაღაზიები</h3>
                <p>სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემებით.</p>
            </div>
            <div class="card-image">🛒</div>
        </div>

        <div class="stacking-card" style="margin-top: -50px;">
            <div class="card-content">
                <h3>03. UI/UX დიზაინი</h3>
                <p>ინტუიციური ინტერფეისები საუკეთესო გამოცდილებისთვის.</p>
            </div>
            <div class="card-image">🎨</div>
        </div>
    </section>

    <script>
        // Custom Cursor Logic
        const cursor = document.getElementById('cursor');
        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
        });

        // Hover Effect on buttons
        document.querySelectorAll('a').forEach(link => {
            link.addEventListener('mouseenter', () => {
                cursor.style.transform = 'scale(3)';
                cursor.style.background = 'rgba(37, 99, 235, 0.2)';
            });
            link.addEventListener('mouseleave', () => {
                cursor.style.transform = 'scale(1)';
                cursor.style.background = '#2563eb';
            });
        });
    </script>

</body>
</html>
