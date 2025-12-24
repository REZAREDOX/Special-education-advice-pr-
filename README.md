<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>کاتالوگ هوشمند خدمات مشاوره</title>

    <!-- Tailwind -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- فونت وزیر -->
    <link href="https://cdn.jsdelivr.net/gh/rastikerdar/vazirmatn@v33.003/dist/font-face.css" rel="stylesheet"/>

    <style>
        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: #0f172a;
            margin: 0;
            scroll-behavior: smooth;
            color: white;
        }

        .text-gold {
            background: linear-gradient(to bottom, #fde68a, #d4af37, #b45309);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(4, 47, 36, 0.9);
            backdrop-filter: blur(10px);
            z-index: 2000;
            border-bottom: 1px solid rgba(212, 175, 55, 0.3);
            display: none;
        }

        .nav-link {
            padding: 15px 10px;
            font-size: 0.9rem;
            color: #fef3c7;
            cursor: pointer;
        }

        .nav-link:hover {
            color: #fbbf24;
        }

        #intro-screen {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle, #065f46 0%, #042f24 100%);
            position: fixed;
            width: 100%;
            z-index: 3000;
            transition: transform 0.8s ease-in-out;
        }

        .hidden-intro {
            transform: translateY(-100%);
        }

        .enter-btn {
            background: linear-gradient(135deg, #fde68a, #d4af37);
            color: #042f24;
            padding: 18px 45px;
            border-radius: 50px;
            font-weight: 900;
            font-size: 1.3rem;
            border: none;
            cursor: pointer;
        }

        .page {
            max-width: 900px;
            min-height: 85vh;
            margin: 80px auto;
            padding: 60px;
            border-radius: 20px;
            background: radial-gradient(circle, #065f46 0%, #042f24 100%);
            opacity: 0;
            transform: translateY(40px);
            transition: 0.8s;
        }

        .page.active {
            opacity: 1;
            transform: translateY(0);
        }

        .title-gold {
            font-size: 2.5rem;
            font-weight: 900;
            border-right: 8px solid #d4af37;
            padding-right: 20px;
            margin-bottom: 30px;
        }

        .content-list li {
            margin-bottom: 14px;
            font-size: 1.1rem;
            display: flex;
            color: #fef3c7;
        }

        .gold-dot {
            color: #d4af37;
            margin-left: 12px;
        }
    </style>
</head>

<body>

<div id="intro-screen">
    <h1 class="text-5xl md:text-7xl font-black text-gold mb-6 text-center">
        مشاوره تخصصی تحصیلی
    </h1>
    <p class="text-xl opacity-70 mb-10">مدیریت هوشمند مسیر موفقیت</p>
    <button class="enter-btn" onclick="startExperience()">ورود به نسخه دیجیتال</button>
</div>

<nav id="main-nav">
    <div class="flex justify-center overflow-x-auto">
        <span class="nav-link" onclick="scrollToSection('sec1')">ارزیابی</span>
        <span class="nav-link" onclick="scrollToSection('sec2')">سنجش‌ها</span>
        <span class="nav-link" onclick="scrollToSection('sec3')">برنامه‌ریزی</span>
        <span class="nav-link" onclick="scrollToSection('sec4')">پشتیبانی</span>
        <span class="nav-link" onclick="scrollToSection('sec5')">مهارت‌ها</span>
        <span class="nav-link" onclick="scrollToSection('sec6')">روانشناسی</span>
        <span class="nav-link" onclick="scrollToSection('sec7')">انتخاب رشته</span>
    </div>
</nav>

<main id="catalog" style="display:none;" class="pt-20">

<section id="sec1" class="page">
    <h2 class="title-gold text-gold">مصاحبه و ارزیابی</h2>
    <ul class="content-list">
        <li><span class="gold-dot">●</span> مصاحبه تشخیصی و روان‌سنجی</li>
        <li><span class="gold-dot">●</span> شناسایی وضعیت تحصیلی و شخصیتی</li>
        <li><span class="gold-dot">●</span> تعیین اهداف کوتاه و بلندمدت</li>
    </ul>
</section>

<section id="sec2" class="page">
    <h2 class="title-gold text-gold">آزمون‌ها و سنجش‌ها</h2>
    <ul class="content-list">
        <li><span class="gold-dot">●</span> آزمون سبک یادگیری</li>
        <li><span class="gold-dot">●</span> رغبت‌سنج شغلی</li>
        <li><span class="gold-dot">●</span> آزمون شخصیت</li>
    </ul>
</section>

<section id="sec3" class="page">
    <h2 class="title-gold text-gold">برنامه‌ریزی تحصیلی</h2>
    <ul class="content-list">
        <li><span class="gold-dot">●</span> برنامه شخصی‌سازی‌شده</li>
        <li><span class="gold-dot">●</span> مدیریت زمان و انرژی</li>
    </ul>
</section>

</main>

<script>
function startExperience() {
    document.getElementById('intro-screen').classList.add('hidden-intro');
    document.getElementById('main-nav').style.display = 'block';
    document.getElementById('catalog').style.display = 'block';

    setTimeout(observePages, 800);
}

function scrollToSection(id) {
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}

function observePages() {
    const observer = new IntersectionObserver(entries => {
        entries.forEach(e => e.isIntersecting && e.target.classList.add('active'));
    }, { threshold: 0.2 });

    document.querySelectorAll('.page').forEach(p => observer.observe(p));
}
</script>

</body>
</html>