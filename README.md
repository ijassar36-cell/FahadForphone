# FahadForphone
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اختبار الرخصة المهنية للمعلمين العام</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #121212;
            --secondary: #1e1e1e;
            --accent: #6a11cb;
            --accent-light: #2575fc;
            --correct: #00c853;
            --incorrect: #ff1744;
            --text: #e0e0e0;
            --text-light: #b0b0b0;
            --border: #333;
            --card-bg: #252525;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--primary), #2c3e50);
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
            box-shadow: 0 5px 15px rgba(106, 17, 203, 0.4);
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
            background: rgba(37, 37, 37, 0.7);
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
            background: linear-gradient(135deg, rgba(106, 17, 203, 0.1), rgba(37, 117, 252, 0.1));
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
            background-color: rgba(37, 37, 37, 0.7);
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
            background-color: rgba(50, 50, 50, 0.7);
            transform: translateX(-5px);
        }
        
        .option:hover::before {
            transform: scaleY(1);
        }
        
        .option.selected.correct {
            background-color: rgba(0, 200, 83, 0.15);
            border-color: var(--correct);
            color: var(--correct);
        }
        
        .option.selected.correct::before {
            background-color: var(--correct);
            transform: scaleY(1);
        }
        
        .option.selected.incorrect {
            background-color: rgba(255, 23, 68, 0.15);
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
            box-shadow: 0 4px 10px rgba(106, 17, 203, 0.3);
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
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.85);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(5px);
            padding: 20px;
            overflow-y: auto;
        }
        
        .modal-content {
            background: linear-gradient(135deg, var(--secondary), #2a2a2a);
            padding: 25px;
            border-radius: 20px;
            max-width: 500px;
            width: 100%;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
            position: relative;
            border: 1px solid rgba(255, 255, 255, 0.1);
            animation: modalAppear 0.4s ease-out;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        @keyframes modalAppear {
            from {
                opacity: 0;
                transform: translateY(-30px) scale(0.9);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }
        
        .close-btn {
            position: absolute;
            top: 15px;
            left: 15px;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--text);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s ease;
            z-index: 10;
        }
        
        .close-btn:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: rotate(90deg);
        }
        
        .modal-title {
            color: white;
            margin-bottom: 20px;
            text-align: center;
            font-size: 1.6rem;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .modal-title.correct {
            color: var(--correct);
        }
        
        .modal-title.incorrect {
            color: var(--incorrect);
        }
        
        .modal-title i {
            margin-left: 10px;
        }
        
        .explanation {
            margin-top: 20px;
            padding: 20px;
            background-color: rgba(37, 37, 37, 0.7);
            border-radius: 12px;
            line-height: 1.7;
            border-right: 4px solid var(--accent);
        }
        
        .correct-answer-box {
            background-color: rgba(0, 200, 83, 0.15);
            border: 1px solid var(--correct);
            border-radius: 12px;
            padding: 20px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            box-shadow: 0 5px 15px rgba(0, 200, 83, 0.2);
        }
        
        .correct-answer-box::before {
            content: "✅";
            margin-left: 15px;
            font-size: 1.8rem;
        }
        
        .incorrect-answer-box {
            background-color: rgba(255, 23, 68, 0.15);
            border: 1px solid var(--incorrect);
            border-radius: 12px;
            padding: 20px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            box-shadow: 0 5px 15px rgba(255, 23, 68, 0.2);
        }
        
        .incorrect-answer-box::before {
            content: "❌";
            margin-left: 15px;
            font-size: 1.8rem;
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
            box-shadow: 0 5px 15px rgba(106, 17, 203, 0.4);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(106, 17, 203, 0.6);
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
            
            .modal-content {
                padding: 20px;
                max-width: 95%;
                margin: 10px;
            }
            
            .modal-title {
                font-size: 1.4rem;
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
                padding: 15px;
            }
            
            .explanation {
                padding: 15px;
            }
            
            .close-btn {
                top: 10px;
                left: 10px;
                width: 35px;
                height: 35px;
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
            
            .modal-content {
                padding: 15px;
            }
            
            .modal-title {
                font-size: 1.3rem;
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
                <i class="fas fa-graduation-cap"></i>
            </div>
            <h1>اختبار الرخصة المهنية للمعلمين</h1>
            <p class="subtitle">الجزء العام - اختبار تأهيلي</p>
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
            <p>يتكون الاختبار من 10 أسئلة متعددة الخيارات في المجال التربوي العام. لكل سؤال إجابة واحدة صحيحة فقط. انقر على الإجابة التي تعتقد أنها صحيحة، ثم ستظهر نافذة توضح الإجابة الصحيحة مع الشرح.</p>
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
            <p>تم تصميم هذا الاختبار لمحاكاة اختبار الرخصة المهنية للمعلمين في الجزء العام</p>
            <p>© 2023 هيئة تقويم التعليم والتدريب</p>
        </div>
    </div>
    
    <div class="modal" id="result-modal">
        <div class="modal-content">
            <span class="close-btn" id="close-modal">&times;</span>
            <h3 class="modal-title" id="modal-title">
                <i class="fas fa-check-circle"></i> إجابة صحيحة
            </h3>
            <div id="modal-content">
                <!-- سيتم إضافة محتوى النافذة ديناميكيًا -->
            </div>
        </div>
    </div>

    <script>
        // بيانات الأسئلة مع الإجابات الصحيحة والشرح
        const questions = [
            {
                question: "أي من النظريات التربوية التالية تؤكد على أهمية التفاعل الاجتماعي في عملية التعلم؟",
                options: [
                    "النظرية السلوكية",
                    "النظرية البنائية الاجتماعية",
                    "النظرية الإنسانية",
                    "النظرية المعرفية"
                ],
                correctAnswer: 1,
                explanation: "النظرية البنائية الاجتماعية (لـفيجوتسكي) تؤكد على أهمية التفاعل الاجتماعي في عملية التعلم، حيث يرى أن التعلم يحدث من خلال التفاعل مع الآخرين في سياق ثقافي واجتماعي. بينما تركز النظريات الأخرى على جوانب مختلفة مثل السلوك المرئي أو العمليات المعرفية الداخلية."
            },
            {
                question: "ما المبدأ الأساسي الذي تقوم عليه استراتيجية التعلم التعاوني؟",
                options: [
                    "تنافس الطلاب للحصول على أعلى الدرجات",
                    "اعتماد الطالب على نفسه في اكتساب المعرفة",
                    "تعاون الطلاب في مجموعات صغيرة لتحقيق هدف مشترك",
                    "تركيز العملية التعليمية على المعلم فقط"
                ],
                correctAnswer: 2,
                explanation: "التعلم التعاوني هو استراتيجية تعليمية تعتمد على تقسيم الطلاب إلى مجموعات صغيرة غير متجانسة، يعملون معًا لتحقيق هدف مشترك، حيث يعتمد نجاح كل فرد على نجاح المجموعة ككل. وهذا يعزز المسؤولية الفردية والجماعية وينمي مهارات العمل الجماعي."
            },
            {
                question: "أي من المهارات التالية تعتبر من مهارات التفكير العليا وفق تصنيف بلوم؟",
                options: [
                    "الحفظ والتذكر",
                    "الفهم والاستيعاب",
                    "التحليل والتركيب",
                    "التطبيق الآلي"
                ],
                correctAnswer: 2,
                explanation: "تصنيف بلوم للمجال المعرفي يتضمن ستة مستويات: التذكر، الفهم، التطبيق، التحليل، التركيب، التقويم. تعتبر مستويات التحليل والتركيب والتقويم من مهارات التفكير العليا، بينما التذكر والفهم والتطبيق الآلي تعتبر من مهارات التفكير الدنيا."
            },
            {
                question: "ما المقصود بالتقويم البنائي في العملية التعليمية؟",
                options: [
                    "التقويم الذي يتم في نهاية الوحدة الدراسية",
                    "التقويم الذي يهدف إلى تحسين التعلم أثناء حدوثه",
                    "التقويم الذي يقارن أداء الطالب بزملائه",
                    "التقويم الذي يعتمد على الاختبارات الموحدة فقط"
                ],
                correctAnswer: 1,
                explanation: "التقويم البنائي (التكويني) هو ذلك النوع من التقويم الذي يحدث أثناء عملية التعلم، ويهدف إلى تحسين التعلم والتعليم من خلال تزويد المعلم والطالب بالتغذية الراجعة الفورية. يساعد في تحديد نقاط القوة والضعف واتخاذ القرارات المناسبة لتحسين الأداء."
            },
            {
                question: "أي من الاستراتيجيات التالية تعتبر الأكثر فعالية في تعليم الطلاب ذوي صعوبات التعلم؟",
                options: [
                    "التدريس الجماعي لجميع الطلاب بنفس الطريقة",
                    "استخدام طريقة واحدة ثابتة في التدريس",
                    "التدريس المباشر والمنظم مع توفير الدعم",
                    "التركيز على الحفظ والتكرار فقط"
                ],
                correctAnswer: 2,
                explanation: "التدريس المباشر والمنظم مع توفير الدعم هو الأكثر فعالية لذوي صعوبات التعلم، حيث يتضمن تقديم المعلومة بشكل واضح ومنظم، وتجزئة المهام إلى خطوات صغيرة، وتوفير التغذية الراجعة المستمرة، واستخدام الوسائل البصرية والسمعية، وتكيف طرق التدريس حسب احتياجات كل طالب."
            },
            {
                question: "ما الهدف الرئيسي من استخدام المناقشة الصفية كاستراتيجية تعليمية؟",
                options: [
                    "ملء وقت الحصة الدراسية",
                    "تقليل عبء العمل على المعلم",
                    "تنمية مهارات التفكير الناقد والتعبير لدى الطلاب",
                    "التركيز على حفظ المعلومات فقط"
                ],
                correctAnswer: 2,
                explanation: "المناقشة الصفية كاستراتيجية تعليمية تهدف primarily إلى تنمية مهارات التفكير الناقد والتعبير الشفوي لدى الطلاب، حيث تتيح لهم تبادل الآراء والأفكار، والاستماع لوجهات نظر مختلفة، وتدربهم على احترام الرأي الآخر، وتطوير حججهم logically، والتعبير عن أفكارهم بوضوح."
            },
            {
                question: "أي من العوامل التالية يعتبر الأكثر تأثيراً في تحقيق التعلم الفعال؟",
                options: [
                    "تزيين الفصل الدراسي بشكل جذاب",
                    "استخدام أحدث التقنيات التعليمية",
                    "جودة التدريس وملاءمة طرق التعليم لاحتياجات الطلاب",
                    "حجم الفصل الدراسي"
                ],
                correctAnswer: 2,
                explanation: "تشير الدراسات التربوية إلى أن جودة التدريس وملاءمة طرق التعليم لاحتياجات الطلاب هي العامل الأكثر تأثيراً في تحقيق التعلم الفعال. فالمعلم الكفؤ القادر على تصميم خبرات تعليمية مناسبة وتقديم الدعم المناسب هو المحدد الرئيسي لنجاح العملية التعليمية، أكثر من العوامل المادية أو التكنولوجية."
            },
            {
                question: "ما المقصود بالمنهج الخفي في العملية التعليمية؟",
                options: [
                    "المنهج الذي يتم تدريسه خارج أوقات الدوام الرسمي",
                    "القيم والاتجاهات التي يكتسبها الطلاب من خلال البيئة المدرسية",
                    "المنهج الذي يركز على المواد السرية والخاصة",
                    "المنهج الذي لا يتم تقويمه بشكل رسمي"
                ],
                correctAnswer: 1,
                explanation: "المنهج الخفي يشير إلى القيم والاتجاهات والمعايير الاجتماعية والسلوكيات التي يكتسبها الطلاب من خلال البيئة المدرسية والتفاعلات اليومية، دون أن تكون مخططة بشكل رسمي في المنهج الدراسي. يتضمن ذلك علاقات المعلمين بالطلاب، وقواعد المدرسة، والأنشطة غير الصفية، والثقافة المدرسية السائدة."
            },
            {
                question: "أي من المبادئ التالية يعتبر أساسياً في تصميم الأنشطة الصفية لتنمية الإبداع؟",
                options: [
                    "تحديد إجابة واحدة صحيحة لكل سؤال",
                    "توفير بيئة آمنة تشجع على التجريب وتحمل المخاطرة",
                    "التركيز على الحلول التقليدية والمثبتة",
                    "تقييم الطلاب بناءً على سرعة إنجاز المهمة فقط"
                ],
                correctAnswer: 1,
                explanation: "لتنمية الإبداع لدى الطلاب، من الأساسي توفير بيئة آمنة تشجع على التجريب وتحمل المخاطرة، حيث يشعر الطلاب بالأمان للتعبير عن أفكارهم غير التقليدية وتجربة حلول جديدة دون خوف من الفشل أو النقد. كما يجب تشجيع التساؤل والاستكشاف وتقبل الأخطاء كجزء من عملية التعلم."
            },
            {
                question: "ما الدور الأساسي للمعلم في ظل نموذج التعلم المتمركز حول الطالب؟",
                options: [
                    "مصدر وحيد للمعرفة وناقل للمعلومات",
                    "ميسر وموجه لعملية التعلم",
                    "مسيطر على جميع أنشطة الصف",
                    "مراقب فقط لأداء الطلاب"
                ],
                correctAnswer: 1,
                explanation: "في نموذج التعلم المتمركز حول الطالب، يتحول دور المعلم من being مصدر وحيد للمعرفة إلى being ميسر وموجه لعملية التعلم. حيث يقوم بتصميم بيئات تعلم غنية، وتقديم التوجيه والدعم، وتشجيع الاستقصاء والتفكير الناقد، وتسهيل عملية بناء المعرفة من قبل الطلاب أنفسهم."
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
                `;
                
                questionsContainer.appendChild(questionElement);
            });
        }

        // دالة لعرض النافذة المنبثقة مع نتيجة السؤال
        function showResultModal(questionIndex, selectedOptionIndex, isCorrect) {
            const modal = document.getElementById('result-modal');
            const modalTitle = document.getElementById('modal-title');
            const modalContent = document.getElementById('modal-content');
            const question = questions[questionIndex];
            
            // العثور على الإجابة الصحيحة بعد الخلط
            const shuffledOptions = shuffleArray([...question.options]);
            const correctOptionIndex = shuffledOptions.indexOf(question.options[question.correctAnswer]);
            const correctAnswerText = shuffledOptions[correctOptionIndex];
            
            // تحديث عنوان النافذة
            if (isCorrect) {
                modalTitle.innerHTML = '<i class="fas fa-check-circle"></i> إجابة صحيحة';
                modalTitle.className = 'modal-title correct';
            } else {
                modalTitle.innerHTML = '<i class="fas fa-times-circle"></i> إجابة خاطئة';
                modalTitle.className = 'modal-title incorrect';
            }
            
            let content = `
                <div class="question-text">${question.question}</div>
            `;
            
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
            
            modalContent.innerHTML = content;
            modal.style.display = 'flex';
            
            // منع التمرير في الخلفية عند فتح النافذة
            document.body.style.overflow = 'hidden';
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
            
            const modal = document.getElementById('result-modal');
            const modalTitle = document.getElementById('modal-title');
            const modalContent = document.getElementById('modal-content');
            
            modalTitle.innerHTML = '<i class="fas fa-chart-line"></i> نتيجة الاختبار';
            modalTitle.className = 'modal-title';
            
            let resultClass = 'incorrect';
            let resultMessage = 'نحتاج إلى المزيد من التحضير';
            
            if (percentage >= 75) {
                resultClass = 'correct';
                resultMessage = 'ممتاز! لقد اجتزت الاختبار بنجاح';
            } else if (percentage >= 50) {
                resultMessage = 'جيد ولكن تحتاج إلى تحسين';
            }
            
            modalContent.innerHTML = `
                <div style="text-align: center; padding: 20px;">
                    <div style="font-size: 3rem; margin-bottom: 20px; color: ${percentage >= 75 ? 'var(--correct)' : 'var(--incorrect)'}">${percentage}%</div>
                    <div style="font-size: 1.5rem; margin-bottom: 15px;">${resultMessage}</div>
                    <div style="margin-bottom: 20px;">الإجابات الصحيحة: ${score} من ${questions.length}</div>
                    <div class="action-buttons">
                        <button class="btn btn-primary" id="review-btn">
                            <i class="fas fa-eye"></i> مراجعة الإجابات
                        </button>
                    </div>
                </div>
            `;
            
            modal.style.display = 'flex';
            
            // إضافة مستمع حدث لزر المراجعة
            document.getElementById('review-btn').addEventListener('click', function() {
                modal.style.display = 'none';
                document.body.style.overflow = 'auto';
            });
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
                    
                    // تحديث شريط التقدم
                    updateProgress();
                });
            });
            
            // إضافة مستمع حدث لإغلاق النافذة المنبثقة
            document.getElementById('close-modal').addEventListener('click', function() {
                document.getElementById('result-modal').style.display = 'none';
                document.body.style.overflow = 'auto';
            });
            
            // إغلاق النافذة عند النقر خارجها
            window.addEventListener('click', function(event) {
                const modal = document.getElementById('result-modal');
                if (event.target === modal) {
                    modal.style.display = 'none';
                    document.body.style.overflow = 'auto';
                }
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
