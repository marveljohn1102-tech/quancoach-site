<!doctype html>
<html lang="zh-Hant">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>泉教練 | 關節優化・術後復健・動作控制</title>
<meta name="description" content="關節優化 × 動作控制 × 術後復健，把每次訓練都變成恢復與進步。">
<meta property="og:title" content="泉教練">
<meta property="og:description" content="關節優化 × 動作控制 × 術後復健。">
<style>
:root{
  --brand:#8E9AF3; /* 長春花藍 */
  --cta:#4056F4;
  --text:#1b1b1b;
  --muted:#5b6b7a;
  --paper:#fff;
}
body{
  font-family: system-ui, sans-serif;
  margin:0;
  background:var(--paper);
  color:var(--text);
}
header{
  background:var(--brand);
  color:white;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0.5rem 1rem;
  position:sticky;
  top:0;
}
header nav a{
  color:white;
  text-decoration:none;
  margin-left:1rem;
  font-weight:500;
  display:inline-flex;
  align-items:center;
}
header nav a svg{
  margin-right:0.3rem;
}
.hero{
  position:relative;
  height:70vh;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  color:white;
  background:url('https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat;
}
.hero::after{
  content:"";
  position:absolute;
  top:0;left:0;width:100%;height:100%;
  background:linear-gradient(to bottom right, rgba(142,154,243,0.8), rgba(64,86,244,0.8));
}
.hero-content{
  position:relative;
  z-index:1;
  max-width:700px;
  padding:1rem;
}
.hero h1{
  font-size:2.5rem;
  margin-bottom:1rem;
}
.hero p{
  font-size:1.2rem;
  line-height:1.6;
}
main{
  padding:2rem;
  max-width:800px;
  margin:auto;
}
form{
  display:flex;
  flex-direction:column;
  gap:1rem;
}
input, textarea{
  padding:0.6rem;
  font-size:1rem;
  border:1px solid var(--muted);
  border-radius:4px;
}
button{
  background:var(--cta);
  color:white;
  border:none;
  padding:0.8rem;
  font-size:1rem;
  cursor:pointer;
  border-radius:4px;
}
footer{
  text-align:center;
  font-size:0.9rem;
  padding:1rem;
  color:var(--muted);
}
</style>
</head>
<body>

<header>
  <div style="font-weight:bold;display:flex;align-items:center;">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="white" viewBox="0 0 24 24"><path d="M12 2a10 10 0 1 0 10 10A10.011 10.011 0 0 0 12 2Zm1 15h-2v-2h2Zm0-4h-2V7h2Z"/></svg>
    泉教練
  </div>
  <nav>
    <a href="#about">
      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="white" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4S8 5.79 8 8s1.79 4 4 4Zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4Z"/></svg>
      關於我
    </a>
    <a href="#contact">
      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="white" viewBox="0 0 24 24"><path d="M20 4H4a2.006 2.006 0 0 0-2 2v12a2.006 2.006 0 0 0 2 2h16a2.006 2.006 0 0 0 2-2V6a2.006 2.006 0 0 0-2-2Zm0 2v.511l-8 5.333-8-5.333V6Zm0 12H4V8.511l8 5.333 8-5.333Z"/></svg>
      聯絡我
    </a>
  </nav>
</header>

<section class="hero">
  <div class="hero-content">
    <h1>恢復動作・重拾自信</h1>
    <p>術後復健、關節優化、動作控制 —— 為你的每一步重建力量與穩定。</p>
  </div>
</section>

<main>
  <section id="about">
    <h2>關於我</h2>
    <p>我專注於幫助術後、關節不適者恢復動作能力，結合科學化訓練與個人化調整，讓你的每一次訓練都是進步與恢復。</p>
  </section>

  <section id="contact" style="margin-top:3rem;">
    <h2>聯絡我</h2>
    <form name="contact" method="POST" data-netlify="true" netlify-honeypot="bot-field">
      <input type="hidden" name="form-name" value="contact">
      <p style="display:none">
        <label>不要填寫：<input name="bot-field"></label>
      </p>
      <label>姓名：<input type="text" name="name" required></label>
      <label>Email：<input type="email" name="email" required></label>
      <label>訊息：<textarea name="message"></textarea></label>
      <button type="submit">送出</button>
    </form>
  </section>
</main>

<footer>
  © 2025 泉教練 | <a href="mailto:waterfit1102@gmail.com">waterfit1102@gmail.com</a>
</footer>

</body>
</html>