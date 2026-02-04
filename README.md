<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hotel Management Dashboard 2.0</title>
    <style>
        :root {
            --primary-color: #2563eb; /* ძირითადი ლურჯი */
            --bg-color: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-sub: #64748b;
            --border-color: #e2e8f0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            margin: 0;
            padding: 20px;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            margin-bottom: 30px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }

        h1 { font-size: 1.5rem; font-weight: 600; }

        /* Dashboard Grid */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .card {
            background: var(--card-bg);
            padding: 20px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            transition: transform 0.2s;
        }

        .card:hover { transform: translateY(-3px); }

        .card-title {
            color: var(--text-sub);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }

        .card-value {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        .card-desc {
            font-size: 0.85rem;
            color: var(--text-sub);
            margin-top: 5px;
        }

        /* Digital Key Section */
        .action-section {
            margin-top: 40px;
            background: #fff;
            padding: 25px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }

        .btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.9rem;
        }

        .status-badge {
            display: inline-block;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.75rem;
            background: #dcfce7;
            color: #166534;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>სასტუმროს მართვა</h1>
        <p style="color: var(--text-sub);">ადმინისტრატორი: admin | <a href="#">გასვლა</a></p>
    </header>

    <div class="dashboard-grid">
        <div class="card">
            <div class="card-title">დღევანდელი ნაკადი</div>
            <div class="card-value">5 / 3</div>
            <div class="card-desc">შემოდის 5, გადის 3 სტუმარი</div>
        </div>

        <div class="card">
            <div class="card-title">ოთახების სტატუსი</div>
            <div class="card-value">12 თავისუფალი</div>
            <div class="card-desc">3 საჭიროებს დასუფთავებას</div>
        </div>

        <div class="card">
            <div class="card-title">ავტომატური შეტყობინებები</div>
            <div class="card-value">8 გაგზავნილი</div>
            <div class="card-desc">დასტური: 5 | შეხსენება: 3</div>
        </div>
    </div>

    <div class="action-section">
        <h3>ციფრული გასაღები და სერვისები</h3>
        <table style="width: 100%; border-collapse: collapse; margin-top: 15px;">
            <tr style="border-bottom: 1px solid #eee;">
                <th style="text-align: left; padding: 10px;">სტუმარი</th>
                <th style="text-align: left; padding: 10px;">ოთახი</th>
                <th style="text-align: left; padding: 10px;">სტატუსი</th>
                <th style="text-align: right; padding: 10px;">მოქმედება</th>
            </tr>
            <tr>
                <td style="padding: 10px;">გიორგი ბერიძე</td>
                <td style="padding: 10px;">#204</td>
                <td style="padding: 10px;"><span class="status-badge">აქტიური გასაღები</span></td>
                <td style="padding: 10px; text-align: right;">
                    <button class="btn" onclick="sendKey()">გასაღების გაგზავნა</button>
                </td>
            </tr>
        </table>
    </div>
</div>

<script>
    function sendKey() {
        alert("ციფრული გასაღები გაიგზავნა სტუმრის სმარტფონზე!");
    }

    // ლოგიკა ავტომატური შეტყობინებებისთვის (იმიტაცია)
    function autoNotifications() {
        console.log("სისტემა ამოწმებს ჯავშნებს...");
        console.log("1. ჯავშნის დასტური გაეგზავნა ახალ მომხმარებელს.");
        console.log("2. შეხსენება (1 დღით ადრე) გაეგზავნა ხვალინდელ სტუმრებს.");
    }
</script>

</body>
</html>
