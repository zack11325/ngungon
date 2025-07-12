# ngungon
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Ngủ ngon 💖</title>
  <style>
    body {
      margin:0;
      background:#fff0f5;
      overflow:hidden;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      height:100vh;
      font-family:sans-serif;
    }
    .character {
      animation:bounce 1s infinite;
    }
    .character img {
      width:180px;
    }
    @keyframes bounce { 0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);} }
    .heart {
      position:absolute;
      width:20px;height:20px;
      background:red;
      transform:rotate(45deg);
      opacity:0.8;
      animation:floatUp 4s linear forwards;
    }
    .heart::before,.heart::after {
      content:"";
      width:20px;height:20px;
      background:red;border-radius:50%;
      position:absolute;
    }
    .heart::before{top:-10px;left:0;}
    .heart::after{left:-10px;top:0;}
    @keyframes floatUp {
      to {transform:translate(var(--x), -100vh) scale(1.5) rotate(360deg);opacity:0;}
    }
    .message {
      margin-top:20px;
      font-size:20px;
      color:#d63384;
      text-align:center;
      animation:fadeIn 3s ease forwards;
    }
    @keyframes fadeIn { from{opacity:0;} to{opacity:1;} }
  </style>
</head>
<body>
  <div class="character" id="char">
    <img src="https://i.postimg.cc/59wtWRG8/que.jpg" alt="character">
  </div>
  <div class="message">Chúc bạn KiuTrang ngủ ngon nhaa~ mơ siu siu đẹp và dethunn nèe~</div>
  <script>
    const char = document.getElementById('char');
    function createHeart(){
      const h = document.createElement('div');
      h.className = 'heart';
      const x = (Math.random()*200 -100) + 'px';
      h.style.setProperty('--x', x);
      const rect = char.getBoundingClientRect();
      h.style.left = rect.left + rect.width/2 + 'px';
      h.style.top  = rect.top + 40 + 'px';
      document.body.appendChild(h);
      setTimeout(()=>h.remove(), 4000);
    }
    setInterval(createHeart, 300);
  </script>
</body>
</html>
