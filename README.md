backend: { name: git-gateway, branch: main }
media_folder: "assets/uploads"
public_folder: "/assets/uploads"

collections:
  - name: "homepage"
    label: "首頁"
    files:
      - file: "data/homepage.json"
        label: "首頁內容"
        name: "home"
        fields:
          - {label: 首屏標題, name: hero_title, widget: string}
          - {label: 首屏說明, name: hero_subtitle, widget: text}
          - {label: 名單引導文, name: lead_copy, widget: string}
          - label: 你能帶來的價值
            name: values
            widget: list
            fields:
              - {label: 標題, name: title, widget: string}
              - {label: 說明, name: desc, widget: text}
          - label: 資歷與證照
            name: creds
            widget: list
            fields: [{label: 內容, name: text, widget: string}]
          - {label: 首屏背景圖, name: hero_image, widget: image, allow_multiple: false, required: false}

  - name: "courses"
    label: "課程（3種）"
    files:
      - file: "data/course_private.json"
        label: "私人課程"
        name: "private"
        fields:
          - {label: 標題, name: title, widget: string, default: "私人課程"}
          - {label: 適合對象, name: fit, widget: list, field: {label: 項目, name: item, widget: string}}
          - {label: 不適合, name: not_for, widget: list, required: false, field: {label: 項目, name: item, widget: string}}
          - {label: 課程模組, name: modules, widget: list, field: {label: 模組, name: text, widget: string}}
          - {label: 費用說明, name: price_note, widget: string, default: "請加 LINE 詢價"}
          - {label: CTA 連結, name: cta, widget: string, default: "https://line.me/ti/p/LIhC5Zxq4i"}
      - file: "data/course_online.json"
        label: "線上課程"
        name: "online"
        fields: *private.fields
      - file: "data/course_group.json"
        label: "多人課程"
        name: "group"
        fields: *private.fields

  - name: "cases"
    label: "案例分享"
    folder: "data/cases"
    create: true
    slug: "{{slug}}"
    fields:
      - {label: 標題, name: title, widget: string}
      - {label: 一句收穫, name: summary, widget: string}
      - {label: 前照片, name: before, widget: image, required: false}
      - {label: 後照片, name: after, widget: image, required: false}
      - {label: 重點, name: bullets, widget: list, field: {label: 條目, name: item, widget: string}}
      - {label: 排序（數字越小越前）, name: order, widget: number, default: 10}

  - name: "gallery"
    label: "上課照片"
    folder: "data/gallery"
    create: true
    slug: "{{slug}}"
    fields:
      - {label: 照片, name: image, widget: image}
      - {label: 說明, name: caption, widget: string, required: false}
      - {label: 排序, name: order, widget: number, default: 10}

  # 👇 新增：文章集合（可上傳封面與圖文）
  - name: "posts"
    label: "最新文章"
    files:
      - file: "data/posts.json"
        label: "文章列表"
        name: "posts"
        fields:
          - label: 文章
            name: items
            widget: list
            summary: "{{fields.title}}"
            fields:
              - {label: ID, name: id, widget: string, hint: "英文或數字，做為網址 hash 使用"}
              - {label: 標題, name: title, widget: string}
              - {label: 日期, name: date, widget: datetime, format: "YYYY-MM-DD"}
              - {label: 封面圖, name: cover, widget: image, required: false}
              - {label: 摘要, name: excerpt, widget: text}
              - {label: 內文（支援 Markdown）, name: body, widget: markdown}

{
  "items": [
    {
      "id": "shoulder-3weeks",
      "title": "五十肩 3 週改善：怎麼安排更有效？",
      "date": "2025-08-01",
      "cover": "/assets/uploads/post-shoulder.jpg",
      "excerpt": "從呼吸核心→關節中立→肩胛節律，三步驟把夜間疼痛壓下來。",
      "body": "### 重點\n- 週一做**呼吸核心**建立壓力\n- 週三做**關節優化**（胸椎/肱骨滑動）\n- 週五做**低負重強化**（不痛原則）\n\n> 居家處方一樣重要，建議 48 小時內回報影片。"
    },
    {
      "id": "knee-squat",
      "title": "膝蓋痛深蹲：別急著撐護膝，先把髖主導找回來",
      "date": "2025-07-20",
      "cover": "/assets/uploads/post-knee.jpg",
      "excerpt": "先讓膝蓋不當主角，髖主導＋中立踩穩後再談負重。",
      "body": "1. 以髖摺疊尋找**中立**\n2. **足弓—膝蓋—髖**對線\n3. 逐步增加**離心控制**\n\n**加碼**：兩個在家就能做的練習影片（見 IG）"
    }
  ]
}

