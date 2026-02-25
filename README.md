<!DOCTYPE html>

<html lang="vi">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Ultra Welcome Screen -->

<div id="welcome-screen">

<canvas id="stars"></canvas>

<div class="welcome-content">

<h1 class="glow-text">Minamoto no Tora</h1>

<h2 class="kanji">源の虎</h2>

<p>

Khi cánh cửa ký ức mở ra,<br>

những vì sao của thanh xuân lại một lần nữa tỏa sáng.<br>

Chào mừng bạn đến với hành trình rực rỡ của chúng tôi.

</p>

<button onclick="enterSite()">Khởi Hành</button>

</div>

</div>

<style>

#welcome-screen{

position:fixed;

width:100%;

height:100vh;

background:radial-gradient(circle at center,#1a1a2e,#0f0c29,#000);

overflow:hidden;

display:flex;
justify-content:center;

align-items:center;

text-align:center;

color:white;

z-index:9999;

}

#welcome-screen canvas{

position:absolute;

top:0;

left:0;

width:100%;

height:100%;

}

.welcome-content{

position:relative;

z-index:2;

max-width:700px;

padding:40px;

}

.glow-text{

font-size:48px;

letter-spacing:5px;

animation:glow 2s ease-in-out infinite alternate;

}

.kanji{font-size:36px;

margin-bottom:20px;

opacity:0.8;

}

.welcome-content p{

line-height:1.8;

margin-bottom:30px;

font-size:18px;

opacity:0.9;

}

