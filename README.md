<!doctype html>
<html lang="zh-Hant">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>泉教練｜關節優化・術後復健・動作控制</title>
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
      font-family: Arial, sans-serif;
      margin:0;
      background: var(--paper);
      color: var(--text);
      line-height: 1.6;
    }
    header{
      background: var(--brand);
      color: white;
      padding: 1rem;
      text-align: center;
    }
    h1{ margin:0; }
    section{
      padding: 1.5rem;
      max-width: 800px;
      margin: auto;
    }
    form{
      background: #f9f9f9;
      padding: 1rem;
      border-radius: 8px;
    }
    input, textarea, button{
      width: 100%;
      padding: 0.5rem;
      margin-top: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
    }
    button{
      background: var(--cta);
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover{
      background: #3046d6;
    }
    #form-success{
      color: green;
      display: none;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <header>
    <h1>泉教練</h1>
    <p>關節優化 × 動作控制 × 術後復健</p>
  </header>

  <section>
    <h2>聯絡我</h2>
    <form name="contact" method="POST" data-netlify="true">
      <input type="hidden" name="form-name" value="contact">
      <label>姓名：
        <input type="text" name="name" required>
      </label>
      <label>Email：
        <input type="email" name="email" required>
      </label>
      <label>訊息：
        <textarea name="message" rows="5" required></textarea>
      </label>
      <button type="submit">送出</button>
      <p id="form-success">✅ 已成功送出，我們會盡快與您聯繫！</p>
    </form>
  </section>

  <script>
  document.querySelector('form').addEventListener('submit', function(event) {
    event.preventDefault();

    var form = this;
    var formData = new FormData(form);

    fetch('/', {
      method: 'POST',
      body: formData
    }).then(function() {
      document.getElementById('form-success').style.display = 'block';
      form.reset();
    }).catch(function(error) {
      alert('送出失敗，請稍後再試');
      console.error(error);
    });
  });
  </script>
</body>
</html>