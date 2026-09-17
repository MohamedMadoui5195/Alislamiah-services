<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Alislamiah | الإسلامية</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:Tahoma, Arial, sans-serif;
    background:#061a3a;
    color:#fff;
    min-height:100vh;
}

/* ================= HEADER ================= */

header{
    height:75px;
    background:#04142e;
    border-bottom:1px solid rgba(255,255,255,.08);
    display:flex;
    align-items:center;
    justify-content:center;
    position:fixed;
    top:0;
    right:0;
    left:0;
    z-index:1000;
}

.logo{
    width:52px;
    height:52px;
    object-fit:contain;
    border-radius:14px;
}

/* زر القائمة */

.menu-btn{
    position:absolute;
    right:18px;
    width:45px;
    height:45px;
    border:none;
    border-radius:13px;
    background:#0b2a5b;
    color:white;
    font-size:25px;
    cursor:pointer;
}

.menu-btn:active{
    transform:scale(.96);
}

/* ================= SIDE MENU ================= */

.side-menu{
    position:fixed;
    top:0;
    right:-320px;
    width:300px;
    height:100vh;
    background:#04142e;
    z-index:2000;
    padding:25px 18px;
    overflow-y:auto;
    transition:right .3s ease;
    box-shadow:-8px 0 30px rgba(0,0,0,.35);
}

.side-menu.open{
    right:0;
}

.close-btn{
    width:42px;
    height:42px;
    border:none;
    border-radius:12px;
    background:#0b2a5b;
    color:white;
    font-size:24px;
    cursor:pointer;
    margin-bottom:25px;
}

.menu-title{
    font-size:21px;
    font-weight:bold;
    margin:15px 0;
    color:#fff;
}

.menu-section{
    margin-bottom:25px;
}

.menu-link{
    display:block;
    text-decoration:none;
    color:#dce9ff;
    background:#081f43;
    border:1px solid rgba(255,255,255,.06);
    padding:14px 15px;
    border-radius:12px;
    margin:8px 0;
    transition:.2s;
}

.menu-link:hover{
    background:#0b2a5b;
}

/* ================= OVERLAY ================= */

.overlay{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.55);
    z-index:1500;
    display:none;
}

.overlay.show{
    display:block;
}

/* ================= MAIN ================= */

main{
    padding-top:75px;
}

/* ================= HERO ================= */

.hero{
    min-height:calc(100vh - 75px);
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    padding:45px 22px;
    background:
        radial-gradient(circle at top, #0b2a5b 0%, #061a3a 42%, #030d1f 100%);
}

.hero-logo{
    width:105px;
    height:105px;
    object-fit:contain;
    margin-bottom:25px;
    filter:drop-shadow(0 8px 25px rgba(0,0,0,.4));
}

.hero h1{
    font-size:42px;
    margin-bottom:12px;
}

.hero h1 span{
    color:#5fa8ff;
}

.hero-subtitle{
    color:#b9c9df;
    font-size:18px;
    max-width:650px;
    line-height:1.9;
}

/* ================= ABOUT ================= */

.about{
    padding:75px 20px;
    max-width:1050px;
    margin:auto;
}

.section-title{
    text-align:center;
    font-size:30px;
    margin-bottom:35px;
}

.section-title span{
    color:#5fa8ff;
}

.about-card{
    background:#071d3f;
    border:1px solid rgba(255,255,255,.07);
    border-radius:22px;
    padding:30px;
    line-height:2;
    box-shadow:0 12px 35px rgba(0,0,0,.2);
}

.about-card p{
    color:#d6e2f2;
    font-size:17px;
}

/* ================= SERVICES ================= */

.services{
    padding:25px 20px 80px;
    max-width:1050px;
    margin:auto;
}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
    gap:18px;
}

.card{
    background:#071d3f;
    border:1px solid rgba(255,255,255,.07);
    border-radius:20px;
    padding:25px;
}

.card-icon{
    font-size:34px;
    margin-bottom:15px;
}

.card h3{
    margin-bottom:10px;
}

.card p{
    color:#b8c9df;
    line-height:1.8;
}

/* ================= BUTTON ================= */

/*
   الزر يظهر بعد 5 ثوانٍ.
   مكانه أسفل الشاشة ولكن فوق المحتوى
   ولا يتداخل مع القائمة الجانبية.
*/

.goto-button{
    position:fixed;
    bottom:20px;
    right:20px;
    z-index:900;

    background:#0b4f9c;
    color:#fff;
    text-decoration:none;

    padding:15px 22px;
    border-radius:15px;

    font-weight:bold;
    box-shadow:0 8px 25px rgba(0,0,0,.35);

    opacity:0;
    visibility:hidden;
    pointer-events:none;

    transition:opacity .4s ease;
}

.goto-button.show{
    opacity:1;
    visibility:visible;
    pointer-events:auto;
}

/* عندما تكون القائمة مفتوحة، الزر يدخل تحتها */

.side-menu.open ~ .goto-button{
    z-index:1400;
}

/* ================= FOOTER ================= */

footer{
    text-align:center;
    padding:30px 20px;
    background:#030d1f;
    color:#8fa4c0;
    line-height:1.8;
}

/* ================= MOBILE ================= */

@media(max-width:600px){

    .hero h1{
        font-size:32px;
    }

    .hero-subtitle{
        font-size:16px;
    }

    .side-menu{
        width:285px;
    }

    .goto-button{
        right:15px;
        left:15px;
        text-align:center;
        bottom:15px;
    }

    .about-card{
        padding:22px;
    }
}
</style>
</head>

