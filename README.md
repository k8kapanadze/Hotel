<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Identisite | Premium Web Studio</title>
    <style>
        /* ვიყენებთ სტანდარტულ, სუფთა Sans-Serif ფონტს */
        body {
            margin: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: #ffffff; /* სუფთა თეთრი ფონი */
            color: #1d1d1f;
            line-height: 1.5;
        }

        /* --- HERO SECTION --- */
        .hero-wrapper {
            display: flex;
            align-items: center;
            justify-content: space-between;
            min-height: 90vh;
            padding: 0 7%;
            gap: 50px;
        }

        .hero-left {
            flex: 1;
            max-width: 650px;
        }

        .hero-left h1 {
            font-size: clamp(42px, 5vw, 72px);
            font-weight: 800; /* ძალიან სქელი და მკაფიო */
            line-height: 1.1;
            margin-bottom: 25px;
            letter-spacing: -1.5px;
        }

        .hero-left h1 span {
            color: #2563eb; /* ლურჯი აქცენტი იდენტობაზე */
        }

        .hero-description {
            font-size: 19px;
            color: #515154;
            line-height: 1.7;
            margin-bottom: 40px;
            font-weight: 400;
            max-width: 550px;
            /* გაშლილი სტილი, ოღონდ ზედმეტობის გარეშე */
            letter-spacing: 0.5px;
        }

        /* ღილაკები - სუფთა და თხელი */
        .cta-group {
            display: flex;
            gap: 20px;
        }

        .btn {
            padding: 16px 35px;
            border-radius: 12px;
            font-size: 15px;
            font-weight: 600;
            text-decoration: none;
            transition: 0.3s;
        }

        .btn-dark {
            background: #1d1d1f;
            color: #ffffff;
        }

        .btn-outline {
            border: 1px solid #d2d2d7;
            color: #1d1d1f;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        /* --- STACKING CARDS (სერვისები) --- */
        .services-section {
            padding: 100px 7%;
            background: #fbfbfd; /* ოდნავ განსხვავებული ფონი სერვისებისთვის */
        }

        .stack-container {
            position: relative;
            max-width: 1100px;
            margin: 0 auto;
        }

        .service-card {
            position: sticky;
            top: 100px; /* სად გაჩერდეს სქროლვისას */
            background: #ffffff;
            border-radius: 35px;
            padding: 60px;
            height: 400px;
            margin-bottom: 50px; /* დაცილება ბარათებს შორის */
            box-shadow: 0 20px 50px rgba(0,0,0,0.05);
            border: 1px solid rgba(0,0,0,0.03);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .service-info { flex: 1; }
        .service-info h2 { font-size: 32px; margin-bottom: 20px; color: #1d1d1f; }
        .service-info p { font-size: 17px; color: #86868b; max-width: 400px; }

        .service-icon {
            font-size: 100px;
            opacity: 0.15;
            filter: grayscale(100%);
        }

        /* მობილური ვერსია */
        @media (max-width: 900px) {
            .hero-wrapper { flex-direction: column; text-align: center; padding-top: 80px; }
            .hero-left { padding-right: 0; }
            .cta-group { justify-content: center; }
            .service-card { flex-direction: column; height: auto; text-align: center; padding: 40px 20px; }
            .service-icon { margin-top: 30px; font-size: 60px; }
        }
    </style>
</head>
<body>

    <section class="hero-wrapper">
        <div class="hero-left">
            <h1>შენი ბიზნესის <br> <span>იდენტობა</span> იწყება აქ</h1>
            <p class="hero-description">
                წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
            </p>
            <div class="cta-group">
                <a href="#" class="btn btn-dark">დავიწყოთ პროექტი</a>
                <a href="#" class="btn btn-outline">ნამუშევრები</a>
            </div>
        </div>

        <div class="hero-right">
            <img src="https://via.placeholder.com/500x450/f4f4f7/2563eb?text=Digital+Identity" alt="Design" style="max-width: 100%; border-radius: 30px;">
        </div>
    </section>

    <section class="services-section">
        <div class="stack-container">
            
            <div class="service-card" style="background: #ffffff;">
                <div class="service-info">
                    <h2>კორპორატიული საიტები</h2>
                    <p>პროფესიონალური ვებსაიტები, რომლებიც თქვენს ბრენდს სათანადოდ წარმოაჩენს და კლიენტებს მოიზიდავს.</p>
                </div>
                <div class="service-icon">🌐</div>
            </div>

            <div class="service-card" style="background: #f9f9fb;">
                <div class="service-info">
                    <h2>E-commerce მაღაზიები</h2>
                    <p>სრულფასოვანი ონლაინ მაღაზიები გადახდის სისტემებით და მარაგის მართვით.</p>
                </div>
                <div class="service-icon">🛒</div>
            </div>

            <div class="service-card" style="background: #f1f5ff;">
                <div class="service-info">
                    <h2>UI/UX დიზაინი</h2>
                    <p>მომხმარებელზე ორიენტირებული ინტერფეისების დიზაინი საუკეთესო გამოცდილებისთვის.</p>
                </div>
                <div class="service-icon">🎨</div>
            </div>

        </div>
    </section>

</body>
</html>
