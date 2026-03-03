<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --bg-white: #fcfcfc;
            --card-bg: #ffffff;
            --primary-blue: #2563eb;
            --text-black: #1a1a1a;
            --text-gray: #666666;
            --border-radius: 32px; /* მომრგვალებული კუთხეები, როგორც ფოტოზეა */
        }

        body {
            background-color: var(--bg-white);
            font-family: 'Helvetica Neue', Arial, sans-serif;
            display: flex;
            justify-content: center;
            padding: 50px 20px;
            margin: 0;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 24px;
            max-width: 1100px;
            width: 100%;
        }

        .service-card {
            background: var(--card-bg);
            border-radius: var(--border-radius);
            padding: 40px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.03); /* ძალიან ნაზი ჩრდილი */
            transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
            display: flex;
            flex-direction: column;
            border: 1px solid rgba(0, 0, 0, 0.02);
            position: relative;
        }

        /* Hover ეფექტი - ბარათი ოდნავ "იწევა" და ჩრდილი მუქდება */
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.08);
        }

        .icon-box {
            width: 60px;
            height: 60px;
            margin-bottom: 30px;
        }

        .icon-box img {
            width: 100%;
            height: auto;
            filter: grayscale(1); /* აიკონები თავიდან ნაცრისფერია */
            transition: filter 0.3s ease;
        }

        .service-card:hover .icon-box img {
            filter: grayscale(0); /* Hover-ზე აიკონი ფერადდება */
        }

        h3 {
            font-size: 24px;
            font-weight: 700;
            color: var(--text-black);
            margin: 0 0 15px 0;
        }

        p {
            font-size: 15px;
            line-height: 1.6;
            color: var(--text-gray);
            margin-bottom: 30px;
            flex-grow: 1;
        }

        .learn-more {
            display: flex;
            align-items: center;
            text-decoration: none;
            color: var(--text-black);
            font-weight: 700;
            font-size: 16px;
            gap: 10px;
            transition: color 0.3s ease;
        }

        .learn-more:hover {
            color: var(--primary-blue);
        }

        .learn-more svg {
            width: 20px;
            transition: transform 0.3s ease;
        }

        .learn-more:hover svg {
            transform: translateX(5px);
        }
    </style>
</head>
<body>

<div class="services-grid">
    
    <div class="service-card">
        <div class="icon-box">
            <img src="https://cdn-icons-png.flaticon.com/512/5202/5202951.png" alt="UX UI">
        </div>
        <h3>UX/UI დიზაინი</h3>
        <p>ჩვენ ვქმნით ინტერფეისებს, სადაც ესთეტიკა და ფუნქციონალი ჰარმონიაშია. თქვენი ბრენდის იდენტობა გადაგვყავს ინტუიციურ ციფრულ გამოცდილებაში.</p>
        <a href="#" class="learn-more">
            გაიგე მეტი 
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
        </a>
    </div>

    <div class="service-card">
        <div class="icon-box">
            <img src="https://cdn-icons-png.flaticon.com/512/2010/2010990.png" alt="Dev">
        </div>
        <h3>ვებ დეველოპმენტი</h3>
        <p>მაღალტექნოლოგიური და სუფთა კოდი, რომელიც თქვენს საიტს სისწრაფესა და მდგრადობას სძენს. ჩვენ ვაშენებთ ციფრულ არქიტექტურას, რომელიც მუშაობს.</p>
        <a href="#" class="learn-more">
            გაიგე მეტი 
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
        </a>
    </div>

</div>

</body>
</html>
