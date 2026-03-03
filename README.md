<style>
    :root {
        --bg-color: #f8f9fa;
        --card-shadow: 0 10px 30px rgba(0, 0, 0, 0.04);
        --accent-blue: #2563eb;
        --text-dark: #1d1d1f;
        --text-muted: #86868b;
    }

    body {
        background-color: var(--bg-color);
        font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Helvetica Neue", Arial, sans-serif;
        color: var(--text-dark);
        margin: 0;
    }

    /* --- HERO SECTION --- */
    .hero-section {
        padding: 120px 20px;
        text-align: center;
        background: white;
        margin-bottom: 40px;
    }

    .badge {
        background: #f2f2f7;
        color: var(--accent-blue);
        padding: 8px 20px;
        border-radius: 40px;
        font-size: 14px;
        font-weight: 600;
        display: inline-block;
        margin-bottom: 24px;
    }

    .hero-section h1 {
        font-size: 48px;
        font-weight: 700;
        letter-spacing: -0.02em;
        line-height: 1.1;
        margin-bottom: 20px;
    }

    .hero-section h1 span {
        color: var(--accent-blue);
    }

    .hero-section p {
        font-size: 19px;
        color: var(--text-muted);
        max-width: 600px;
        margin: 0 auto 40px;
        line-height: 1.5;
    }

    /* --- BUTTONS --- */
    .btn-group {
        display: flex;
        gap: 16px;
        justify-content: center;
    }

    .btn-main {
        background: var(--accent-blue);
        color: white;
        padding: 16px 32px;
        border-radius: 12px;
        text-decoration: none;
        font-weight: 600;
        transition: transform 0.2s;
    }

    .btn-outline {
        background: white;
        color: var(--text-dark);
        border: 1px solid #d2d2d7;
        padding: 16px 32px;
        border-radius: 12px;
        text-decoration: none;
        font-weight: 600;
    }

    .btn-main:hover { transform: scale(1.02); }

    /* --- SERVICES GRID (ზუსტად შენს ფოტოსავით) --- */
    .services-container {
        max-width: 1100px;
        margin: 60px auto;
        padding: 0 20px;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
        gap: 30px;
    }

    .service-card {
        background: white;
        padding: 40px;
        border-radius: 32px; /* ზუსტად ისეთივე მომრგვალება */
        box-shadow: var(--card-shadow);
        border: 1px solid rgba(0,0,0,0.02);
        transition: all 0.3s ease;
        text-align: left;
    }

    .service-card:hover {
        transform: translateY(-8px);
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
    }

    .service-card img {
        width: 48px;
        height: 48px;
        margin-bottom: 24px;
    }

    .service-card h3 {
        font-size: 24px;
        margin-bottom: 16px;
    }

    .service-card p {
        color: var(--text-muted);
        font-size: 16px;
        line-height: 1.6;
        margin-bottom: 24px;
    }

    .go-more {
        font-weight: 600;
        color: var(--text-dark);
        text-decoration: none;
        display: flex;
        align-items: center;
        gap: 8px;
    }

    .go-more:after {
        content: "→";
        transition: transform 0.2s;
    }

    .go-more:hover:after { transform: translateX(5px); }
</style>

<section class="hero-section">
    <div class="badge">პრემიუმ ვებ სააგენტო</div>
    <h1>შენი ბიზნესის <br> <span>იდენტობა</span> იწყება აქ</h1>
    <p>იდენტობა რომელიც საიტად იქცევა — ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს გამოარჩევს და შედეგს მოგიტანთ.</p>
    <div class="btn-group">
        <a href="#contact" class="btn-main">დავიწყოთ პროექტი</a>
        <a href="#portfolio" class="btn-outline">ვნახოთ ნამუშევრები</a>
    </div>
</section>

<div class="services-container">
    <div class="service-card">
        <img src="https://cdn-icons-png.flaticon.com/512/5202/5202951.png" alt="UX">
        <h3>UX/UI დიზაინი</h3>
        <p>თუ თქვენი ვებ გვერდის დიზაინი არ პასუხობს თანამედროვე სტანდარტებს, მაშინ სწორ ადგილას მოხვედით!</p>
        <a href="#" class="go-more">გაიგე მეტი</a>
    </div>

    <div class="service-card">
        <img src="https://cdn-icons-png.flaticon.com/512/2010/2010990.png" alt="Web">
        <h3>ვებ დეველოპმენტი</h3>
        <p>მაღალტექნოლოგიური და სუფთა კოდი, რომელიც თქვენს საიტს სისწრაფესა და მდგრადობას სძენს.</p>
        <a href="#" class="go-more">გაიგე მეტი</a>
    </div>
</div>