<body>

<!-- ================= HEADER ================= -->

<header>

    <button class="menu-btn" onclick="openMenu()" aria-label="فتح القائمة">
        ☰
    </button>

    <img src="icon.png" class="logo" alt="Alislamiah">

</header>


<!-- ================= SIDE MENU ================= -->

<div class="overlay" id="overlay" onclick="closeMenu()"></div>

<aside class="side-menu" id="sideMenu">

    <button class="close-btn" onclick="closeMenu()" aria-label="إغلاق">
        ×
    </button>

    <!-- المنصات -->

    <div class="menu-section">

        <div class="menu-title">منصاتنا</div>

        <a class="menu-link"
           href="https://youtube.com/@alislamiah5195?si=Xu0kvsc6jQliUWbc"
           target="_blank">
           ▶️ يوتيوب
        </a>

        <a class="menu-link"
           href="https://tiktok.com/@alislamiah5195"
           target="_blank">
           🎵 تيك توك
        </a>

        <a class="menu-link"
           href="https://www.instagram.com/alislamiahbusines?stkn=MWpiM2xwYW10b3Qybg=="
           target="_blank">
           📷 أنستاغرام
        </a>

        <a class="menu-link"
           href="https://www.facebook.com/share/1GfWQLXq5o/"
           target="_blank">
           📘 فايسبوك
        </a>

    </div>


    <!-- الخدمات -->

    <div class="menu-section">

        <div class="menu-title">خدماتنا</div>

        <a class="menu-link"
           href="https://mohamedmadoui5195.github.io/Alislamiah-AI/ads.html">
           📢 حجز إعلانك
        </a>

        <a class="menu-link"
           href="https://mohamedmadoui5195.github.io/Alislamiah-search-console/">
           🔎 طلب فهرسة موقعك
        </a>

        <a class="menu-link"
           href="https://mohamedmadoui5195.github.io/Alislamiah-_net/">
           📚 المنصة التعليمية
        </a>

        <a class="menu-link"
           href="https://mohamedmadoui5195.github.io/Alislamiah-_net/comunucation.html">
           💬 تواصل معنا
        </a>

    </div>

</aside>


<!-- ================= MAIN ================= -->

<main>

    <!-- HERO -->

    <section class="hero">

        <img src="icon.png"
             class="hero-logo"
             alt="Alislamiah Logo">

        <h1>
            مرحباً بك في
            <span>Alislamiah</span>
        </h1>

        <p class="hero-subtitle">
            شبكة رقمية متكاملة تقدم خدمات ومنصات رقمية متنوعة
            تجمع بين التعليم، التقنية، والمحتوى الهادف.
        </p>

    </section>


    <!-- ABOUT -->

    <section class="about">

        <h2 class="section-title">
            عن <span>Alislamiah</span>
        </h2>

        <div class="about-card">

            <p>
                الإسلامية هي شبكة رقمية توفر خدمات متعددة،
                منها منصة تعليمية متكاملة ومتصفح آمن خالٍ من الإباحات،
                بالإضافة إلى مجموعة من المنصات والخدمات الرقمية
                التي تهدف إلى توفير تجربة تقنية آمنة ومفيدة للمستخدمين.
            </p>

        </div>

    </section>


    <!-- SERVICES -->

    <section class="services">

        <h2 class="section-title">
            ماذا تقدم <span>الإسلامية؟</span>
        </h2>

        <div class="cards">

            <div class="card">
                <div class="card-icon">📚</div>
                <h3>منصة تعليمية</h3>
                <p>
                    منصة تعليمية متكاملة للوصول إلى المحتوى
                    التعليمي والدروس بطريقة سهلة.
                </p>
            </div>

            <div class="card">
                <div class="card-icon">🌐</div>
                <h3>تجربة تصفح آمنة</h3>
                <p>
                    متصفح آمن يركز على توفير تجربة تصفح
                    خالية من المحتوى الإباحي.
                </p>
            </div>

            <div class="card">
                <div class="card-icon">🔎</div>
                <h3>خدمات رقمية</h3>
                <p>
                    مجموعة من الخدمات الرقمية مثل فهرسة المواقع
                    والإعلانات والتواصل.
                </p>
            </div>

        </div>

    </section>

</main>


<!-- ================= GOTO BUTTON ================= -->

<a href="https://mohamedmadoui5195.github.io/Alislamiah-_net/"
   class="goto-button"
   id="gotoButton">
   الانتقال إلى Alislamiah
</a>


<!-- ================= FOOTER ================= -->

<footer>

    © Alislamiah
    <br>
    الإسلامية دائماً الأفضل

</footer>


<script>

/* فتح القائمة */

function openMenu(){

    document.getElementById("sideMenu").classList.add("open");

    document.getElementById("overlay").classList.add("show");

}


/* إغلاق القائمة */

function closeMenu(){

    document.getElementById("sideMenu").classList.remove("open");

    document.getElementById("overlay").classList.remove("show");

}


/* إظهار زر الانتقال بعد 5 ثوانٍ */

setTimeout(function(){

    document.getElementById("gotoButton").classList.add("show");

},5000);

</script>

</body>
</html>

بعد وضع الكود، ضع "icon.png" في نفس مجلد ملف HTML حتى يظهر اللوجو بشكل صحيح.