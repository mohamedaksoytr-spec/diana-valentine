<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>💖</title>

<style>
body{
  margin:0;
  min-height:100vh;
  display:grid;
  place-items:center;
  background:#ffe9ee;
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
}

.card{
  background:white;
  border-radius:26px;
  padding:28px 22px;
  width:min(720px,92vw);
  text-align:center;
  box-shadow:0 20px 60px rgba(210,4,45,.2);
}

.badge{
  display:inline-block;
  padding:6px 12px;
  border-radius:999px;
  background:#ffe1e7;
  color:#a0002a;
  font-weight:700;
  margin-bottom:12px;
}

.name{
  background:#ffd6df;
  padding:4px 12px;
  border-radius:999px;
}

.stage{
  height:240px;
  border:2px dashed #d2042d;
  border-radius:20px;
  margin-top:16px;
  position:relative;
}

button{
  border:0;
  border-radius:999px;
  padding:14px 20px;
  font-size:18px;
  font-weight:800;
  cursor:pointer;
}

#yes{
  background:#d2042d;
  color:white;
}

#no{
  position:absolute;
  background:white;
  border:2px solid #d2042d;
  color:#a0002a;
}

.success{
  display:none;
  margin-top:16px;
  background:#ffe6ec;
  padding:14px;
  border-radius:16px;
  font-weight:700;
}
</style>
</head>

<body>

<div class="card">
  <div class="badge">🍒 Cherry & White Theme</div>

  <h1>Hey <span class="name">Diana</span> 💖</h1>
  <p>Will you be my Valentine?</p>

  <p>📅 Feb 14 &nbsp; 🕗 8:00 PM</p>

  <div class="stage" id="stage">
    <button id="yes">Yes 💘</button>
    <button id="no">No 🙈</button>
  </div>

  <div class="success" id="success">
    YAY!! 💞 Diana said YES.<br>
    🎶 “You are my fire…”
  </div>

  <audio id="song" src="iwantitthatway.mp3"></audio>
</div>

<script>
const no = document.getElementById("no");
const stage = document.getElementById("stage");
const yes = document.getElementById("yes");
const success = document.getElementById("success");
const song = document.getElementById("song");

function moveNo(){
  const maxX = stage.clientWidth - no.offsetWidth;
  const maxY = stage.clientHeight - no.offsetHeight;
  no.style.left = Math.random()*maxX + "px";
  no.style.top = Math.random()*maxY + "px";
}

stage.addEventListener("mousemove", moveNo);
no.addEventListener("click", moveNo);

yes.addEventListener("click", ()=>{
  success.style.display="block";
  stage.style.display="none";
  song.play();
});
</script>

</body>
</html>
