<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Diana 💖</title>


  <style>
    :root{
      --cherry:#D2042D;
      --cherryDark:#A0002A;
      --card:#ffffff;
      --shadow: 0 20px 60px rgba(122,0,31,0.22);
      --ring: rgba(210,4,45,0.25);
    }


    *{ box-sizing:border-box; font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; }


    body{
      margin:0;
      min-height:100vh;
      display:grid;
      place-items:center;
      color:#1f1f1f;


      /* Default: uses background.jpg if you upload it */
      background:
        linear-gradient(180deg, rgba(255,245,248,0.70), rgba(255,245,248,0.85)),
        url("background.jpg");
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      overflow:hidden;
    }


    /* darken/soften the image a bit */
    .overlay{
      position:fixed;
      inset:0;
      background: radial-gradient(circle at 20% 20%, rgba(210,4,45,0.12), transparent 45%),
                  radial-gradient(circle at 80% 30%, rgba(230,58,90,0.12), transparent 55%),
                  rgba(255,255,255,0.15);
      pointer-events:none;
    }


    .card{
      width:min(760px, 92vw);
      background: rgba(255,255,255,0.92);
      border: 1px solid rgba(210,4,45,0.14);
      border-radius: 28px;
      padding: 24px 20px;
      box-shadow: var(--shadow);
      text-align:center;
      backdrop-filter: blur(10px);
      position:relative;
    }


    .topRow{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:12px;
      flex-wrap:wrap;
      margin-bottom: 10px;
    }


    .badge{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(210,4,45,0.06);
      border: 1px solid rgba(210,4,45,0.14);
      color: var(--cherryDark);
      font-weight: 900;
      font-size: 13px;
    }


    .bgBtn{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 8px 12px;
      border-radius: 999px;
      background: #fff;
      border: 1px solid rgba(210,4,45,0.18);
      color: #7A001F;
      font-weight: 800;
      font-size: 13px;
      cursor:pointer;
      box-shadow: 0 10px 25px rgba(122,0,31,0.08);
    }
    .bgBtn:focus-visible{
      outline:none;
      box-shadow: 0 0 0 6px var(--ring), 0 10px 25px rgba(122,0,31,0.10);
    }


    h1{
      margin: 10px 0 6px;
      font-size: clamp(26px, 4vw, 46px);
      letter-spacing: -0.6px;
    }
    .name{
      display:inline-block;
      padding: 2px 10px;
      border-radius: 999px;
      background: rgba(210,4,45,0.10);
      border: 1px solid rgba(210,4,45,0.18);
      color: #7A001F;
      font-weight: 900;
    }


    p{
      margin: 6px 0 14px;
      font-size: clamp(14px, 2vw, 18px);
      color: rgba(20,20,20,0.70);
      line-height: 1.45;
    }


    .when{
      display:flex;
      justify-content:center;
      gap:10px;
      flex-wrap:wrap;
      margin: 10px 0 16px;
      font-weight: 800;
      color: rgba(0,0,0,0.75);
    }
    .pill{
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(255,255,255,0.95);
      border: 1px solid rgba(210,4,45,0.16);
      box-shadow: 0 10px 25px rgba(122,0,31,0.08);
    }


    .stage{
      margin-top: 8px;
      height: 280px;
      border-radius: 22px;
      background: linear-gradient(180deg, rgba(255,255,255,0.92), rgba(255,246,248,0.70));
      border: 1px dashed rgba(210,4,45,0.30);
      position: relative;
      overflow: hidden;
      display:flex;
      align-items:center;
      justify-content:center;
    }


    .buttons{
      position:absolute;
      inset:0;
      display:flex;
      align-items:center;
      justify-content:center;
      gap: 14px;
      padding: 18px;
    }


    button{
      border:0;
      border-radius: 999px;
      padding: 14px 18px;
      font-size: 18px;
      font-weight: 900;
      cursor:pointer;
      box-shadow: 0 12px 28px rgba(122,0,31,0.16);
      user-select:none;
      touch-action: manipulation;
    }


    #yesBtn{
      background: linear-gradient(180deg, var(--cherry), var(--cherryDark));
      color:white;
      min-width: 140px;
    }


    #noBtn{
      background: rgba(255,255,255,0.98);
      color: var(--cherryDark);
      border: 1px solid rgba(210,4,45,0.22);
      min-width: 120px;
      position:absolute;
      left: 60%;
      top: 58%;
      transform: translate(-50%, -50%);
    }


    .success{
      display:none;
      margin-top: 14px;
      padding: 16px;
      border-radius: 18px;
      background: rgba(210,4,45,0.06);
      border: 1px solid rgba(210,4,45,0.18);
      color: #7A001F;
      font-weight: 900;
    }


    .tiny{
      margin-top: 10px;
      font-size: 13px;
      opacity: 0.78;
    }


    input[type="file"]{ display:none; }
  </style>
