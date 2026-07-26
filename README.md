<welcome>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Happy Time · 博客</title>
  <meta name="description" content="Happy Time — 简单静态博客示例（单文件、粉红主题）" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg-1: #ffeff7;
      --bg-2: #ffe6f0;
      --card: rgba(255,255,255,0.85);
      --accent: #ff6fa3;
      --muted: rgba(0,0,0,0.55);
      --glass: rgba(255,255,255,0.06);
      --shadow: 0 8px 30px rgba(107,0,56,0.18);
    }
    html,body{height:100%;margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial;color:#2b001f;background:linear-gradient(135deg,var(--bg-1),var(--bg-2));-webkit-font-smoothing:antialiased}
    a{color:var(--accent);text-decoration:none}
    .wrap{max-width:1000px;margin:28px auto;padding:20px;box-sizing:border-box}
    header{display:flex;align-items:center;justify-content:space-between;gap:16px;margin-bottom:18px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:52px;height:52px;border-radius:12px;background:linear-gradient(135deg,#ff9cc8,#ff6fa3);display:flex;align-items:center;justify-content:center;color:white;font-weight:700;box-shadow:0 6px 16px rgba(255,111,163,0.24)}
    .title{font-size:20px;font-weight:700;color:#400022}
    .subtitle{font-size:12px;color:var(--muted)}
    nav{display:flex;gap:12px;align-items:center}
    button.btn{background:transparent;border:1px solid rgba(67,0,28,0.06);padding:8px 12px;border-radius:10px;font-weight:600;color:#400022;cursor:pointer}
    main{display:grid;grid-template-columns:340px 1fr;gap:18px}
    .left{position:sticky;top:24px;height:calc(100vh - 56px);overflow:auto;padding-right:6px}
    .search{display:flex;gap:8px;margin-bottom:12px}
    input.search{flex:1;padding:10px;border-radius:10px;border:1px solid rgba(0,0,0,0.06);background:transparent}
    .card{background:var(--card);border-radius:12px;padding:12px;box-shadow:var(--shadow);margin-bottom:12px}
    .post-item{display:flex;flex-direction:column;gap:8px;padding:10px;border-radius:10px;background:linear-gradient(180deg,rgba(255,255,255,0.9),rgba(255,255,255,0.86));cursor:pointer;border:1px solid rgba(255,111,163,0.06)}
    .post-title{font-weight:700;color:#400022}
    .post-meta{font-size:12px;color:var(--muted)}
    .mainview{min-height:60vh;padding:14px}
    .article-header{display:flex;flex-direction:column;gap:6px;margin-bottom:12px}
    .article-title{font-size:28px;color:#290018;margin:0}
    .article-date{font-size:13px;color:var(--muted)}
    .article-body{line-height:1.75;color:#40142a}
    .comment-box{margin-top:18px}
    textarea{width:100%;min-height:88px;padding:10px;border-radius:8px;border:1px solid rgba(0,0,0,0.06)}
    input[type="text"]{width:100%;padding:8px;border-radius:8px;border:1px solid rgba(0,0,0,0.06)}
    .comment-list{margin-top:12px;display:flex;flex-direction:column;gap:8px}
    .comment-item{background:rgba(255,255,255,0.95);padding:10px;border-radius:8px;border:1px solid rgba(0,0,0,0.03)}
    footer{margin-top:26px;text-align:center;color:var(--muted);font-size:13px}
    @media (max-width:920px){
      main{grid-template-columns:1fr; }
      .left{position:relative;height:auto}
      .wrap{padding:12px}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo">HT</div>
        <div>
          <div class="title">Happy Time</div>
          <div class="subtitle">it is my happy time — 粉红主题单页博客</div>
        </div>
      </div>

      <nav>
        <button class="btn" id="homeBtn">首页</button>
        <button class="btn" id="aboutBtn">关于</button>
        <a class="btn" href="#" id="domainBtn">绑定域名部署</a>
      </nav>
    </header>

    <main>
      <aside class="left">
        <div class="card">
          <div style="font-weight:700;margin-bottom:8px">文章列表</div>
          <div class="search">
            <input class="search" id="searchInput" placeholder="搜索标题或标签..." />
            <button class="btn" id="clearSearchBtn">清除</button>
          </div>
          <div id="postsList"></div>
        </div>

        <div class="card">
          <div style="font-weight:700;margin-bottom:8px">标签</div>
          <div id="tagsWrap" style="display:flex;gap:8px;flex-wrap:wrap"></div>
        </div>
      </aside>

      <section class="mainview card" id="contentArea">
        <!-- 主内容由 JS 渲染 -->
        <div id="welcomeView">
          <h2 style="margin-top:0;color:#400022">欢迎来到 Happy Time</h2>
          <p style="color:var(--muted)">这是我的个人网站。</p>
          <p>点击左侧文章查看我的博客内容。</p>
        </div>

        <div id="postView" style="display:none">
          <!-- article content injected here -->
        </div>

        <div id="aboutView" style="display:none">
          <h3 style="margin-top:0;color:#400022">关于</h3>
          <p style="color:var(--muted)">这是一个把 Next.js 博客转换为单文件静态网站的示例，主题为粉红色。页面包含：文章列表、文章详情、客户本地评论（localStorage），无需后端即可在本地或静态主机运行。</p>
          <h4 style="margin-bottom:6px">部署建议</h4>
          <ul style="color:var(--muted);line-height:1.6">
            <li>把本文件上传到你的服务器（或 GitHub Pages / Netlify 等静态站点托管）即可对外提供访问。</li>
            <li>如果想要 HTTPS 与自定义域名：将文件托管到支持 HTTPS 的静态托管服务并在 DNS 中将域名指向该服务。</li>
            <li>若您需要后端评论或多用户支持，请改用我们之前准备的 Next.js + Prisma 项目。</li>
          </ul>
        </div>

      </section>
    </main>

    <footer>
      © <span id="year"></span> Happy Time — 本地静态站点 · 粉红主题
    </footer>
  </div>

  <script>
    // Sample posts (converted from your MDX sample)
    const posts = [
      {
        slug: "welcome",
        title: "欢迎来到我的博客",
        date: "2026-07-26",
        summary: "哈哈哈哈哈我的第二个博客终于写完了。",
        tags: ["demo", "nextjs"],
        content: `
<p>这是第一篇示例文章，支持 <strong>静态 HTML</strong> 内容。</p>
<p>你可以写 Markdown （已转为 HTML）、内嵌图片或更多说明。</p>
<p>此页面为单文件静态站点示例，评论保存在本地浏览器（localStorage）。</p>
`
      },
      {
        slug: "blog-第一篇",
        title: "这是本博客诞生的第一天",
        date: "2026-07-27",
        summary: "随便做了一个主题，不知道你喜不喜欢，反正我很喜欢。",
        tags: ["第一篇","web"],
        content: `
<p>推荐使用 Next.js + MDX + Prisma（Postgres）构建一个可扩展的博客。</p>
<ul>
<li>前端：Next.js（App Router）、MDX 渲染</li>
<li>后端：Postgres + Prisma；缓存 Redis，可选 Algolia 搜索</li>
<li>部署：Vercel 或 Docker/Trafik 自托管</li>
</ul>
<p>上面是简要概览；原项目还包含评论 API、示例 MDX 内容与部署脚本。</p>
`
      }
    ];

    // utilities
    const el = id => document.getElementById(id);
    const postsListEl = el('postsList');
    const tagsWrapEl = el('tagsWrap');
    const contentArea = el('contentArea');
    const postView = el('postView');
    const welcomeView = el('welcomeView');
    const aboutView = el('aboutView');
    const searchInput = el('searchInput');
    const clearSearchBtn = el('clearSearchBtn');
    const yearEl = el('year');

    yearEl.textContent = new Date().getFullYear();

    // render posts list
    function renderPosts(filter = '') {
      postsListEl.innerHTML = '';
      const q = filter.trim().toLowerCase();
      const filtered = posts.filter(p => {
        if (!q) return true;
        return p.title.toLowerCase().includes(q) || (p.tags || []).join(' ').toLowerCase().includes(q) || (p.summary||'').toLowerCase().includes(q);
      });
      if (filtered.length === 0) {
        postsListEl.innerHTML = '<div style="color:var(--muted);padding:8px">无匹配文章</div>';
        return;
      }
      filtered.forEach(p => {
        const item = document.createElement('div');
        item.className = 'post-item';
        item.innerHTML = `
          <div>
            <div class="post-title">${escapeHTML(p.title)}</div>
            <div class="post-meta">${escapeHTML(p.date)} · ${escapeHTML(p.tags.join(', '))}</div>
            <div style="color:var(--muted);margin-top:6px">${escapeHTML(p.summary)}</div>
          </div>
        `;
        item.addEventListener('click', () => openPost(p.slug));
        postsListEl.appendChild(item);
      });
    }

    // render tags
    function renderTags() {
      const tagSet = new Set();
      posts.forEach(p => (p.tags || []).forEach(t => tagSet.add(t)));
      tagsWrapEl.innerHTML = '';
      Array.from(tagSet).sort().forEach(t => {
        const b = document.createElement('button');
        b.className = 'btn';
        b.style.background = 'transparent';
        b.textContent = t;
        b.addEventListener('click', () => {
          searchInput.value = t;
          renderPosts(t);
        });
        tagsWrapEl.appendChild(b);
      });
    }

    // open post view
    function openPost(slug) {
      const p = posts.find(x => x.slug === slug);
      if (!p) return;
      welcomeView.style.display = 'none';
      aboutView.style.display = 'none';
      postView.style.display = 'block';
      postView.innerHTML = `
        <div class="article-header">
          <div style="display:flex;justify-content:space-between;align-items:flex-start;gap:12px">
            <div>
              <h1 class="article-title">${escapeHTML(p.title)}</h1>
              <div class="article-date">${escapeHTML(p.date)} · ${escapeHTML(p.tags.join(', '))}</div>
            </div>
            <div>
              <button class="btn" id="backBtn">返回</button>
            </div>
          </div>
        </div>
        <div class="article-body">${p.content}</div>

        <div class="comment-box card">
          <h3 style="margin-top:0;color:#400022">评论</h3>
          <div style="display:grid;gap:8px">
            <input id="commentName" type="text" placeholder="你的名字" />
            <textarea id="commentBody" placeholder="写下你的评论..."></textarea>
            <div style="display:flex;gap:8px;align-items:center">
              <button class="btn" id="submitComment">提交评论</button>
              <button class="btn" id="clearComments">清空评论（本地）</button>
            </div>
          </div>
          <div class="comment-list" id="commentList"></div>
        </div>
      `;
      document.getElementById('backBtn').addEventListener('click', () => {
        postView.style.display = 'none';
        welcomeView.style.display = 'block';
      });

      // comment handlers
      const cname = el('commentName'), cbody = el('commentBody'), csubmit = el('submitComment'), clist = el('commentList'), clearBtn = el('clearComments');
      function getComments() {
        try {
          const raw = localStorage.getItem('comments_' + p.slug);
          return raw ? JSON.parse(raw) : [];
        } catch (e) { return []; }
      }
      function saveComments(arr) {
        localStorage.setItem('comments_' + p.slug, JSON.stringify(arr));
      }
      function renderComments() {
        const arr = getComments();
        if (arr.length === 0) {
          clist.innerHTML = '<div style="color:var(--muted)">还没有评论</div>';
          return;
        }
        clist.innerHTML = '';
        arr.slice().reverse().forEach(c => {
          const d = document.createElement('div');
          d.className = 'comment-item';
          d.innerHTML = `<div style="font-weight:700">${escapeHTML(c.name)} <span style="font-weight:400;color:var(--muted);font-size:12px">· ${new Date(c.createdAt).toLocaleString()}</span></div><div style="margin-top:6px">${escapeHTML(c.body)}</div>`;
          clist.appendChild(d);
        });
      }
      csubmit.addEventListener('click', () => {
        const name = (cname.value || '').trim();
        const body = (cbody.value || '').trim();
        if (!name || !body) return alert('请输入姓名与评论内容');
        const arr = getComments();
        arr.push({ name, body, createdAt: new Date().toISOString() });
        saveComments(arr);
        cname.value = ''; cbody.value = '';
        renderComments();
      });
      clearBtn.addEventListener('click', () => {
        if (!confirm('确认清空此文章的本地评论吗？')) return;
        localStorage.removeItem('comments_' + p.slug);
        renderComments();
      });

      renderComments();
      // scroll to top of content area
      contentArea.scrollIntoView({behavior:'smooth'});
    }

    function escapeHTML(s){ return String(s||'').replace(/[&<>"']/g, c=>({ '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;' })[c]); }

    // initial
    renderPosts();
    renderTags();

    // search
    searchInput.addEventListener('input', e => renderPosts(e.target.value));
    clearSearchBtn.addEventListener('click', () => { searchInput.value=''; renderPosts(); });

    // header buttons
    document.getElementById('homeBtn').addEventListener('click', () => {
      postView.style.display='none'; aboutView.style.display='none'; welcomeView.style.display='block';
      window.scrollTo({top:0,behavior:'smooth'});
    });
    document.getElementById('aboutBtn').addEventListener('click', () => {
      welcomeView.style.display='none'; postView.style.display='none'; aboutView.style.display='block';
      contentArea.scrollIntoView({behavior:'smooth'});
    });
    document.getElementById('domainBtn').addEventListener('click', (e) => {
      e.preventDefault();
      alert('要绑定域名并用 HTTPS 运行，请参考项目 README 中的部署步骤或使用静态主机（GitHub Pages / Netlify）提供的自定义域名功能。');
    });

    // keyboard: press '/' to focus search
    window.addEventListener('keydown', (e) => {
      if (e.key === '/') { e.preventDefault(); searchInput.focus(); }
    });
  </script>
</body>
</html>
