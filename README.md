<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Identisite - Editorial Style</title>
    <style>
        /* სათაურისთვის ვიყენებთ ელეგანტურ სერიფს, ქვედა ტექსტისთვის - სუფთა სან-სერიფს */
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,900;1,900&family=Montserrat:wght@200;300&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            background-color: #ffffff;
            color: #1a1a1a;
            font-family: 'Montserrat', sans-serif;
            height: 100vh;
            overflow: hidden;
            display: flex;
            align-items: center;
        }

        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 50px;
            position: relative;
        }

        /* სათაური - ასიმეტრიული და მასიური */
        .hero-title {
            font-family: 'Playfair Display', serif;
            font-size: clamp(60px, 10vw, 120px);
            font-weight: 900;
            line-height: 0.9;
            margin: 0;
            text-transform: uppercase;
            letter-spacing: -4px;
        }

        .hero-title span {
            display: block;
            margin-left: 15%; /* აცდენილი ტექსტი */
            color: #2563eb;
            font-style: italic; /* "იდენტობა" დახრილია უფრო მეტი აქცენტისთვის */
        }

        /* ქვედა ტექსტი - ძალიან გაშლილი და თხელი */
        .hero-sub {
            margin-top: 60px;
            margin-left: 40%; /* განთავსებულია მარჯვენა მხარეს */
            max-width: 500px;
            font-size: 14px;
            font-weight: 300;
            line-height: 2;
            letter-spacing: 4px; /* სუპერ გაშლილი */
            text-transform: uppercase;
            color: #666;
        }

        /* ღილაკები - ძალიან თხელი და ელეგანტური */
        .nav-actions {
            margin-top: 80px;
            display: flex;
            gap: 60px;
            justify-content: flex-end;
        }

        .action-link {
            text-decoration: none;
            color: #1a1a1a;
            font-size: 12px;
            font-weight: 400;
            letter-spacing: 3px;
            text-transform: uppercase;
            position: relative;
            padding-bottom: 5px;
            transition: 0.4s;
        }

        .action-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 30px; /* თავიდან მოკლე ხაზი */
            height: 1px;
            background: #1a1a1a;
            transition: 0.4s;
        }

        .action-link:hover::after {
            width: 100%; /* hover-ზე ივსება */
        }

        .action-link.primary {
            color: #2563eb;
        }
        .action-link.primary::after {
            background: #2563eb;
        }

        /* მობილურისთვის ადაპტაცია */
        @media (max-width: 900px) {
            .hero-title span { margin-left: 0; }
            .hero-sub { margin-left: 0; margin-top: 40px; letter-spacing: 2px; }
            .nav-actions { justify-content: flex-start; gap: 30px; }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1 class="hero-title">
            შენი ბიზნესის <br>
            <span>იდენტობა</span> 
            იწყება აქ
        </h1>

        <p class="hero-sub">
            წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
        </p>

        <div class="nav-actions">
            <a href="#" class="action-link primary">დავიწყოთ პროექტი</a>
            <a href="#" class="action-link">ვნახოთ ნამუშევრები</a>
        </div>
    </div>

</body>
</html>
