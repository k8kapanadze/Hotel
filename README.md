<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Identisite - Digital Authenticity</title>
    <style>
        :root {
            --primary: #2563eb;
            --text-main: #1d1d1f;
            --text-muted: #86868b;
            --bg-light: #fbfbfd;
            --white: #ffffff;
            --card-radius: 28px;
            --shadow: 0 8px 30px rgba(0, 0, 0, 0.04);
        }

        body {
            background-color: var(--bg-light);
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            color: var(--text-main);
            margin: 0;
            line-height: 1.6;
        }

        section { padding: 80px 20px; max-width: 1200px; margin: 0 auto; }
        .center { text-align: center; }

        /* --- Hero Section --- */
        .hero { background: var(--white); text-align: center; padding: 120px 20px; }
        .badge { background: #f2f2f7; color: var(--primary); padding: 8px 20px; border-radius: 40px; font-size: 14px; font-weight: 600; display: inline-block; margin-bottom: 20px; }
        .hero h1 { font-size: 48px; font-weight: 800; line-height: 1.1; margin-bottom: 24px; }
        .hero h1 span { color: var(--primary); }
        .hero p { font-size: 19px; color: var(--text-muted); max-width: 700px; margin: 0 auto 40px; }

        /* --- Buttons --- */
        .btn-group { display: flex; gap: 15px; justify-content: center; flex-wrap: wrap; }
        .btn { padding: 16px 32px; border-radius: 14px; font-weight: 600; text-decoration: none; transition: 0.3s; }
        .btn-blue { background: var(--primary); color: white; box-shadow: 0 10px 20px rgba(37,99,235,0.2); }
        .btn-white { background: white; color: var(--text-main); border: 1px solid #d2d2d7; }

        /* --- Stats --- */
        .stats { display: flex; justify-content: center; gap: 40px; margin-top: 60px; border-top: 1px solid #eee; padding-top: 40px; }
        .stat-item h2 { font-size: 32px; color: var(--primary); margin: 0; }
        .stat-item p { color: var(--text-muted); font-size: 14px; margin: 5px 0 0; }

        /* --- Card Grid --- */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 25px; margin-top: 40px; }
        .card { background: var(--white); padding: 40px; border-radius: var(--card-radius); box-shadow: var(--shadow); border: 1px solid rgba(0,0,0,0.02); transition: 0.3s; }
        .card:hover { transform: translateY(-8px); box-shadow: 0 15px 35px rgba(0,0,0,0.08); }
        .card h3 { font-size: 22px; margin-bottom: 15px; }
        .card p { color: var(--text-muted); font-size: 15px; }
        .icon-box { width: 50px; height: 50px; background: #f0f4ff; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin-bottom: 20px; color: var(--primary); font-size: 20px; }

        .list-item { display: flex; align-items: center; gap: 10px; color: var(--text-muted); font-size: 14px; margin-bottom: 8px; }
        .check { color: var(--primary); font-weight: bold; }

        /* --- Team --- */
        .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 20px; }
        .member { text-align: center; background: white; padding: 30px; border-radius: 24px; box-shadow: var(--shadow); }
        .avatar { width: 80px; height: 80px; background: #eee; border-radius: 50%; margin: 0 auto 15px; display: flex; align-items: center; justify-content: center; font-weight: bold; color: var(--primary); font-size: 24px; }

        @media (max-width: 768px) { .hero h1 { font-size: 34px; } .stats { flex-direction: column; gap: 20px; } }
    </style>
</head>
<body>

    <section class="hero">
        <div class="badge">პრემიუმ ვებ სააგენტო</div>
        <h1>შენი ბიზნესის <br><span>იდენტობა</span> იწყება აქ</h1>
        <p>წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.</p>
        <div class="btn-group">
            <a href="#contact" class="btn btn-blue">დავიწყოთ პროექტი</a>
            <a href="#portfolio" class="btn btn-white">ვნახოთ ნამუშევრები</a>
        </div>
        <div class="stats">
            <div class="stat-item"><h2>150+</h2><p>პროექტი</p></div>
            <div class="stat-item"><h2>98%</h2><p>კმაყოფილება</p></div>
            <div class="stat-item"><h2>5+</h2><p>წლიანი გამოცდილება</p></div>
        </div>
    </section>

    <section>
        <div class="center">
            <div class="badge">ჩვენ შესახებ</div>
            <h2>ციფრული ავთენტურობის სივრცე</h2>
            <p style="max-width: 800px; margin: 0 auto; color: var(--text-muted);">IDENTISITE არის პრემიუმ ვებ-არქიტექტურის სივრცე. ჩვენი მისიაა ბიზნესის იდენტობა ვაქციოთ პრესტიჟულ ციფრულ გამოცდილებად.</p>
        </div>
        <div class="grid">
            <div class="card">
                <h3>მისია</h3>
                <p>ბიზნესების გაძლიერება ინოვაციური ციფრული გადაწყვეტილებებით.</p>
            </div>
            <div class="card">
                <h3>ხედვა</h3>
                <p>გახდეთ რეგიონის წამყვანი ციფრული პარტნიორი.</p>
            </div>
        </div>
    </section>

    <section id="services">
        <div class="center">
            <div class="badge">სერვისები</div>
            <h2>რას გთავაზობთ</h2>
            <p>სრული სპექტრი ციფრული გადაწყვეტილებები თქვენი ბიზნესის ზრდისთვის.</p>
        </div>
        <div class="grid">
            <div class="card">
                <div class="icon-box">🌐</div>
                <h3>კორპორატიული საიტები</h3>
                <p>პროფესიონალური ვებსაიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს.</p>
                <div class="list-item"><span class="check">✓</span> უნიკალური დიზაინი</div>
                <div class="list-item"><span class="check">✓</span> SEO ოპტიმიზაცია</div>
                <a href="#" class="btn btn-white" style="display: block; text-align: center; margin-top: 20px;">შეკვეთა</a>
            </div>
            <div class="card">
                <div class="icon-box">🛒</div>
                <h3>E-commerce მაღაზიები</h3>
                <p>სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემებით და მარაგის მართვით.</p>
                <div class="list-item"><span class="check">✓</span> გადახდის ინტეგრაცია</div>
                <div class="list-item"><span class="check">✓</span> ადმინ პანელი</div>
                <a href="#" class="btn btn-white" style="display: block; text-align: center; margin-top: 20px;">შეკვეთა</a>
            </div>
            <div class="card">
                <div class="icon-box">🎨</div>
                <h3>UI/UX დიზაინი</h3>
                <p>მომხმარებელზე ორიენტირებული ინტერფეისების დიზაინი საუკეთესო გამოცდილებისთვის.</p>
                <div class="list-item"><span class="check">✓</span> Wireframing</div>
                <div class="list-item"><span class="check">✓</span> პროტოტიპირება</div>
                <a href="#" class="btn btn-white" style="display: block; text-align: center; margin-top: 20px;">შეკვეთა</a>
            </div>
        </div>
    </section>

    <section>
        <div class="center"><div class="badge">ჩვენი გუნდი</div><br><br></div>
        <div class="team-grid">
            <div class="member"><div class="avatar">გ.კ</div><h4>გიორგი კვარაცხელია</h4><p>CEO</p></div>
            <div class="member"><div class="avatar">ნ.ბ</div><h4>ნინო ბერიძე</h4><p>დიზაინერი</p></div>
            <div class="member"><div class="avatar">დ.მ</div><h4>დავით მამულაშვილი</h4><p>CTO</p></div>
        </div>
    </section>

</body>
</html>
