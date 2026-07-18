# wedding-invitation
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>دعوة زفاف فاخرة</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Reem+Kufi:wght@400;700&family=Cairo:wght@400;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --bg-cream: #fbf7f4;
            --gold-dark: #b89742;
            --gold-light: #dfc88b;
            --text-dark: #3a2e2b;
            --rose-taupe: #8c6b6d;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Amiri', serif;
            background-color: var(--bg-cream);
            color: var(--text-dark);
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* خلفية الزخارف الملكية المتكررة */
        .background-ornaments {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            opacity: 0.08;
            background-image: url('https://www.transparenttextures.com/patterns/arabesque.png');
        }

        /* حاوية الظرف بأسلوب الفيديو */
        #envelope-wrapper {
            position: relative;
            width: 100%;
            max-width: 420px;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10;
            padding: 20px;
            transition: all 1s ease-in-out;
        }

        .envelope-card {
            width: 100%;
            height: 550px;
            background: #ffffff;
            border-radius: 20px;
            box-shadow: 0 20px 50px rgba(58, 46, 43, 0.15);
            border: 2px solid var(--gold-light);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            cursor: pointer;
            background-image: radial-gradient(circle at top left, var(--bg-cream) 0%, #ffffff 70%);
        }

        .frame-ornament {
            position: absolute;
            top: 15px;
            left: 15px;
            right: 15px;
            bottom: 15px;
            border: 1px solid var(--gold-light);
            border-radius: 15px;
            pointer-events: none;
        }

        .frame-ornament::before {
            content: '❖';
            position: absolute;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
            background: #ffffff;
            color: var(--gold-dark);
            padding: 0 10px;
            font-size: 1.2rem;
        }

        .envelope-title {
            font-size: 2rem;
            color: var(--gold-dark);
            margin-bottom: 40px;
            font-family: 'Reem Kufi', sans-serif;
        }

        /* الختم الشمعي الدائري التفاعلي */
        .wax-seal-container {
            position: relative;
            width: 130px;
            height: 130px;
            display: flex;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle, #e9c366 0%, #b89742 100%);
            border-radius: 50%;
            box-shadow: 0 10px 25px rgba(184, 151, 66, 0.5), inset 0 2px 5px rgba(255,255,255,0.4);
            border: 4px double #ffffff;
            transition: transform 0.5s ease;
        }

        .wax-seal-container:hover {
            transform: scale(1.08) rotate(5deg);
        }

        .wax-seal-text {
            font-family: 'Reem Kufi', sans-serif;
            font-size: 2.2rem;
            color: #ffffff;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .click-hint {
            margin-top: 40px;
            font-family: 'Cairo', sans-serif;
            font-size: 0.9rem;
            color: var(--rose-taupe);
            animation: pulseHint 1.8s infinite;
        }

        /* بطاقة الدعوة الرئيسية الفخمة */
        #main-wedding-card {
            display: none;
            width: 100%;
            max-width: 450px;
            background: #ffffff;
            border: 3px double var(--gold-light);
            padding: 40px 25px;
            text-align: center;
            position: relative;
            z-index: 5;
            opacity: 0;
            transform: translateY(30px);
            transition: all 1.2s ease;
        }

        .islamic-header {
            font-size: 1.4rem;
            line-height: 2;
            color: var(--rose-taupe);
            margin-bottom: 25px;
            font-weight: bold;
        }

        .wedding-label {
            font-family: 'Reem Kufi', sans-serif;
            color: var(--gold-dark);
            font-size: 1.4rem;
            margin-bottom: 10px;
        }

        .bride-groom-names {
            font-family: 'Reem Kufi', sans-serif;
            font-size: 2.8rem;
            color: var(--text-dark);
            margin: 20px 0;
            line-weight: 700;
        }

        .bride-groom-names span {
            display: block;
            font-family: 'Amiri', serif;
            font-size: 1.8rem;
            color: var(--gold-dark);
            margin: 5px 0;
        }

        .invitation-details {
            font-size: 1.3rem;
            line-height: 1.9;
            color: #4a4a4a;
            margin: 25px 0;
        }

        /* العداد التنازلي */
        .countdown-section {
            background-color: #faf6f2;
            border-top: 1px solid var(--gold-light);
            border-bottom: 1px solid var(--gold-light);
            padding: 20px 10px;
            margin: 30px 0;
        }

        .countdown-section h3 {
            font-size: 1.2rem;
            color: var(--gold-dark);
            margin-bottom: 15px;
            font-family: 'Cairo', sans-serif;
        }

        .timer-display {
            display: flex;
            justify-content: center;
            gap: 12px;
        }

        .time-segment {
            background: #ffffff;
            border: 1px solid #ebdcc5;
            min-width: 70px;
            padding: 10px 5px;
            border-radius: 8px;
        }

        .time-value {
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--rose-taupe);
            display: block;
            font-family: 'Cairo', sans-serif;
        }

        .time-label {
            font-size: 0.8rem;
            color: #7a6e67;
            font-family: 'Cairo', sans-serif;
        }

        /* أزرار التفاعل والموقع والواتساب */
        .action-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            width: 100%;
            max-width: 340px;
            padding: 14px 25px;
            margin: 12px 0;
            border: none;
            font-family: 'Cairo', sans-serif;
            font-size: 1rem;
            font-weight: 700;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            text-decoration: none;
            border-radius: 30px;
        }

        .btn-gold-gradient {
            background: linear-gradient(135deg, #b89742 0%, #dcd1a1 50%, #b89742 100%);
            color: #ffffff;
            box-shadow: 0 5px 20px rgba(184, 151, 66, 0.3);
        }

        .btn-gold-gradient:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(184, 151, 66, 0.45);
        }

        .btn-whatsapp-style {
            background-color: #25D366;
            color: #ffffff;
            box-shadow: 0 5px 20px rgba(37, 211, 102, 0.25);
        }

        .btn-whatsapp-style:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.4);
        }

        /* بتلات الورد المتساقطة مثل الفيديو */
        .rose-petal {
            position: fixed;
            top: -20px;
            pointer-events: none;
            z-index: 999;
            background: radial-gradient(circle, #ffcbd5 0%, #fca3b5 100%);
            border-radius: 50% 0 50% 50%;
            opacity: 0.6;
            animation: fallingPetal linear infinite;
        }

        @keyframes pulseHint {
            0%, 100% { transform: scale(1); opacity: 0.7; }
            50% { transform: scale(1.03); opacity: 1; }
        }

        @keyframes fallingPetal {
            0% { transform: translateY(0) rotate(0deg); opacity: 0; }
            10% { opacity: 0.7; }
            100% { transform: translateY(105vh) rotate(450deg); opacity: 0; }
        }

        .fade-out-envelope {
            opacity: 0;
            transform: scale(0.9);
            pointer-events: none;
        }
    </style>
</head>
<body>

    <div class="background-ornaments"></div>

    <div id="envelope-wrapper">
        <div class="envelope-card" onclick="openWeddingInvitation()">
            <div class="frame-ornament"></div>
            <h2 class="envelope-title">دعوة زفاف ممتنة</h2>
            
            <div class="wax-seal-container">
                <div class="wax-seal-text">فرح</div>
            </div>
            
            <div class="click-hint">اضغط على الختم لفتح الدعوة الملكية ✨</div>
        </div>
    </div>

    <div id="main-wedding-card">
        <div class="islamic-header">
            بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ <br>
            ﴿وَمِنْ آيَاتِهِ أَنْ خَلَقَ لَكُمْ مِنْ أَنْفُسِكُمْ أَزْوَاجًا لِتَسْكُنُوا إِلَيْهَا وَجَعَلَ بَيْنَكُمْ مَوَدَّةً وَرَحْمَةً﴾
        </div>

        <div class="wedding-label">يوم الزفاف السعيد</div>
        
        <div class="bride-groom-names">
            اسم العريس
            <span>＆</span>
            اسم العروس
        </div>

        <p class="invitation-details">
            بقلوب تفيض بالحب والبهجة، وبأجمل عبارات الترحيب، ندعوكم لمشاركتنا ليلة العمر وتوثيق أسعد لحظاتنا، حضوركم يكمل أنسنا ويبهج ليلتنا.
        </p>

        <div class="countdown-section">
            <h3>اقترب موعد الفرح 🤍</h3> 