</head>


<body>
  <div class="overlay" aria-hidden="true"></div>


  <main class="card">
    <div class="topRow">
      <div class="badge">🍒 Cherry & White Theme</div>


      <!-- Upload background image (optional) -->
      <label class="bgBtn" for="bgInput" title="Choose a background photo">
        🖼️ Choose background
      </label>
      <input id="bgInput" type="file" accept="image/*" />
    </div>


    <h1>Hey <span class="name">Diana</span> 💖</h1>
    <p>I have one important question…</p>


    <div class="when">
      <div class="pill">📅 Feb 14</div>
      <div class="pill">🕗 8:00 PM</div>
    </div>


    <p><strong>Will you be my Valentine?</strong></p>


    <section class="stage" id="stage">
      <div class="buttons">
        <button id="yesBtn" type="button">Yes 💘</button>
        <button id="noBtn" type="button">No 🙈</button>
      </div>
    </section>


    <div class="success" id="successMsg">
      YAY!! 🍒💞 Diana said YES.<br>
      See you Feb 14 at 8:00 PM 😄<br>
      🎶 “You are my fire…”
    </div>


    <!-- Optional: upload your MP3 with this exact name in the repo root -->
    <audio id="song" src="iwantitthatway.mp3" preload="auto"></audio>


    <div class="tiny">
      Tip: To set a permanent background, upload a file named <b>background.jpg</b> next to <b>index.html</b>.
    </div>
  </main>


  <script>
    const stage = document.getElementById("stage");
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const successMsg = document.getElementById("successMsg");
    const song = document.getElementById("song");
    const bgInput = document.getElementById("bgInput");


    let noDodges = 0;


    function clamp(n, min, max){ return Math.max(min, Math.min(max, n)); }


    function moveNoButton() {
      const pad = 10;
      const stageRect = stage.getBoundingClientRect();
      const btnRect = noBtn.getBoundingClientRect();


      const maxX = stageRect.width - btnRect.width - pad;
      const maxY = stageRect.height - btnRect.height - pad;


      const x = Math.random() * maxX + pad;
      const y = Math.random() * maxY + pad;


      noBtn.style.left = clamp(x, pad, maxX) + "px";
      noBtn.style.top  = clamp(y, pad, maxY) + "px";
      noBtn.style.transform = "translate(0, 0)";
    }


    function dodgeIfNearPointer(clientX, clientY) {
      const btnRect = noBtn.getBoundingClientRect();
      const cx = btnRect.left + btnRect.width / 2;
      const cy = btnRect.top + btnRect.height / 2;


      const dist = Math.hypot(clientX - cx, clientY - cy);
      const danger = 150 + Math.min(noDodges * 12, 220);


      if (dist < danger) {
        noDodges++;
        moveNoButton();
        const scale = 1 + Math.min(noDodges * 0.05, 0.7);
        yesBtn.style.transform = `scale(${scale})`;
      }
    }


    stage.addEventListener("mousemove", (e) => dodgeIfNearPointer(e.clientX, e.clientY));
    stage.addEventListener("pointermove", (e) => dodgeIfNearPointer(e.clientX, e.clientY));


    noBtn.addEventListener("pointerdown", (e) => { e.preventDefault(); noDodges++; moveNoButton(); });


    yesBtn.addEventListener("click", async () => {
      successMsg.style.display = "block";
      stage.style.display = "none";
      try { await song.play(); } catch {}
    });


    // Let user choose a background image (temporary per device)
    bgInput.addEventListener("change", () => {
      const file = bgInput.files && bgInput.files[0];
      if (!file) return;


      const url = URL.createObjectURL(file);
      document.body.style.backgroundImage =
        `linear-gradient(180deg, rgba(255,245,248,0.70), rgba(255,245,248,0.85)), url("${url}")`;
      document.body.style.backgroundSize = "cover";
      document.body.style.backgroundPosition = "center";
      document.body.style.backgroundRepeat = "no-repeat";
    });
  </script>
</body>
</html>
