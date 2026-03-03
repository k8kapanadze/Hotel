<style>
    /* 1. ძირითადი პარამეტრები და ფონტები */
    :root {
        --primary: #2563eb;
        --text-main: #1d1d1f;
        --text-muted: #86868b;
        --bg-light: #fbfbfd;
        --white: #ffffff;
        --card-radius: 32px;
        --shadow: 0 8px 30px rgba(0, 0, 0, 0.04);
    }

    body {
        background-color: var(--bg-light);
        font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
        color: var(--text-main);
        margin: 0;
        line-height: 1.5;
    }

    /* 2. საერთო სექციების სტილი */
    section {
        padding: 80px 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .section-title {
        text-align: center;
        font-size: 40px;
        font-weight: 700;
        margin-bottom: 50px;
    }

    /* 3. HERO სექცია (image 1 & 4) */
    .hero {
        text-align: center;
        padding-top: 120px;
        background: white;
    }

    .hero h1 {
        font-size: 52px;
        letter-spacing: -0.02em;
        margin-bottom: 20px;
    }

    .hero h1 span { color: var(--primary); }

    .hero p {
        font-size: 20px;
        color: var(--text-muted);
        max-width: 700px;
        margin: 0 auto 40px;
    }

    /* 4. ბარათების სისტემა (Card Grid - image 2, 8, 9) */
    .card-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
        gap: 24px;
    }

    .card {
        background: var(--white);
        padding: 40px;
        border-radius: var(--card-radius);
        box-shadow: var(--shadow);
        border: 1px solid rgba(0,0,0,0.03);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        text-align: left;
    }

    .card:hover {
        transform: translateY(-10px);
        box-shadow: 0 20px 40px rgba(0,0,0,0.08);
    }

    .card-icon {
        width: 56px;
        height: 56px;
        background: #f0f4ff;
        border-radius: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 24px;
        color: var(--primary);
        font-size: 24px;
    }

    .card h3 {
        font-size: 24px;
        margin-bottom: 16px;
    }

    .card p {
        color: var(--text-muted);
        font-size: 16px;
        margin-bottom: 24px;
    }

    /* 5. ღილაკების სტილი (image 1) */
    .btn {
        display: inline-block;
        padding: 16px 32px;
        border-radius: 14px;
        font-weight: 600;
        text-decoration: none;
        transition: 0.2s;
    }

    .btn-blue { background: var(--primary); color: white; }
    .btn-white { background: white; color: var(--text-main); border: 1px solid #d2d2d7; }

    /* 6. მობილური ვერსია */
    @media (max-width: 768px) {
        .hero h1 { font-size: 36px; }
        .card-grid { grid-template-columns: 1fr; }
        .card { padding: 30px; }
    }
</style>

<section class="hero">
    <h1>შენი ბიზნესის <span>იდენტობა</span> იწყება აქ</h1>
    <p>ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს და გამორჩეულს ხდის.</p>
    <div style="display: flex; gap: 15px; justify-content: center;">
        <a href="#" class="btn btn-blue">დავიწყოთ პროექტი</a>
        <a href="#" class="btn btn-white">ნამუშევრები</a>
    </div>
</section>

<section id="services">
    <h2 class="section-title">რას გთავაზობთ</h2>
    <div class="card-grid">
        <div class="card">
            <div class="card-icon">🎨</div>
            <h3>UI/UX დიზაინი</h3>
            <p>მომხმარებელზე ორიენტირებული ინტერფეისების დიზაინი საუკეთესო გამოცდილებისთვის.</p>
            <a href="#" style="color: var(--text-main); font-weight: 600; text-decoration: none;">გაიგე მეტი →</a>
        </div>
        
        <div class="card">
            <div class="card-icon">🌐</div>
            <h3>კორპორატიული საიტები</h3>
            <p>პროფესიონალური ვებ-გვერდები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს.</p>
            <a href="#" style="color: var(--text-main); font-weight: 600; text-decoration: none;">გაიგე მეტი →</a>
        </div>
    </div>
</section>
