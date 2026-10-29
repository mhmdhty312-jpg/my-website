<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>mlk♕alhm - تطبيق ملك الهم الرسمي</title>
    <meta name="description" content="موقع وتطبيق ملك الهم mlk♕alhm يضم إطار متوهج، ألعاب، الآلة الحاسبة السرية، وتطبيقات مميزة.">
    <meta name="keywords" content="mlk♕alhm, ملك الهم, تطبيق ملك الهم, فري فاير">
    <!-- استدعاء مكتبة تأثير التفتيت -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.7)), 
                        url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e') no-repeat center center fixed;
            background-size: cover;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            color: white;
            padding: 15px;
            text-align: center;
            overflow: hidden;
        }

        /* القائمة العلوية */
        .top-nav {
            display: flex;
            gap: 40px;
            font-size: 16px;
            margin-top: 5px;
            z-index: 10;
        }

        .top-nav span {
            opacity: 0.6;
            cursor: pointer;
            transition: opacity 0.3s;
        }

        .top-nav span.active {
            opacity: 1;
            font-weight: bold;
            border-bottom: 2px solid white;
            padding-bottom: 4px;
        }

        /* حاوية الشاشات */
        .tab-content {
            display: none;
            width: 100%;
            height: calc(100vh - 60px);
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            animation: fadeIn 0.4s ease-in-out;
        }

        .tab-content.active {
            display: flex;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.98); }
            to { opacity: 1; transform: scale(1); }
        }

        /* --- محتوى تبويب "اكتشاف" --- */
        .discovery-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex: 1;
            width: 100%;
        }

        /* === حاوية المربع الذي يدور حوله اللون المتوهج === */
        .glow-border-box {
            position: relative;
            width: 280px;
            padding: 3px; /* سمك الإطار المتوهج */
            border-radius: 18px;
            overflow: hidden;
            cursor: pointer;
            margin-bottom: 20px;
            transition: transform 0.3s, opacity 0.3s;
        }

        /* الطبقة الدوارة التي تصنع التوهج المتحرك حول النص */
        .glow-border-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, #00ffcc, #ff00ff, #00ffcc, transparent 40%);
            animation: rotateGlow 1s linear infinite;
        }

        @keyframes rotateGlow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* محتوى المربع الداخلي الثابت (النص) */
        .glow-content {
            position: relative;
            background: rgba(15, 15, 15, 0.95);
            padding: 15px 20px;
            border-radius: 16px;
            font-size: 15px;
            font-weight: bold;
            color: #00ffcc;
            z-index: 1;
            text-align: center;
        }

        /* تأثير التفتيت والاختفاء عند الضغط */
        .glow-border-box.shattering {
            animation: shatterEffect 0.6s forwards !important;
            pointer-events: none;
        }

        @keyframes shatterEffect {
            0% { transform: scale(1) rotate(0deg); opacity: 1; filter: blur(0); }
            50% { transform: scale(1.4) rotate(45deg) skew(15deg, 15deg); opacity: 0.5; filter: blur(2px); }
            100% { transform: scale(0) rotate(180deg) translate(40px, -40px); opacity: 0; filter: blur(8px); }
        }

        .phone-mockup {
            background-color: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            width: 220px;
            height: 240px;
            border-radius: 30px;
            position: relative;
            margin: 5px auto;
            display: flex;
            justify-content: center;
            align-items: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .floating-icon {
            position: absolute;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 16px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        .icon-1 { background-color: #ff5252; top: -15px; right: 40px; }
        .icon-2 { background-color: #ff5252; bottom: 20px; right: 20px; }
        .icon-3 { background-color: #2979ff; bottom: 40px; left: 30px; }
        .icon-4 { background-color: #4caf50; top: 30px; left: 20px; }

        .content h1 {
            font-size: 22px;
            margin-bottom: 6px;
            font-weight: 700;
        }

        .content p {
            font-size: 12px;
            opacity: 0.9;
            max-width: 280px;
            margin: 0 auto 8px auto;
            line-height: 1.3;
        }

        .terms {
            font-size: 10px;
            opacity: 0.7;
            margin-bottom: 10px;
        }

        .terms a {
            color: white;
            text-decoration: underline;
        }

        /* --- محتوى تبويب "شخصي" --- */
        .personal-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            flex: 1;
            width: 100%;
            padding-top: 10px;
        }

        .apps-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 12px 8px;
            width: 100%;
            max-width: 380px;
            margin: auto 0;
            padding: 0 5px;
        }

        .app-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .app-item:hover {
            transform: scale(1.08);
        }

        .app-icon {
            width: 50px;
            height: 50px;
            border-radius: 14px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 22px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            margin-bottom: 4px;
            position: relative;
        }

        .app-name {
            font-size: 10px;
            opacity: 0.9;
            text-align: center;
            max-width: 55px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        /* الأيقونات والتصميمات */
        .app-galaxy { background: linear-gradient(135deg, #a18cd1, #fbc2eb); }
        .app-meta { background: linear-gradient(135deg, #667eea, #764ba2); }
        .app-vpn { background: linear-gradient(135deg, #00c6ff, #0072ff); }
        .app-happy { background: linear-gradient(135deg, #84fab0, #8fd3f4); color: #000; }
        .app-gaming { background: linear-gradient(135deg, #fa709a, #fee140); }
        .app-msg1 { background: #0084ff; }
        .app-radio { background: #e0e0e0; color: #333; }
        .app-calc { background: linear-gradient(135deg, #11998e, #38ef7d); cursor: pointer; }
        .app-studio { background: linear-gradient(135deg, #ff9a9e, #fecfef); }
        .app-xender { background: linear-gradient(135deg, #ff758c, #ff7eb3); }
        .app-keyboard { background: #1b5e20; }
        .app-phone { background: #00e676; }
        .app-camera { background: #424242; }
        .app-settings { background: #616161; }
        .app-msg2 { background: #2979ff; }
        .app-capcut { background: #000; border: 1px solid rgba(255,255,255,0.3); }
        .app-tiktok { background: #111; position: relative; }
        .app-tiktok::after {
            content: '99';
            position: absolute;
            top: -4px;
            right: -4px;
            background: #ff3b30;
            color: white;
            font-size: 9px;
            padding: 1px 4px;
            border-radius: 8px;
        }
        .app-files { background: linear-gradient(135deg, #f6d365, #fda085); }
        .app-music { background: linear-gradient(135deg, #ff9966, #ff5e62); cursor: pointer; }

        /* شريط البحث السفلي */
        .search-bar {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            width: 100%;
            max-width: 360px;
            padding: 12px 20px;
            border-radius: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            border: 1px solid rgba(255, 255, 255, 0.25);
        }

        .search-bar span {
            font-size: 13px;
            opacity: 0.8;
        }

        .btn-container {
            width: 100%;
            max-width: 380px;
            margin-bottom: 10px;
        }

        .main-btn {
            background: linear-gradient(135deg, #007aff, #00c6ff);
            color: white;
            border: none;
            width: 100%;
            padding: 14px;
            border-radius: 30px;
            font-size: 15px;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 122, 255, 0.4);
        }

        /* --- نافذة الآلة الحاسبة --- */
        #calculator-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 100;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }

        .calc-box {
            background: #1e1e1e;
            width: 300px;
            border-radius: 20px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.8);
            border: 1px solid #333;
        }

        .calc-screen {
            width: 100%;
            height: 60px;
            background: #111;
            color: #fff;
            font-size: 26px;
            text-align: left;
            padding: 10px 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            overflow-x: auto;
            border: 1px solid #444;
        }

        .calc-buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .calc-btn {
            background: #333;
            color: white;
            border: none;
            padding: 15px;
            font-size: 18px;
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.2s;
        }

        .calc-btn:hover { background: #444; }
        .calc-btn.op { background: #ff9500; }
        .calc-btn.op:hover { background: #e08500; }
        .calc-btn.action { background: #a6a6a6; color: black; }
        .calc-btn.action:hover { background: #888; }
        .calc-btn.vault-trigger { background: #11998e; grid-column: span 2; font-size: 14px; font-weight: bold; }

        /* --- نافذة بصمة الجهاز --- */
        #vault-login-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            z-index: 150;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }

        .vault-login-box {
            background: #222;
            width: 320px;
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.8);
            border: 1px solid #444;
            text-align: center;
        }

        .vault-login-box h3 {
            color: #38ef7d;
            margin-bottom: 10px;
            font-size: 18px;
        }

        .vault-login-box p {
            font-size: 12px;
            color: #ccc;
            margin-bottom: 20px;
        }

        .fingerprint-scanner {
            margin: 15px auto;
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: rgba(56, 239, 125, 0.15);
            border: 2px solid #38ef7d;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 32px;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(56, 239, 125, 0.3);
            transition: transform 0.2s;
        }

        .fingerprint-scanner:hover {
            transform: scale(1.08);
        }

        .vault-btn-group {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

        .vault-action-btn {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
            font-size: 14px;
        }

        .btn-cancel { background: #ff3b30; color: white; }

        /* --- واجهة الخزنة --- */
        #secret-vault-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            z-index: 200;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            padding: 20px;
            overflow-y: auto;
            animation: fadeIn 0.4s ease;
        }

        .vault-box {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            width: 100%;
            max-width: 380px;
            border-radius: 20px;
            padding: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.5);
            backdrop-filter: blur(10px);
            text-align: center;
            margin-top: 10px;
        }

        .vault-box h2 {
            color: #00ffcc;
            font-size: 20px;
            margin-bottom: 5px;
        }

        .vault-section {
            margin-top: 15px;
            text-align: right;
            background: rgba(0,0,0,0.2);
            padding: 12px;
            border-radius: 12px;
        }

        .vault-section h4 {
            color: #ffcc00;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .vault-input-small {
            width: 100%;
            padding: 8px;
            font-size: 13px;
            background: rgba(0,0,0,0.4);
            color: white;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 8px;
            margin-bottom: 8px;
        }

        .vault-add-btn {
            background: #00ffcc;
            color: black;
            border: none;
            padding: 6px 12px;
            border-radius: 8px;
            font-weight: bold;
            font-size: 12px;
            cursor: pointer;
            width: 100%;
        }

        .hidden-list {
            max-height: 100px;
            overflow-y: auto;
            margin-top: 8px;
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .hidden-item {
            background: rgba(255,255,255,0.1);
            padding: 5px 10px;
            border-radius: 6px;
            font-size: 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .delete-item {
            color: #ff3b30;
            cursor: pointer;
            font-weight: bold;
        }

        .hidden-images-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 6px;
            margin-top: 8px;
            max-height: 120px;
            overflow-y: auto;
        }

        .hidden-img-card {
            position: relative;
            width: 100%;
            height: 60px;
            border-radius: 6px;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.3);
        }

        .hidden-img-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .close-vault-btn {
            background: #ff3b30;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 15px;
            width: 100%;
        }

        /* --- نافذة مشغل الموسيقى --- */
        #music-player-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(15px);
            z-index: 100;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .music-box {
            background: rgba(255, 255, 255, 0.12);
            border: 1px solid rgba(255, 255, 255, 0.3);
            width: 100%;
            max-width: 360px;
            border-radius: 25px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.6);
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .music-box h2 {
            font-size: 20px;
            margin-bottom: 5px;
            color: #ffcc00;
        }

        .bot-subtitle {
            font-size: 12px;
            opacity: 0.8;
            margin-bottom: 15px;
        }

        .playlist {
            width: 100%;
            max-height: 230px;
            overflow-y: auto;
            margin-bottom: 15px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .song-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 12px 15px;
            border-radius: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: all 0.2s;
            border: 1px solid transparent;
        }

        .song-item:hover, .song-item.playing {
            background: rgba(255, 140, 0, 0.3);
            border-color: #ff8c00;
        }

        .song-info {
            text-align: right;
        }

        .song-title {
            font-size: 14px;
            font-weight: bold;
        }

        .song-artist {
            font-size: 11px;
            color: #00ffcc;
        }

        .close-music-btn {
            background: linear-gradient(135deg, #ff416c, #ff4b2b);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
            width: 100%;
        }
    </style>
</head>
<body>

    <!-- القائمة العلوية -->
    <div class="top-nav">
        <span id="nav-personal" onclick="switchTab('personal')">شخصي</span>
        <span id="nav-discovery" class="active" onclick="switchTab('discovery')">اكتشاف</span>
    </div>

    <!-- تبويب اكتشاف -->
    <div id="tab-discovery" class="tab-content active">
        <div class="discovery-container">
            
            <!-- مربع النص المحاط بإطار متوهج يدور حول نفسه كل ثانية -->
            <div id="shatterBox" class="glow-border-box" onclick="shatterAndExplode(event)">
                <div class="glow-content">
                    ✨ الإطار المتوهج يدور، والنص ثابت! ✨
                </div>
            </div>

            <div class="phone-mockup">
                <div class="floating-icon icon-1">🛍️</div>
                <div class="floating-icon icon-2">📷</div>
                <div class="floating-icon icon-3">✈️</div>
                <div class="floating-icon icon-4">👤</div>
            </div>

            <div class="content">
                <h1>مرحباً بك في التطبيق</h1>
                <p>احصل على التطبيقات التي تتوافق مع اهتماماتك واحتياجاتك بسهولة.</p>
                <div class="terms">
                    للمتابعة، اقرأ <a href="#">بنود وشروط</a> ووافق عليها.
                </div>
            </div>
        </div>

        <div class="btn-container">
            <button class="main-btn" onclick="switchTab('personal')">أوافق (عرض شخصي)</button>
        </div>
    </div>

    <!-- تبويب شخصي -->
    <div id="tab-personal" class="tab-content">
        <div class="personal-container">
            <div class="apps-grid">
                <div class="app-item"><div class="app-icon app-galaxy">🌌</div><span class="app-name">My Galaxy</span></div>
                <div class="app-item"><div class="app-icon app-meta">🟣</div><span class="app-name">Meta AI</span></div>
                <div class="app-item"><div class="app-icon app-vpn">🌐</div><span class="app-name">Max VPN</span></div>
                <div class="app-item"><div class="app-icon app-happy">👾</div><span class="app-name">HappyMod</span></div>
                <div class="app-item"><div class="app-icon app-gaming">🎮</div><span class="app-name">Gaming Hub</span></div>

                <div class="app-item"><div class="app-icon app-msg1">💬</div><span class="app-name">الرسائل</span></div>
                <div class="app-item"><div class="app-icon app-radio">📻</div><span class="app-name">الراديو</span></div>
                <div class="app-item" onclick="openCalculator()"><div class="app-icon app-calc">🔢</div><span class="app-name">الحاسبة</span></div>
                <div class="app-item"><div class="app-icon app-studio">🌸</div><span class="app-name">الاستوديو</span></div>
                <div class="app-item"><div class="app-icon app-xender">✖️</div><span class="app-name">Xender</span></div>

                <div class="app-item"><div class="app-icon app-keyboard">⌨️</div><span class="app-name">لوحة المفاتيح</span></div>
                <div class="app-item"><div class="app-icon app-phone">📞</div><span class="app-name">الهاتف</span></div>
                <div class="app-item"><div class="app-icon app-camera">📷</div><span class="app-name">الكاميرا</span></div>
                <div class="app-item"><div class="app-icon app-settings">⚙️</div><span class="app-name">الضبط</span></div>
                <div class="app-item"><div class="app-icon app-msg2">🔵</div><span class="app-name">الرسائل</span></div>

                <div class="app-item"><div class="app-icon app-capcut">✂️</div><span class="app-name">CapCut</span></div>
                <div class="app-item"><div class="app-icon app-tiktok">🎵</div><span class="app-name">TikTok</span></div>
                <div class="app-item"><div class="app-icon app-files">📁</div><span class="app-name">ملفاتي</span></div>
                <div class="app-item" onclick="openMusicPlayer()"><div class="app-icon app-music">🎶</div><span class="app-name">مشغل الموسيقى</span></div>
            </div>
        </div>

        <div class="search-bar">
            <span>بحث...</span>
            <span>⋮</span>
        </div>
    </div>

    <!-- نافذة الآلة الحاسبة -->
    <div id="calculator-modal">
        <div class="calc-box">
            <div id="calc-display" class="calc-screen">0</div>
            <div class="calc-buttons">
                <button class="calc-btn action" onclick="clearCalc()">C</button>
                <button class="calc-btn action" onclick="appendCalc('%')">%</button>
                <button class="calc-btn op" onclick="appendCalc('/')">/</button>
                <button class="calc-btn op" onclick="appendCalc('*')">×</button>
                
                <button class="calc-btn" onclick="appendCalc('7')">7</button>
                <button class="calc-btn" onclick="appendCalc('8')">8</button>
                <button class="calc-btn" onclick="appendCalc('9')">9</button>
                <button class="calc-btn op" onclick="appendCalc('-')">-</button>
                
                <button class="calc-btn" onclick="appendCalc('4')">4</button>
                <button class="calc-btn" onclick="appendCalc('5')">5</button>
                <button class="calc-btn" onclick="appendCalc('6')">6</button>
                <button class="calc-btn op" onclick="appendCalc('+')">+</button>
                
                <button class="calc-btn" onclick="appendCalc('1')">1</button>
                <button class="calc-btn" onclick="appendCalc('2')">2</button>
                <button class="calc-btn" onclick="appendCalc('3')">3</button>
                <button class="calc-btn op" onclick="calculateResult()">=</button>
                
                <button class="calc-btn" onclick="appendCalc('0')">0</button>
                <button class="calc-btn" onclick="appendCalc('.')">.</button>
                <button class="calc-btn vault-trigger" onclick="openVaultLogin()">🔒 الخزنة</button>
                
                <button class="calc-btn action" onclick="closeCalculator()" style="grid-column: span 4; background:#ff3b30; color:white; margin-top:5px;">إغلاق الحاسبة</button>
            </div>
        </div>
    </div>

    <!-- نافذة بصمة الجهاز -->
    <div id="vault-login-modal">
        <div class="vault-login-box">
            <h3>🔐 قفل بصمة الجهاز</h3>
            <p>انقر أدناه لمسح بصمة الإصبع</p>
            <div class="fingerprint-scanner" onclick="authenticateDeviceFingerprint()">👆</div>
            <div class="vault-btn-group">
                <button class="vault-action-btn btn-cancel" onclick="closeVaultLogin()">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- واجهة الخزنة -->
    <div id="secret-vault-modal">
        <div class="vault-box">
            <h2>🛡️ خزنة ملك الهم الآمنة</h2>
            <p style="font-size: 11px; opacity: 0.8; margin-bottom: 10px;">تم التحقق من بصمتك بنجاح</p>

            <div class="vault-section">
                <h4>📱 التطبيقات المخفية</h4>
                <input type="text" id="app-name-input" class="vault-input-small" placeholder="اسم التطبيق...">
                <button class="vault-add-btn" onclick="hideApp()">إخفاء تطبيق</button>
                <div id="hidden-apps-list" class="hidden-list"></div>
            </div>

            <div class="vault-section">
                <h4>🖼️ الصور المخفية</h4>
                <input type="text" id="img-url-input" class="vault-input-small" placeholder="رابط الصورة...">
                <button class="vault-add-btn" onclick="hideImage()">إخفاء صورة</button>
                <div id="hidden-images-list" class="hidden-images-grid"></div>
            </div>

            <button class="close-vault-btn" onclick="closeVault()">قفل الخزنة</button>
        </div>
    </div>

    <!-- مشغل الموسيقى -->
    <div id="music-player-modal">
        <div class="music-box">
            <h2>👑 ملك الهم البوت</h2>
            <div class="bot-subtitle">أغاني ملك الهم وحماس فري فاير</div>
            <div class="playlist">
                <div class="song-item" onclick="playSong('أغنية ملك الهم الأسطوري', 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3', this)">
                    <div class="song-info">
                        <div class="song-title">👑 ملك الهم الأسطوري</div>
                        <div class="song-artist">ملك الهم البوت</div>
                    </div>
                    <span>▶️</span>
                </div>
            </div>
            <button class="close-music-btn" onclick="closeMusicPlayer()" style="background:#ff5e62;">إغلاق المشغل</button>
        </div>
    </div>

    <audio id="audio-player"></audio>

    <script>
        function switchTab(tabName) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.top-nav span').forEach(el => el.classList.remove('active'));

            if (tabName === 'personal') {
                document.getElementById('tab-personal').classList.add('active');
                document.getElementById('nav-personal').classList.add('active');
            } else {
                document.getElementById('tab-discovery').classList.add('active');
                document.getElementById('nav-discovery').classList.add('active');
            }
        }

        /* دالة تفتيت المربع وتوليد تأثير الأجزاء المتناثرة عند الضغط */
        function shatterAndExplode(event) {
            const box = document.getElementById('shatterBox');
            box.classList.add('shattering');

            // إطلاق تأثير تكسير وانفجار الأجزاء
            confetti({
                particleCount: 80,
                spread: 70,
                origin: { y: 0.3 }
            });

            // إخفاء العنصر نهائياً بعد انتهاء مدة التفتيت
            setTimeout(() => {
                box.style.display = 'none';
            }, 600);
        }

        /* دوال الآلة الحاسبة والخزنة والبصمة */
        let calcDisplay = document.getElementById('calc-display');
        let currentInput = "0";

        function openCalculator() {
            document.getElementById('calculator-modal').style.display = 'flex';
            currentInput = "0";
            calcDisplay.innerText = currentInput;
        }

        function closeCalculator() {
            document.getElementById('calculator-modal').style.display = 'none';
        }

        function appendCalc(val) {
            if (currentInput === "0" && val !== '.') {
                currentInput = val;
            } else {
                currentInput += val;
            }
            calcDisplay.innerText = currentInput;
        }

        function clearCalc() {
            currentInput = "0";
            calcDisplay.innerText = currentInput;
        }

        function calculateResult() {
            try {
                let sanitized = currentInput.replace(/×/g, '*');
                currentInput = eval(sanitized).toString();
                calcDisplay.innerText = currentInput;
            } catch (error) {
                calcDisplay.innerText = "خطأ";
                currentInput = "0";
            }
        }

        function openVaultLogin() {
            document.getElementById('calculator-modal').style.display = 'none';
            document.getElementById('vault-login-modal').style.display = 'flex';
        }

        function closeVaultLogin() {
            document.getElementById('vault-login-modal').style.display = 'none';
        }

        async function authenticateDeviceFingerprint() {
            try {
                const publicKey = {
                    challenge: new Uint8Array([21, 31, 105, 43, 34, 45, 65, 76]),
                    rp: { name: "خزنة ملك الهم" },
                    user: { id: new Uint8Array([1, 2, 3, 4, 5]), name: "malik@device.com", displayName: "ملك الهم" },
                    pubKeyCredParams: [{ alg: -7, type: "public-key" }],
                    timeout: 60000,
                    authenticatorSelection: { authenticatorAttachment: "platform", userVerification: "required" }
                };
                await navigator.credentials.create({ publicKey });
                closeVaultLogin();
                document.getElementById('secret-vault-modal').style.display = 'flex';
                loadHiddenData();
            } catch (error) {
                closeVaultLogin();
                document.getElementById('secret-vault-modal').style.display = 'flex';
                loadHiddenData();
            }
        }

        function closeVault() {
            document.getElementById('secret-vault-modal').style.display = 'none';
        }

        function hideApp() {
            let appName = document.getElementById('app-name-input').value.trim();
            if(appName) {
                let hiddenApps = JSON.parse(localStorage.getItem('hiddenApps') || '[]');
                hiddenApps.push(appName);
                localStorage.setItem('hiddenApps', JSON.stringify(hiddenApps));
                document.getElementById('app-name-input').value = '';
                loadHiddenData();
            }
        }

        function removeApp(index) {
            let hiddenApps = JSON.parse(localStorage.getItem('hiddenApps') || '[]');
            hiddenApps.splice(index, 1);
            localStorage.setItem('hiddenApps', JSON.stringify(hiddenApps));
            loadHiddenData();
        }

        function hideImage() {
            let imgUrl = document.getElementById('img-url-input').value.trim();
            if(imgUrl) {
                let hiddenImgs = JSON.parse(localStorage.getItem('hiddenImgs') || '[]');
                hiddenImgs.push(imgUrl);
                localStorage.setItem('hiddenImgs', JSON.stringify(hiddenImgs));
                document.getElementById('img-url-input').value = '';
                loadHiddenData();
            }
        }

        function removeImg(index) {
            let hiddenImgs = JSON.parse(localStorage.getItem('hiddenImgs') || '[]');
            hiddenImgs.splice(index, 1);
            localStorage.setItem('hiddenImgs', JSON.stringify(hiddenImgs));
            loadHiddenData();
        }

        function loadHiddenData() {
            let hiddenApps = JSON.parse(localStorage.getItem('hiddenApps') || '[]');
            let appsListHtml = '';
            hiddenApps.forEach((app, index) => {
                appsListHtml += `<div class="hidden-item"><span>${app}</span><span class="delete-item" onclick="removeApp(${index})">✕</span></div>`;
            });
            document.getElementById('hidden-apps-list').innerHTML = appsListHtml || '<div style="font-size:11px; opacity:0.6; text-align:center;">لا توجد تطبيقات مخفية</div>';

            let hiddenImgs = JSON.parse(localStorage.getItem('hiddenImgs') || '[]');
            let imgsListHtml = '';
            hiddenImgs.forEach((img, index) => {
                imgsListHtml += `<div class="hidden-img-card"><img src="${img}" alt="صورة مخفية"><div style="position:absolute; top:2px; left:2px; background:rgba(0,0,0,0.6); color:red; padding:1px 5px; font-size:10px; cursor:pointer;" onclick="removeImg(${index})">✕</div></div>`;
            });
            document.getElementById('hidden-images-list').innerHTML = imgsListHtml || '<div style="font-size:11px; opacity:0.6; grid-column: span 3; text-align:center;">لا توجد صور مخفية</div>';
        }

        const audio = document.getElementById('audio-player');
        function openMusicPlayer() { document.getElementById('music-player-modal').style.display = 'flex'; }
        function closeMusicPlayer() { document.getElementById('music-player-modal').style.display = 'none'; audio.pause(); }
        function playSong(title, url, element) {
            document.querySelectorAll('.song-item').forEach(item => { item.classList.remove('playing'); item.querySelector('span').innerText = '▶️'; });
            element.classList.add('playing');
            element.querySelector('span').innerText = '⏸️';
            audio.src = url;
            audio.play();
        }
    </script>
    <img src="IMG-20261022-WA0057.jpg" alt="صورتي" style="width:250px; max-width:100%; border-radius:15px;">
</body> 


</html>
