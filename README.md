# personality-test<!DOCTYPE html><html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اختبار تحليل الشخصية</title>
    <style>
        body { font-family: Arial, sans-serif; direction: rtl; text-align: center; background: #f4f4f4; padding: 20px; }
        .container { background: white; padding: 20px; border-radius: 8px; max-width: 500px; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        button { padding: 10px 20px; margin-top: 15px; cursor: pointer; background: #007BFF; color: white; border: none; border-radius: 4px; }
        .hidden { display: none; }
    </style>
</head>
<body>
<div class="container">
    <h2>اختبار تحليل الشخصية</h2>
    <div id="step1">
        <p>من خلال إجابتك على هذه الأسئلة، نحدد بعض ملامح شخصيتك. جاهز؟</p>
        <button onclick="nextStep(2)">ابدأ</button>
    </div><div id="step2" class="hidden">
    <p>من أكثر شخص ترتاح له من الأقارب؟</p>
    <input type="text" id="favPerson" placeholder="اكتب الاسم أو الصفة">
    <button onclick="nextStep(3)">التالي</button>
</div>

<div id="step3" class="hidden">
    <p>ما أكثر صفة تحبها في الشخص القريب منك؟</p>
    <input type="text" id="bestTrait" placeholder="اكتب الصفة">
    <button onclick="nextStep(4)">التالي</button>
</div>

<div id="step4" class="hidden">
    <p>إذا أتيحت لك فرصة تختار شخص من الأقارب يكون معك طول حياتك، من تختار؟</p>
    <input type="text" id="lifePartner" placeholder="اكتب الاسم">
    <button onclick="showResult()">عرض النتيجة</button>
</div>

<div id="result" class="hidden">
    <h3>نتيجة تحليل الشخصية:</h3>
    <p id="output"></p>
</div>

</div><script>
    function nextStep(step) {
        document.querySelectorAll('.container > div').forEach(div => div.classList.add('hidden'));
        document.getElementById(`step${step}`).classList.remove('hidden');
    }

    function showResult() {
        const favPerson = document.getElementById('favPerson').value.trim();
        const bestTrait = document.getElementById('bestTrait').value.trim();
        const lifePartner = document.getElementById('lifePartner').value.trim();

        let message = `شخصيتك تحب الأشخاص مثل ${favPerson} بسبب ${bestTrait}.\n`;
        message += `وتتمنى أن يكون معك ${lifePartner} طول حياتك.\n`;
        message += "هذا يعكس روحك الاجتماعية واهتمامك بالمقربين منك.";

        document.getElementById('output').innerText = message;
        nextStep('result');
    }
</script></body>
</html>
