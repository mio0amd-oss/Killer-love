
<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>subkazani.ir</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Vazirmatn', sans-serif;
      min-height: 100vh;
      background:
        radial-gradient(circle at 25% 15%, rgba(107, 33, 168, 0.30), transparent 55%),
        radial-gradient(circle at 85% 75%, rgba(59, 7, 100, 0.35), transparent 55%),
        linear-gradient(165deg, #000000 0%, #0a0510 25%, #170a29 50%, #250b45 75%, #38105f 100%);
      background-attachment: fixed;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      overflow-x: hidden;
    }

    /* ---- Header (Telegram-channel style) ---- */
    .header {
      width: 100%;
      height: 140px;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(168, 85, 247, 0.35);
      position: relative;
    }

    .avatar {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      position: absolute;
      left: 50%;
      bottom: -60px;
      transform: translateX(-50%);
      background: linear-gradient(135deg, #2d1052, #12071f);
      border: 3px solid #a855f7;
      box-shadow: 0 0 35px rgba(168, 85, 247, 0.55);
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    /* ---- Main content ---- */
    .content {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      text-align: center;
      padding: 96px 20px 0;
      gap: 18px;
    }

    .fa-text {
      font-size: clamp(1.6rem, 5vw, 2.6rem);
      font-weight: 600;
      background: linear-gradient(90deg, #e9d5ff, #a855f7, #7c3aed);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: glow 4s ease-in-out infinite alternate;
    }

    .en-text {
      font-size: clamp(1rem, 3vw, 1.4rem);
      font-weight: 300;
      letter-spacing: 4px;
      color: rgba(233, 213, 255, 0.75);
      direction: ltr;
    }

    @keyframes glow {
      from { filter: drop-shadow(0 0 6px rgba(168, 85, 247, 0.3)); }
      to   { filter: drop-shadow(0 0 18px rgba(168, 85, 247, 0.8)); }
    }

    .divider {
      width: 55%;
      max-width: 260px;
      height: 1px;
      margin: 14px auto 6px;
      background: rgba(255, 255, 255, 0.65);
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.45);
    }

    .quote-fa {
      max-width: 620px;
      font-size: clamp(1.1rem, 3.6vw, 1.5rem);
      font-weight: 500;
      line-height: 2;
      color: #e9d5ff;
      text-shadow: 0 0 14px rgba(168, 85, 247, 0.35);
    }

    .morse {
      max-width: 640px;
      margin-top: 14px;
      padding: 18px 22px;
      border: 1px solid rgba(216, 180, 254, 0.45);
      border-radius: 10px;
      background: rgba(255, 255, 255, 0.04);
      box-shadow: 0 0 22px rgba(168, 85, 247, 0.25) inset, 0 0 14px rgba(168, 85, 247, 0.2);
      font-family: 'Courier New', Courier, monospace;
      font-size: clamp(0.95rem, 2.8vw, 1.2rem);
      font-weight: 700;
      letter-spacing: 2px;
      word-spacing: 8px;
      line-height: 2.1;
      color: #ffffff;
      text-shadow: 0 0 8px rgba(255, 255, 255, 0.65);
      direction: ltr;
    }

    /* ---- Empty gap before subkazani ---- */
    .gap-footer {
      width: 100%;
      min-height: 65vh;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      padding-bottom: 36px;
    }

    .footer {
      font-size: 0.85rem;
      letter-spacing: 2px;
      color: rgba(255, 255, 255, 0.3);
      direction: ltr;
    }

    .footer a {
      color: rgba(192, 132, 252, 0.55);
      text-decoration: none;
      transition: color 0.4s ease, text-shadow 0.4s ease;
    }

    .footer a:hover {
      color: #c084fc;
      text-shadow: 0 0 10px rgba(192, 132, 252, 0.6);
    }
  </style>
</head>
<body>
  <audio id="bgm" src="Music.mp3" loop preload="auto"></audio>

  <header class="header">
    <div class="avatar">
      <!-- عکس خودت رو با اسم avatar.jpg کنار این فایل بذار -->
      <img src="avatar.jpg" alt="avatar" onerror="this.style.display='none'" />
    </div>
  </header>

  <main class="content">
    <div class="fa-text">شاید در زندگی بعدی</div>
    <div class="en-text">maybe in the next life</div>

    <div class="divider"></div>

    <div class="quote-fa">گاهی یک جنگ برای ماندن محترم از یک صلح است برای رفتن</div>
    <div class="en-text">Sometimes a war fought to stay is more honorable than a peace made to leave.</div>

    <div class="morse">... ..- -- . - .. -- . ...&nbsp;&nbsp; .-&nbsp;&nbsp; .-- .- .-.&nbsp;&nbsp; ..-. --- ..- --. .... -&nbsp;&nbsp; - ---&nbsp;&nbsp; ... - .- -.--&nbsp;&nbsp; .. ...&nbsp;&nbsp; -- --- .-. .&nbsp;&nbsp; .... --- -. --- .-. .- -... .-.. .&nbsp;&nbsp; - .... .- -.&nbsp;&nbsp; .- &nbsp;&nbsp;.--. . .- -.-. .&nbsp;&nbsp; -- .- -.. .&nbsp;&nbsp; - ---&nbsp;&nbsp; .-.. . .- ...- .</div>
  </main>

  <div class="gap-footer">
    <footer class="footer">
      <a href="https://subkazani.ir">subkazani.ir</a>
    </footer>
  </div>

  <script>
    // جابه‌جایی و کوچیک شدن تدریجی آواتار، متناسب با میزان اسکرول کاربر
    const avatarEl = document.querySelector('.avatar');
    const scrollRange = 220; // این مقدار رو بیشتر/کمتر کن تا حرکت کندتر/سریع‌تر بشه
    const minScale = 0.55; // کوچیک‌ترین اندازه‌ی آواتار در انتهای حرکت
    function updateAvatarPosition() {
      const progress = Math.min(Math.max(window.scrollY / scrollRange, 0), 1);
      const leftPercent = 50 + progress * 30; // از وسط (50%) تا سمت راست (80%)
      const scale = 1 - progress * (1 - minScale);
      avatarEl.style.left = leftPercent + '%';
      avatarEl.style.transform = `translateX(-50%) scale(${scale})`;
    }
    window.addEventListener('scroll', () => {
      requestAnimationFrame(updateAvatarPosition);
    });
    updateAvatarPosition();

    // پخش خودکار آهنگ محض لود صفحه
    const bgm = document.getElementById('bgm');
    function tryPlay() {
      const p = bgm.play();
      if (p !== undefined) {
        p.catch(() => {
          // اگر مرورگر پخش خودکار صدادار رو بلاک کرد (سیاست همه‌ی مرورگرهاست، نه محدودیت این کد)،
          // با اولین تعامل کاربر (کلیک/لمس/اسکرول/کلید) بلافاصله پخش می‌شه
          const resume = () => {
            bgm.play();
            ['click', 'touchstart', 'scroll', 'keydown'].forEach(evt =>
              document.removeEventListener(evt, resume)
            );
          };
          ['click', 'touchstart', 'scroll', 'keydown'].forEach(evt =>
            document.addEventListener(evt, resume, { once: true })
          );
        });
      }
    }
    tryPlay();
    window.addEventListener('load', tryPlay);
  </script>
</body>
</html>
