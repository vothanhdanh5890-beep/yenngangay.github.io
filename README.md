# yenngangay.github.io
<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tin Nhóm 5 — Giới thiệu thành viên</title>
  <meta name="description" content="Trang giới thiệu nhóm 5 - danh sách thành viên, mô tả và liên kết" />
  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#7c3aed;
      --glass: rgba(255,255,255,0.04);
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg,#071029 0%,#071936 100%);
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
    }

    header{
      padding:28px 20px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      max-width:1100px;
      margin:0 auto;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:14px;
    }
    .logo{
      width:56px;height:56px;border-radius:10px;
      background:linear-gradient(135deg,var(--accent),#06b6d4);
      display:flex;align-items:center;justify-content:center;
      font-weight:700;color:white;font-size:20px;box-shadow:0 6px 18px rgba(0,0,0,0.45);
    }
    h1.title{
      margin:0;font-size:20px;
      letter-spacing:0.2px;
    }
    p.lead{margin:0;color:var(--muted);font-size:13px}

    main{max-width:1100px;margin:18px auto;padding:18px}

    .controls{
      display:flex;gap:10px;align-items:center;justify-content:space-between;margin-bottom:18px;
      flex-wrap:wrap;
    }
    .search{
      flex:1;min-width:200px;
      display:flex;gap:8px;align-items:center;
      background:var(--glass);padding:8px;border-radius:10px;
    }
    .search input{
      border:0;background:transparent;color:inherit;outline:none;font-size:14px;width:100%;
    }

    .grid{
      display:grid;
      grid-template-columns: repeat(auto-fill,minmax(240px,1fr));
      gap:18px;
    }

    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.04);
      padding:16px;border-radius:14px;
      transition:transform .18s ease,box-shadow .18s ease;
      display:flex;flex-direction:column;gap:12px;
    }
    .card:hover{ transform:translateY(-6px); box-shadow: 0 14px 30px rgba(2,6,23,0.6); }

    .avatar{
      width:84px;height:84px;border-radius:14px;flex-shrink:0;
      background:linear-gradient(135deg,#1f2937,#111827);
      display:inline-flex;align-items:center;justify-content:center;color:#fff;font-weight:700;font-size:28px;
      overflow:hidden;
    }
    .meta{
      display:flex;gap:12px;align-items:center;
    }
    .name{font-weight:700;font-size:16px;margin:0}
    .role{font-size:13px;color:var(--muted);margin:0}
    .desc{font-size:13px;color: #cbd5e1;margin-top:6px}

    .tags{display:flex;gap:8px;flex-wrap:wrap;margin-top:6px}
    .tag{font-size:12px;padding:6px 8px;border-radius:999px;background:rgba(255,255,255,0.03);color:var(--muted)}

    .socials{margin-top:auto;display:flex;gap:8px}
    .btn{
      display:inline-flex;gap:8px;align-items:center;padding:8px 10px;border-radius:10px;border:1px solid rgba(255,255,255,0.04);
      background:transparent;color:inherit;text-decoration:none;font-size:13px;cursor:pointer;
    }
    .btn svg{width:16px;height:16px;opacity:.9}

    footer{max-width:1100px;margin:26px auto;color:var(--muted);font-size:13px;padding:18px}
    @media (max-width:620px){
      .brand h1.title{font-size:16px}
      .avatar{width:64px;height:64px;font-size:22px}
    }
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo">N5</div>
      <div>
        <h1 class="title">Tin Nhóm 5</h1>
        <p class="lead">Trang giới thiệu thành viên — nhóm 5</p>
      </div>
    </div>

    <nav style="display:flex;gap:10px;align-items:center">
      <a href="#" class="btn" onclick="toggleTheme(event)">🌓 Giao diện</a>
      <a href="#" class="btn" target="_blank" rel="noopener">Github</a>
    </nav>
  </header>

  <main>
    <div class="controls">
      <div class="search" role="search" aria-label="Tìm thành viên">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M21 21l-4.35-4.35" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/><circle cx="11" cy="11" r="6" stroke="currentColor" stroke-width="2"/></svg>
        <input id="q" placeholder="Tìm theo tên, vai trò, kỹ năng..." oninput="filterCards()" />
      </div>

      <div style="display:flex;gap:8px">
        <select id="filter-role" onchange="filterCards()" style="background:var(--glass);border:0;padding:8px;border-radius:10px;color:inherit;">
          <option value="">Tất cả vai trò</option>
          <option>Front-end</option>
          <option>Back-end</option>
          <option>Designer</option>
          <option>Tester</option>
        </select>
      </div>
    </div>

    <section class="grid" id="members">
      <!-- Thêm/bớt card ở đây -->
      <article class="card" data-name="Nguyen Van A" data-role="Front-end" data-tags="html,css,js">
        <div class="meta">
          <div class="avatar">
            <!-- Thay src nếu muốn dùng ảnh: <img src="..." alt=""> -->
            NA
          </div>
          <div>
            <p class="name">Nguyễn Văn A</p>
            <p class="role">Front-end Developer</p>
          </div>
        </div>
        <p class="desc">Thích xây dựng giao diện mượt, tối ưu trải nghiệm người dùng. Sở trường: HTML, CSS, JS, React.</p>
        <div class="tags">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">React</span>
        </div>
        <div class="socials">
          <a class="btn" href="https://github.com/username" target="_blank" rel="noopener">
            <svg viewBox="0 0 24 24" fill="none"><path d="M12 .5C5.73.5.97 5.26.97 11.53c0 4.69 3.03 8.67 7.24 10.07.53.1.72-.23.72-.51 0-.25-.01-.92-.01-1.8-2.95.64-3.57-1.42-3.57-1.42-.48-1.23-1.17-1.56-1.17-1.56-.96-.66.07-.65.07-.65 1.06.07 1.62 1.09 1.62 1.09.94 1.6 2.48 1.14 3.09.87.1-.68.37-1.14.67-1.4-2.36-.27-4.84-1.19-4.84-5.28 0-1.17.42-2.13 1.1-2.88-.11-.27-.48-1.37.1-2.86 0 0 .9-.29 2.95 1.1a10.3 10.3 0 0 1 2.68-.36c.91.01 1.83.12 2.68.36 2.04-1.39 2.95-1.1 2.95-1.1.58 1.49.21 2.59.1 2.86.69.75 1.1 1.71 1.1 2.88 0 4.1-2.49 5-4.86 5.27.38.33.72.98.72 1.99 0 1.44-.01 2.6-.01 2.95 0 .28.19.61.73.5 4.21-1.41 7.24-5.39 7.24-10.07C23.03 5.26 18.27.5 12 .5z" fill="currentColor"/></svg>
            Github
          </a>
          <a class="btn" href="mailto:email@example.com">
            <svg viewBox="0 0 24 24" fill="none"><path d="M3 8.5v7A2.5 2.5 0 0 0 5.5 18h13a2.5 2.5 0 0 0 2.5-2.5v-7" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/><path d="M21 7l-9 6-9-6" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>
            Email
          </a>
        </div>
      </article>

      <!-- Ví dụ thêm 1 card -->
      <article class="card" data-name="Tran Thi B" data-role="Designer" data-tags="figma,ui,ux">
        <div class="meta">
          <div class="avatar">TB</div>
          <div>
            <p class="name">Trần Thị B</p>
            <p class="role">UI/UX Designer</p>
          </div>
        </div>
        <p class="desc">Thiết kế giao diện, prototype trên Figma, tập trung vào usability và micro-interactions.</p>
        <div class="tags"><span class="tag">Figma</span><span class="tag">UI</span></div>
        <div class="socials">
          <a class="btn" href="#" target="_blank">Portfolio</a>
        </div>
      </article>

      <!-- Bạn có thể copy/paste block trên để thêm nhiều member -->
    </section>
  </main>

  <footer>
    © Tin Nhóm 5 — Thiết kế nhanh. Thay avatar bằng <code>&lt;img src="..." alt="Tên"&gt;</code> trong .avatar nếu muốn.
  </footer>

  <script>
    // Tìm và lọc
    function filterCards(){
      const q = document.getElementById('q').value.trim().toLowerCase();
      const role = document.getElementById('filter-role').value;
      const cards = document.querySelectorAll('#members .card');
      cards.forEach(c=>{
        const name = c.dataset.name.toLowerCase();
        const r = c.dataset.role || '';
        const tags = (c.dataset.tags||'').toLowerCase();
        const matchQ = q === '' || name.includes(q) || tags.includes(q) || c.querySelector('.desc').textContent.toLowerCase().includes(q);
        const matchRole = role === '' || r.toLowerCase() === role.toLowerCase();
        c.style.display = (matchQ && matchRole) ? 'flex' : 'none';
      });
    }

    // Theme toggle (simple)
    function toggleTheme(e){
      e.preventDefault();
      const root = document.documentElement;
      if(root.style.getPropertyValue('--bg') === '') {
        root.style.setProperty('--bg','#0f1724');
      }
      // đơn giản: chuyển nền sáng tối
      if(document.body.style.background.includes('linear-gradient')) {
        document.body.style.background = '#f7fafc';
        document.body.style.color = '#0b1220';
      } else {
        document.body.style.background = 'linear-gradient(180deg,#071029 0%,#071936 100%)';
        document.body.style.color = '#e6eef8';
      }
    }
  </script>
</body>
</html>
