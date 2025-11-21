
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اختبار الرخصة المهنية - تخصص الجغرافيا</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #0d1b2a;
            --secondary: #1b263b;
            --accent: #415a77;
            --accent-light: #778da9;
            --correct: #2ecc71;
            --incorrect: #e74c3c;
            --text: #e0e1dd;
            --text-light: #b0b0b0;
            --border: #415a77;
            --card-bg: #1b263b;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--primary), #1b263b);
            color: var(--text);
            line-height: 1.6;
            padding: 20px;
            direction: rtl;
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            background-color: var(--secondary);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--accent), var(--accent-light));
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border);
            position: relative;
        }
        
        .logo {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--accent), var(--accent-light));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 2rem;
            color: white;
            box-shadow: 0 5px 15px rgba(65, 90, 119, 0.4);
        }
        
        h1 {
            color: white;
            margin-bottom: 10px;
            font-size: 2.2rem;
            background: linear-gradient(to right, #fff, var(--text-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .subtitle {
            color: var(--text-light);
            font-size: 1.2rem;
        }
        
        .exam-info {
            display: flex;
            justify-content: space-between;
            background: rgba(27, 38, 59, 0.7);
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 25px;
            border: 1px solid var(--border);
        }
        
        .info-item {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .info-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--accent-light);
        }
        
        .info-label {
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        .instructions {
            background: linear-gradient(135deg, rgba(65, 90, 119, 0.1), rgba(119, 141, 169, 0.1));
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 25px;
            border-right: 4px solid var(--accent);
        }
        
        .instructions h3 {
            color: var(--accent-light);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }
        
        .instructions h3 i {
            margin-left: 10px;
        }
        
        .question {
            margin-bottom: 30px;
            padding: 25px;
            background-color: var(--card-bg);
            border-radius: 15px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .question::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 4px;
            height: 100%;
            background: linear-gradient(to bottom, var(--accent), var(--accent-light));
        }
        
        .question:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }
        
        .question-number {
            font-weight: bold;
            color: var(--accent-light);
            margin-bottom: 15px;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
        }
        
        .question-number::before {
            content: '';
            display: inline-block;
            width: 10px;
            height: 10px;
            background-color: var(--accent);
            border-radius: 50%;
            margin-left: 10px;
        }
        
        .question-text {
            margin-bottom: 20px;
            font-size: 1.15rem;
            line-height: 1.7;
        }
        
        .options {
            display: grid;
            gap: 12px;
        }
        
        .option {
            padding: 15px 20px;
            background-color: rgba(27, 38, 59, 0.7);
            border: 1px solid var(--border);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        
        .option::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 4px;
            height: 100%;
            background-color: var(--accent);
            transition: all 0.3s ease;
            transform: scaleY(0);
        }
        
        .option:hover {
            background-color: rgba(40, 55, 82, 0.7);
            transform: translateX(-5px);
        }
        
        .option:hover::before {
            transform: scaleY(1);
        }
        
        .option.selected.correct {
            background-color: rgba(46, 204, 113, 0.15);
            border-color: var(--correct);
            color: var(--correct);
        }
        
        .option.selected.correct::before {
            background-color: var(--correct);
            transform: scaleY(1);
        }
        
        .option.selected.incorrect {
            background-color: rgba(231, 76, 60, 0.15);
            border-color: var(--incorrect);
            color: var(--incorrect);
        }
        
        .option.selected.incorrect::before {
            background-color: var(--incorrect);
            transform: scaleY(1);
        }
        
        .option-letter {
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--accent), var(--accent-light));
            border-radius: 10px;
            margin-left: 15px;
            font-weight: bold;
            flex-shrink: 0;
            transition: all 0.3s ease;
            color: white;
            box-shadow: 0 4px 10px rgba(65, 90, 119, 0.3);
        }
        
        .option:hover .option-letter {
            transform: scale(1.1);
        }
        
        .option.selected.correct .option-letter {
            background: var(--correct);
        }
        
        .option.selected.incorrect .option-letter {
            background: var(--incorrect);
        }
        
        .result-modal {
            display: none;
            margin-top: 20px;
            padding: 20px;
            border-radius: 12px;
            background-color: rgba(27, 38, 59, 0.9);
            border: 1px solid var(--border);
            animation: fadeIn 0.4s ease-out;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .result-title {
            color: white;
            margin-bottom: 15px;
            text-align: center;
            font-size: 1.4rem;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .result-title.correct {
            color: var(--correct);
        }
        
        .result-title.incorrect {
            color: var(--incorrect);
        }
        
        .result-title i {
            margin-left: 10px;
        }
        
        .explanation {
            margin-top: 15px;
            padding: 15px;
            background-color: rgba(13, 27, 42, 0.7);
            border-radius: 10px;
            line-height: 1.7;
            border-right: 4px solid var(--accent);
        }
        
        .correct-answer-box {
            background-color: rgba(46, 204, 113, 0.15);
            border: 1px solid var(--correct);
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            display: flex;
            align-items: center;
            box-shadow: 0 5px 15px rgba(46, 204, 113, 0.2);
        }
        
        .correct-answer-box::before {
            content: "✅";
            margin-left: 10px;
            font-size: 1.5rem;
        }
        
        .incorrect-answer-box {
            background-color: rgba(231, 76, 60, 0.15);
            border: 1px solid var(--incorrect);
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            display: flex;
            align-items: center;
            box-shadow: 0 5px 15px rgba(231, 76, 60, 0.2);
        }
        
        .incorrect-answer-box::before {
            content: "❌";
            margin-left: 10px;
            font-size: 1.5rem;
        }
        
        .progress-container {
            margin: 25px 0;
            background-color: var(--card-bg);
            padding: 15px;
            border-radius: 12px;
            border: 1px solid var(--border);
        }
        
        .progress-text {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 1rem;
        }
        
        .progress-bar {
            height: 12px;
            background-color: var(--primary);
            border-radius: 6px;
            overflow: hidden;
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .progress {
            height: 100%;
            background: linear-gradient(to right, var(--accent), var(--accent-light));
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 6px;
            position: relative;
            overflow: hidden;
        }
        
        .progress::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background: linear-gradient(90deg, 
                rgba(255,255,255,0) 0%, 
                rgba(255,255,255,0.3) 50%, 
                rgba(255,255,255,0) 100%);
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .footer {
            text-align: center;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid var(--border);
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .action-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--accent), var(--accent-light));
            color: white;
            box-shadow: 0 5px 15px rgba(65, 90, 119, 0.4);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(65, 90, 119, 0.6);
        }
        
        .btn-outline {
            background: transparent;
            color: var(--text);
            border: 1px solid var(--border);
        }
        
        .btn-outline:hover {
            background: rgba(255, 255, 255, 0.05);
        }
        
        /* تحسينات للهواتف المحمولة */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
                border-radius: 15px;
            }
            
            .question {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .exam-info {
                flex-direction: column;
                gap: 15px;
            }
            
            .action-buttons {
                flex-direction: column;
            }
            
            .result-modal {
                padding: 15px;
            }
            
            .result-title {
                font-size: 1.2rem;
            }
            
            .question-text {
                font-size: 1.1rem;
            }
            
            .option {
                padding: 12px 15px;
            }
            
            .option-letter {
                width: 35px;
                height: 35px;
                margin-left: 10px;
            }
            
            .correct-answer-box,
            .incorrect-answer-box {
                padding: 12px;
            }
            
            .explanation {
                padding: 12px;
            }
        }
        
        @media (max-width: 480px) {
            body {
                padding: 10px;
            }
            
            .container {
                padding: 15px 10px;
            }
            
            .question {
                padding: 15px;
            }
            
            h1 {
                font-size: 1.5rem;
            }
            
            .subtitle {
                font-size: 1rem;
            }
            
            .logo {
                width: 60px;
                height: 60px;
                font-size: 1.5rem;
            }
            
            .result-modal {
                padding: 12px;
            }
            
            .result-title {
                font-size: 1.1rem;
            }
            
            .question-text {
                font-size: 1rem;
            }
            
            .option {
                padding: 10px 12px;
            }
            
            .option-letter {
                width: 30px;
                height: 30px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-globe-americas"></i>
            </div>
            <h1>اختبار الرخصة المهنية للمعلمين</h1>
            <p class="subtitle">تخصص: الجغرافيا</p>
        </header>
        
        <div class="exam-info">
            <div class="info-item">
                <div class="info-value">10</div>
                <div class="info-label">عدد الأسئلة</div>
            </div>
            <div class="info-item">
                <div class="info-value">40</div>
                <div class="info-label">دقيقة</div>
            </div>
            <div class="info-item">
                <div class="info-value">75%</div>
                <div class="info-label">النسبة المطلوبة</div>
            </div>
        </div>
        
        <div class="instructions">
            <h3><i class="fas fa-info-circle"></i> تعليمات الاختبار</h3>
            <p>يتكون الاختبار من 10 أسئلة صعبة في تخصص الجغرافيا. لكل سؤال إجابة واحدة صحيحة فقط. انقر على الإجابة التي تعتقد أنها صحيحة، ثم ستظهر نافذة أسفل السؤال توضح الإجابة الصحيحة مع الشرح.</p>
        </div>
        
        <div class="progress-container">
            <div class="progress-text">
                <span>تقدم الاختبار</span>
                <span id="progress-percent">0%</span>
            </div>
            <div class="progress-bar">
                <div class="progress" id="progress"></div>
            </div>
        </div>
        
        <div id="questions-container">
            <!-- سيتم إضافة الأسئلة ديناميكيًا باستخدام JavaScript -->
        </div>
        
        <div class="action-buttons">
            <button class="btn btn-primary" id="submit-btn">
                <i class="fas fa-paper-plane"></i> إنهاء الاختبار
            </button>
            <button class="btn btn-outline" id="reset-btn">
                <i class="fas fa-redo"></i> بدء اختبار جديد
            </button>
        </div>
        
        <div class="footer">
            <p>تم تصميم هذا الاختبار لمحاكاة اختبار الرخصة المهنية للمعلمين في تخصص الجغرافيا</p>
            <p>© 2023 هيئة تقويم التعليم والتدريب</p>
        </div>
    </div>

    <script>
        // بيانات الأسئلة مع الإجابات الصحيحة والشرح
        const questions = [
            {
                question: "ما هي الظاهرة الجغرافية التي تنتج عن تصادم الصفيحة العربية بالصفيحة الأوراسية وتسببت في تشكل جبال زاغروس؟",
                options: [
                    "الانزياح القاري",
                    "الطية المتصدعة",
                    "الانزياح التكتوني للقارات",
                    "الاندساس القاري"
                ],
                correctAnswer: 1,
                explanation: "تتشكل جبال زاغروس نتيجة لظاهرة الطية المتصدعة التي تحدث عند تصادم الصفيحة العربية بالصفيحة الأوراسية. هذه العملية التكتونية تؤدي إلى طي وتصدع القشرة الأرضية مكونة سلاسل جبلية ضخمة. تعتبر هذه المنطقة من أكثر المناطق نشاطاً زلزالياً في العالم بسبب استمرار حركة الصفائح."
            },
            {
                question: "أي من العوامل التالية يلعب الدور الأكبر في تشكيل المناخ الصحراوي الحار في شبه الجزيرة العربية؟",
                options: [
                    "التيارات المحيطية الباردة",
                    "ظاهرة الظل المطري",
                    "الموقع ضمن نطاق الضغط المرتفع شبه المداري",
                    "قرب المنطقة من خط الاستواء"
                ],
                correctAnswer: 2,
                explanation: "الموقع ضمن نطاق الضغط المرتفع شبه المداري هو العامل الرئيسي في تشكيل المناخ الصحراوي الحار في شبه الجزيرة العربية. تسبب هذه الخلايا ذات الضغط المرتفع هبوط الكتل الهوائية واحتباس الرطوبة، مما يمنع تكون السحب وهطول الأمطار. هذا النطاق يقع بين خطي عرض 20-30 درجة شمال وجنوب خط الاستواء."
            },
            {
                question: "ما هو المفهوم الجغرافي الذي يصف التباين في توزيع الموارد المائية بين دول حوض النيل؟",
                options: [
                    "الجيوبوليتيكا المائية",
                    "الصراع المائي الإقليمي",
                    "الهيدروبوليتيك",
                    "الجيوهيدرولوجيا"
                ],
                correctAnswer: 2,
                explanation: "مفهوم الهيدروبوليتيك يصف دراسة العلاقات السياسية والاستراتيجية المرتبطة بالموارد المائية المشتركة بين الدول. في حالة حوض النيل، يتجلى هذا المفهوم في التفاوض حول توزيع حصص المياه بين الدول المشاطئة، والتأثير على الأمن المائي والسياسات الإقليمية."
            },
            {
                question: "أي من النماذج التالية يصف بدقة عملية التحضر في الدول النامية خلال القرن الحادي والعشرين؟",
                options: [
                    "نموذج التحضر المعتدل",
                    "نموذج المدينة العالمية",
                    "نموذج التحضر السريع غير المخطط",
                    "نموذج المدينة المستدامة"
                ],
                correctAnswer: 2,
                explanation: "نموذج التحضر السريع غير المخطط يصف بدقة عملية التحضر في معظم الدول النامية، حيث يؤدي النمو السكاني والهجرة من الريف إلى المدن إلى توسع حضري سريع وغير منظم. هذا النموذج يتسم بتكون الأحياء العشوائية، وعدم كفاية البنية التحتية، والضغط على الخدمات العامة."
            },
            {
                question: "ما هي الآلية الرئيسية التي تساهم في تفاقم مشكلة التصحر في منطقة الساحل الأفريقي؟",
                options: [
                    "الرعي الجائر وتدهور الغطاء النباتي",
                    "الأنشطة البركانية المتكررة",
                    "زيادة ملوحة التربة بسبب ارتفاع منسوب البحر",
                    "التغير في مسار التيارات المحيطية"
                ],
                correctAnswer: 0,
                explanation: "الرعي الجائر وتدهور الغطاء النباتي هما الآليتان الرئيسيتان المسببان لتفاقم التصحر في منطقة الساحل الأفريقي. يؤدي الرعي المكثف إلى إزالة الغطاء النباتي الذي يحمي التربة من التعرية، كما أن قطع الأشجار للحصول على الوقود يسرع من عملية التصحر. هذه العوامل البشرية تفاقم تأثير التغيرات المناخية الطبيعية."
            },
            {
                question: "أي من النظريات التالية تقدم التفسير الأكثر شمولية لظاهرة الاحتباس الحراري وتأثيراته على المنظومات الجغرافية؟",
                options: [
                    "نظرية التغير المناخي الدوري",
                    "نظرية الانزياح المداري",
                    "نظرية تأثير البيت الزجاجي المعزز",
                    "نظرية التباين الشمسي"
                ],
                correctAnswer: 2,
                explanation: "نظرية تأثير البيت الزجاجي المعزز تقدم التفسير الأكثر شمولية لظاهرة الاحتباس الحراري. تشرح هذه النظرية كيف تؤدي زيادة تركيز غازات الدفيئة (مثل ثاني أكسيد الكربون والميثان) في الغلاف الجوي إلى احتباس المزيد من الحرارة المنبعثة من الأرض، مما يتسبب في ارتفاع درجة حرارة الكوكب وتغير المنظومات الجغرافية المختلفة."
            },
            {
                question: "ما هو المفهوم الجغرافي الذي يصف تحول الأراضي الزراعية إلى استخدامات حضرية على أطراف المدن؟",
                options: [
                    "التوسع الحضري الدائري",
                    "زحف الضواحي",
                    "الانتشار العمراني",
                    "تآكل الحزام الأخضر"
                ],
                correctAnswer: 2,
                explanation: "الانتشار العمراني هو المفهوم الجغرافي الذي يصف تحول الأراضي الزراعية والطبيعية إلى استخدامات حضرية على أطراف المدن. هذه الظاهرة تؤدي إلى فقدان الأراضي الخصبة، وزيادة الاعتماد على وسائل النقل، وتشكل تحديات بيئية واقتصادية واجتماعية للمناطق الحضرية."
            },
            {
                question: "أي من العوامل التالية كان الأكثر تأثيراً في تشكيل شبكة النقل في شبه الجزيرة العربية؟",
                options: [
                    "التضاريس الجبلية",
                    "توزيع الواحات ومصادر المياه",
                    "المراكز السكانية والتجارية التاريخية",
                    "الحدود السياسية بين الدول"
                ],
                correctAnswer: 1,
                explanation: "توزيع الواحات ومصادر المياه هو العامل الأكثر تأثيراً في تشكيل شبكة النقل التقليدية في شبه الجزيرة العربية. حيث كانت القوافل التجارية والمسافرين يتبعون المسارات التي توفر مصادر مائية، مما شكل شبكة طرق تربط بين الواحات. هذا العامل الطبيعي كان حاسماً في بيئة صحراوية قاسية."
            },
            {
                question: "ما هو النظام البيئي الأكثر تأثراً بارتفاع منسوب مياه البحر نتيجة لذوبان الجليد القطبي؟",
                options: [
                    "الغابات الاستوائية المطيرة",
                    "المناطق الساحلية والأراضي الرطبة",
                    "المناطق الجبلية المرتفعة",
                    "السهول العشبية المعتدلة"
                ],
                correctAnswer: 1,
                explanation: "المناطق الساحلية والأراضي الرطبة هي النظم البيئية الأكثر تأثراً بارتفاع منسوب مياه البحر. يؤدي هذا الارتفاع إلى تآكل السواحل، وتملح المياه الجوفية، وغمر المناطق المنخفضة، وفقدان الموائل الساحلية الهامة مثل أشجار المانغروف والأراضي الرطبة التي تعتبر حاضنات للعديد من الأنواع البحرية."
            },
            {
                question: "أي من النماذج التالية يصف بدقة العلاقة بين التنمية الاقتصادية والضغوط البيئية في الدول النامية؟",
                options: [
                    "منحنى كوزنتس البيئي",
                    "نموذج التحول الديموغرافي",
                    "نظرية التبعية الهيكلية",
                    "نموذج المركز والهامش"
                ],
                correctAnswer: 0,
                explanation: "منحنى كوزنتس البيئي يصف العلاقة بين التنمية الاقتصادية والضغوط البيئية، حيث تزداد التدهورات البيئية في المراحل الأولى للتنمية الاقتصادية، ثم تبدأ في الانخفاض بعد بلوغ مستوى معين من الدخل الفردي. هذا النموذج يفسر لماذا تواجه الدول النامية تحديات بيئية كبيرة خلال مسيرة تنميتها الاقتصادية."
            }
        ];

        // دالة لخلط الخيارات بشكل عشوائي
        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        // دالة لتحويل الأرقام إلى أحرف (أ، ب، ج، د)
        function numberToArabicLetter(number) {
            const letters = ['أ', 'ب', 'ج', 'د'];
            return letters[number];
        }

        // دالة لعرض الأسئلة
        function displayQuestions() {
            const questionsContainer = document.getElementById('questions-container');
            questionsContainer.innerHTML = '';
            
            questions.forEach((q, index) => {
                // خلط الخيارات بشكل عشوائي مع تتبع الإجابة الصحيحة
                const shuffledOptions = shuffleArray([...q.options]);
                const correctOptionIndex = shuffledOptions.indexOf(q.options[q.correctAnswer]);
                
                const questionElement = document.createElement('div');
                questionElement.className = 'question';
                questionElement.innerHTML = `
                    <div class="question-number">السؤال ${index + 1}</div>
                    <div class="question-text">${q.question}</div>
                    <div class="options">
                        ${shuffledOptions.map((option, i) => `
                            <div class="option" data-question="${index}" data-option="${i}" data-correct="${i === correctOptionIndex}">
                                <span class="option-letter">${numberToArabicLetter(i)}</span>
                                ${option}
                            </div>
                        `).join('')}
                    </div>
                    <div class="result-modal" id="result-modal-${index}">
                        <!-- سيتم إضافة محتوى النافذة ديناميكيًا -->
                    </div>
                `;
                
                questionsContainer.appendChild(questionElement);
            });
        }

        // دالة لعرض النافذة المنبثقة مع نتيجة السؤال
        function showResultModal(questionIndex, selectedOptionIndex, isCorrect) {
            const modal = document.getElementById(`result-modal-${questionIndex}`);
            const question = questions[questionIndex];
            
            // العثور على الإجابة الصحيحة بعد الخلط
            const shuffledOptions = shuffleArray([...question.options]);
            const correctOptionIndex = shuffledOptions.indexOf(question.options[question.correctAnswer]);
            const correctAnswerText = shuffledOptions[correctOptionIndex];
            
            let content = '';
            
            // تحديث عنوان النافذة
            if (isCorrect) {
                content += `
                    <div class="result-title correct">
                        <i class="fas fa-check-circle"></i> إجابة صحيحة
                    </div>
                `;
            } else {
                content += `
                    <div class="result-title incorrect">
                        <i class="fas fa-times-circle"></i> إجابة خاطئة
                    </div>
                `;
            }
            
            // عرض الإجابة الصحيحة فقط
            if (isCorrect) {
                content += `
                    <div class="correct-answer-box">
                        ${correctAnswerText}
                    </div>
                `;
            } else {
                content += `
                    <div class="incorrect-answer-box">
                        إجابتك غير صحيحة
                    </div>
                    <div class="correct-answer-box">
                        ${correctAnswerText}
                    </div>
                `;
            }
            
            content += `
                <div class="explanation">
                    <strong>الشرح:</strong><br>
                    ${question.explanation}
                </div>
            `;
            
            modal.innerHTML = content;
            modal.style.display = 'block';
        }

        // دالة لتحديث شريط التقدم
        function updateProgress() {
            const answeredQuestions = document.querySelectorAll('.option.selected').length;
            const progress = (answeredQuestions / questions.length) * 100;
            document.getElementById('progress').style.width = `${progress}%`;
            document.getElementById('progress-percent').textContent = `${Math.round(progress)}%`;
        }

        // دالة لحساب النتيجة النهائية
        function calculateScore() {
            let correctAnswers = 0;
            document.querySelectorAll('.option.selected.correct').forEach(() => {
                correctAnswers++;
            });
            return correctAnswers;
        }

        // دالة لعرض النتيجة النهائية
        function showFinalScore() {
            const score = calculateScore();
            const percentage = (score / questions.length) * 100;
            
            let resultClass = 'incorrect';
            let resultMessage = 'نحتاج إلى المزيد من التحضير';
            
            if (percentage >= 75) {
                resultClass = 'correct';
                resultMessage = 'ممتاز! لقد اجتزت الاختبار بنجاح';
            } else if (percentage >= 50) {
                resultMessage = 'جيد ولكن تحتاج إلى تحسين';
            }
            
            // إنشاء نافذة النتيجة النهائية
            const finalResultModal = document.createElement('div');
            finalResultModal.className = 'question';
            finalResultModal.innerHTML = `
                <div class="result-modal" style="display: block;">
                    <div class="result-title ${resultClass}">
                        <i class="fas fa-chart-line"></i> نتيجة الاختبار
                    </div>
                    <div style="text-align: center; padding: 20px;">
                        <div style="font-size: 3rem; margin-bottom: 20px; color: ${percentage >= 75 ? 'var(--correct)' : 'var(--incorrect)'}">${percentage}%</div>
                        <div style="font-size: 1.5rem; margin-bottom: 15px;">${resultMessage}</div>
                        <div style="margin-bottom: 20px;">الإجابات الصحيحة: ${score} من ${questions.length}</div>
                    </div>
                </div>
            `;
            
            document.getElementById('questions-container').appendChild(finalResultModal);
            
            // التمرير إلى النتيجة
            finalResultModal.scrollIntoView({ behavior: 'smooth' });
        }

        // تهيئة الصفحة عند التحميل
        document.addEventListener('DOMContentLoaded', function() {
            displayQuestions();
            
            // إضافة مستمعي الأحداث للخيارات
            document.querySelectorAll('.option').forEach(option => {
                option.addEventListener('click', function() {
                    const questionIndex = parseInt(this.getAttribute('data-question'));
                    const optionIndex = parseInt(this.getAttribute('data-option'));
                    const isCorrect = this.getAttribute('data-correct') === 'true';
                    
                    // إزالة التحديد من جميع خيارات هذا السؤال
                    const questionOptions = document.querySelectorAll(`.option[data-question="${questionIndex}"]`);
                    questionOptions.forEach(opt => {
                        opt.classList.remove('selected', 'correct', 'incorrect');
                    });
                    
                    // إضافة التحديد للخيار المختار
                    this.classList.add('selected');
                    this.classList.add(isCorrect ? 'correct' : 'incorrect');
                    
                    // عرض النافذة المنبثقة
                    showResultModal(questionIndex, optionIndex, isCorrect);
                    
                    // التمرير إلى النافذة المنبثقة
                    document.getElementById(`result-modal-${questionIndex}`).scrollIntoView({ behavior: 'smooth', block: 'nearest' });
                    
                    // تحديث شريط التقدم
                    updateProgress();
                });
            });
            
            // زر إنهاء الاختبار
            document.getElementById('submit-btn').addEventListener('click', function() {
                const answeredQuestions = document.querySelectorAll('.option.selected').length;
                if (answeredQuestions < questions.length) {
                    alert(`لم تقم بالإجابة على جميع الأسئلة. لديك ${questions.length - answeredQuestions} أسئلة لم تتم الإجابة عليها.`);
                    return;
                }
                showFinalScore();
            });
            
            // زر بدء اختبار جديد
            document.getElementById('reset-btn').addEventListener('click', function() {
                if (confirm('هل تريد فعلاً بدء اختبار جديد؟ سيتم مسح جميع إجاباتك الحالية.')) {
                    displayQuestions();
                    document.getElementById('progress').style.width = '0%';
                    document.getElementById('progress-percent').textContent = '0%';
                    
                    // إعادة إضافة مستمعي الأحداث للخيارات الجديدة
                    document.querySelectorAll('.option').forEach(option => {
                        option.addEventListener('click', function() {
                            const questionIndex = parseInt(this.getAttribute('data-question'));
                            const optionIndex = parseInt(this.getAttribute('data-option'));
                            const isCorrect = this.getAttribute('data-correct') === 'true';
                            
                            const questionOptions = document.querySelectorAll(`.option[data-question="${questionIndex}"]`);
                            questionOptions.forEach(opt => {
                                opt.classList.remove('selected', 'correct', 'incorrect');
                            });
                            
                            this.classList.add('selected');
                            this.classList.add(isCorrect ? 'correct' : 'incorrect');
                            
                            showResultModal(questionIndex, optionIndex, isCorrect);
                            updateProgress();
                        });
                    });
                }
            });
        });
    </script>
</body>
</html>
