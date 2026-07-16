
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
      position: absolute;
      left: 50%;
      bottom: -60px;
      transform: translateX(-50%);
    }

    .avatar-frame {
      position: absolute;
      inset: 0;
      border-radius: 50%;
      background: linear-gradient(135deg, #2d1052, #12071f);
      border: 3px solid #a855f7;
      box-shadow: 0 0 35px rgba(168, 85, 247, 0.55);
      pointer-events: none;
      transition: opacity 0.05s linear;
    }

    .avatar-shards {
      position: absolute;
      inset: 0;
      border-radius: 50%;
      overflow: hidden;
    }

    .shard {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #2d1052, #12071f);
      transform: translate(0, 0) rotate(0deg);
      will-change: transform;
      filter: drop-shadow(3px 8px 10px rgba(0, 0, 0, 0.6)) drop-shadow(-1px -1px 0 rgba(255, 255, 255, 0.12));
    }

    .shard::after {
      content: '';
      position: absolute;
      inset: 0;
      background:
        linear-gradient(125deg, rgba(255, 255, 255, 0.55) 0%, rgba(255, 255, 255, 0.08) 18%, rgba(255, 255, 255, 0) 45%, rgba(255, 255, 255, 0) 70%, rgba(255, 255, 255, 0.2) 100%);
      mix-blend-mode: overlay;
      pointer-events: none;
    }

    .shard::before {
      content: '';
      position: absolute;
      inset: 0;
      box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.35);
      pointer-events: none;
    }

    .shard img {
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

    /* ---- Morse Code with Circular Text ---- */
    .morse-container {
      max-width: 700px;
      margin-top: 40px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 30px;
    }

    .circular-morse {
      position: relative;
      width: 240px;
      height: 240px;
      cursor: pointer;
    }

    .morse-circle {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: linear-gradient(135deg, rgba(168, 85, 247, 0.15), rgba(124, 58, 237, 0.1));
      border: 2px solid rgba(168, 85, 247, 0.5);
      box-shadow: 0 0 40px rgba(168, 85, 247, 0.3) inset, 0 0 30px rgba(168, 85, 247, 0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s ease;
      position: relative;
    }

    .circular-morse:hover .morse-circle {
      border-color: rgba(168, 85, 247, 0.8);
      box-shadow: 0 0 50px rgba(168, 85, 247, 0.5) inset, 0 0 40px rgba(168, 85, 247, 0.4);
      background: linear-gradient(135deg, rgba(168, 85, 247, 0.25), rgba(124, 58, 237, 0.2));
    }

    .morse-emoticon {
      font-size: 70px;
      font-weight: bold;
      color: #e9d5ff;
      text-shadow: 0 0 20px rgba(168, 85, 247, 0.6);
      user-select: none;
      transition: all 0.3s ease;
    }

    .circular-morse:hover .morse-emoticon {
      text-shadow: 0 0 30px rgba(233, 213, 255, 1);
      transform: scale(1.1);
    }

    .morse-circle::before {
      content: '';
      position: absolute;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      animation: pulse 2s ease-in-out infinite;
      border: 2px solid rgba(168, 85, 247, 0.3);
      opacity: 0;
    }

    @keyframes pulse {
      0%, 100% {
        transform: scale(1);
        opacity: 0;
      }
      50% {
        transform: scale(1.15);
        opacity: 1;
      }
    }

    .circular-morse:hover .morse-circle::before {
      animation: pulse 1.5s ease-in-out infinite;
    }

    /* SVG Text on Circle */
    .morse-text-svg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }

    .morse-text-svg text {
      font-family: 'Courier New', monospace;
      font-size: 14px;
      font-weight: 700;
      fill: rgba(255, 255, 255, 0.8);
      text-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
      letter-spacing: 1px;
    }

    .morse-text-svg text:hover {
      fill: rgba(233, 213, 255, 1);
      filter: drop-shadow(0 0 8px rgba(168, 85, 247, 0.8));
    }

    /* ---- Empty gap before footer ---- */
    .gap-footer {
      width: 100%;
      min-height: 65vh;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      padding-bottom: 36px;
    }

    .footer {
      font-size: 0.65rem;
      letter-spacing: 0.5px;
      color: rgba(255, 255, 255, 0.3);
      direction: ltr;
      padding: 0 16px;
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

    /* Playing state indicator */
    .playing-indicator {
      position: fixed;
      bottom: 30px;
      left: 30px;
      font-size: 14px;
      color: rgba(168, 85, 247, 0.7);
      display: none;
      animation: blink 0.6s ease-in-out infinite;
    }

    @keyframes blink {
      0%, 49%, 100% { opacity: 1; }
      50%, 99% { opacity: 0.3; }
    }

    .playing-indicator.active {
      display: block;
    }
  </style>
</head>
<body>
  <audio id="morseAudio" src="Music.mp3" preload="auto"></audio>
  <audio id="aktorAudio" src="aktor.mp3" preload="auto"></audio>
  <audio id="totoAudio" src="toto.mp3" preload="auto"></audio>

  <header class="header">
    <div class="avatar" id="avatar">
      <div class="avatar-frame" id="avatarFrame"></div>
      <div class="avatar-shards" id="avatarShards">
        <!-- عکس خودت رو با اسم avatar.jpg کنار این فایل بذار -->
        <div class="shard" data-power="1.18" style="clip-path:polygon(50% 50%,50.00% 0.00%,73.53% 0.00%); --tx:63px; --ty:-168px; --rot:-69deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.18" style="clip-path:polygon(50% 50%,73.53% 0.00%,97.06% 0.00%); --tx:-38px; --ty:-197px; --rot:-40deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="0.89" style="clip-path:polygon(50% 50%,97.06% 0.00%,100.00% 20.59%); --tx:73px; --ty:-329px; --rot:64deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="0.89" style="clip-path:polygon(50% 50%,100.00% 20.59%,100.00% 44.12%); --tx:8px; --ty:-148px; --rot:-68deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.1" style="clip-path:polygon(50% 50%,100.00% 44.12%,100.00% 67.65%); --tx:-41px; --ty:-269px; --rot:-69deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.04" style="clip-path:polygon(50% 50%,100.00% 67.65%,100.00% 91.18%); --tx:83px; --ty:-306px; --rot:64deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.21" style="clip-path:polygon(50% 50%,100.00% 91.18%,85.29% 100.00%); --tx:14px; --ty:-290px; --rot:-4deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.16" style="clip-path:polygon(50% 50%,85.29% 100.00%,61.76% 100.00%); --tx:-99px; --ty:-334px; --rot:-35deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="0.95" style="clip-path:polygon(50% 50%,61.76% 100.00%,38.24% 100.00%); --tx:-13px; --ty:-211px; --rot:-36deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="0.89" style="clip-path:polygon(50% 50%,38.24% 100.00%,14.71% 100.00%); --tx:95px; --ty:-226px; --rot:-49deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.12" style="clip-path:polygon(50% 50%,14.71% 100.00%,0.00% 91.18%); --tx:-76px; --ty:-231px; --rot:13deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.09" style="clip-path:polygon(50% 50%,0.00% 91.18%,0.00% 67.65%); --tx:-89px; --ty:-326px; --rot:42deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="0.98" style="clip-path:polygon(50% 50%,0.00% 67.65%,0.00% 44.12%); --tx:-4px; --ty:-160px; --rot:66deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.11" style="clip-path:polygon(50% 50%,0.00% 44.12%,0.00% 20.59%); --tx:60px; --ty:-298px; --rot:17deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.15" style="clip-path:polygon(50% 50%,0.00% 20.59%,2.94% 0.00%); --tx:80px; --ty:-157px; --rot:-64deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.23" style="clip-path:polygon(50% 50%,2.94% 0.00%,26.47% 0.00%); --tx:97px; --ty:-214px; --rot:-55deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
        <div class="shard" data-power="1.05" style="clip-path:polygon(50% 50%,26.47% 0.00%,50.00% 0.00%); --tx:-75px; --ty:-237px; --rot:-4deg;"><img src="avatar.jpg" alt="" onerror="this.style.display='none'" /></div>
      </div>
    </div>
  </header>

  <main class="content">
    <div class="fa-text">شاید در زندگی بعدی</div>
    <div class="en-text">maybe in the next life</div>

    <div class="divider"></div>

    <div class="quote-fa">گاهی یک جنگ برای ماندن محترم از یک صلح است برای رفتن</div>
    <div class="en-text">Sometimes a war fought to stay is more honorable than a peace made to leave.</div>

    <!-- Morse Code with Circular Text -->
    <div class="morse-container">
      <div class="circular-morse" id="morseButton">
        <svg class="morse-text-svg" viewBox="0 0 240 240">
          <defs>
            <path id="circle" d="M 120, 120 m -105, 0 a 105,105 0 1,1 210,0 a 105,105 0 1,1 -210,0" fill="none" />
          </defs>
          <text font-size="11" font-weight="700" fill="rgba(255,255,255,0.75)" letter-spacing="1">
            <textPath href="#circle" startOffset="0%" text-anchor="start">
              🎵 PLAY ME &nbsp;•&nbsp; اضغط علي &nbsp;•&nbsp; 我来播放 &nbsp;•&nbsp; क्लिक करे &nbsp;•&nbsp; クリック &nbsp;•&nbsp; Klik Mig &nbsp;•&nbsp; 🎵 PLAY ME
            </textPath>
          </text>
        </svg>
        <div class="morse-circle">
          <div class="morse-emoticon">:(</div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="quote-fa">فهمیدم دل خوش نکنم به این رویش<br>به قول ونگوگ، غم همیشه باقیه</div>
    <div class="en-text">I realized I shouldn't get my hopes up over this blooming:<br>As Van Gogh said, "The sadness will last forever."</div>

    <div class="morse-container">
      <div class="circular-morse" id="aktorButton">
        <svg class="morse-text-svg" viewBox="0 0 240 240">
          <defs>
            <path id="circle2" d="M 120, 120 m -105, 0 a 105,105 0 1,1 210,0 a 105,105 0 1,1 -210,0" fill="none" />
          </defs>
          <text font-size="11" font-weight="700" fill="rgba(255,255,255,0.75)" letter-spacing="1">
            <textPath href="#circle2" startOffset="0%" text-anchor="start">
              🎵 PLAY ME &nbsp;•&nbsp; اضغط علي &nbsp;•&nbsp; 我来播放 &nbsp;•&nbsp; क्लिक करे &nbsp;•&nbsp; クリック &nbsp;•&nbsp; Klik Mig &nbsp;•&nbsp; 🎵 PLAY ME
            </textPath>
          </text>
        </svg>
        <div class="morse-circle">
          <div class="morse-emoticon">:(</div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div class="quote-fa">ـ حالا بزار روحِ من دور بشه اَزَت ـ</div>

    <div class="morse-container">
      <div class="circular-morse" id="totoButton">
        <svg class="morse-text-svg" viewBox="0 0 240 240">
          <defs>
            <path id="circle3" d="M 120, 120 m -105, 0 a 105,105 0 1,1 210,0 a 105,105 0 1,1 -210,0" fill="none" />
          </defs>
          <text font-size="11" font-weight="700" fill="rgba(255,255,255,0.75)" letter-spacing="1">
            <textPath href="#circle3" startOffset="0%" text-anchor="start">
              🎵 PLAY ME &nbsp;•&nbsp; اضغط علي &nbsp;•&nbsp; 我来播放 &nbsp;•&nbsp; क्लिक करे &nbsp;•&nbsp; クリック &nbsp;•&nbsp; Klik Mig &nbsp;•&nbsp; 🎵 PLAY ME
            </textPath>
          </text>
        </svg>
        <div class="morse-circle">
          <div class="morse-emoticon">:(</div>
        </div>
      </div>
    </div>
  </main>

  <div class="gap-footer">
    <footer class="footer" id="siteFooter">Perhaps the memory of you will never fade from my mind.</footer>
  </div>

  <div class="playing-indicator" id="playingIndicator">🎵 در حال پخش...</div>

  <script>
    // شکستن شیشه‌ای اواتار با یک بار کلیک - تکه‌ها روی زمین، بالای متن فوتر، فرود میان و باقی می‌مونن
    const avatarEl = document.getElementById('avatar');
    const avatarFrame = document.getElementById('avatarFrame');
    const avatarShards = document.getElementById('avatarShards');
    const shards = Array.from(avatarShards.querySelectorAll('.shard'));
    const siteFooter = document.getElementById('siteFooter');
    let isBroken = false;

    avatarEl.style.cursor = 'pointer';

    avatarEl.addEventListener('click', () => {
      if (isBroken) return;
      isBroken = true;
      avatarEl.style.cursor = 'default';

      const rect = avatarShards.getBoundingClientRect();
      const footerRect = siteFooter.getBoundingClientRect();
      // تبدیل مختصات به فضای سند (نه ویوپورت) تا با اسکرول صفحه هماهنگ بمونن
      const startLeft = rect.left + window.scrollX;
      const startTop = rect.top + window.scrollY;
      // فضای کف: درست بالای متن فوتر، جایی که تکه‌ها روی هم بریزن
      const floorY = footerRect.top + window.scrollY - 34;

      avatarFrame.style.transition = 'opacity 0.3s ease';
      avatarFrame.style.opacity = '0';

      shards.forEach((shard) => {
        // خارج کردن تکه از داخل هدر تا محدود به overflow والدش نشه
        document.body.appendChild(shard);

        shard.style.position = 'absolute';
        shard.style.left = startLeft + 'px';
        shard.style.top = startTop + 'px';
        shard.style.right = 'auto';
        shard.style.bottom = 'auto';
        shard.style.width = rect.width + 'px';
        shard.style.height = rect.height + 'px';
        shard.style.margin = '0';
        shard.style.zIndex = '500';
        shard.style.transform = 'translate(0px, 0px) rotate(0deg)';
        shard.style.opacity = '1';

        // ریفلو اجباری تا ترنزیشن از حالت اولیه شروع بشه
        void shard.offsetWidth;

        const tx = Math.round((Math.random() - 0.5) * 320);
        const restY = Math.round((floorY - startTop) - 40 + Math.random() * 40);
        const overshootY = restY + 25 + Math.round(Math.random() * 15);
        const rot = Math.round((Math.random() - 0.5) * 500);
        const delay = Math.round(Math.random() * 250);

        // مرحله اول: افتادن شتاب‌دار به‌همراه کمی رد شدن از نقطه فرود
        shard.style.transition = `transform 1.5s cubic-bezier(.55,.06,.68,.19) ${delay}ms`;
        shard.style.transform = `translate(${tx}px, ${overshootY}px) rotate(${rot}deg)`;

        // مرحله دوم: برگشت کوچیک به نقطه فرود نهایی (حس برخورد با زمین)
        setTimeout(() => {
          shard.style.transition = 'transform 0.35s cubic-bezier(.34,1.56,.64,1)';
          shard.style.transform = `translate(${tx}px, ${restY}px) rotate(${rot}deg)`;
        }, delay + 1480);
      });
    });

    // موسیقی - کلیک روی دایره‌های پخش
    const playingIndicator = document.getElementById('playingIndicator');

    const players = [
      { button: document.getElementById('morseButton'), audio: document.getElementById('morseAudio') },
      { button: document.getElementById('aktorButton'), audio: document.getElementById('aktorAudio') },
      { button: document.getElementById('totoButton'), audio: document.getElementById('totoAudio') }
    ];

    function stopAll(except) {
      players.forEach(p => {
        if (p.audio !== except) {
          p.audio.pause();
          p.audio.currentTime = 0;
        }
      });
    }

    players.forEach(({ button, audio }) => {
      button.addEventListener('click', (e) => {
        e.preventDefault();

        if (audio.paused) {
          stopAll(audio);
          audio.play()
            .then(() => {
              playingIndicator.classList.add('active');
            })
            .catch(() => {
              console.log('خطا در پخش صدا');
            });
        } else {
          audio.pause();
          audio.currentTime = 0;
          playingIndicator.classList.remove('active');
        }
      });

      audio.addEventListener('ended', () => {
        playingIndicator.classList.remove('active');
      });
    });
  </script>
</body>
</html>
