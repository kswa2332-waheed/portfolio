[index.html](https://github.com/user-attachments/files/27850945/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ملخص الأحياء 2-2 - شامل المنهج (الفصل 1 إلى 10)</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap');
        
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #f1f5f9;
            color: #1e293b;
        }

        /* تنسيق الأوراق (A4) للشاشة */
        .worksheet-page {
            background-color: white;
            width: 210mm;
            min-height: 297mm;
            margin: 2rem auto;
            padding: 15mm;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            border-top: 10px solid #22c55e;
            position: relative;
            box-sizing: border-box;
        }

        /* تنسيقات صفحة الغلاف */
        .cover-page {
            border-top: none;
            background: linear-gradient(135deg, #f0fdf4 0%, #ffffff 100%);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            overflow: hidden;
            border: 2px solid #e2e8f0;
        }

        /* أشكال زخرفية للغلاف */
        .cover-shape-1 {
            position: absolute;
            top: -100px;
            right: -100px;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(34, 197, 94, 0.15) 0%, rgba(255,255,255,0) 70%);
            z-index: 0;
        }
        .cover-shape-2 {
            position: absolute;
            bottom: -150px;
            left: -100px;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.1) 0%, rgba(255,255,255,0) 70%);
            z-index: 0;
        }
        .cover-border {
            position: absolute;
            top: 15mm; left: 15mm; right: 15mm; bottom: 15mm;
            border: 3px double #22c55e;
            border-radius: 20px;
            z-index: 1;
            pointer-events: none;
        }

        .cover-content {
            position: relative;
            z-index: 2;
        }

        .header-table {
            width: 100%;
            margin-bottom: 20px;
            border-bottom: 2px solid #22c55e;
            padding-bottom: 10px;
        }

        .header-table td {
            vertical-align: top;
            font-size: 14px;
            font-weight: 600;
        }

        .qa-row {
            display: flex;
            flex-direction: column;
            margin-bottom: 15px;
            border: 1px solid #e2e8f0;
            border-radius: 8px;
            overflow: hidden;
            page-break-inside: avoid;
        }

        .q-box {
            background-color: #f8fafc;
            padding: 10px 15px;
            border-bottom: 1px dashed #cbd5e1;
            font-weight: 700;
            color: #0f172a;
            display: flex;
            align-items: center; /* Changed from flex-start to center for better alignment with arrow */
            gap: 10px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .q-box:hover {
            background-color: #e2e8f0;
        }

        .a-box {
            background-color: #ffffff;
            padding: 10px 15px 10px 40px;
            color: #334155;
            font-weight: 500;
            display: none; /* الإجابة مخفية افتراضياً */
            align-items: flex-start;
            gap: 10px;
            line-height: 1.6;
        }

        .a-box.show {
            display: flex; /* إظهار الإجابة عند إضافة الكلاس */
        }

        .q-icon { color: #3b82f6; font-size: 1.2rem; }
        .a-icon { color: #22c55e; font-size: 1.2rem; margin-top: 5px; }

        /* إعدادات الطباعة لورق A4 بالضبط */
        @page {
            size: A4 portrait;
            margin: 0; /* إزالة هوامش المتصفح الافتراضية لتجنب ظهور الروابط والتاريخ */
        }

        @media print {
            body { 
                background-color: white; 
                margin: 0; 
                padding: 0; 
                -webkit-print-color-adjust: exact !important; 
                print-color-adjust: exact !important;
            }
            .worksheet-page {
                box-shadow: none;
                margin: 0;
                width: 210mm;
                height: 297mm; /* فرض الارتفاع ليكون A4 بالضبط */
                padding: 15mm; /* مساحة داخلية للمحتوى */
                border-top: 5px solid #22c55e !important;
                page-break-after: always;
                page-break-inside: avoid;
                overflow: hidden; /* لمنع أي تجاوز خارج الصفحة */
            }
            .cover-page {
                border-top: none !important;
                border: none !important;
            }
            .hide-on-print { display: none !important; }
            .a-box {
                display: flex !important; /* إجبار ظهور الإجابات عند الطباعة دائماً */
            }
            .q-box i.fa-chevron-down {
                display: none !important; /* إخفاء سهم التوسيع عند الطباعة */
            }
        }
    </style>
</head>
<body>

    <!-- Print Button -->
    <button onclick="window.print()" class="hide-on-print fixed bottom-8 left-8 z-50 bg-green-600 text-white px-6 py-3 rounded-full font-bold shadow-xl hover:bg-green-700 hover:scale-105 transition-all duration-300 flex items-center gap-2">
        <i class="fas fa-print text-xl"></i>
        <span>طباعة الأوراق / PDF</span>
    </button>

    <!-- ==================== صفحة الغلاف ==================== -->
    <div class="worksheet-page cover-page">
        <div class="cover-shape-1"></div>
        <div class="cover-shape-2"></div>
        <div class="cover-border"></div>

        <div class="cover-content flex flex-col h-full justify-between pt-8 pb-12 px-8">
            
            <!-- رأس الغلاف -->
            <div class="flex justify-between items-start w-full">
                <div class="text-right text-gray-700 font-bold leading-relaxed">
                    <p class="text-lg">المملكة العربية السعودية</p>
                    <p class="text-lg">وزارة التعليم</p>
                    <p class="text-lg text-green-700 mt-1">الثانوية الثالثة بصبيا (بنين)</p>
                </div>
                <div class="text-center">
                    <img src="pngegg.png" alt="شعار الوزارة" class="h-24 mx-auto mb-2 drop-shadow-sm">
                </div>
                <div class="text-left text-gray-700 font-bold leading-relaxed">
                    <p class="text-lg">العام الدراسي: 1447هـ</p>
                    <p class="text-lg">الفصل الدراسي: ...............</p>
                </div>
            </div>

            <!-- وسط الغلاف (العنوان الرئيسي) -->
            <div class="text-center my-16">
                <div class="flex justify-center gap-6 text-4xl text-green-600 mb-8 opacity-80">
                    <i class="fas fa-dna"></i>
                    <i class="fas fa-microscope"></i>
                    <i class="fas fa-leaf"></i>
                    <i class="fas fa-lungs"></i>
                </div>
                
                <h2 class="text-3xl font-bold text-gray-500 mb-2">التعليم الثانوي - نظام المسارات</h2>
                <h3 class="text-2xl font-bold text-gray-400 mb-6">السنة الثانية</h3>
                
                <h1 class="text-6xl font-black text-green-700 mb-6 drop-shadow-md" style="line-height: 1.4;">
                    ملخص الأحياء 2-2
                </h1>
                
                <div class="inline-block bg-gradient-to-r from-green-500 to-green-600 text-white px-8 py-3 rounded-full text-xl font-bold shadow-md">
                    <i class="fas fa-check-circle ml-2"></i> شامل المنهج كاملاً (الفصل 1 إلى 10)
                </div>
            </div>

            <!-- أسفل الغلاف (بيانات الطالب والمعلم) -->
            <div class="w-full text-center space-y-6 mt-8 mb-4">
                <div class="text-2xl font-bold text-gray-800">
                    <i class="fas fa-user-graduate ml-2 text-green-600"></i> اسم الطالب: 
                </div>
                <div class="text-2xl font-bold text-gray-800">
                    <i class="fas fa-users ml-2 text-green-600"></i> الصف / الشعبة: 
                </div>
                <div class="text-2xl font-bold text-gray-800 pt-4">
                    <i class="fas fa-chalkboard-teacher ml-2 text-blue-600"></i> إعداد المعلم: وحيد حدادي
                </div>
            </div>
            
        </div>
    </div>
    <!-- ======================================================== -->


    <!-- Worksheet 1 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................<br>التاريخ: ..... / ..... / 144هـ</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الأول: الجهازان الهيكلي والعضلي
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي الوظائف الرئيسية للجهاز الهيكلي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الدعامة، الحماية (مثل حماية الجمجمة للدماغ)، تكوين خلايا الدم (في النخاع الأحمر)، التخزين (الكالسيوم والفوسفور)، والحركة.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>قارن بين العظم الكثيف والعظم الإسفنجي.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>العظم الكثيف: صلب وقوي يوفر الحماية والدعامة.<br>العظم الإسفنجي: أقل كثافة، يحتوي تجاويف ونخاع عظمي ويوجد عادة في نهايات العظام الطويلة.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما وظيفة الأربطة في الجهاز الهيكلي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>أشرطة من نسيج ضام صلب تربط العظام ببعضها البعض في المفصل.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>اذكر أنواع العضلات الثلاثة، ومكان وجود كل منها.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>1. الهيكلية: إرادية مرتبطة بالعظام.<br>2. الملساء: لا إرادية توجد في الأعضاء الداخلية (كالمعدة والأوعية الدموية).<br>3. القلبية: لا إرادية توجد في القلب فقط.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ماذا يحدث للعضلات إذا لم تتوافر كمية كافية من الأكسجين أثناء المجهود؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>تنتج الطاقة عن طريق التخمر اللبني مما يؤدي إلى تراكم (حمض اللاكتيك)، والذي يسبب الإعياء والعضلات المجهدة.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 2 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الثاني: الجهاز العصبي
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>مما تتكون الخلية العصبية (العصبون)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الزوائد الشجيرية (تستقبل الإشارات)، جسم الخلية (يحتوي النواة)، والمحور الأسطواني (ينقل السيال العصبي).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هو السيال العصبي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>شحنة كهربائية تنتقل على طول الخلية العصبية للتحكم في استجابة الجسم للمؤثرات.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما الفرق بين الجهاز العصبي المركزي والجهاز العصبي الطرفي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>المركزي: يتكون من الدماغ والحبل الشوكي ووظيفته التنسيق والتحليل.<br>الطرفي: يتكون من شبكة أعصاب تنقل الإشارات من وإلى الجهاز المركزي.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي الوظيفة الأساسية للمخيخ ومنطقة تحت المهاد؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>المخيخ: المحافظة على اتزان الجسم وتنسيق حركاته.<br>تحت المهاد: تنظيم درجة حرارة الجسم، والعطش، والجوع، والنوم.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>كيف تؤثر العقاقير والمنبهات (مثل الكافيين) على الجهاز العصبي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>تزيد المنبهات من اليقظة والنشاط الجسمي عبر زيادة إفراز النواقل العصبية أو منع امتصاصها، بينما المهدئات تقلل من نشاط الجهاز العصبي.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 3 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الثالث: جهاز الدوران (الدوري)
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>قارن بين الشرايين والأوردة والشعيرات الدموية.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الشرايين: تحمل الدم بعيداً عن القلب (جدرانها سميكة ومرنة).<br>الأوردة: تحمل الدم للقلب (تحتوي صمامات تمنع عودة الدم).<br>الشعيرات: رقيقة جداً لتبادل المواد بين الدم والخلايا.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي مكونات الدم الأساسية؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>البلازما (السائل)، خلايا الدم الحمراء (نقل الأكسجين)، خلايا الدم البيضاء (مقاومة الأمراض)، والصفائح الدموية (تخثر الدم).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي فصائل الدم الأربع؟ وأيها يُعرف بـ (المعطي العام)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الفصائل هي: A, B, AB, O. وتعتبر فصيلة (O) معطياً عاماً لأنها لا تحتوي على مولدات ضد (A أو B).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هو منظم النبض (العقدة الجيبية الأذينية)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>مجموعة من الخلايا في الأذين الأيمن ترسل إشارات كهربائية تسبب انقباض القلب بانتظام.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما الفرق بين الدورة الدموية الرئوية (الصغرى) والدورة الجسمية (الكبرى)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الرئوية: ينقل القلب الدم للرئتين لأخذ الأكسجين.<br>الجسمية: يضخ القلب الدم المؤكسج إلى جميع أنحاء الجسم.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 4 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الرابع: جهازا التنفس والإخراج
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>تتبع مسار الهواء من الأنف حتى يصل إلى الرئتين.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الأنف ← البلعوم ← الحنجرة ← القصبة الهوائية ← القصبتان الهوائيتان ← الشعيبات الهوائية ← الحويصلات الهوائية.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>كيف تعمل عضلة الحجاب الحاجز أثناء عمليتي الشهيق والزفير؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الشهيق: تنقبض وتنزل لأسفل لتوسيع التجويف الصدري.<br>الزفير: تنبسط وترتفع لأعلى لدفع الهواء خارج الرئتين.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي الأعضاء التي يتكون منها الجهاز الإخراجي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الكليتان (لإخراج البول)، الرئتان (لإخراج ثاني أكسيد الكربون وبخار الماء)، والجلد (لإخراج العرق والأملاح).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي الوحدة الأنبوبية الكلوية (النفرون) وما وظيفتها؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>هي الوحدة الوظيفية في الكلية المسؤولة عن ترشيح الدم وتخليصه من الفضلات لإنتاج البول.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>لماذا يعد الحفاظ على الاتزان الداخلي (نسبة الماء والأملاح) مهماً للجسم؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>لأن تراكم الفضلات السمية وتغير نسب الماء يخل بالضغط الأسموزي ويؤدي لتسمم الخلايا وضعف وظائف الأعضاء.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 5 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الخامس: جهازا الهضم والغدد الصم
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>قارن بين الهضم الميكانيكي والهضم الكيميائي مع ذكر مثال.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الميكانيكي: تمزيق الطعام وتقطيعه دون تغير في تركيبه (المضغ).<br>الكيميائي: تحليل الغذاء بواسطة الإنزيمات (هضم النشا بالأميليز).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما وظيفة إنزيم الببسين، وفي أي عضو يُفرز؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يُفرز في المعدة (في وسط شديد الحموضة)، ووظيفته هضم وتكسير البروتينات.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما الدور الذي تلعبه خملات الأمعاء الدقيقة (الخملات المعوية)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>بروزات تشبه الأصابع تزيد من مساحة سطح الأمعاء لتسريع وتسهيل امتصاص الغذاء المهضوم إلى مجرى الدم.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>عرّف الغدد الصم وكيف تقوم بعملها؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>هي غدد لا قنوية تفرز الهرمونات (الرسائل الكيميائية) مباشرة في مجرى الدم لتنظيم أنشطة الخلايا والأعضاء المستهدفة.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ماذا يفرز البنكرياس للتحكم في مستوى السكر في الدم؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يفرز هرمون (الإنسولين) لخفض مستوى السكر، وهرمون (الجلوكاجون) لرفع مستواه في الدم.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 6 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل السادس: التكاثر والنمو في الإنسان
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>أين يتم إنتاج الحيوانات المنوية، وما الهرمون الذكري الذي ينظمها؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>تنتج في الأنابيب المنوية داخل الخصيتين، والهرمون المنظم هو التستوستيرون.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>أين تحدث عملية الإخصاب عادة في الجهاز التناسلي الأنثوي؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>في الجزء العلوي من قناة البيض (قناة فالوب).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي المشيمة (Placenta)، وما وظيفتها الأساسية؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>عضو يرتبط بجدار الرحم ويوفر الأكسجين والغذاء للجنين، ويخلصه من الفضلات طوال فترة الحمل.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>رتب المراحل الأولى لنمو الجنين: (الكبسولة البلاستولية، اللاقحة، التوتية).</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>1- اللاقحة (البويضة المخصبة الزيجوت)<br>2- التوتية (المورولا)<br>3- الكبسولة البلاستولية (البلاستيولا).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>في أي مرحلة (أشهر) من الحمل يمكن سماع نبض قلب الجنين بوضوح؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>في مرحلة الشهور الثلاثة الأولى (تحديداً حول الأسبوع العاشر).</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 7 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل السابع: جهاز المناعة
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما الفرق بين المناعة غير المتخصصة (العامة) والمناعة المتخصصة (النوعية)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>غير المتخصصة: لا تستهدف مسبباً مرضياً بعينه (مثل الجلد وحمض المعدة والدموع).<br>المتخصصة: تستهدف مرضاً محدداً وتُكوّن خلايا ذاكرة للحماية منه مستقبلاً.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما دور الخلايا الليمفية البائية (B) والتائية (T)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الخلايا البائية (B): مسؤولة عن إنتاج الأجسام المضادة.<br>الخلايا التائية (T): تدمر الخلايا المصابة وتساعد الخلايا البائية.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي الأجسام المضادة؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>بروتينات تنتجها الخلايا الليمفية البائية، تتفاعل مع مولدات الضد الغريبة (البكتيريا/الفيروسات) لتبطل مفعولها.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>كيف تعمل اللقاحات (التطعيمات) في جسم الإنسان؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>حقن الجسم بمولد ضد (فيروس/بكتيريا) ضعيف أو ميت، لتحفيز الجهاز المناعي على إنتاج أجسام مضادة وتكوين (خلايا ذاكرة).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>كيف يسبب فيروس (HIV) مرض الإيدز (AIDS)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يقوم الفيروس باستهداف وتدمير الخلايا التائية المساعدة (T-helper)، مما يعطل جهاز المناعة ويجعل الجسم عرضة لأي مرض بسيط.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 8 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل الثامن: أساسيات علم الوراثة
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هو (قانون الانعزال) الذي وضعه مندل؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>ينص على أن أليلا كل صفة وراثية ينفصلان (ينعزلان) أثناء الانقسام المنصف لتكوين الأمشاج، ويتحدان مرة أخرى عند الإخصاب.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>وضح الفرق بين: الصفة السائدة والصفة المتنحية.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>السائدة: الصفة التي تظهر في الجيل الأول وتخفي أثر الصفة الأخرى (تُرمز بحرف كبير).<br>المتنحية: الصفة التي لا تظهر إلا إذا اجتمع أليلان متنحيان معاً (حرف صغير).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>قارن بين الطراز الجيني والطراز الشكلي.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الطراز الجيني: يمثل أزواج الأليلات المتقابلة للمخلوق الحي (مثل YY أو Yy).<br>الطراز الشكلي: يمثل الخصائص المظهرية والفيزيائية الناتجة عن الجينات (مثل لون البذرة أصفر).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما أهمية استخدام مربع بانيت (Punnett square)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يُستخدم لتوقع احتمالات الطرز الجينية والشكلية للأبناء الناتجة عن تزاوج معين.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>متى يكون الفرد (متماثل الجينات) ومتى يكون (غير متماثل الجينات)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>متماثل: إذا كان يحمل أليلين متطابقين للصفة (مثل TT أو tt).<br>غير متماثل (هجين): إذا كان يحمل أليلين مختلفين للصفة (مثل Tt).</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 9 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل التاسع: الوراثة المعقدة والوراثة البشرية
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هو (مخطط السلالة)، وفيما يستخدم؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>شكل (رسم) يتتبع وراثة صفة معينة عبر عدة أجيال في العائلة. يستخدم لتوقع الطرز الجينية للأبناء وتحديد الأمراض المتنحية أو السائدة.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>أعط مثالاً لاختلال وراثي متنحٍ، وآخر لاختلال وراثي سائد في الإنسان.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>متنحٍ: المهاق (غياب الميلانين) أو التليف الكيسي.<br>سائد: مرض هنتجتون (يؤثر على الجهاز العصبي) أو القمأ (عدم نمو الغضروف).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>بماذا يتميز نمط الوراثة في (السيادة المشتركة)؟ اذكر مثالاً.</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يتميز بظهور أثر كلا الأليلين معاً في الفرد الهجين. المثال: مرض فقر الدم المنجلي، أو فصيلة الدم AB.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>بماذا يتحدد الجنس في الإنسان؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>بواسطة الكروموسومات الجنسية (الزوج رقم 23). الطراز الجيني للأنثى (XX) وللذكر (XY).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما السبب الوراثي للإصابة بمتلازمة داون؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>وجود ثلاث نسخ من الكروموسوم رقم (21) بدلاً من نسختين، نتيجة لعدم انفصال الكروموسومات أثناء الانقسام المنصف.</span></div>
            </div>
        </div>
    </div>

    <!-- Worksheet 10 -->
    <div class="worksheet-page">
        <table class="header-table">
            <tr>
                <td style="text-align: right; width: 33%;">المملكة العربية السعودية<br>وزارة التعليم<br>المدرسة: الثانوية الثالثة بصبيا بنين</td>
                <td style="text-align: center; width: 34%;"><img src="pngegg.png" alt="Logo" style="height: 50px; opacity: 0.8; margin: 0 auto;"><br><span class="text-green-700 text-lg font-bold">ملخص الأحياء 2-2</span></td>
                <td style="text-align: left; width: 33%;">اسم الطالب: .........................<br>الصف / الشعبة: .................</td>
            </tr>
        </table>

        <div class="text-center mb-6">
            <h2 class="text-xl font-bold text-gray-800 bg-green-100 inline-block px-6 py-2 rounded-full border border-green-200 shadow-sm">
                الفصل العاشر: الوراثة الجزيئية
            </h2>
        </div>

        <div class="space-y-4">
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>مما يتكون النيوكليوتيد، الذي يعتبر الوحدة الأساسية لبناء الأحماض النووية؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يتكون من 3 أجزاء: مجموعة فوسفات، سكر خماسي الكربون، وقاعدة نيتروجينية.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>كيف ترتبط القواعد النيتروجينية في جزيء الـ DNA؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>يرتبط الأدينين (A) دائماً مع الثايمين (T)، ويرتبط الجوانين (G) دائماً مع السايتوسين (C).</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما الفروق الرئيسية بين تركيب الـ DNA والـ RNA؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>الـ DNA: شريط مزدوج، السكر فيه منقوص الأكسجين، ويحتوي على قاعدة الثايمين (T).<br>الـ RNA: شريط مفرد، السكر فيه ريبوز، ويحتوي على قاعدة اليوراسيل (U) بدلاً من الثايمين.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هي عملية النسخ (Transcription) في بناء البروتين؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>عملية تصنيع شريط من RNA الرسول (mRNA) من قالب الـ DNA، وتحدث داخل النواة.</span></div>
            </div>
            <div class="qa-row">
                <div class="q-box"><i class="fas fa-question-circle q-icon"></i> <span>ما هو الطفرة (Mutation)؟</span></div>
                <div class="a-box"><i class="fas fa-check-circle a-icon"></i> <span>تغير دائم في تسلسل القواعد النيتروجينية (DNA) للخلية، وقد تؤدي إلى تغير في إنتاج البروتينات وظهور صفات جديدة أو أمراض.</span></div>
            </div>
        </div>
    </div>

    <!-- كود الجافاسكربت لإضافة التفاعلية (إخفاء وإظهار الإجابات) -->
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            // تحديد جميع مربعات الأسئلة
            const qBoxes = document.querySelectorAll('.q-box');
            
            qBoxes.forEach(box => {
                // إضافة أيقونة السهم لتدل على القابلية للضغط لكل سؤال
                const arrowIcon = document.createElement('i');
                arrowIcon.className = 'fas fa-chevron-down text-gray-400 mr-auto text-sm transition-transform duration-300';
                box.appendChild(arrowIcon);

                // إضافة حدث الضغط (Click Event)
                box.addEventListener('click', function() {
                    const answerBox = this.nextElementSibling;
                    
                    // إظهار أو إخفاء الإجابة
                    answerBox.classList.toggle('show');
                    
                    // قلب السهم عند الإظهار
                    arrowIcon.classList.toggle('rotate-180');
                });
            });
        });
    </script>
</body>
</html>
