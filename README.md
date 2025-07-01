<body style="font-family: Arial, sans-serif; background-color: #f2f2f2; text-align: center; padding: 20px;">
<div class="container" style="background: white; padding: 20px; margin: auto; max-width: 400px; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1);">

  <h2>اختبار العلاقات العائلية</h2>
  <p>اختر ثم اكتب اسم الشخص الذي تفضله</p>

  <form id="testForm">
    <!-- حقل اسم المستخدم الجديد -->
    <label>اسمك:</label>
    <input type="text" name="userName" id="userName" required><br><br>

    <label>من أقرب أولاد العم/الخال/العمة/الخالة إليك؟</label><br><br>
    <input type="radio" name="relativeType" value="ابن عمك"> ابن عمك<br>
    <input type="radio" name="relativeType" value="ابن خالك"> ابن خالك<br>
    <input type="radio" name="relativeType" value="ابن عمتك"> ابن عمتك<br>
    <input type="radio" name="relativeType" value="ابن خالتك"> ابن خالتك<br><br>

    <label>اكتب اسمه:</label>
    <input type="text" name="relativeName" id="relativeName"><br><br>

    <label>من تفضل أن يكون شريكك في مشروع تجاري؟</label><br><br>
    <input type="radio" name="partnerType" value="ابن عمك"> ابن عمك<br>
    <input type="radio" name="partnerType" value="ابن خالك"> ابن خالك<br>
    <input type="radio" name="partnerType" value="ابن عمتك"> ابن عمتك<br>
    <input type="radio" name="partnerType" value="ابن خالتك"> ابن خالتك<br><br>

    <label>اكتب اسمه:</label>
    <input type="text" name="partnerName" id="partnerName"><br><br>

    <button type="button" onclick="showResult()" style="padding: 10px 20px; margin-top: 20px; background-color: #4CAF50; color: white; border: none; border-radius: 5px; cursor: pointer;">إظهار النتيجة</button>
  </form>

  <div id="result" style="margin-top:20px; display:none;"></div>
</div>

<script>
function showResult() {
  const userName = document.getElementById("userName").value;
  const relativeType = document.querySelector('input[name="relativeType"]:checked');
  const relativeName = document.getElementById("relativeName").value;
  const partnerType = document.querySelector('input[name="partnerType"]:checked');
  const partnerName = document.getElementById("partnerName").value;
  
  if (!userName || !relativeType || !relativeName || !partnerType || !partnerName) {
    alert('الرجاء إدخال اسمك والإجابة على جميع الأسئلة');
    return;
  }

  const resultDiv = document.getElementById("result");
  resultDiv.style.display = 'block';
  resultDiv.innerHTML = `
    <h3>نتيجة اختبار ${userName}</h3>
    <p>أقرب شخص إليك هو: <strong>${relativeType.value} (${relativeName})</strong></p>
    <p>المرشح ليكون شريكك: <strong>${partnerType.value} (${partnerName})</strong></p>
  `;
}
</script>
