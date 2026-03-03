<style>
    .accordion-section {
        max-width: 1100px;
        margin: 60px auto;
        font-family: -apple-system, sans-serif;
    }

    .accordion-item {
        border-bottom: 1px solid #e5e5e5;
        overflow: hidden;
    }

    /* სათაურის სტილი */
    .accordion-header {
        width: 100%;
        padding: 24px;
        background: #f9f9fb;
        border: none;
        outline: none;
        text-align: left;
        display: flex;
        align-items: center;
        cursor: pointer;
        transition: background 0.3s;
    }

    .accordion-header:hover {
        background: #f0f0f5;
    }

    .accordion-number {
        font-size: 14px;
        color: #86868b;
        margin-right: 20px;
        font-weight: 600;
    }

    .accordion-title {
        font-size: 20px;
        font-weight: 700;
        color: #1d1d1f;
        text-transform: uppercase;
    }

    /* შინაარსის სტილი */
    .accordion-content {
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.5s cubic-bezier(0, 1, 0, 1);
        background: white;
        display: flex;
        flex-wrap: wrap;
    }

    /* როცა აკორდეონი ღიაა */
    .accordion-item.active .accordion-content {
        max-height: 1000px;
        transition: max-height 1s ease-in-out;
    }

    .accordion-item.active .accordion-header {
        background: white;
    }

    .content-inner {
        padding: 40px;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 40px;
        align-items: center;
    }

    .content-text h3 {
        font-size: 32px;
        margin-bottom: 20px;
        color: #2563eb;
    }

    .content-text p {
        font-size: 17px;
        color: #424245;
        line-height: 1.6;
    }

    .content-image {
        width: 100%;
        border-radius: 12px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    }

    @media (max-width: 768px) {
        .content-inner { grid-template-columns: 1fr; }
        .accordion-title { font-size: 16px; }
    }
</style>

<div class="accordion-section">
    <div class="accordion-item active">
        <button class="accordion-header" onclick="toggleAccordion(this)">
            <span class="accordion-number">1</span>
            <span class="accordion-title">ჩვენი ისტორია</span>
        </button>
        <div class="accordion-content">
            <div class="content-inner">
                <div class="content-text">
                    <h3>Identisite-ის გზა</h3>
                    <p>Identisite შეიქმნა მათთვის, ვისაც ესმის, რომ ციფრულ ეპოქაში ვებგვერდი ბიზნესის მთავარი ინტელექტუალური აქტივია. ჩვენ გავიარეთ გზა ტექნიკური შესრულებიდან შემოქმედებით სტრატეგიამდე.</p>
                </div>
                <img src="https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&w=600&q=80" class="content-image" alt="History">
            </div>
        </div>
    </div>

    <div class="accordion-item">
        <button class="accordion-header" onclick="toggleAccordion(this)">
            <span class="accordion-number">2</span>
            <span class="accordion-title">მისია</span>
        </button>
        <div class="accordion-content">
            <div class="content-inner">
                <div class="content-text">
                    <h3>ჩვენი მისია</h3>
                    <p>ბიზნესების გაძლიერება ინოვაციური ციფრული გადაწყვეტილებებით. ჩვენი მიზანია, თითოეული პროექტი იყოს უნიკალური და შედეგზე ორიენტირებული.</p>
                </div>
                <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&w=600&q=80" class="content-image" alt="Mission">
            </div>
        </div>
    </div>

    <div class="accordion-item">
        <button class="accordion-header" onclick="toggleAccordion(this)">
            <span class="accordion-number">3</span>
            <span class="accordion-title">ხედვა</span>
        </button>
        <div class="accordion-content">
            <div class="content-inner">
                <div class="content-text">
                    <h3>ციფრული მომავალი</h3>
                    <p>გახდეთ რეგიონის წამყვანი ციფრული პარტნიორი, რომელიც ბიზნესებს ეხმარება ციფრული ტრანსფორმაციის ყველა ეტაპზე.</p>
                </div>
                <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&w=600&q=80" class="content-image" alt="Vision">
            </div>
        </div>
    </div>
</div>

<script>
    function toggleAccordion(element) {
        const item = element.parentElement;
        const allItems = document.querySelectorAll('.accordion-item');
        
        allItems.forEach(i => {
            if (i !== item) i.classList.remove('active');
        });
        
        item.classList.toggle('active');
    }
</script>
