<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* ფონტის იმპორტი (მსგავსი სტილისთვის ვიყენებთ სერიფულ ფონტს) */
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Inter:wght@300;400&display=swap');

        :root {
            --bg-white: #ffffff;
            --primary-blue: #1a4cd3;
            --text-dark: #000000;
            --text-muted: #555555;
        }

        body, html {
            margin: 0;
            padding: 0;
            background-color: var(--bg-white);
            font-family: 'Inter', sans-serif;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-wrapper {
            text-align: center;
            max-width: 1000px;
            padding: 20px;
        }

        /* სათაური: Robakidze Style (Serif, Bold, Elegant) */
        h1 {
            font-family: 'Playfair Display', serif; /* სერიფული ფონტი სათაურისთვის */
            font-size: clamp(45px, 7vw, 85px);
            font-weight: 900;
            line-height: 1.05;
            color: var(--text-dark);
            margin-bottom: 35px;
            letter-spacing: -1px;
        }

        h1 span {
            color: var(--primary-blue);
        }

        /* ქვედა ტექსტი: უფრო გაშლილი (Letter-spacing) */
        .hero-description {
            font-size: clamp(16px, 2vw, 20px);
            color: var(--text-muted);
            max-width: 800px;
            margin: 0 auto 50px;
            line-height: 1.8;
            letter-spacing: 1.5px; /* ტექსტის გაშლა */
            font-weight: 300;
            text-transform: lowercase; /* სურვილისამებრ, უფრო მოდერნისტული იერისთვის */
        }

        /* ღილაკები: უფრო თხელი (Thin/Minimalist) */
        .btn-wrap {
            display: flex;
            gap: 25px;
            justify-content: center;
            align-items: center;
        }

        .btn {
            font-family: 'Inter', sans-serif;
            font-weight: 300; /* თხელი ფონტი */
            font-size: 15px;
            text-decoration: none;
            letter-spacing: 2px;
            text-transform: uppercase;
            padding: 12px 35px;
            transition: all 0.4s ease;
            border-radius: 2px; /* მკვეთრი, თხელი კუთხეები */
        }

        .btn-primary {
            background-color: var(--text-dark);
            color: #fff;
            border: 1px solid var(--text-dark);
        }

        .btn-primary:hover {
            background-color: transparent;
            color: var(--text-dark);
        }

        .btn-secondary {
            color: var(--text-dark);
            border-bottom: 1px solid var(--text-dark); /* მხოლოდ ქვედა ხაზი თხელი ეფექტისთვის */
            padding: 12px 10px;
        }

        .btn-secondary:hover {
            opacity: 0.6;
        }

        /* მობილურისთვის */
        @media (max-width: 600px) {
            h1 { font-size: 40px; }
            .hero-description { letter-spacing: 1px; }
            .btn-wrap { flex-direction: column; gap: 15px; }
        }
    </style>
</head>
<body>

    <div class="hero-wrapper">
        <h1>შენი ბიზნესის <br> <span>იდენტობა</span> იწყება აქ</h1>
        
        <p class="hero-description">
            წაშალეთ ზღვარი იდეასა და რეალობას შორის. ჩვენ ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს, გამორჩეულს და შედეგზე ორიენტირებულს ხდის.
        </p>

        <div class="btn-wrap">
            <a href="#" class="btn btn-primary">დავიწყოთ პროექტი</a>
            <a href="#" class="btn btn-secondary">ვნახოთ ნამუშევრები</a>
        </div>
    </div>

</body>
</html>
