# نون
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>كود خصم نون</title>

<style>
* {
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family: system-ui, Arial;
}

body {
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background: linear-gradient(135deg,#fff200,#ffd000);
  overflow:hidden;
}

/* خلفية احترافية */
.bg-logo {
  position:absolute;
  font-size:120px;
  color:rgba(0,0,0,0.05);
  animation: float 6s infinite ease-in-out;
}

@keyframes float {
  0%{transform:translateY(0)}
  50%{transform:translateY(-20px)}
  100%{transform:translateY(0)}
}

/* الكرت */
.card {
  position:relative;
  width:90%;
  max-width:420px;
  background:#fff;
  padding:35px;
  border-radius:20px;
  text-align:center;
  box-shadow:0 20px 50px rgba(0,0,0,0.25);
  animation:fadeIn 1s ease;
}

@keyframes fadeIn {
  from{opacity:0;transform:scale(0.9)}
  to{opacity:1;transform:scale(1)}
}

/* الكود */
.coupon {
  background:#e60023;
  color:#fff;
  padding:20px;
  font-size:36px;
  border-radius:12px;
  margin-bottom:15px;
  font-weight:bold;
  letter-spacing:3px;
  animation:pulse 1.5s infinite;
}

@keyframes pulse {
  0%{transform:scale(1)}
  50%{transform:scale(1.07)}
  100%{transform:scale(1)}
}

/* النص */
.title {
  font-size:18px;
  font-weight:bold;
}

.desc {
  color:#666;
  margin-top:10px;
}

/* العداد */
.timer {
  margin-top:15px;
  font-weight:bold;
  color:#0a8f2f;
}

/* زر احترافي */
button {
  margin-top:25px;
  width:100%;
  padding:16px;
  font-size:16px;
  border:none;
  border-radius:12px;
  cursor:pointer;
  color:#fff;
  background:linear-gradient(45deg,#ff4d2d,#ff0000);
  position:relative;
  overflow:hidden;
}

/* تأثير ضوء */
button::after {
  content:'';
  position:absolute;
  top:0;
  left:-100%;
  width:100%;
  height:100%;
  background:rgba(255,255,255,0.4);
  transform:skewX(-20deg);
}

button:hover::after {
  left:120%;
  transition:0.6s;
}

button:hover {
  transform:scale(1.05);
}

/* رسالة النسخ */
.toast {
  position:fixed;
  bottom:20px;
  left:50%;
  transform:translateX(-50%);
  background:#000;
  color:#fff;
  padding:12px 20px;
  border-radius:8px;
  opacity:0;
  transition:0.3s;
}

.toast.show {
  opacity:1;
}
</style>

</head>

<body>

<div class="bg-logo">noon</div>

<div class="card">

  <div id="coupon" class="coupon">OKTB</div>

  <div class="title">
    أعلى كود خصم نون خصم فوري حتى 100 ريال
  </div>

  <div class="desc">
    ساري على جميع المنتجات لمدة 24 ساعة فقط ✅
  </div>

  <div id="timer" class="timer"></div>

  <button id="btn" onclick="copyAndGo()">
    اضغط هنا لنسخ الكوبون
  </button>

</div>

<div id="toast" class="toast">تم النسخ — تسوق ممتع 🛍️</div>

<!-- صوت -->
<audio id="sound" src="https://assets.mixkit.co/sfx/preview/mixkit-select-click-1109.mp3"></audio>

<script>
// 🔥 عداد 24 ساعة
let endTime = localStorage.getItem("endTime");

if (!endTime) {
  endTime = new Date().getTime() + 24*60*60*1000;
  localStorage.setItem("endTime", endTime);
}

function updateTimer(){
  let now = new Date().getTime();
  let d = endTime - now;

  let h = Math.floor(d/(1000*60*60));
  let m = Math.floor((d%(1000*60*60))/(1000*60));
  let s = Math.floor((d%(1000*60))/1000);

  document.getElementById("timer").innerHTML =
  `ينتهي خلال: ${h} ساعة ${m} دقيقة ${s} ثانية`;

  if(d<0){
    document.getElementById("timer").innerHTML="انتهى العرض ❌";
  }
}
setInterval(updateTimer,1000);

// 🔥 نسخ + صوت + تحويل
function copyAndGo(){
  let text = document.getElementById("coupon").innerText;

  navigator.clipboard.writeText(text).then(()=>{

    document.getElementById("sound").play();

    let toast = document.getElementById("toast");
    toast.classList.add("show");

    document.getElementById("btn").innerText = "تم النسخ — تسوق ممتع 🛍️";

    setTimeout(()=>{
      window.location.href="https://www.google.com/aclk?sa=L&ai=DChsSEwjLnd7HieaTAxUPqf0FHVXtCDoYACICCAEQMhoCd2Y&co=1&gclid=CjwKCAjw4ufOBhBkEiwAfuC7-W2noUiIU2grMp4ZBydzVkYfDWyyUiVjELV2M8w36fIWuf5AmiZ_JhoCc6MQAvD_BwE&sph&cid=CAAS0wHkaHOUI0HRMru24r5slXVr6WW3V_D5-oURMvp9xGdAYaCH1bljBV7Q0QE_iej0Fx2c543WQh5ewzEuqgzWaE-y0s4LioBZDIQ1FW8nacCnxwXKf3iMrZFQTEJ-GvdJmKJMC0KVsm5s5wnSXB_CXXL9M5eXeqtQ3U-Bny4i7g8CsU7o4ZOYs8fRoHwqKL3Wx6dGTE5MZ-xydOf_ZpCxvEAlaiNq3hOO7ay2udvh7DV_ue-xuZCbKHdphsBihQ_4l1A3ltc9wbuza_Mx2uH_YU8d-A2C&cce=1&sig=AOD64_0OAAQkbrW2-W8uMF6XwdrWOm0IIA&q&adurl&ved=2ahUKEwjl3dnHieaTAxUWTaQEHdZIFPcQ0Qx6BAgMEAE";
    },1500);

  });
}
</script>

</body>
</html>
