<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Nacy · 赛博世界</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Great+Vibes&display=swap" rel="stylesheet">

  <style>
    /* ========== 变量色彩 ========== */
    :root{
      --bg-1: #F8F9FF;
      --pastel-blue: #DDEBFF;
      --pastel-lav: #EBDDFB;
      --cream-gold: #F6E9D6;
      --accent: #F7C9F1;
      --glass: rgba(255,255,255,0.55);
      --card-shadow: 0 12px 30px rgba(110,90,150,0.08);
      --soft-shadow: 0 8px 24px rgba(80,60,120,0.06);
      --muted: #6B6179;
      --gold-tinge: rgba(255, 220, 140, 0.08);
    }

    /* ========== 全局样式 ========== */
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background:
        radial-gradient(1200px 600px at 10% 10%, rgba(227,240,255,0.45), transparent 8%),
        radial-gradient(900px 500px at 90% 80%, rgba(241,229,255,0.35), transparent 10%),
        var(--bg-1);
      color: #3b3350;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      overflow-x:hidden;
    }

    a{color:inherit; text-decoration:none}
    .container{
      width:1200px;
      max-width:calc(100% - 64px);
      margin:0 auto;
    }

    /* ========== Top Nav ========== */
    header.topbar{
      position:fixed;
      left:50%;
      transform:translateX(-50%);
      top:20px;
      z-index:60;
      width:1100px;
      max-width:calc(100% - 48px);
      pointer-events:auto;
    }
    .nav-wrap{
      backdrop-filter: blur(8px) saturate(110%);
      background: linear-gradient(180deg, rgba(255,255,255,0.7), rgba(255,255,255,0.55));
      border-radius:28px;
      padding:10px 18px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      box-shadow: var(--card-shadow);
      border: 1px solid rgba(255,255,255,0.6);
    }
    .logo{display:flex;align-items:center;gap:12px}
    .logo .mark{width:46px;height:46px;border-radius:12px;background: linear-gradient(135deg,var(--pastel-blue),var(--pastel-lav));display:flex;align-items:center;justify-content:center;box-shadow: 0 6px 18px rgba(160,140,200,0.12), inset 0 2px 6px rgba(255,255,255,0.5);border: 1px solid rgba(255,255,255,0.6);}
    .logo .title{font-weight:600;letter-spacing:0.2px;color:#4a3f5b}
    nav.topnav{display:flex;gap:12px;align-items:center}
    nav.topnav a{padding:10px 14px;border-radius:12px;color:var(--muted);font-weight:500;transition:all .28s cubic-bezier(.2,.9,.2,1)}
    nav.topnav a:hover{transform:translateY(-4px);box-shadow: 0 6px 18px rgba(150,120,210,0.06);color:#412B5B;background: linear-gradient(90deg, rgba(255,255,255,0.45), rgba(255,255,255,0.15));border:1px solid rgba(255,255,255,0.5)}
    .cta{background: linear-gradient(90deg, rgba(255,238,210,0.9), rgba(255,245,230,0.6));padding:8px 16px;border-radius:14px;box-shadow: 0 8px 20px rgba(240,200,140,0.08);font-weight:600;}

    /* ========== Hero Banner ========== */
    .hero{
      min-height:92vh;
      padding-top:120px;
      position:relative;
      overflow:visible;
      display:flex;
      align-items:center;
      margin-bottom:48px;
    }
    .hero-inner{display:flex;gap:48px;align-items:center;width:100%}
    .hero-left{flex:0 0 540px;max-width:60%}
    .kicker{display:inline-flex;align-items:center;gap:10px;background: linear-gradient(90deg, rgba(255,255,255,0.6), rgba(255,255,255,0.2));padding:8px 12px;border-radius:999px;font-weight:600;color:#5b4b67;box-shadow: 0 6px 18px rgba(120,90,160,0.06);width:max-content;}
    .hero-title{margin-top:18px;font-size:46px;line-height:1.05;letter-spacing:-1px;color:#392a4d;font-weight:700}
    .hero-sub{margin-top:12px;color:#675e78;max-width:46ch}
    .hero-actions{margin-top:22px;display:flex;gap:12px;align-items:center}
    .btn{padding:12px 18px;border-radius:14px;border:none;cursor:pointer;font-weight:600;background:linear-gradient(90deg, rgba(231,211,255,0.85), rgba(255,240,245,0.72));box-shadow: 0 8px 26px rgba(170,120,220,0.08);transition:all .28s cubic-bezier(.2,.9,.2,1);position:relative;overflow:visible;}
    .btn:hover{ transform:translateY(-6px); box-shadow: 0 18px 40px rgba(180,120,230,0.12)}
    .btn.secondary{ background: linear-gradient(90deg, rgba(255,255,255,0.65), rgba(255,255,255,0.4)); border:1px solid rgba(255,255,255,0.6); color:#5a4666; }

    .ribbon{margin-top:18px;width:220px;height:36px;border-radius:999px;background: linear-gradient(90deg, rgba(255,245,238,0.8), rgba(255,240,250,0.6));box-shadow: 0 8px 20px rgba(200,160,220,0.06);display:flex;align-items:center;justify-content:center;color:#6b5571;font-size:13px;gap:8px;}

    .hero-right{flex:1;position:relative;min-height:540px;display:flex;align-items:center;justify-content:center}
    .scene{width:620px;max-width:92%;aspect-ratio: 16/10;border-radius:28px;background:radial-gradient(circle at 10% 20%, rgba(255,255,255,0.6), transparent 8%), linear-gradient(180deg,var(--pastel-blue),var(--pastel-lav));box-shadow: 0 20px 60px rgba(90,60,140,0.08), inset 0 -8px 20px rgba(255,255,255,0.25);position:relative;overflow:visible;padding:18px}
    .scene::before{content:"";position:absolute;left:-12px;right:-12px;top:-12px;bottom:-12px;border-radius:34px;background: radial-gradient(80% 40% at 10% 0%, rgba(255,255,255,0.28), transparent 20%), linear-gradient(180deg, rgba(255,255,255,0.06), transparent 30%);z-index:0;pointer-events:none;mask-image: radial-gradient(circle at top center, rgba(0,0,0,1) 40%, rgba(0,0,0,0.9) 60%, rgba(0,0,0,0));}

    .castle, .fairy, .crystals{position:absolute;z-index:2;transform-style:preserve-3d;transition:transform .18s ease-out}
    .castle{left:18%;top:10%;width:340px;opacity:0.98;filter:drop-shadow(0 10px 30px rgba(120,80,200,0.12))}
    .fairy{right:10%;bottom:6%;width:160px;filter:drop-shadow(0 8px 24px rgba(255,200,230,0.08))}
    .crystals{left:62%;top:56%;width:130px;opacity:0.95}

    .stars{position:absolute;inset:8px;pointer-events:none;z-index:1;border-radius:20px;overflow:hidden}
    .star{position:absolute;width:4px;height:4px;background: radial-gradient(circle, #fff 0%, rgba(255,255,255,0.8) 30%, rgba(255,255,255,0.2) 60%, transparent 100%);border-radius:50%;filter:blur(0.6px);opacity:0.85;animation: twinkle 3.6s infinite ease-in-out;}
    @keyframes twinkle {0%,100%{ transform:scale(0.6); opacity:0.6 }50%{ transform:scale(1.8); opacity:1 }}

    /* ========== Main Sections ========== */
    main{position:relative;z-index:2}
    section{padding:48px 0}

    /* About Card */
    .about{display:flex;gap:28px;align-items:flex-start;justify-content:space-between}
    .avatar{width:220px;height:220px;border-radius:28px;background: linear-gradient(135deg, rgba(255,255,255,0.6), rgba(255,245,255,0.2));box-shadow: var(--soft-shadow);display:flex;align-items:center;justify-content:center;border:1px solid rgba(255,255,255,0.6);overflow:hidden;position:relative;flex-shrink:0}
    .about-card{flex:1;background: linear-gradient(180deg, rgba(255,255,255,0.6), rgba(255,255,255,0.45));border-radius:22px;padding:20px;box-shadow: var(--card-shadow);border:1px solid rgba(255,255,255,0.6);position:relative;backdrop-filter: blur(6px) saturate(120%)}
    .about h3{margin:0 0 8px 0;font-size:20px}
    .about p{color:#5f546f}
    .skill-badges{display:flex;flex-wrap:wrap;gap:12px;margin-top:14px}
    .badge{padding:8px 12px;border-radius:999px;background: linear-gradient(90deg, rgba(255,255,255,0.6), rgba(255,255,255,0.25));box-shadow: 0 8px 18px rgba(140,110,190,0.05);color:#5b4868;font-weight:600}

    /* Skills Cards */
    .skills-grid{display:grid;grid-template-columns:repeat(3, 1fr);gap:18px}
    .skill-card{background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.45));border-radius:18px;padding:18px;box-shadow: var(--soft-shadow);border:1px solid rgba(255,255,255,0.6);transition:transform .28s ease, box-shadow .28s ease}
    .skill-card:hover{transform: translateY(-8px);box-shadow: 0 20px 40px rgba(120,90,180,0.08)}
    .skill-card h4{margin:0 0 8px 0}
    .progress{height:10px;border-radius:999px;background:rgba(120,90,160,0.06);overflow:hidden}
    .progress > i{display:block;height:100%;background:linear-gradient(90deg, #FFEBB8, #FFD4F8);border-radius:inherit}

    /* ====== Logs (替代原画廊) ====== */
    .logs-list{
      display:flex;
      flex-direction:column;
      gap:18px;
      max-width:1100px;
      margin:0 auto;
    }
    .log-entry{
      display:flex;
      gap:18px;
      align-items:flex-start;
      padding:18px;
      border-radius:18px;
      background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.46));
      box-shadow: var(--card-shadow);
      border:1px solid rgba(255,255,255,0.6);
      transition:transform .22s ease, box-shadow .22s ease;
      overflow:hidden;
    }
    .log-entry:hover{ transform:translateY(-6px); box-shadow: 0 22px 48px rgba(110,80,170,0.08) }
    .log-meta{
      width:120px;
      flex-shrink:0;
      display:flex;
      flex-direction:column;
      align-items:flex-start;
      gap:8px;
    }
    .log-date{
      font-weight:700;
      color:#5a3f65;
      font-size:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.45));
      padding:8px 10px;border-radius:12px;
      box-shadow: 0 8px 20px rgba(180,130,220,0.04);
    }
    .log-tags{display:flex;flex-direction:column;gap:6px;font-size:13px;color:#6a5877}
    .log-body{flex:1;display:flex;flex-direction:column;gap:10px}
    .log-title{font-size:18px;margin:0;color:#3b2b4a;font-weight:700}
    .log-excerpt{color:#6e5f78;margin:0}
    .log-actions{display:flex;gap:12px;align-items:center}
    .pill{padding:8px 12px;border-radius:999px;background: linear-gradient(90deg, rgba(255,255,255,0.6), rgba(255,255,255,0.25));font-weight:600;color:#5b4868;border:1px solid rgba(255,255,255,0.6)}

    /* optional image on right for each log */
    .log-thumb{width:160px;height:110px;border-radius:12px;overflow:hidden;flex-shrink:0;background:linear-gradient(180deg,#fff4ff,#eef7ff);display:flex;align-items:center;justify-content:center}

    /* Contact */
    .contact-wrap{display:flex;gap:22px;align-items:flex-start}
    .contact-card{flex:1;border-radius:16px;padding:18px;background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.46));border:1px solid rgba(255,255,255,0.6);box-shadow: var(--soft-shadow)}
    .form-row{display:flex;gap:12px}
    .form-row .field{flex:1}
    input[type=text], input[type=email], textarea{width:100%;padding:12px 14px;border-radius:12px;border:none;background: rgba(255,255,255,0.7);box-shadow: inset 0 2px 6px rgba(0,0,0,0.03);font-size:14px;color:#4b3f54;outline:none}
    textarea{min-height:120px;resize:vertical}

    /* Footer */
    footer{padding:30px 0 80px;color:#6a586f}
    .footer-inner{border-radius:18px;padding:18px;background:linear-gradient(180deg, rgba(255,255,255,0.55), rgba(255,255,255,0.4));box-shadow:var(--soft-shadow);border:1px solid rgba(255,255,255,0.6)}

    /* tiny toast */
    .toast{position:fixed;right:20px;bottom:24px;background: linear-gradient(90deg, rgba(255,245,230,0.95), rgba(255,238,255,0.9));padding:12px 16px;border-radius:12px;box-shadow:0 10px 28px rgba(120,80,180,0.08);display:none;z-index:90;font-weight:600;color:#4a3c58}

    /* responsive */
    @media (max-width:1100px){
      .hero-inner{flex-direction:column;align-items:flex-start}
      .hero-left{max-width:100%;flex:1}
      .hero-right{width:100%}
      .skills-grid{grid-template-columns:repeat(2,1fr)}
      .logs-list{max-width:100%}
    }
    @media (max-width:720px){
      header.topbar{top:12px}
      .nav-wrap{padding:8px}
      .hero-title{font-size:32px}
      .skills-grid{grid-template-columns:1fr}
      .container{padding:0 14px}
      .log-entry{flex-direction:column}
      .log-meta{flex-direction:row;width:auto}
      .log-thumb{width:100%;height:160px}
    }

    /* small helper */
    .visually-hidden{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0 0 0 0);white-space:nowrap;border:0}
  </style>
</head>
<body>
  <header class="topbar">
    <div class="container nav-wrap" role="navigation" aria-label="主导航">
      <div class="logo">
        <div class="mark" aria-hidden="true">
          <svg viewBox="0 0 24 24" width="24" height="24" fill="none" aria-hidden="true">
            <defs><linearGradient id="g" x1="0" x2="1"><stop offset="0" stop-color="#fff"/><stop offset="1" stop-color="#FFD8F0"/></linearGradient></defs>
            <path d="M12 3c1.8 2 4 2.5 6 3-1.6 1.6-2 4-1.8 6.2C14.6 11.8 9.8 11.4 7 14c-2-2 .5-6 5-11z" fill="url(#g)" opacity="0.95"/>
          </svg>
        </div>
        <div>
          <div class="title">童话梦境 · Cahad</div>
          <div style="font-size:12px;color:var(--muted)">梦幻插画 & 个人日志</div>
        </div>
      </div>

      <nav class="topnav" aria-label="主菜单">
        <a href="#about">关于</a>
        <a href="#skills">技能</a>
        <a href="#logs">日志</a>
        <a href="#contact">联系</a>
        <a class="cta" href="#logs">查看日志</a>
      </nav>
    </div>
  </header>

  <!-- Hero Banner -->
  <main>
    <section class="hero">
      <div class="container hero-inner">
        <div class="hero-left">
          <div class="kicker">作者Nacy（大美女）</div>
          <h1 class="hero-title">欢迎来到<br/><small style="font-weight:500;color:#6b5b79">我的赛博世界</small></h1>
          <p class="hero-sub">本站建于2026/7/27。</p>

          <div class="hero-actions">
            <button class="btn" onclick="scrollToSection('logs')">查看日志</button>
            <button class="btn secondary" onclick="scrollToSection('contact')">留言联系</button>
          </div>

          <div class="ribbon" aria-hidden="true">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" style="filter:drop-shadow(0 4px 8px rgba(200,150,220,0.08));">
              <path d="M12 2l2.5 6H22l-5 3.8L18.8 22 12 17.8 5.2 22 7 11.8 2 8h7.5L12 2z" fill="#FFF0F8" opacity="0.95"/>
            </svg>
            日志记录
          </div>
        </div>

        <div class="hero-right" aria-hidden="true">
          <div class="scene" id="scene">
            <div class="stars" id="stars"></div>

            <div class="castle" id="castle">
              <!-- simplified castle svg -->
              <svg viewBox="0 0 640 420" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet">
                <defs>
                  <linearGradient id="gSky" x1="0" x2="1"><stop offset="0" stop-color="#E9F6FF"/><stop offset="1" stop-color="#F9EEFF"/></linearGradient>
                </defs>
                <rect x="0" y="0" width="640" height="420" rx="24" fill="url(#gSky)" opacity="0.95"/>
              </svg>
            </div>

            <div class="crystals" id="crystals">
              <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <defs><linearGradient id="c1" x1="0" x2="1"><stop offset="0" stop-color="#FFEFF8"/><stop offset="1" stop-color="#E7F7FF"/></linearGradient></defs>
                <g transform="translate(10,8) scale(0.9)"><polygon points="40,10 70,60 10,60" fill="url(#c1)" opacity="0.95"/></g>
              </svg>
            </div>

            <div class="fairy" id="fairy">
              <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <g transform="translate(8,8) scale(0.9)"><circle cx="50" cy="40" r="22" fill="#FFF8F9" opacity="0.98"/></g>
              </svg>
            </div>

          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" aria-labelledby="about-h" class="container">
      <div class="about">
        <div class="avatar" aria-hidden="true">
          <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
            <defs><linearGradient id="ag" x1="0" x2="1"><stop offset="0" stop-color="#FFF7FF"/><stop offset="1" stop-color="#FFEFD6"/></linearGradient></defs>
            <rect width="100%" height="100%" rx="18" fill="url(#ag)"/>
            <g transform="translate(30,28)" fill="#5F4967">
              <ellipse cx="70" cy="60" rx="24" ry="28" fill="#fff7fb" />
              <path d="M50 100 q40 36 80 0" fill="#FFEFEF" opacity="0.9"/>
            </g>
          </svg>
        </div>

        <div class="about-card">
          <h3 id="about-h">你好，我是Nacy。</h3>
          <p>物种：智人（Homo Sapiens)</p>
          <p>活跃时期：白天</p>
          <p>技术依赖：每天触摸玻璃屏幕超过6小时</p>
          <p>日常消耗：每日约2000千卡食物</p>

          <div class="skill-badges" aria-hidden="true">
            <div class="badge">活着</div>
            <div class="badge">吃饭</div>
            <div class="badge">呼吸</div>
            <div class="badge">睡觉</div>
            <div class="badge">不思考</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills" class="container">
      <h3 style="margin-bottom:18px">日志目录</h3>
      <div class="skills-grid" role="list">
        <div class="skill-card" role="listitem">
          <h4>第一章：千年之后</h4>
          <p style="margin:6px 0;color:#6b5b7d">千年之后，如果人类文明还存在。</p>
          <div class="progress"><i style="width:92%"></i></div>
        </div>
        <div class="skill-card" role="listitem">
          <h4>第二章：我的思考</h4>
          <p style="margin:6px 0;color:#6b5b7d">基于宇宙大爆炸对活着意义的思考和论证。</p>
          <div class="progress"><i style="width:86%"></i></div>
        </div>
        <div class="skill-card" role="listitem">
          <h4>第三章：诗神现世。</h4>
          <p style="margin:6px 0;color:#6b5b7d">诗神（自封）的诗词鉴赏。</p>
          <div class="progress"><i style="width:88%"></i></div>
        </div>
      </div>
    </section>

    <!-- Logs (替代原 Works Gallery) -->
    <section id="logs" class="container" aria-labelledby="logs-h">
      <h3 id="logs-h" style="margin-bottom:18px">赛博日志</h3>

      <div class="logs-list" id="logsList">
        <article class="log-entry" aria-labelledby="log-1-title">
          <div class="log-meta" aria-hidden="true">
            <div class="log-date">2026-07-27</div>
            <div class="log-tags">
              <span class="pill">千年之后</span>
              <span class="pill">人类文明</span>
            </div>
          </div>
          <div class="log-body">
            <h4 id="log-1-title" class="log-title">千年之后，如果人类文明还存在</h4>
            <p class="log-excerpt">本次尝试以低对比度的紫粉与奶油金为主，控制高光区域的柔化，重点在于云朵边框的渐变自然过渡与星光的层次感处理。</p>
            <div class="log-actions">
              <button class="btn" onclick="openLog(1)">阅读全文</button>
              <div style="color:#7a6a85;font-size:13px">阅读需 2 分钟</div>
            </div>
          </div>
          <div class="log-thumb" aria-hidden="true">
            <!-- decorative svg placeholder -->
            <svg width="100%" height="100%" viewBox="0 0 160 110" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
              <defs><linearGradient id="lg1" x1="0" x2="1"><stop offset="0" stop-color="#FDEFF8"/><stop offset="1" stop-color="#E8F6FF"/></linearGradient></defs>
              <rect width="100%" height="100%" rx="8" fill="url(#lg1)"/>
              <text x="50%" y="52%" font-family="Poppins,Arial" font-size="12" fill="#6b5b79" text-anchor="middle">暮光城堡 · 练习图</text>
            </svg>
          </div>
        </article>

        <article class="log-entry" aria-labelledby="log-2-title">
          <div class="log-meta" aria-hidden="true">
            <div class="log-date">2026-06-04</div>
            <div class="log-tags">
              <span class="pill">思考</span>
              <span class="pill">宇宙</span>
            </div>
          </div>
          <div class="log-body">
            <h4 id="log-2-title" class="log-title">基于宇宙大爆炸对活着意义的思考和论证</h4>
            <p class="log-excerpt">记录了在 CSS 与少量 JS 中实现星光 twinkle、鼠标视差与卡片悬浮光影的实现思路与性能优化要点。</p>
            <div class="log-actions">
              <button class="btn" onclick="openLog(2)">阅读全文</button>
              <div style="color:#7a6a85;font-size:13px">阅读需 3 分钟</div>
            </div>
          </div>
          <div class="log-thumb" aria-hidden="true">
            <svg width="100%" height="100%" viewBox="0 0 160 110" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
              <rect width="100%" height="100%" rx="8" fill="#FFF8F5"/>
              <text x="50%" y="52%" font-family="Poppins,Arial" font-size="12" fill="#6b5b79" text-anchor="middle">交互笔记</text>
            </svg>
          </div>
        </article>

        <article class="log-entry" aria-labelledby="log-3-title">
          <div class="log-meta" aria-hidden="true">
            <div class="log-date">2026-05-10</div>
            <div class="log-tags">
              <span class="pill">诗神</span>
              <span class="pill">诗歌</span>
            </div>
          </div>
          <div class="log-body">
            <h4 id="log-3-title" class="log-title">诗神（自封）的诗词鉴赏。</h4>
            <p class="log-excerpt">早期草稿主要围绕“轻盈”与“梦幻”两点，尝试不同羽翼造型与配色方案，记录了 6 版小稿的优缺点。</p>
            <div class="log-actions">
              <button class="btn" onclick="openLog(3)">阅读全文</button>
              <div style="color:#7a6a85;font-size:13px">阅读需 4 分钟</div>
            </div>
          </div>
          <div class="log-thumb" aria-hidden="true">
            <svg width="100%" height="100%" viewBox="0 0 160 110" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
              <rect width="100%" height="100%" rx="8" fill="#FFF4FF"/>
              <text x="50%" y="52%" font-family="Poppins,Arial" font-size="12" fill="#6b5b79" text-anchor="middle">角色草稿</text>
            </svg>
          </div>
        </article>

        <article class="log-entry" aria-labelledby="log-4-title">
          <div class="log-meta" aria-hidden="true">
            <div class="log-date">2026-04-01</div>
            <div class="log-tags">
              <span class="pill">待补充</span>
              <span class="pill">素材库</span>
            </div>
          </div>
          <div class="log-body">
            <h4 id="log-4-title" class="log-title">本段待补充</h4>
            <p class="log-excerpt">整理并分类了可复用的星光/云朵/丝带/蝴蝶结素材，并记录了导出 web-friendly SVG/PNG 的流程与命名规范。</p>
            <div class="log-actions">
              <button class="btn" onclick="openLog(4)">阅读全文</button>
              <div style="color:#7a6a85;font-size:13px">阅读需 2 分钟</div>
            </div>
          </div>
          <div class="log-thumb" aria-hidden="true">
            <svg width="100%" height="100%" viewBox="0 0 160 110" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
              <rect width="100%" height="100%" rx="8" fill="#F9F1FF"/>
              <text x="50%" y="52%" font-family="Poppins,Arial" font-size="12" fill="#6b5b79" text-anchor="middle">素材笔记</text>
            </svg>
          </div>
        </article>

      </div>

      <!-- a simple modal for reading logs -->
      <div id="logModal" aria-hidden="true" style="display:none;position:fixed;inset:0;background:rgba(24,12,36,0.45);backdrop-filter: blur(6px);z-index:120;align-items:center;justify-content:center;padding:24px;">
        <div style="max-width:880px;width:100%;background:linear-gradient(180deg,rgba(255,255,255,0.98),rgba(255,255,255,0.95));border-radius:18px;padding:20px;box-shadow:0 30px 80px rgba(60,20,90,0.2);position:relative;">
          <button onclick="closeLog()" aria-label="关闭" style="position:absolute;right:14px;top:14px;border:none;background:transparent;font-weight:700;color:#5a3f65;cursor:pointer">✕</button>
          <h3 id="modalTitle" style="margin-top:6px;color:#3b2b4a"></h3>
          <div id="modalDate" style="color:#6b5b7d;font-size:13px;margin-bottom:12px"></div>
          <div id="modalContent" style="color:#5e5168;line-height:1.7"></div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="container">
      <h3 style="margin-bottom:18px">留言与评论</h3>
      <div class="contact-wrap">
        <div class="contact-card">
          <form id="contactForm" onsubmit="submitForm(event)">
            <div style="display:flex;gap:12px;">
              <div style="flex:1"><label class="visually-hidden">姓名</label><input type="text" id="name" placeholder="你的名字（必填）" required></div>
              <div style="flex:1"><label class="visually-hidden">邮箱</label><input type="email" id="email" placeholder="邮箱（必填）" required></div>
            </div>
            <div style="margin-top:12px">
              <textarea id="message" placeholder="写下你的需求/留言，我会在 1-2 个工作日内回复 😊" required></textarea>
            </div>
            <div style="margin-top:12px;display:flex;gap:12px;align-items:center">
              <button class="btn" type="submit">发送消息</button>
              <div style="color:#7a6a85;font-size:13px">或发送邮件：<strong style="color:#5a3f65">lhylucy9816@163.com</strong></div>
            </div>
          </form>
        </div>

        <div style="width:360px">
          <div class="contact-card" style="padding:16px;">
            <h4 style="margin-top:0">联系方式</h4>
            <p style="color:#6c5a77;margin:6px 0">位于：猎户座-M42</p>
            <p style="margin:6px 0;color:#6c5a77">期待你的来信。</p>
            <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap">
              <div class="badge">Figma</div><div class="badge">SVG 动效</div><div class="badge">CSS / JS</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="container">
      <div class="footer-inner">
        <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px">
          <div>
            <div style="font-weight:700">Nacy的赛博世界</div>
            <div style="color:#6b586f;font-size:13px">© 2026 Cahad — 所有内容归作者所有</div>
          </div>
          <div style="display:flex;gap:10px;align-items:center">
            <a href="#" aria-label="微博" title="微博" style="color:var(--muted)">微博</a>
            <a href="#" aria-label="Dribbble" title="Dribbble" style="color:var(--muted)">Nacy</a>
            <a href="#" aria-label="邮箱" title="邮箱" style="color:var(--muted)">邮箱</a>
          </div>
        </div>
      </div>
    </footer>

  </main>

  <div class="toast" id="toast">消息已发送，感谢你的联系 ✨</div>

  <script>
    // Smooth scroll
    function scrollToSection(id){
      const el = document.getElementById(id);
      if(el) el.scrollIntoView({behavior:'smooth', block:'start'});
    }

    // Form submit demo
    function submitForm(e){
      e.preventDefault();
      const t = document.getElementById('toast');
      t.style.display='block';
      t.style.opacity='1';
      setTimeout(()=>{ t.style.opacity='0'; setTimeout(()=>t.style.display='none',300) }, 2600);
      document.getElementById('contactForm').reset();
    }

    // Create twinkling stars in scene
    (function createStars(){
      const starWrap = document.getElementById('stars');
      if(!starWrap) return;
      const count = 28;
      for(let i=0;i<count;i++){
        const s = document.createElement('div');
        s.className='star';
        const left = Math.random()*100;
        const top = Math.random()*100;
        const size = 1 + Math.random()*3;
        s.style.left = left + '%';
        s.style.top = top + '%';
        s.style.width = size + 'px';
        s.style.height = size + 'px';
        s.style.animationDuration = (2 + Math.random()*3) + 's';
        s.style.animationDelay = Math.random()*3 + 's';
        starWrap.appendChild(s);
      }
    })();

    // Parallax subtle tilt based on mouse move
    (function sceneParallax(){
      const scene = document.getElementById('scene');
      const items = [
        document.getElementById('castle'),
        document.getElementById('fairy'),
        document.getElementById('crystals')
      ];
      if(!scene) return;
      scene.addEventListener('mousemove', (e) => {
        const r = scene.getBoundingClientRect();
        const px = (e.clientX - r.left) / r.width - 0.5;
        const py = (e.clientY - r.top) / r.height - 0.5;
        items.forEach((it, idx) => {
          if(!it) return;
          const depth = (idx+1) * 4;
          const tx = px * depth;
          const ty = py * depth * -1;
          it.style.transform = `translate3d(${tx}px, ${ty}px, 0) rotate(${tx*0.4}deg)`;
        });
      });
      scene.addEventListener('mouseleave', ()=>{
        items.forEach(it=> { if(it) it.style.transform='none' });
      });
    })();

    // Tiny logs content store (could be loaded from CMS/API)
    const LOGS = {
      1: {
        title: "暮光城堡 · 调色与光影练习",
        date: "2026-07-20",
        content: "<p>本次尝试以低对比度的紫粉与奶油金为主，控制高光区域的柔化，重点在于云朵边框的渐变自然过渡与星光的层次感处理。</p><p>实践要点：</p><ul><li>以半透明的层叠渐变构建云朵边界，减少硬边缘。</li><li>将星光做成小尺寸重复图层，并使用不同透明度与模糊半径以增强深度感。</li><li>在页面实现时使用 CSS 的合成层（transform/opacity）来降低重绘成本。</li></ul>",
      },
      2: {
        title: "网站首页交互微动效实现笔记",
        date: "2026-06-04",
        content: "<p>记录了如何在保证性能的前提下，实现星光 twinkle、鼠标视差与卡片悬浮光影。</p><p>要点：</p><ol><li>尽量使用 CSS 动画与 will-change 优化；JS 事件中只更新 transform。</li><li>星光数量可根据屏幕大小动态调整，移动端降低数量与复杂度。</li><li>卡片阴影使用渐进式模糊，避免频繁 layout 更新。</li></ol>",
      },
      3: {
        title: "羽翼小仙子 · 角色设计草稿",
        date: "2026-05-10",
        content: "<p>角色草稿阶段关注体态与羽翼形态的可读性。共尝试了 6 个变体，最终选用轻薄羽毛、尾部轻卷形态。</p><p>灵感来源：经典绘本中针对轻盈感的笔触处理，配色上采用低对比的奶油金高光与淡紫阴影。</p>",
      },
      4: {
        title: "创建梦幻素材库 · 光斑与云朵资源",
        date: "2026-04-01",
        content: "<p>整理并分类了可复用的星光/云朵/丝带/蝴蝶结素材，记录导出 web-friendly SVG/PNG 的流程与命名规范。</p><p>建议：为每个素材提供 1x/2x PNG 与独立 SVG，同时记录作者许可与用途说明。</p>",
      }
    };

    // Modal open/close
    function openLog(id){
      const modal = document.getElementById('logModal');
      const mTitle = document.getElementById('modalTitle');
      const mDate = document.getElementById('modalDate');
      const mContent = document.getElementById('modalContent');
      const entry = LOGS[id];
      if(!entry) return;
      mTitle.innerHTML = entry.title;
      mDate.innerHTML = entry.date;
      mContent.innerHTML = entry.content;
      modal.style.display = 'flex';
      setTimeout(()=> modal.setAttribute('aria-hidden','false'), 30);
      document.body.style.overflow = 'hidden';
    }
    function closeLog(){
      const modal = document.getElementById('logModal');
      modal.setAttribute('aria-hidden','true');
      modal.style.display = 'none';
      document.body.style.overflow = '';
    }

    // accessibility: close modal with Esc
    document.addEventListener('keydown', (e) => {
      if(e.key === 'Escape') {
        const modal = document.getElementById('logModal');
        if(modal && modal.style.display === 'flex') closeLog();
      }
      if(e.key === 'Tab') document.body.classList.add('user-tabbing');
    });

  </script>
</body>
</html>
