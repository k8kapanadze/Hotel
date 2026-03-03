<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --primary-gradient: linear-gradient(135px, #2563eb 0%, #1e40af 100%);
            --glass: rgba(255, 255, 255, 0.8);
            --text-dark: #1d1d1f;
            --text-muted: #424245;
        }

        body {
            margin: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: #fbfbfd;
            color: var(--text-dark);
            overflow-x: hidden;
        }

        /* --- ანიმირებული HERO სექცია --- */
        .hero-container {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #ffffff;
            overflow: hidden;
        }

        /* მოძრავი ფონი (Abstract Shapes) */
        .bg-blob {
            position: absolute;
            width: 500px;
            height: 500px;
            background: rgba(37, 99, 235, 0.1);
            filter: blur(80px);
            border-radius: 50%;
            z-index: 0;
            animation: move 20s infinite alternate;
        }

        @keyframes move {
            from { transform: translate(-20%, -20%); }
            to { transform: translate(20%, 20%); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            text-align: center;
            max-width: 900px;
            padding: 40px;
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.2);
            border-radius: 40px;
            border: 1px solid rgba(255, 255, 255, 0.4);
        }

        .hero-badge {
            background: #f2f2f7;
            color: #2563eb;
            padding: 10px 24px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 24px;
        }

        .hero-content h1 {
            font-size: clamp(40px, 8vw, 72px);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 30px;
            letter-spacing: -0.03em;
        }

        .hero-content h1 span {
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-content p {
            font-size: clamp(18px, 2vw, 22px);
            color: var(--text-muted);
            line-height: 1.6;
            margin-bottom: 40px;
        }

        /* --- ღილაკები --- */
        .btn-box {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: #2563eb;
            color: white;
            padding: 20px 40px;
            border-radius: 18px;
            text-decoration: none;
            font-weight: 700;
            transition: 0.3s;
            box-shadow: 0 10px 20px rgba(37, 99, 235, 0.2);
        }

        .btn-secondary {
            background: white;
            color: var(--text-dark);
            padding: 20px 40px;
            border-radius: 18px;
            text-decoration: none;
            font-weight: 700;
            border: 1px solid #d2d2d7;
            transition: 0.3s;
        }

        .btn-primary:hover { transform: translateY(-5px); box-shadow: 0 15px 30px rgba(37, 99, 235, 0.3); }

        /* --- TEGETA STYLE ACCORDION (ჩვენი ისტორია) --- */
        .acc-section {
            max-width: 1000px;
            margin: 100px auto;
            padding: 0 20px;
        }

        .acc-item {
            border-bottom: 1px solid #e5e5e5;
        }

        .acc-header {
            width: 100%;
            padding: 30px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 24px;
            font-weight: 700;
            text-align: left;
        }

        .acc-body {
            max-height: 0;
            overflow: hidden;
            transition: 0.5s ease;
        }

        .acc-item.active .acc-body {
            max-height: 500px;
            padding-bottom: 40px;
        }

        .acc-text {
            font-size: 18px;
            color: var(--text-muted);
            line-height: 1.7;
        }

    </style>
</head>
<body>

    <div class="hero-container">
        <div class="bg-blob"></div>
        <div class="hero-content">
            <div class="hero-badge">პრემიუმ ვებ სააგენტო</div>
            <h1>შენი ბიზნესის <br> <span>იდენტობა</span> იწყება აქ</h1>
            <p>წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.</p>
            <div class="btn-box">
                <a href="#" class="btn-primary">დავიწყოთ პროექტი</a>
                <a href="#" class="btn-secondary">ვნახოთ ნამუშევრები</a>
            </div>
        </div>
    </div>

    <div class="acc-section">
        <div class="acc-item active">
            <button class="acc-header" onclick="toggleAcc(this)">ჩვენი ისტორია <span>+</span></button>
            <div class="acc-body">
                <div class="acc-text">
                    Identisite შეიქმნა მათთვის, ვისაც ესმის, რომ ციფრულ ეპოქაში ვებგვერდი ბიზნესის მთავარი ინტელექტუალური აქტივია. ჩვენ გავიარეთ გზა ტექნიკური შესრულებიდან შემოქმედებით სტრატეგიამდე.
                </div>
            </div>
        </div>
        <div class="acc-item">
            <button class="acc-header" onclick="toggleAcc(this)">მისია <span>+</span></button>
            <div class="acc-body">
                <div class="acc-text">
                    ბიზნესების გაძლიერება ინოვაციური ციფრული გადაწყვეტილებებით.
                </div>
            </div>
        </div>
        <div class="acc-item">
            <button class="acc-header" onclick="toggleAcc(this)">ხედვა <span>+</span></button>
            <div class="acc-body">
                <div class="acc-text">
                    გახდეთ რეგიონის წამყვანი ციფრული პარტნიორი.
                </div>
            </div>
        </div>
    </div>

    <script>
        function toggleAcc(btn) {
            const item = btn.parentElement;
            item.classList.toggle('active');
        }
    </script>

</body>
</html>
