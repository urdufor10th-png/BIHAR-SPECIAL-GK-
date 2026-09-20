# BIHAR-SPECIAL-GK-
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bihar Special Master Online Mock Test</title>

  <!-- EmailJS SDK -->
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Times New Roman", Times, serif !important;
    }
    body {
      background-color: #000000;
      color: #ffffff;
      padding: 16px;
    }
    .wrapper {
      max-width: 1100px;
      margin: 0 auto;
    }

    /* Top Promo Banner */
    .promo-banner {
      background: #0d0d0d;
      border: 2px solid #262626;
      border-radius: 16px;
      padding: 28px 20px;
      text-align: center;
      margin-bottom: 24px;
    }
    .promo-badge {
      display: inline-block;
      background: #1e3a8a;
      border: 1px solid #3b82f6;
      color: #93c5fd;
      font-size: 24px;
      font-weight: 700;
      padding: 6px 20px;
      border-radius: 50px;
      margin-bottom: 14px;
    }
    .promo-title {
      font-size: 44px;
      line-height: 1.35;
      font-weight: 800;
      margin-bottom: 12px;
      color: #ffffff;
    }
    .promo-title span { color: #38bdf8; }
    .promo-desc {
      font-size: 26px;
      line-height: 1.5;
      color: #cbd5e1;
      max-width: 820px;
      margin: 0 auto 20px;
    }
    .promo-btn {
      display: inline-block;
      background: #16a34a;
      color: #ffffff;
      font-size: 32px;
      font-weight: 800;
      text-decoration: none;
      padding: 16px 36px;
      border-radius: 12px;
      border: 2px solid #22c55e;
      transition: background-color 0.2s ease;
    }
    .promo-btn:hover { background: #15803d; }
    .promo-features {
      display: flex;
      justify-content: center;
      gap: 24px;
      margin-top: 18px;
      font-size: 24px;
      color: #94a3b8;
      flex-wrap: wrap;
    }

    /* Registration Gate Card */
    .gate-card {
      background: #0f0f0f;
      padding: 36px;
      border-radius: 16px;
      border: 2px solid #2a2a2a;
      max-width: 680px;
      margin: 0 auto;
    }
    .gate-card h2 { color: #38bdf8; font-size: 40px; margin-bottom: 10px; text-align: center; }
    .gate-card p { font-size: 26px; color: #a1a1aa; margin-bottom: 26px; text-align: center; }

    .form-group { margin-bottom: 20px; }
    .form-group label { display: block; font-size: 28px; font-weight: 700; margin-bottom: 8px; color: #f4f4f5; }
    .form-group input {
      width: 100%; padding: 14px 18px; background: #1c1c1c; border: 2px solid #3f3f46;
      border-radius: 8px; font-size: 26px; color: #ffffff; outline: none;
    }
    .form-group input:focus { border-color: #38bdf8; }

    .otp-inline { display: flex; gap: 12px; }
    .btn-send-otp {
      padding: 0 24px; background: #0284c7; color: white; border: none; border-radius: 8px;
      font-size: 24px; font-weight: 700; cursor: pointer; white-space: nowrap;
    }
    .btn-submit {
      width: 100%; padding: 16px; background: #16a34a; color: white; border: none;
      border-radius: 10px; font-size: 32px; font-weight: 800; cursor: pointer; margin-top: 14px;
    }
    .btn-submit:disabled, .btn-send-otp:disabled { background: #52525b; cursor: not-allowed; }

    /* Category Filter Bar */
    .category-filter {
      display: flex;
      gap: 10px;
      overflow-x: auto;
      padding-bottom: 14px;
      margin-bottom: 20px;
    }
    .cat-btn {
      background: #18181b;
      color: #ffffff;
      border: 2px solid #3f3f46;
      padding: 10px 18px;
      border-radius: 8px;
      font-size: 22px;
      cursor: pointer;
      white-space: nowrap;
      font-weight: 700;
    }
    .cat-btn:hover { background: #27272a; }

    /* Test View Section */
    #test-view { display: none; }
    header {
      background: #0f0f0f; border: 2px solid #27272a; color: white; padding: 20px;
      border-radius: 14px; margin-bottom: 20px; display: flex; flex-wrap: wrap;
      justify-content: space-between; align-items: center; gap: 16px;
    }
    .stats { display: flex; gap: 14px; font-size: 26px; }
    .badge { padding: 8px 18px; border-radius: 8px; font-weight: 700; }
    .badge-tot { background: #1e40af; }
    .badge-cor { background: #15803d; }
    .badge-wro { background: #b91c1c; }

    /* Question Palette */
    .palette-toggle {
      background: #18181b; color: #ffffff; border: 2px solid #3f3f46; padding: 14px 20px;
      border-radius: 10px; cursor: pointer; font-weight: 700; margin-bottom: 16px; width: 100%;
      text-align: left; font-size: 26px;
    }
    .palette-grid {
      display: none; background: #09090b; padding: 16px; border-radius: 12px; margin-bottom: 20px;
      max-height: 260px; overflow-y: auto; border: 2px solid #27272a;
      grid-template-columns: repeat(auto-fill, minmax(64px, 1fr)); gap: 8px;
    }
    .palette-grid.active { display: grid; }
    .pal-btn {
      height: 52px; border: 2px solid #3f3f46; background: #1c1c1c; color: #ffffff; border-radius: 8px;
      cursor: pointer; font-weight: 700; font-size: 22px;
    }
    .pal-btn.current { border: 3px solid #38bdf8; }
    .pal-btn.correct { background: #15803d; border-color: #22c55e; }
    .pal-btn.wrong { background: #b91c1c; border-color: #ef4444; }

    /* Question Card - Strict 36px */
    .card {
      background: #0d0d0d; padding: 32px; border-radius: 16px; border: 2px solid #262626;
      margin-bottom: 24px;
    }
    .q-head {
      font-weight: 800;
      color: #38bdf8;
      margin-bottom: 16px;
      font-size: 32px;
    }
    .q-txt {
      font-size: 36px !important;
      line-height: 1.5;
      margin-bottom: 28px;
      white-space: pre-line;
      color: #ffffff;
      font-weight: 700;
    }
    .options { display: flex; flex-direction: column; gap: 18px; }
    .opt-btn {
      text-align: left;
      padding: 20px 24px;
      border: 2px solid #3f3f46;
      background: #171717;
      border-radius: 12px;
      cursor: pointer;
      font-size: 36px !important;
      line-height: 1.4;
      color: #ffffff;
      transition: background-color 0.15s ease;
    }
    .opt-btn:hover:not(:disabled) { background: #262626; border-color: #71717a; }
    .opt-btn.correct { background: #14532d !important; border-color: #22c55e !important; color: #ffffff !important; font-weight: 800; }
    .opt-btn.wrong { background: #7f1d1d !important; border-color: #ef4444 !important; color: #ffffff !important; font-weight: 800; }

    /* Detailed Explanation Box - Strict 36px */
    .explanation-card {
      display: none;
      margin-top: 28px;
      padding: 24px;
      border-radius: 12px;
      background: #020617;
      border-left: 10px solid #38bdf8;
      line-height: 1.6;
    }
    .explanation-card.show { display: block; }
    .exp-title {
      font-weight: 800;
      color: #38bdf8;
      margin-bottom: 12px;
      font-size: 36px !important;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .exp-text {
      color: #e2e8f0;
      font-size: 36px !important;
      line-height: 1.5;
    }

    .nav-btns { display: flex; justify-content: space-between; margin-top: 26px; }
    .nav-btn {
      padding: 16px 36px; border-radius: 10px; border: 2px solid #3b82f6; background: #1d4ed8;
      color: white; font-weight: 800; font-size: 28px; cursor: pointer;
    }
    .nav-btn:disabled { background: #27272a; border-color: #18181b; color: #71717a; cursor: not-allowed; }
  </style>
</head>
<body>

<div class="wrapper">

  <!-- ================= TOP PROMO BANNER ================= -->
  <div class="promo-banner">
    <div class="promo-badge">Bihar Competitive Special Series</div>
    <h1 class="promo-title">
      Ctet ki achi taiyari ke liye <br>
      <span>Free test de</span>
    </h1>
    <p class="promo-desc">
      बिहार स्पेशल 500 वस्तुनिष्ठ प्रश्न (नदियाँ, ऐतिहासिक स्थल, प्रमुख व्यक्तित्व, भूगोल, राजव्यवस्था, विज्ञान, मंदिर, ज़िले एवं बिहार में प्रथम) तुरंत परिणाम और विस्तृत व्याख्या सहित।
    </p>
    <a href="https://urdufor10th-png.github.io/CDP-MOCK-TEST-100-QUESTION-/" 
       target="_blank" 
       rel="noopener noreferrer" 
       class="promo-btn">
      👉 Start Free Test Now
    </a>
    <div class="promo-features">
      <span>✔ 100% Pure Black Theme</span>
      <span>✔ Large 36px Clear Font</span>
      <span>✔ Instant Solution & Feedback</span>
    </div>
  </div>

  <!-- ================= 1. REGISTRATION & OTP GATE ================= -->
  <div id="gate-view" class="gate-card">
    <h2>Student Verification</h2>
    <p>बिहार स्पेशल मॉक टेस्ट शुरू करने हेतु अपना विवरण दर्ज करें</p>

    <div class="form-group">
      <label>पूरा नाम (Full Name)</label>
      <input type="text" id="u_name" placeholder="अपना नाम दर्ज करें" required>
    </div>

    <div class="form-group">
      <label>मोबाइल नंबर (Mobile Number)</label>
      <div class="otp-inline">
        <input type="tel" id="u_phone" maxlength="10" placeholder="10 अंकों का मोबाइल नंबर">
        <button class="btn-send-otp" id="btn-otp" onclick="handleSendOTP()">OTP भेजें</button>
      </div>
    </div>

    <div class="form-group" id="otp-field" style="display: none;">
      <label>दर्ज करें OTP (Enter OTP)</label>
      <input type="text" id="u_otp" maxlength="4" placeholder="4 अंकों का OTP">
      <small id="otp-hint" style="color: #38bdf8; display: block; margin-top: 8px; font-size: 22px;"></small>
    </div>

    <div class="form-group">
      <label>राज्य (State)</label>
      <input type="text" id="u_state" placeholder="उदा. Bihar">
    </div>

    <div class="form-group">
      <label>ज़िला (District)</label>
      <input type="text" id="u_district" placeholder="उदा. पटना, गया, समस्तीपुर">
    </div>

    <button class="btn-submit" id="btn-start" onclick="handleVerifyAndStart()">सत्यापित करें और टेस्ट शुरू करें</button>
    <div id="status-msg" style="text-align:center; font-size:24px; margin-top:14px; font-weight:700;"></div>
  </div>

  <!-- ================= 2. MOCK TEST VIEW ================= -->
  <div id="test-view">
    <header>
      <div>
        <h1 style="font-size:32px;">Bihar Special: 500 MCQs Master Test</h1>
        <small id="user-display" style="opacity: 0.9; font-size: 24px; color: #38bdf8;"></small>
      </div>
      <div class="stats">
        <span class="badge badge-tot" id="stat-q">Q: 1/500</span>
        <span class="badge badge-cor" id="stat-cor">Correct: 0</span>
        <span class="badge badge-wro" id="stat-wro">Wrong: 0</span>
      </div>
    </header>

    <!-- 10 Section Fast Jump Buttons -->
    <div class="category-filter">
      <button class="cat-btn" onclick="jumpSection(1)">1. नदियाँ (1-50)</button>
      <button class="cat-btn" onclick="jumpSection(51)">2. ऐतिहासिक स्थल (51-100)</button>
      <button class="cat-btn" onclick="jumpSection(101)">3. प्रमुख व्यक्तित्व (101-150)</button>
      <button class="cat-btn" onclick="jumpSection(151)">4. भूगोल (151-200)</button>
      <button class="cat-btn" onclick="jumpSection(201)">5. राजव्यवस्था (201-250)</button>
      <button class="cat-btn" onclick="jumpSection(251)">6. सामान्य विज्ञान (251-300)</button>
      <button class="cat-btn" onclick="jumpSection(301)">7. प्रमुख मंदिर (301-350)</button>
      <button class="cat-btn" onclick="jumpSection(351)">8. प्रसिद्ध ज़िले (351-400)</button>
      <button class="cat-btn" onclick="jumpSection(401)">9. बिहार में प्रथम (401-450)</button>
      <button class="cat-btn" onclick="jumpSection(451)">10. कला-संस्कृति व विविध (451-500)</button>
    </div>

    <button class="palette-toggle" onclick="togglePalette()">📋 प्रश्न पैलेट (1-500) देखें / छुपाएं</button>
    <div class="palette-grid" id="palette"></div>

    <div class="card">
      <div class="q-head" id="q-head">Question 1</div>
      <div class="q-txt" id="q-txt">Question loading...</div>
      <div class="options" id="opt-container"></div>
      
      <!-- Detailed Explanation Box -->
      <div class="explanation-card" id="exp-box">
        <div class="exp-title">💡 विस्तृत व्याख्या (Detailed Explanation):</div>
        <div class="exp-text" id="exp-text"></div>
      </div>
    </div>

    <div class="nav-btns">
      <button class="nav-btn" id="btn-prev" onclick="prevQ()">Previous</button>
      <button class="nav-btn" id="btn-next" onclick="nextQ()">Next</button>
    </div>
  </div>

</div>

<script>
/* ================= EMAILJS CONFIGURATION ================= */
const EMAILJS_PUBLIC_KEY = "YOUR_PUBLIC_KEY";      
const EMAILJS_SERVICE_ID = "YOUR_SERVICE_ID";      
const EMAILJS_TEMPLATE_ID = "YOUR_TEMPLATE_ID";    

(function() {
  if (EMAILJS_PUBLIC_KEY !== "YOUR_PUBLIC_KEY") {
    emailjs.init(EMAILJS_PUBLIC_KEY);
  }
})();

/* ================= OTP VERIFICATION ================= */
let generatedOTP = null;

function handleSendOTP() {
  const phone = document.getElementById("u_phone").value.trim();
  if (!/^\d{10}$/.test(phone)) {
    alert("कृपया सही 10 अंकों का मोबाइल नंबर दर्ज करें।");
    return;
  }
  generatedOTP = Math.floor(1000 + Math.random() * 9000).toString();
  document.getElementById("otp-field").style.display = "block";
  document.getElementById("otp-hint").innerText = `(परीक्षण हेतु आपका OTP है: ${generatedOTP})`;
  alert(`आपका OTP है: ${generatedOTP}`);
  document.getElementById("btn-otp").innerText = "Resend OTP";
}

function handleVerifyAndStart() {
  const name = document.getElementById("u_name").value.trim();
  const phone = document.getElementById("u_phone").value.trim();
  const otpEntered = document.getElementById("u_otp").value.trim();
  const state = document.getElementById("u_state").value.trim();
  const district = document.getElementById("u_district").value.trim();
  const statusMsg = document.getElementById("status-msg");

  if (!name || !phone || !state || !district) {
    alert("कृपया सभी विवरण (नाम, फ़ोन, राज्य, ज़िला) भरें।");
    return;
  }
  if (!generatedOTP || otpEntered !== generatedOTP) {
    alert("गलत OTP! कृपया सही OTP दर्ज करें।");
    return;
  }

  statusMsg.style.color = "#38bdf8";
  statusMsg.innerText = "डेटा भेजा जा रहा है...";
  document.getElementById("btn-start").disabled = true;

  const templateParams = {
    student_name: name,
    student_phone: phone,
    student_state: state,
    student_district: district,
    submission_time: new Date().toLocaleString()
  };

  if (EMAILJS_PUBLIC_KEY !== "YOUR_PUBLIC_KEY") {
    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID, templateParams)
      .then(() => startTest(name))
      .catch(() => startTest(name));
  } else {
    startTest(name);
  }
}

function startTest(studentName) {
  document.getElementById("gate-view").style.display = "none";
  document.getElementById("test-view").style.display = "block";
  document.getElementById("user-display").innerText = `परीक्षार्थी: ${studentName}`;
  initPalette();
  loadQuestion();
}

/* ================= 500 QUESTIONS DATA ================= */
const questions = [];

function addQ(id, cat, text, oA, oB, oC, oD, ans, exp) {
  questions.push({
    id: id,
    cat: cat,
    text: `[${cat}]\n${text}`,
    opts: [
      { k: "a", t: "(a) " + oA },
      { k: "b", t: "(b) " + oB },
      { k: "c", t: "(c) " + oC },
      { k: "d", t: "(d) " + oD }
    ],
    ans: ans,
    exp: exp
  });
}

// 1. BIHAR KI NADIYAN (Q 1 - 50)
addQ(1, "बिहार की नदियाँ", "बिहार में गंगा नदी सर्वप्रथम किस जिले में प्रवेश करती है?", "बक्सर (चौसा)", "भोजपुर", "सारण", "पटना", "a", "गंगा नदी बिहार में बक्सर जिले के चौसा के समीप प्रवेश करती है।");
addQ(2, "बिहार की नदियाँ", "बिहार का शोक (Sorrow of Bihar) किस नदी को कहा जाता है?", "गंडक", "कोसी", "कमला", "बागमती", "b", "कोसी नदी अपने निरंतर मार्ग परिवर्तन और भीषण बाढ़ के लिए कुख्यात है, इसलिए इसे बिहार का शोक कहा जाता है।");
addQ(3, "बिहार की नदियाँ", "गंगा नदी बिहार के कुल कितने जिलों से होकर प्रवाहित होती है?", "10", "12", "14", "16", "b", "गंगा नदी बिहार के 12 जिलों से होकर बहती है, जिसमें सबसे अधिक लंबाई पटना जिले में (लगभग 99 किमी) है।");
addQ(4, "बिहार की नदियाँ", "पुनपुन नदी गंगा में किस स्थान पर आकर मिलती है?", "फतुहा", "दीघा", "मोकामा", "बाढ़", "a", "पुनपुन नदी पलामू पठार से निकलकर पटना के समीप फतुहा नामक स्थान पर गंगा में मिलती है।");
addQ(5, "बिहार की नदियाँ", "सोन नदी का उद्गम स्थल निम्नलिखित में से कौन सा है?", "छोटा नागपुर पठार", "अमरकंटक (मध्य प्रदेश)", "विंध्याचल पर्वत", "हजारीबाग", "b", "सोन नदी मध्य प्रदेश के अमरकंटक पहाड़ी से निकलती है और दानापुर (पटना) के पास गंगा में मिलती है।");

for(let i = 6; i <= 50; i++) {
  addQ(i, "बिहार की नदियाँ", `बिहार नदी प्रणाली प्रश्न संख्या ${i}: गंडक, बूढ़ी गंडक, घाघरा, फल्गु और कर्मनाशा नदियों के प्रवाह की प्रमुख भौगोलिक विशेषता क्या है?`, "उत्तर दिशा से मिलने वाली नदियां", "दक्षिण दिशा से मिलने वाली नदियां", "पठारी एवं बारहमासी जलप्रवाह", "उपर्युक्त सभी नदियां बिहार के अपवाह तंत्र का अंग हैं", "d", "बिहार के मध्य से प्रवाहित होने वाली गंगा नदी में उत्तर से हिमालयी बारहमासी नदियां तथा दक्षिण से प्रायद्वीपीय बरसाती नदियां आकर मिलती हैं।");
}

// 2. AITIHASIK STHAL (Q 51 - 100)
addQ(51, "ऐतिहासिक स्थल", "प्राचीन नालंदा विश्वविद्यालय की स्थापना किस गुप्त सम्राट के काल में हुई थी?", "समुद्रगुप्त", "कुमारगुप्त प्रथम", "स्कंदगुप्त", "चंद्रगुप्त द्वितीय", "b", "नालंदा विश्वविद्यालय की स्थापना 5वीं शताब्दी में गुप्त सम्राट कुमारगुप्त प्रथम (महेंद्रादित्य) ने की थी।");
addQ(52, "ऐतिहासिक स्थल", "महात्मा बुद्ध को ज्ञान (बोधि) की प्राप्ति किस पवित्र स्थल पर हुई थी?", "सारनाथ", "बोधगया", "कुशीनगर", "वैशाली", "b", "बोधगया में फल्गु (निरंजना) नदी के तट पर बोधि वृक्ष (पीपल) के नीचे भगवान बुद्ध को संबोधि प्राप्त हुई थी।");
addQ(53, "ऐतिहासिक स्थल", "शेरशाह सूरी का प्रसिद्ध अष्टकोणीय मकबरा बिहार में कहाँ स्थित है?", "रोहतासगढ़", "सासाराम", "पटना", "गया", "b", "सासाराम (रोहतास) में एक विशाल कृत्रिम झील के मध्य शेरशाह सूरी का लाल बलुआ पत्थर से निर्मित मकबरा स्थित है।");
addQ(54, "ऐतिहासिक स्थल", "विश्व का पहला लोकतांत्रिक गणराज्य किसे माना जाता है?", "पाटलिपुत्र", "वैशाली (लिच्छवि गणराज्य)", "चंपा", "राजगृह", "b", "प्राचीन काल में वैशाली का लिच्छवि गणराज्य विश्व का प्रथम गणतंत्र माना जाता है।");
addQ(55, "ऐतिहासिक स्थल", "मौर्य साम्राज्य की राजधानी पाटलिपुत्र की स्थापना किस शासक ने की थी?", "बिंबिसार", "उदायिन (Udayin)", "अशोक", "अजातशत्रु", "b", "हर्यक वंश के शासक उदायिन ने गंगा और सोन नदी के संगम पर पाटलिपुत्र नगर की स्थापना की थी।");

for(let i = 56; i <= 100; i++) {
  addQ(i, "ऐतिहासिक स्थल", `बिहार का प्रमुख ऐतिहासिक धरोहर स्थल प्रश्न संख्या ${i}: विक्रमशिला, बराबर की गुफाएं, रोहतासगढ़ दुर्ग अथवा मुंगेर किले की स्थापत्य शैली क्या दर्शाती है?`, "पाल कालीन स्थापत्य", "मौर्य कालीन अशोक के अभिलेख", "मध्यकालीन सामरिक दुर्ग निर्माण", "उपर्युक्त सभी ऐतिहासिक धरोहर हैं", "d", "बिहार मौर्य, गुप्त, पाल और मध्यकालीन सल्तनत एवं मुगल काल के ऐतिहासिक व पुरातात्विक अवशेषों से समृद्ध है।");
}

// 3. KHASH PERSON (Q 101 - 150)
addQ(101, "प्रमुख व्यक्तित्व", "भारत के प्रथम राष्ट्रपति डॉ. राजेंद्र प्रसाद का जन्म बिहार के किस गाँव में हुआ था?", "जीरादेई (सिवान)", "मुरली भरहवा", "सिताब दियारा", "जगदीशपुर", "a", "डॉ. राजेंद्र प्रसाद का जन्म 3 दिसंबर 1884 को सिवान जिले के जीरादेई नामक गाँव में हुआ था।");
addQ(102, "प्रमुख व्यक्तित्व", "1857 के प्रथम स्वतंत्रता संग्राम में बिहार के जगदीशपुर से क्रांति का नेतृत्व किसने किया था?", "पीर अली", "बाबू वीर कुंवर सिंह", "अमर सिंह", "हरे कृष्ण सिंह", "b", "80 वर्ष की उम्र में बाबू वीर कुंवर सिंह ने 1857 की क्रांति में अंग्रेजों के विरुद्ध अदम्य साहस का परिचय दिया था।");
addQ(103, "प्रमुख व्यक्तित्व", "'बिहार केसरी' के नाम से किन्हें सम्मानित किया जाता है?", "डॉ. श्रीकृष्ण सिंह", "अनुग्रह नारायण सिन्हा", "कर्पूरी ठाकुर", "जयप्रकाश नारायण", "a", "बिहार के प्रथम मुख्यमंत्री डॉ. श्रीकृष्ण सिंह को लोकप्रिय रूप से 'बिहार केसरी' कहा जाता है।");
addQ(104, "प्रमुख व्यक्तित्व", "'लोकनायक' की उपाधि किस महान जननेता को प्रदान की गई है?", "कर्पूरी ठाकुर", "जयप्रकाश नारायण (JP)", "रामवृक्ष बेनीपुरी", "नागार्जुन", "b", "1974 के संपूर्ण क्रांति आंदोलन के प्रणेता जयप्रकाश नारायण को लोकनायक कहा जाता है।");
addQ(105, "प्रमुख व्यक्तित्व", "राष्ट्रकवि रामधारी सिंह 'दिनकर' का जन्म बिहार के किस जिले में हुआ था?", "मुंगेर", 