.welcome-content button{

padding:12px 40px;

border:none;

border-radius:30px;

background:linear-gradient(45deg,#ff6ec4,#7873f5);

color:white;

font-size:16px;

cursor:pointer;

transition:0.3s;

}

.welcome-content button:hover{

transform:scale(1.1);

}

@keyframes glow{

from{text-shadow:0 0 10px #fff,0 0 20px #ff6ec4;}
to{text-shadow:0 0 20px #fff,0 0 40px #7873f5;}

}

</style>

<script>

// Fade out

function enterSite(){

document.getElementById("welcome-screen").style.opacity="0";

setTimeout(()=>{

document.getElementById("welcome-screen").style.display="none";

},800);

}

// Star animation

const canvas=document.getElementById("stars");

const ctx=canvas.getContext("2d");

canvas.width=window.innerWidth;

canvas.height=window.innerHeight;

let stars=[];

for(let i=0;i<150;i++){

stars.push({

x:Math.random()*canvas.width,

y:Math.random()*canvas.height,

r:Math.random()*2,

d:Math.random()*1

});

}
function drawStars(){

ctx.clearRect(0,0,canvas.width,canvas.height);

ctx.fillStyle="white";

stars.forEach(s=>{

ctx.beginPath();

ctx.arc(s.x,s.y,s.r,0,Math.PI*2);

ctx.fill();

});

moveStars();

}

function moveStars(){

stars.forEach(s=>{

s.y+=s.d;

if(s.y>canvas.height){

s.y=0;

s.x=Math.random()*canvas.width;

}

});

}

setInterval(drawStars,30);

</script>

<style>

#welcome-screen{

position:fixed;

width:100%;

height:100vh;background:linear-gradient(135deg,#0f0c29,#302b63,#24243e);

display:flex; justify-content:center;

align-items:center;

text-align:center;

color:white;

z-index:9999;

animation:fadeIn 1.5s ease;

}

.welcome-content{

max-width:700px;

padding:40px;

}

.welcome-content h1{

font-size:42px;

margin-bottom:25px;

letter-spacing:4px;

text-shadow:0 0 15px rgba(255,255,255,0.6);

}

.welcome-content p{

font-size:18px;

line-height:1.8;

margin-bottom:30px;

opacity:0.9;

}

.welcome-content button{padding:12px 35px;

font-size:16px;

border:none;

border-radius:30px;

background:white;

color:#24243e;

cursor:pointer;

transition:0.3s;

}

.welcome-content button:hover{

transform:scale(1.1);

}

@keyframes fadeIn{

from{opacity:0;}

to{opacity:1;}

}

</style>

<script>

function enterSite(){

document.getElementById("welcome-screen").style.display="none";

}

</script>

<style>

*{

margin:0;padding:0;

box-sizing:border-box;

font-family: 'Segoe UI', Arial, sans-serif;

}

html{

scroll-behavior:smooth;

}

body{

background:#f1f5f9;

color:#0f172a;

line-height:1.6;

}

/* ===== BANNER ===== */

header{

position: relative;

text-align: center;

padding: 100px 20px;

color: white;

overflow: hidden;

background: #333; /* Màu nền dự phòng */

}

/* Lớp nền ảnh có thêm Overlay để nổi bật chữ */

header::before{

content: "";

position: absolute;inset: 0;

background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)),

url("https://i.ibb.co/TMtFcdHv/image.png") center/cover no-repeat;

filter: blur(1px);

z-index: 1;

}

/* Đưa nội dung lên trên lớp nền */

header .container {

position: relative;

z-index: 2;

}

header h1{

font-size: 40px;

margin-bottom: 10px;

text-shadow: 2px 2px 4px rgba(0,0,0,0.5);

}

header p{

font-size: 20px;

font-weight: 500;

text-shadow: 1px 1px 3px rgba(0,0,0,0.5);

}

nav{

margin-top:30px;
nav a{

display:inline-block;

color:white;

text-decoration:none;

padding:12px 25px;

margin:5px;

border-radius:30px;

transition:0.3s;

background:rgba(255,255,255,0.2);

backdrop-filter: blur(5px);

border: 1px solid rgba(255,255,255,0.3);

}

nav a:hover{

background:white;

color:#7c3aed;

}

/* ===== SECTION ===== */

section{

padding:40px 20px;

max-width:1100px;

margin:auto;

}

.card{

background:white;

padding:30px;

border-radius:18px;
}margin-bottom:30px;

box-shadow:0 10px 25px rgba(0,0,0,0.05);

transition:0.3s;

}

.card:hover{

transform:translateY(-5px);

}

h2{

color:#7c3aed;

margin-bottom:20px;

border-left: 5px solid #7c3aed;

padding-left: 15px;

}

/* ===== ACTIVITIES ===== */

.activities-menu{

display:grid;

grid-template-columns:repeat(auto-fit,minmax(200px,1fr));

gap:15px;

margin-bottom:25px;

}

.activity-btn{

background:linear-gradient(135deg,#6366f1,#a855f7);

border:none; padding:18px;

border-radius:15px;

color:white;font-size:17px;

font-weight: bold;

cursor:pointer;

transition:0.3s;

}

.activity-btn:hover, .activity-btn.active{

transform:scale(1.05);

box-shadow: 0 5px 15px rgba(124, 58, 237, 0.4);

filter: brightness(1.1);

}

.activity-content{

display:none;

animation:fade 0.6s ease-out;

}

@keyframes fade{

from{opacity:0; transform:translateY(15px);}

to{opacity:1; transform:translateY(0);}

}

/* ===== GALLERY ===== */

.gallery{

display:grid;

grid-template-columns:repeat(auto-fill,minmax(240px,1fr));

gap:15px;

margin-top:20px;

}.gallery img{

width:100%;

height:220px;

object-fit:cover;

border-radius:12px;

transition:0.4s;

cursor: pointer;

}

.gallery img:hover{

transform:scale(1.03);

}

/* ===== FOOTER ===== */

footer{

text-align:center;

padding:50px 20px;

background:#e2e8f0;

margin-top:60px;

border-top: 1px solid #cbd5e1;

}

.contact-info {

margin-bottom: 20px;

}

footer p {

color: #475569;font-size: 15px;

}

</style>

</head>

<body>

<header id="home">

<div class="container">

<h1>CLB Minamoto no Tora 源の虎</h1>

<p>12.9 – Trường THPT Huỳnh Văn Nghệ</p>

<p>"Thanh xuân là hành trình, không phải đích đến."</p>

<nav>

<a href="#home">Trang Chủ</a>

<a href="#activities">Hoạt Động</a>

<a href="#contact">Liên Hệ</a>

</nav>

</div>

</header>

<section>

<div class="card">

<h2>📌 Thông Tin Chuyến Đi</h2>

<p><b>Lớp:</b> 12.9</p>

<p><b>Câu lạc bộ:</b> Minamoto no Tora</p>

<p><b>Trường:</b> THPT Huỳnh Văn Nghệ</p>

<p><b>Thời gian:</b> 23 – 25 / 01 / 2026</p>

</div></section>

<section id="activities">

<h2>🔥 Hoạt Động Nổi Bật</h2>

<div class="activities-menu">

<button class="activity-btn" onclick="showContent('dalat', this)">Đà Lạt</button>

<button class="activity-btn" onclick="showContent('vannghe', this)">Văn Nghệ</button>

<button class="activity-btn" onclick="showContent('team', this)">Tri Ân</button>

</div>

<div id="dalat" class="activity-content card">

<h3>🌲 Tham Quan Đà Lạt</h3>

<p>Đà Lạt không chỉ là chuyến đi, mà là một phần ký ức thanh xuân.

Giữa cái se lạnh của cao nguyên, chúng mình đã cùng nhau cười thật to, chụp thật nhiều ảnh và lưu lại những khoảnh khắc chẳng thể quay lại lần thứ hai.

Thành phố mộng mơ ấy đã chứng kiến tuổi 17 của 12.9 – vô tư, rực rỡ và đầy yêu thương.</p>

<div class="gallery">

<img src="https://i.ibb.co/4R8Bddpw/image.png" alt="Đà Lạt 1">

<img src="https://i.ibb.co/rRZmXmx2/image.png" alt="Đà Lạt 2">

<img src="https://i.ibb.co/Zp6F7nr1/image.png" alt="Đà Lạt 3">

<img src="https://i.ibb.co/pB7pCz1J/image.png" alt="Đà Lạt 4">

</div>

</div><div id="vannghe" class="activity-content card">

<h3>🎤 Văn Nghệ</h3>

<p>Những tiết mục văn nghệ không chỉ là ánh đèn sân khấu, mà là nơi chúng mình cháy hết mình vì tập thể.

Từng bước nhảy, từng lời ca là cả những ngày tập luyện mồ hôi và tiếng cười.

Dưới ánh đèn ấy, 12.9 đã tỏa sáng theo cách rực rỡ nhất của tuổi trẻ</p>

<div class="gallery"><img src="https://i.ibb.co/5WZC2Dh5/image.png" alt="Văn nghệ 1">

<img src="https://i.ibb.co/607tq6xL/image.png" alt="Văn nghệ 2">

<img src="https://i.ibb.co/NQbGFjc/image.png" alt="Văn nghệ 3">

<img src="https://i.ibb.co/vvRqr5vH/image.png" alt="Văn nghệ 4">

</div>

</div>

<div id="team" class="activity-content card">

<h3>🌸 Lễ Tri Ân</h3>

<p>Chúng em xin gửi lời tri ân chân thành nhất đến thầy cô – những người đã âm thầm gieo mầm tri thức và thắp sáng ước mơ cho chúng em suốt ba năm qua.

Mỗi lời dạy, mỗi sự nghiêm khắc và yêu thương đều trở thành hành trang quý giá để chúng em bước vào tương lai.

Thanh xuân có thể khép lại, nhưng lòng biết ơn thì sẽ còn mãi.</p>

<div class="gallery">

<img src="https://i.ibb.co/HL1HFVf9/image.png" alt="Team 1">

<img src="https://i.ibb.co/Cp9N2rGP/image.png" alt="Team 2">

</div>

</div>

</section>

<section id="contact">

<div class="card">

<h2>📞 Liên Hệ</h2>

<div class="contact-info">

<p><b>Họ tên:</b> Lại Thị Thuý Hà – <b>STT:</b> 10 – <b>Lớp:</b> 12.9</p>

<p><b>Họ tên:</b> Nguyễn Duy Mạnh – <b>STT:</b> 20 – <b>Lớp:</b> 12.9</p>

<p><b>Họ tên:</b>Lê Thị Phương Nhi– <b>STT:</b> 27 – <b>Lớp:</b> 12.9</p>

<p><b>Họ tên:</b>Đỗ Thành Nhân– <b>STT:</b> 26 – <b>Lớp:</b> 12.9</p>
<p><b>Email:</b> thpthuynhvannghe@gmail.com</p>

</div>

</div>

</section>

<footer>

<h3>CLB Minamoto no Tora 源の虎 12.9</h3>

<p>Trường THPT Huỳnh Văn Nghệ</p>

<p>© 2026 - Kỷ yếu Đà Lạt</p>

</footer>

<script>

// Hàm hiển thị nội dung hoạt động

function showContent(id, btn){

// Ẩn tất cả nội dung

document.querySelectorAll('.activity-content').forEach(el=>{

el.style.display='none';

});

// Bỏ class active ở tất cả các nút

document.querySelectorAll('.activity-btn').forEach(b => {

b.classList.remove('active');

});

// Hiển thị nội dung được chọn

const box = document.getElementById(id);

box.style.display='block';

// Thêm class active cho nút vừa nhấnif(btn) btn.classList.add('active');

}

// Tự động hiển thị mục Đà Lạt khi vừa vào trang

window.onload = function() {

const firstBtn = document.querySelector('.activity-btn');

showContent('dalat', firstBtn);

};

</script>

<section class="thanks-section">

<div class="thanks-box">

<section class="thanks-section">

<div class="sparkle"></div>

<div class="thanks-box">

<h2 class="glow-title">✨ Lời cảm ơn</h2>

<p>

Ba năm thanh xuân khép lại bằng biết bao kỷ niệm rực rỡ.

Chúng em xin gửi lời tri ân sâu sắc đến thầy cô, gia đình và bạn bè

– những người đã luôn đồng hành, nâng đỡ và tiếp thêm sức mạnh

cho chúng em trên hành trình trưởng thành.

</p>

<p>

Đặc biệt, chuyến dã ngoại Đà Lạt đã trở thành dấu ấn đẹp nhất

của tuổi 18 – nơi tiếng cười, sự gắn kết và những khoảnh khắc

tuyệt vời sẽ mãi được lưu giữ trong tim.

</p>
<div class="signature">— Minamoto no Tora 源の虎 • 12.9 —</div>

</div>

</section>

<style>

.thanks-section{

position:relative;

padding:100px 20px;

display:flex;

justify-content:center;

align-items:center;

background:radial-gradient(circle at top,#1e3c72,#2a5298,#0f2027);

overflow:hidden;

}

.thanks-box{

position:relative;

max-width:850px;

background:rgba(255,255,255,0.08);

backdrop-filter:blur(20px);

padding:60px;

border-radius:30px;

color:white;

text-align:center;

box-shadow:0 0 40px rgba(255,255,255,0.15);

animation:fadeUp 1.5s ease;

border:1px solid rgba(255,255,255,0.2);

}
.glow-title{

font-size:40px;

margin-bottom:30px;

animation:glow 2s infinite alternate;

}

.thanks-box p{

font-size:19px;

line-height:1.9;

margin-bottom:25px;

opacity:0.95;

}

.signature{

margin-top:35px;

font-size:22px;

letter-spacing:3px;

font-weight:600;

opacity:0.9;

}

/* Glow animation */

@keyframes glow{

from{

text-shadow:0 0 10px #fff,0 0 20px #8ec5fc;

}

to{

text-shadow:0 0 20px #fff,0 0 40px #e0c3fc;}

}

/* Fade up */

@keyframes fadeUp{

from{

opacity:0;

transform:translateY(40px);

}

to{

opacity:1;

transform:translateY(0);

}

}

/* Sparkle animation */

.sparkle{

position:absolute;

width:100%;

height:100%;

background-image:radial-gradient(white 1px, transparent 1px);

background-size:50px 50px;

animation:moveStars 60s linear infinite;

opacity:0.2;

}

@keyframes moveStars{

from{background-position:0 0;}

to{background-position:1000px 1000px;}
}

</style>

</style>

</body>

</html>
