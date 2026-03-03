<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Identisite - Hero</title>
    <style>
        :root {
            --primary-blue: #3b82f6;
            --glass-bg: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
            --text-white: #ffffff;
        }

        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: radial-gradient(circle at center, #1a202c 0%, #0a0a0a 100%);
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            color: var(--text-white);
        }

        /* ფონის დეკორატიული ელემენტები */
        .bg-glow {
            position: absolute;
            width: 400px;
            height: 400px;
            background: var(--primary-blue);
            filter: blur(150px);
            opacity: 0.15;
            z-index: 0;
            top: 20%;
            left: 30%;
            animation: move 20s infinite alternate;
        }

        @keyframes move {
            from { transform: translate(0, 0); }
            to { transform: translate(100px, 100px); }
        }

        /* მთავარი კონტეინერი - "შუშის ბარათი" */
        .hero-card {
            position: relative;
            z-index: 1;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 40px;
            padding: 60px 40px;
            text-align: center;
            max-width: 600px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            margin: 20px;
        }

        .badge {
            background: rgba(59, 130, 246, 0.2);
            color: #60a5fa;
            padding: 8px 20px;
            border-radius: 100px;
            font-size: 14px;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 30px;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        h1 {
            font-size: 3rem;
            line-height: 1.2;
            margin-bottom: 25px;
            font-weight: 800;
        }

        h1 span {
            background: linear-gradient(90deg, #60a5fa, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p {
            font-size: 1.1rem;
            line-height: 1.6;
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 40px;
        }

        /* ღილაკების სტილი */
        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .btn {
            padding: 16px 32px;
            border-radius: 16px;
            font-size: 16px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-primary {
            background: var(--primary-blue);
            color: white;
            border: none;
            box-shadow: 0 10px 20px -5px rgba(59, 130, 246, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 25px -5px rgba(59, 130, 246, 0.5);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 1px solid var(--glass-border);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: rgba(255, 255, 255, 0.3);
        }

        /* მობილური ადაპტაცია */
        @media (max-width: 480px) {
            h1 { font-size: 2.2rem; }
            .hero-card { padding: 40px 20px; }
        }
    </style>
</head>
<body>

    <div class="bg-glow"></div>

    <section class="hero-card">
        <div class="badge">პრემიუმ ვებ სააგენტო</div>
        
        <h1>შენი ბიზნესის <br><span>იდენტობა</span> იწყება აქ</h1>
        
        <p>წაშალეთ ზღვარი იდეასა და რეალობას შორის. ვქმნით ციფრულ გამოცდილებას, რომელიც თქვენს ბრენდს ხილვადს და გამორჩეულს ხდის.</p>

        <div class="btn-container">
            <a href="#" class="btn btn-primary">დავიწყოთ პროექტი</a>
            <a href="#" class="btn btn-secondary">ვნახოთ ნამუშევრები</a>
        </div>
    </section>

</body>
</html>