<!doctype html><html lang="zh-Hant"><head>
<meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>最新文章｜泉教練</title>
<meta name="description" content="泉教練的復健與動作控制文章：案例、方法、在家訓練。">
<style>
:root{--cta:#4056F4}*{box-sizing:border-box}
body{font-family:-apple-system,"Noto Sans TC","PingFang TC",Segoe UI,Roboto,Arial,sans-serif;margin:0;background:#f6f8fa;color:#1b1b1b}
.container{max-width:980px;margin:0 auto;padding:16px}
.grid{display:grid;grid-template-columns:320px 1fr;gap:16px}
.card{background:#fff;border:1px solid #e5e7eb;border-radius:12px;padding:12px}
a{color:var(--cta);text-decoration:none}
.list a{display:block;padding:8px 10px;border-radius:8px}
.list a.active{background:#eef2ff}
.post h1{margin:0 0 10px} .post time{color:#64748b;font-size:14px}
.post img{max-width:100%;border:1px solid #e5e7eb;border-radius:12px}
@media(max-width:900px){.grid{grid-template-columns:1fr}}
</style>
</head><body>
<div class="container">
  <h1>最新文章</h1>
  <div class="grid">
    <aside class="card list" id="post-list">讀取中…</aside>
    <article class="card post" id="post-content">請從左側選擇一篇文章</article>
  </div>
</div>

<script>
(async function(){
  const listEl = document.getElementById('post-list');
  const contentEl = document.getElementById('post-content');

  async function fetchJSON(url){ const r = await fetch(url,{cache:'no-store'}); return r.ok ? r.json() : {items:[]}; }
  const data = await fetchJSON('/data/posts.json');
  const items = (data.items||[]).sort((a,b)=> (a.date<b.date?1:-1));

  function renderList(activeId){
    listEl.innerHTML = items.map(p=>{
      const cls = 'post-link'+(p.id===activeId?' active':'');
      return `<a class="${cls}" href="#${p.id}">${p.title}</a>`;
    }).join('') || '尚無文章';
  }

  function mdToHtml(md){
    // 極簡 Markdown 轉換（粗體/斜體/標題/清單/段落/引言）
    return md
      .replace(/^### (.*$)/gim,'<h3>$1</h3>')
      .replace(/^## (.*$)/gim,'<h2>$1</h2>')
      .replace(/^# (.*$)/gim,'<h1>$1</h1>')
      .replace(/^\> (.*$)/gim,'<blockquote>$1</blockquote>')
      .replace(/^\- (.*$)/gim,'<li>$1</li>')
      .replace(/\*\*(.*?)\*\*/gim,'<strong>$1</strong>')
      .replace(/\*(.*?)\*/gim,'<em>$1</em>')
      .replace(/\n$/gim,'<br />');
  }

  function renderPost(id){
    const p = items.find(x=>x.id===id) || items[0];
    if(!p){ contentEl.innerHTML='尚無文章'; return; }
    const cover = p.cover ? `<p><img src="${p.cover}" alt="${p.title}"></p>` : '';
    contentEl.innerHTML = `
      <h1>${p.title}</h1>
      <time>${p.date||''}</time>
      ${cover}
      <div>${mdToHtml(p.body||'')}</div>
    `;
    renderList(p.id);
  }

  window.addEventListener('hashchange',()=>renderPost(location.hash.replace('#','')));
  renderList(location.hash.replace('#',''));
  if(location.hash){ renderPost(location.hash.replace('#','')); }
})();
</script>
</body></html>

<section id="latest-posts" class="section">
  <h2>最新文章</h2>
  <div id="posts-cards" style="display:grid;grid-template-columns:repeat(3,1fr);gap:12px"></div>
  <p><a href="/posts/">看全部文章 →</a></p>
</section>

<script>
(async function(){
  const wrap = document.getElementById('posts-cards'); if(!wrap) return;
  const r = await fetch('/data/posts.json',{cache:'no-store'}); if(!r.ok) return;
  const items = (await r.json()).items || [];
  const top3 = items.sort((a,b)=> (a.date<b.date?1:-1)).slice(0,3);
  wrap.innerHTML = top3.map(p=>`
    <article style="background:#fff;border:1px solid #e5e7eb;border-radius:12px;padding:12px">
      ${p.cover?`<img src="${p.cover}" alt="${p.title}" style="width:100%;height:160px;object-fit:cover;border-radius:8px;border:1px solid #e5e7eb">`:''}
      <h3 style="margin:8px 0 4px">${p.title}</h3>
      <p style="color:#64748b;margin:0 0 8px">${p.date||''}</p>
      <p style="margin:0 0 8px">${p.excerpt||''}</p>
      <a href="/posts/#${p.id}">閱讀全文 →</a>
    </article>
  `).join('') || '<p>尚無文章</p>';
})();
</script>
