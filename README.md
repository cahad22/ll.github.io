<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>童话梦境 · 个人作品集</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Great+Vibes&display=swap" rel="stylesheet">

  <style>
    /* ========== 变量色彩 ========== */
    :root{
      --bg-1: #F8F9FF; /* 近白乳霜 */
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

    /* Container limiter */
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
    .logo{
      display:flex;
      align-items:center;
      gap:12px;
    }
    .logo .mark{
      width:46px;height:46px;
      border-radius:12px;
      background: linear-gradient(135deg,var(--pastel-blue),var(--pastel-lav));
      display:flex;
      align-items:center;
      justify-content:center;
      box-shadow: 0 6px 18px rgba(160,140,200,0.12), inset 0 2px 6px rgba(255,255,255,0.5);
      border: 1px solid rgba(255,255,255,0.6);
    }
    .logo .mark svg{filter:drop-shadow(0 2px 6px rgba(200,170,255,0.12))}
    .logo .title{
      font-weight:600;
      letter-spacing:0.2px;
      color:#4a3f5b;
    }
    nav.topnav{
      display:flex;
      gap:12px;
      align-items:center;
    }
    nav.topnav a{
      padding:10px 14px;
      border-radius:12px;
      color:var(--muted);
      font-weight:500;
      transition:all .28s cubic-bezier(.2,.9,.2,1);
    }
    nav.topnav a:hover{
      transform:translateY(-4px);
      box-shadow: 0 6px 18px rgba(150,120,210,0.06), 0 0 18px rgba(255,240,210,0.03) inset;
      color:#412B5B;
      background: linear-gradient(90deg, rgba(255,255,255,0.45), rgba(255,255,255,0.15));
      border:1px solid rgba(255,255,255,0.5);
    }
    .cta{
      background: linear-gradient(90deg, rgba(255,238,210,0.9), rgba(255,245,230,0.6));
      padding:8px 16px;
      border-radius:14px;
      box-shadow: 0 8px 20px rgba(240,200,140,0.08);
      font-weight:600;
    }

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
    .hero-inner{
      display:flex;
      gap:48px;
      align-items:center;
      width:100%;
    }
    .hero-left{
      flex:0 0 540px;
      max-width:60%;
    }
    .kicker{
      display:inline-flex;
      align-items:center;
      gap:10px;
      background: linear-gradient(90deg, rgba(255,255,255,0.6), rgba(255,255,255,0.2));
      padding:8px 12px;
      border-radius:999px;
      font-weight:600;
      color:#5b4b67;
      box-shadow: 0 6px 18px rgba(120,90,160,0.06);
      width:max-content;
    }
    .hero-title{
      margin-top:18px;
      font-size:46px;
      line-height:1.05;
      letter-spacing:-1px;
      color:#392a4d;
      font-weight:700;
    }
    .hero-sub{
      margin-top:12px;
      color:#675e78;
      max-width:46ch;
    }

    .hero-actions{
      margin-top:22px;
      display:flex;
      gap:12px;
      align-items:center;
    }
    .btn{
      padding:12px 18px;
      border-radius:14px;
      border:none;
      cursor:pointer;
      font-weight:600;
      background:linear-gradient(90deg, rgba(231,211,255,0.85), rgba(255,240,245,0.72));
      box-shadow: 0 8px 26px rgba(170,120,220,0.08);
      transition:all .28s cubic-bezier(.2,.9,.2,1);
      position:relative;
      overflow:visible;
    }
    .btn:hover{ transform:translateY(-6px); box-shadow: 0 18px 40px rgba(180,120,230,0.12)}
    .btn.secondary{
      background: linear-gradient(90deg, rgba(255,255,255,0.65), rgba(255,255,255,0.4));
      border:1px solid rgba(255,255,255,0.6);
      color:#5a4666;
    }

    /* Soft decorative ribbon under actions */
    .ribbon{
      margin-top:18px;
      width:220px;
      height:36px;
      border-radius:999px;
      background: linear-gradient(90deg, rgba(255,245,238,0.8), rgba(255,240,250,0.6));
      box-shadow: 0 8px 20px rgba(200,160,220,0.06);
      display:flex;
      align-items:center;
      justify-content:center;
      color:#6b5571;
      font-size:13px;
      gap:8px;
    }

    /* Hero right - illustration area */
    .hero-right{
      flex:1;
      position:relative;
      min-height:540px;
      display:flex;
      align-items:center;
      justify-content:center;
    }
    .scene{
      width:620px;
      max-width:92%;
      aspect-ratio: 16/10;
      border-radius:28px;
      background:
        radial-gradient(circle at 10% 20%, rgba(255,255,255,0.6), transparent 8%),
        linear-gradient(180deg,var(--pastel-blue),var(--pastel-lav));
      box-shadow: 0 20px 60px rgba(90,60,140,0.08), inset 0 -8px 20px rgba(255,255,255,0.25);
      position:relative;
      overflow:visible;
      padding:18px;
    }
    /* Cloud frame */
    .scene::before{
      content:"";
      position:absolute;
      left:-12px;right:-12px;top:-12px;bottom:-12px;
      border-radius:34px;
      background:
        radial-gradient(80% 40% at 10% 0%, rgba(255,255,255,0.28), transparent 20%),
        linear-gradient(180deg, rgba(255,255,255,0.06), transparent 30%);
      z-index:0;
      pointer-events:none;
      mask-image: radial-gradient(circle at top center, rgba(0,0,0,1) 40%, rgba(0,0,0,0.9) 60%, rgba(0,0,0,0));
    }

    /* Floating castle & fairy (SVG wrappers) */
    .castle, .fairy, .crystals{
      position:absolute;
      z-index:2;
      transform-style:preserve-3d;
      transition:transform .18s ease-out;
    }
    .castle{
      left:18%;
      top:10%;
      width:340px;
      opacity:0.98;
      filter:drop-shadow(0 10px 30px rgba(120,80,200,0.12));
    }
    .fairy{
      right:10%;
      bottom:6%;
      width:160px;
      filter:drop-shadow(0 8px 24px rgba(255,200,230,0.08));
    }
    .crystals{
      left:62%;
      top:56%;
      width:130px;
      opacity:0.95;
    }

    /* twinkle stars overlay */
    .stars {
      position:absolute;
      inset:8px;
      pointer-events:none;
      z-index:1;
      border-radius:20px;
      overflow:hidden;
    }
    .star {
      position:absolute;
      width:4px;height:4px;
      background: radial-gradient(circle, #fff 0%, rgba(255,255,255,0.8) 30%, rgba(255,255,255,0.2) 60%, transparent 100%);
      border-radius:50%;
      filter:blur(0.6px);
      opacity:0.85;
      animation: twinkle 3.6s infinite ease-in-out;
    }
    @keyframes twinkle {
      0%,100%{ transform:scale(0.6); opacity:0.6 }
      50%{ transform:scale(1.8); opacity:1 }
    }

    /* ========== Main Sections ========== */
    main{position:relative;z-index:2}
    section{
      padding:48px 0;
    }

    /* About Card */
    .about{
      display:flex;
      gap:28px;
      align-items:flex-start;
      justify-content:space-between;
    }
    .avatar{
      width:220px;
      height:220px;
      border-radius:28px;
      background: linear-gradient(135deg, rgba(255,255,255,0.6), rgba(255,245,255,0.2));
      box-shadow: var(--soft-shadow);
      display:flex;
      align-items:center;
      justify-content:center;
      border:1px solid rgba(255,255,255,0.6);
      overflow:hidden;
      position:relative;
      flex-shrink:0;
    }
    .avatar svg{width:86%;height:86%;}
    .about-card{
      flex:1;
      background: linear-gradient(180deg, rgba(255,255,255,0.6), rgba(255,255,255,0.45));
      border-radius:22px;
      padding:20px;
      box-shadow: var(--card-shadow);
      border:1px solid rgba(255,255,255,0.6);
      position:relative;
      backdrop-filter: blur(6px) saturate(120%);
    }
    .about h3{margin:0 0 8px 0; font-size:20px}
    .about p{color:#5f546f}

    .skill-badges{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      margin-top:14px;
    }
    .badge{
      padding:8px 12px;
      border-radius:999px;
      background: linear-gradient(90deg, rgba(255,255,255,0.6), rgba(255,255,255,0.25));
      box-shadow: 0 8px 18px rgba(140,110,190,0.05);
      color:#5b4868;
      font-weight:600;
    }

    /* Skills Cards */
    .skills-grid{
      display:grid;
      grid-template-columns:repeat(3, 1fr);
      gap:18px;
    }
    .skill-card{
      background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.45));
      border-radius:18px;
      padding:18px;
      box-shadow: var(--soft-shadow);
      border:1px solid rgba(255,255,255,0.6);
      transition:transform .28s ease, box-shadow .28s ease;
    }
    .skill-card:hover{
      transform: translateY(-8px);
      box-shadow: 0 20px 40px rgba(120,90,180,0.08);
    }
    .skill-card h4{margin:0 0 8px 0}
    .progress{
      height:10px;border-radius:999px;background:rgba(120,90,160,0.06);overflow:hidden;
    }
    .progress > i{
      display:block;height:100%;
      background:linear-gradient(90deg, #FFEBB8, #FFD4F8);
      border-radius:inherit;
    }

    /* Gallery - Masonry via columns */
    .gallery{
      column-count:3;
      column-gap:18px;
      width:100%;
    }
    .piece{
      break-inside:avoid;
      margin-bottom:18px;
      border-radius:16px;
      overflow:hidden;
      position:relative;
      background:linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.45));
      border:1px solid rgba(255,255,255,0.6);
      box-shadow: var(--card-shadow);
    }
    .piece img{
      width:100%;height:auto;display:block;
    }
    .piece .caption{
      padding:12px 14px;color:#493C59;font-weight:600;
      font-size:14px;
    }

    /* Contact */
    .contact-wrap{
      display:flex;
      gap:22px;
      align-items:flex-start;
    }
    .contact-card{
      flex:1;
      border-radius:16px;
      padding:18px;
      background: linear-gradient(180deg, rgba(255,255,255,0.62), rgba(255,255,255,0.46));
      border:1px solid rgba(255,255,255,0.6);
      box-shadow: var(--soft-shadow);
    }
    .form-row{display:flex;gap:12px}
    .form-row .field{flex:1}
    input[type=text], input[type=email], textarea{
      width:100%;
      padding:12px 14px;border-radius:12px;border:none;
      background: rgba(255,255,255,0.7);
      box-shadow: inset 0 2px 6px rgba(0,0,0,0.03);
      font-size:14px;color:#4b3f54;
      outline:none;
    }
    textarea{min-height:120px;resize:vertical}

    /* Footer */
    footer{
      padding:30px 0 80px;
      color:#6a586f;
    }
    .footer-inner{
      border-radius:18px;
      padding:18px;
      background:linear-gradient(180deg, rgba(255,255,255,0.55), rgba(255,255,255,0.4));
      box-shadow:var(--soft-shadow);
      border:1px solid rgba(255,255,255,0.6);
    }

    /* tiny toast */
    .toast{
      position:fixed;right:20px;bottom:24px;
      background: linear-gradient(90deg, rgba(255,245,230,0.95), rgba(255,238,255,0.9));
      padding:12px 16px;border-radius:12px;box-shadow:0 10px 28px rgba(120,80,180,0.08);
      display:none;z-index:90;font-weight:600;color:#4a3c58;
    }

    /* responsive-ish for narrower screens (still PC-first) */
    @media (max-width:1100px){
      .hero-inner{flex-direction:column;align-items:flex-start}
      .hero-left{max-width:100%;flex:1}
      .hero-right{width:100%}
      .skills-grid{grid-template-columns:repeat(2,1fr)}
      .gallery{column-count:2}
    }
    @media (max-width:720px){
      header.topbar{top:12px}
      .nav-wrap{padding:8px}
      .hero-title{font-size:32px}
      .skills-grid{grid-template-columns:1fr}
      .gallery{column-count:1}
      .container{padding:0 14px}
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="container nav-wrap" role="navigation" aria-label="主导航">
      <div class="logo">
        <div class="mark" aria-hidden="true">
          <!-- tiny fairy mark -->
          <svg viewBox="0 0 24 24" width="24" height="24" fill="none" aria-hidden="true">
            <defs><linearGradient id="g" x1="0" x2="1"><stop offset="0" stop-color="#fff"/><stop offset="1" stop-color="#FFD8F0"/></linearGradient></defs>
            <path d="M12 3c1.8 2 4 2.5 6 3-1.6 1.6-2 4-1.8 6.2C14.6 11.8 9.8 11.4 7 14c-2-2 .5-6 5-11z" fill="url(#g)" opacity="0.95"/>
          </svg>
        </div>
        <div>
          <div class="title">童话梦境 · Cahad</div>
          <div style="font-size:12px;color:var(--muted)">梦幻插画 & 前端作品集</div>
        </div>
      </div>

      <nav class="topnav" aria-label="主菜单">
        <a href="#about">关于</a>
        <a href="#skills">技能</a>
        <a href="#works">作品</a>
        <a href="#contact">联系</a>
        <a class="cta" href="#works">查看作品</a>
      </nav>
    </div>
  </header>

  <!-- Hero Banner -->
  <main>
    <section class="hero">
      <div class="container hero-inner">
        <div class="hero-left">
          <div class="kicker">梦幻 / 插画 / 交互</div>
          <h1 class="hero-title">欢迎来到我的童话梦境网站<br/><small style="font-weight:500;color:#6b5b79">轻盈的色彩，温柔的光——讲述我的每一个创作故事</small></h1>
          <p class="hero-sub">我是 Cahad，一名热爱绘本式插画与细腻前端界面的设计师，将梦幻童话元素与实用作品集结合，打造轻盈、透亮、低对比度的可感知体验。</p>

          <div class="hero-actions">
            <button class="btn" onclick="scrollToSection('works')">我的作品</button>
            <button class="btn secondary" onclick="scrollToSection('contact')">合作联系</button>
          </div>

          <div class="ribbon" aria-hidden="true">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" style="filter:drop-shadow(0 4px 8px rgba(200,150,220,0.08));">
              <path d="M12 2l2.5 6H22l-5 3.8L18.8 22 12 17.8 5.2 22 7 11.8 2 8h7.5L12 2z" fill="#FFF0F8" opacity="0.95"/>
            </svg>
            童话风 · 轻柔手感 · 透明层次
          </div>
        </div>

        <div class="hero-right" aria-hidden="true">
          <div class="scene" id="scene">
            <div class="stars" id="stars"></div>

            <!-- Floating castle (SVG) -->
            <div class="castle" id="castle">
              <svg viewBox="0 0 640 420" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet">
                <!-- soft sky -->
                <defs>
                  <linearGradient id="gSky" x1="0" x2="1"><stop offset="0" stop-color="#E9F6FF"/><stop offset="1" stop-color="#F9EEFF"/></linearGradient>
                  <linearGradient id="gStone" x1="0" x2="1"><stop offset="0" stop-color="#EDE6FF"/><stop offset="1" stop-color="#FFDFF7"/></linearGradient>
                  <filter id="glow" x="-50%" y="-50%" width="200%" height="200%">
                    <feGaussianBlur stdDeviation="8" result="b"/>
                    <feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge>
                  </filter>
                </defs>

                <rect x="0" y="0" width="640" height="420" rx="24" fill="url(#gSky)" opacity="0.95"/>
                <!-- castle towers -->
                <g transform="translate(80,40) scale(0.9)">
                  <g filter="url(#glow)">
                    <path d="M120 200 L140 140 L160 200 Z" fill="#FFDFF7" opacity="0.9"/>
                  </g>
                  <path d="M40 220 L120 120 L200 220 Z" fill="#F6E9D6" opacity="0.88"/>
                  <rect x="52" y="220" width="256" height="120" rx="18" fill="#FFF5FB" opacity="0.95" stroke="rgba(200,170,220,0.4)"/>
                  <!-- windows -->
                  <g fill="#FFF0F8" opacity="0.9">
                    <rect x="86" y="250" width="28" height="36" rx="6"/>
                    <rect x="136" y="250" width="28" height="36" rx="6"/>
                    <rect x="186" y="250" width="28" height="36" rx="6"/>
                  </g>
                  <!-- small floating island base -->
                  <ellipse cx="180" cy="350" rx="160" ry="28" fill="rgba(255,245,240,0.6)"/>
                </g>

              </svg>
            </div>

            <!-- crystals cluster -->
            <div class="crystals" id="crystals">
              <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <defs>
                  <linearGradient id="c1" x1="0" x2="1"><stop offset="0" stop-color="#FFEFF8"/><stop offset="1" stop-color="#E7F7FF"/></linearGradient>
                </defs>
                <g transform="translate(10,8) scale(0.9)">
                  <polygon points="40,10 70,60 10,60" fill="url(#c1)" opacity="0.95"/>
                  <polygon points="120,20 150,80 90,80" fill="#FFEFE7" opacity="0.95"/>
                </g>
              </svg>
            </div>

            <!-- fairy -->
            <div class="fairy" id="fairy">
              <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                <defs>
                  <linearGradient id="fw" x1="0" x2="1"><stop offset="0" stop-color="#FFF2FE"/><stop offset="1" stop-color="#FFEFD6"/></linearGradient>
                </defs>
                <g transform="translate(8,8) scale(0.9)">
                  <circle cx="50" cy="40" r="22" fill="#FFF8F9" opacity="0.98"/>
                  <path d="M20 80 C40 60, 80 60, 100 80" stroke="#FFD8F0" stroke-width="6" stroke-linecap="round" fill="none" opacity="0.85"/>
                  <ellipse cx="110" cy="92" rx="18" ry="36" fill="#FFF0FF" opacity="0.9"/>
                </g>
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
          <!-- hand-drawn avatar SVG style -->
          <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="ag" x1="0" x2="1"><stop offset="0" stop-color="#FFF7FF"/><stop offset="1" stop-color="#FFEFD6"/></linearGradient>
            </defs>
            <rect width="100%" height="100%" rx="18" fill="url(#ag)"/>
            <g transform="translate(30,28)" fill="#5F4967">
              <ellipse cx="70" cy="60" rx="24" ry="28" fill="#fff7fb" />
              <path d="M50 100 q40 36 80 0" fill="#FFEFEF" opacity="0.9"/>
            </g>
          </svg>
        </div>

        <div class="about-card">
          <h3 id="about-h">你好，我是 Cahad — 童话绘本风的 UI 设计师</h3>
          <p>我的作品揉合手绘插画与前端交互，风格偏轻柔的绘本感，常用元素：星光、水晶、羽翼、浮空城堡与云朵边框。关注画面通透与低对比度，营造浪漫温柔的用户体验。</p>

          <div class="skill-badges" aria-hidden="true">
            <div class="badge">插画 · 绘本</div>
            <div class="badge">UI / UX 设计</div>
            <div class="badge">前端开发 (HTML/CSS/JS)</div>
            <div class="badge">动效设计</div>
            <div class="badge">品牌与故事化叙事</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills" class="container">
      <h3 style="margin-bottom:18px">技能展示</h3>
      <div class="skills-grid" role="list">
        <div class="skill-card" role="listitem">
          <h4>插画 & 手绘</h4>
          <p style="margin:6px 0;color:#6b5b7d">水彩质感、手绘线稿，构图/色彩/角色设计。</p>
          <div class="progress"><i style="width:92%"></i></div>
        </div>
        <div class="skill-card" role="listitem">
          <h4>界面设计</h4>
          <p style="margin:6px 0;color:#6b5b7d">卡片式布局、玻璃质感、低对比柔光配色。</p>
          <div class="progress"><i style="width:86%"></i></div>
        </div>
        <div class="skill-card" role="listitem">
          <h4>前端实现</h4>
          <p style="margin:6px 0;color:#6b5b7d">响应式布局、CSS 动画、交互微动效。</p>
          <div class="progress"><i style="width:88%"></i></div>
        </div>
      </div>
    </section>

    <!-- Works Gallery -->
    <section id="works" class="container">
      <h3 style="margin-bottom:18px">作品画廊</h3>
      <div class="gallery" id="gallery" aria-live="polite">
        <!-- Mock pieces with placeholder gradients -->
        <div class="piece">
          <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='1000'><defs><linearGradient id='a' x1='0' x2='1'><stop offset='0' stop-color='%23FDEFF8'/><stop offset='1' stop-color='%23E8F6FF'/></linearGradient></defs><rect width='100%' height='100%' fill='url(%23a)'/><text x='50%' y='50%' font-family='Poppins,Arial' font-size='36' fill='%236b5b79' text-anchor='middle'>作品 · 童话插画 1</text></svg>" alt="作品插画1">
          <div class="caption">暮光城堡 · 插画</div>
        </div>

        <div class="piece">
          <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='600'><defs><linearGradient id='b' x1='0' x2='1'><stop offset='0' stop-color='%23FFF7EE'/><stop offset='1' stop-color='%23FFF0FF'/></linearGradient></defs><rect width='100%' height='100%' fill='url(%23b)'/><text x='50%' y='50%' font-family='Poppins,Arial' font-size='32' fill='%236b5b79' text-anchor='middle'>童话插画 2</text></svg>" alt="作品插画2">
          <div class="caption">羽翼小仙子 · 插画</div>
        </div>

        <div class="piece">
          <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='900'><defs><linearGradient id='c' x1='0' x2='1'><stop offset='0' stop-color='%23EAF6FF'/><stop offset='1' stop-color='%23FCEFF9'/></linearGradient></defs><rect width='100%' height='100%' fill='url(%23c)'/><text x='50%' y='50%' font-family='Poppins,Arial' font-size='34' fill='%236b5b79' text-anchor='middle'>作品插画 3</text></svg>" alt="作品插画3">
          <div class="caption">星光舞会 · 插画</div>
        </div>

        <!-- repeat a few -->
        <div class="piece">
          <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='700'><rect width='100%' height='100%' fill='%23F8F0FF'/><text x='50%' y='50%' font-family='Poppins,Arial' font-size='34' fill='%236b5b79' text-anchor='middle'>作品插画 4</text></svg>" alt="作品插画4">
          <div class="caption">水晶湖畔 · 插画</div>
        </div>

        <div class="piece">
          <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='950'><rect width='100%' height='100%' fill='%23FFF8F3'/><text x='50%' y='50%' font-family='Poppins,Arial' font-size='34' fill='%236b5b79' text-anchor='middle'>作品插画 5</text></svg>" alt="作品插画5">
          <div class="caption">云朵边界 · 插画</div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="container">
      <h3 style="margin-bottom:18px">留言与合作</h3>
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
              <div style="color:#7a6a85;font-size:13px">或发送邮件：<strong style="color:#5a3f65">hello@yourdomain.com</strong></div>
            </div>
          </form>
        </div>

        <div style="width:360px">
          <div class="contact-card" style="padding:16px;">
            <h4 style="margin-top:0">联系方式</h4>
            <p style="color:#6c5a77;margin:6px 0">位于：温柔的童话小镇 · 远程合作优先</p>
            <p style="margin:6px 0;color:#6c5a77">提供：插画委托 / 品牌 VI / 网页界面及动效实现</p>
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
            <div style="font-weight:700">童话梦境 · Cahad</div>
            <div style="color:#6b586f;font-size:13px">© 2026 Cahad — 所有插画与设计归作者所有</div>
          </div>
          <div style="display:flex;gap:10px;align-items:center">
            <a href="#" aria-label="微博" title="微博" style="color:var(--muted)">微博</a>
            <a href="#" aria-label="Dribbble" title="Dribbble" style="color:var(--muted)">Dribbble</a>
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

    // Generate twinkling stars in scene
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
        // small transforms
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

    // tiny accessibility helper: focus visible
    document.addEventListener('keydown', (e) => {
      if(e.key === 'Tab') document.body.classList.add('user-tabbing');
    });
  </script>
</body>
</html>
