<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>مبروك يا بطلتي 🤍</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#FBF6EE;
    --white:#FFFDFB;
    --blush:#F5DEE3;
    --blush-deep:#E7B9C4;
    --gold:#C9A15C;
    --gold-light:#EAD2A0;
    --gold-deep:#A8823E;
    --ink:#3B2C2E;
    --ink-soft:#7A6467;
    --shadow:rgba(120,90,70,0.14);
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html{scroll-behavior:smooth;}

  body{
    background:linear-gradient(180deg,var(--cream) 0%,#F8EFE6 40%,var(--blush) 100%);
    color:var(--ink);
    font-family:'Tajawal',sans-serif;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
    min-height:100vh;
  }

  h1,h2,h3,.serif{
    font-family:'Amiri',serif;
  }

  ::selection{background:var(--gold-light);color:var(--ink);}

  a,button{font-family:inherit;}

  /* ---------- LOADER ---------- */
  #loader{
    position:fixed;inset:0;z-index:9999;
    background:radial-gradient(circle at 50% 40%,#FFFCF7 0%,var(--cream) 60%,var(--blush) 100%);
    display:flex;align-items:center;justify-content:center;flex-direction:column;gap:18px;
    transition:opacity 1s ease, visibility 1s ease;
  }
  #loader.hide{opacity:0;visibility:hidden;pointer-events:none;}
  .loader-icon{
    font-size:2.6rem;
    animation:loaderPulse 1.6s ease-in-out infinite;
    filter:drop-shadow(0 0 12px rgba(201,161,92,0.55));
  }
  @keyframes loaderPulse{
    0%,100%{transform:scale(1);opacity:.8;}
    50%{transform:scale(1.18);opacity:1;}
  }
  .loader-text{
    font-family:'Amiri',serif;
    font-size:1.1rem;
    letter-spacing:.5px;
    color:var(--gold-deep);
    opacity:.85;
  }

  /* ---------- BACKDROP CANVASES ---------- */
  #particles-canvas, #confetti-canvas{
    position:fixed;inset:0;width:100%;height:100%;
    pointer-events:none;z-index:1;
  }
  #confetti-canvas{z-index:9998;}

  .floating-heart{
    position:fixed;bottom:-40px;z-index:3;pointer-events:none;
    font-size:1.2rem;color:var(--blush-deep);
    opacity:.85;
    animation:floatUp linear forwards;
  }
  @keyframes floatUp{
    0%{transform:translateY(0) translateX(0) rotate(0deg);opacity:0;}
    10%{opacity:.9;}
    90%{opacity:.7;}
    100%{transform:translateY(-115vh) translateX(var(--drift,20px)) rotate(25deg);opacity:0;}
  }

  /* ---------- LAYOUT ---------- */
  main{position:relative;z-index:2;}

  section{
    position:relative;
    padding:min(14vw,110px) 6vw;
    max-width:760px;
    margin:0 auto;
  }

  .eyebrow{
    display:inline-flex;align-items:center;gap:10px;
    font-size:.78rem;letter-spacing:2.5px;
    color:var(--gold-deep);
    text-transform:uppercase;
    margin-bottom:18px;
    opacity:.85;
  }
  .eyebrow::before,.eyebrow::after{
    content:'';width:24px;height:1px;background:var(--gold);
  }

  /* ---------- HERO ---------- */
  .hero{
    min-height:100svh;
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    text-align:center;
    max-width:900px;
    padding:8vw 6vw;
  }
  .hero-cap{
    font-size:clamp(2.2rem,7vw,3.4rem);
    margin-bottom:8px;
    filter:drop-shadow(0 4px 18px rgba(201,161,92,0.35));
    animation:capIn 1.2s cubic-bezier(.2,.9,.25,1) both;
    animation-delay:.2s;
  }
  @keyframes capIn{
    from{opacity:0;transform:translateY(-24px) scale(.8) rotate(-8deg);}
    to{opacity:1;transform:translateY(0) scale(1) rotate(0deg);}
  }
  .hero h1{
    font-size:clamp(2rem,7.2vw,3.7rem);
    line-height:1.35;
    font-weight:700;
    color:var(--ink);
    letter-spacing:.5px;
  }
  .hero h1 .type-wrap{
    display:inline-block;
  }
  .hero h1 .char{
    display:inline-block;
    opacity:0;
    animation:charIn .7s cubic-bezier(.2,.8,.25,1) forwards;
  }
  @keyframes charIn{
    from{opacity:0;transform:translateY(14px);filter:blur(4px);}
    to{opacity:1;transform:translateY(0);filter:blur(0);}
  }
  .gold-word{
    background:linear-gradient(90deg,var(--gold-deep),var(--gold-light),var(--gold-deep));
    background-size:200% auto;
    -webkit-background-clip:text;background-clip:text;color:transparent;
  }
  .char.gold-word{
    animation:charIn .7s cubic-bezier(.2,.8,.25,1) forwards, shine 4s linear infinite;
  }
  @keyframes shine{to{background-position:200% center;}}

  .hero p.subtitle{
    margin-top:26px;
    font-size:clamp(1rem,3vw,1.2rem);
    color:var(--ink-soft);
    line-height:2;
    max-width:520px;
    opacity:0;
    animation:fadeUp 1s ease forwards;
    animation-delay:2.6s;
  }
  @keyframes fadeUp{
    from{opacity:0;transform:translateY(18px);}
    to{opacity:1;transform:translateY(0);}
  }

  .scroll-cue{
    margin-top:60px;
    display:flex;flex-direction:column;align-items:center;gap:8px;
    opacity:0;
    animation:fadeUp 1s ease forwards;
    animation-delay:3.3s;
    color:var(--gold-deep);
    font-size:.75rem;
    letter-spacing:1.5px;
  }
  .scroll-cue span.line{
    width:1px;height:34px;
    background:linear-gradient(var(--gold),transparent);
    animation:scrollLine 1.8s ease-in-out infinite;
  }
  @keyframes scrollLine{
    0%{transform:scaleY(0);transform-origin:top;}
    50%{transform:scaleY(1);transform-origin:top;}
    50.01%{transform-origin:bottom;}
    100%{transform:scaleY(0);transform-origin:bottom;}
  }

  /* ---------- REVEAL UTILITY ---------- */
  .reveal{
    opacity:0;
    transform:translateY(40px);
    transition:opacity 1s cubic-bezier(.2,.7,.2,1), transform 1s cubic-bezier(.2,.7,.2,1);
  }
  .reveal.in{opacity:1;transform:translateY(0);}
  .reveal-delay-1{transition-delay:.12s;}
  .reveal-delay-2{transition-delay:.24s;}
  .reveal-delay-3{transition-delay:.36s;}

  /* ---------- GLASS CARD ---------- */
  .glass{
    background:linear-gradient(155deg,rgba(255,255,255,0.72),rgba(255,255,255,0.42));
    backdrop-filter:blur(18px) saturate(140%);
    -webkit-backdrop-filter:blur(18px) saturate(140%);
    border:1px solid rgba(255,255,255,0.55);
    border-radius:26px;
    box-shadow:0 20px 60px -20px var(--shadow), inset 0 1px 0 rgba(255,255,255,0.6);
  }

  /* ---------- LETTER SECTION ---------- */
  .letter-wrap{position:relative;}
  .seal{
    width:64px;height:64px;border-radius:50%;
    background:radial-gradient(circle at 35% 30%,var(--gold-light),var(--gold-deep) 75%);
    display:flex;align-items:center;justify-content:center;
    margin:0 auto 28px;
    box-shadow:0 10px 26px -8px rgba(168,130,62,0.55), inset 0 2px 4px rgba(255,255,255,0.4);
    font-size:1.5rem;
    color:#fff;
    position:relative;
  }
  .seal::after{
    content:'';position:absolute;inset:-6px;border-radius:50%;
    border:1px dashed rgba(201,161,92,0.4);
    animation:sealSpin 26s linear infinite;
  }
  @keyframes sealSpin{to{transform:rotate(360deg);}}

  .letter-card{
    padding:44px 30px;
    text-align:center;
  }
  .letter-card h2{
    font-size:clamp(1.4rem,4.5vw,1.9rem);
    margin-bottom:30px;
    color:var(--gold-deep);
  }
  .letter-card p{
    font-size:clamp(1rem,3vw,1.18rem);
    line-height:2.3;
    color:var(--ink);
    margin-bottom:22px;
    font-family:'Amiri',serif;
  }
  .letter-card p:last-child{margin-bottom:0;}
  .signature{
    margin-top:34px;
    font-size:1rem;
    color:var(--gold-deep);
    letter-spacing:1px;
  }

  /* ---------- ACHIEVEMENT CARD ---------- */
  .achieve-card{
    padding:50px 30px;
    text-align:center;
    position:relative;
    overflow:hidden;
  }
  .achieve-card::before{
    content:'';position:absolute;top:-40%;left:50%;translate:-50% 0;
    width:220px;height:220px;
    background:radial-gradient(circle,rgba(233,201,140,0.55),transparent 70%);
    filter:blur(10px);
    pointer-events:none;
  }
  .achieve-row{
    display:flex;align-items:center;justify-content:center;gap:12px;
    font-size:1.15rem;font-weight:500;
    margin-bottom:10px;
  }
  .achieve-check{color:#8CA97A;}
  .achieve-score{
    font-family:'Amiri',serif;
    font-size:clamp(3.6rem,16vw,5.2rem);
    font-weight:700;
    color:var(--gold-deep);
    line-height:1;
    margin:18px 0 6px;
    position:relative;
    display:inline-block;
  }
  .achieve-score .percent{font-size:.45em;vertical-align:top;top:.4em;position:relative;}
  .achieve-label{
    font-size:.85rem;letter-spacing:1.5px;color:var(--ink-soft);
    text-transform:uppercase;margin-bottom:26px;
  }
  .achieve-quote{
    font-family:'Amiri',serif;
    font-style:italic;
    font-size:clamp(1rem,3vw,1.15rem);
    color:var(--ink);
    line-height:1.9;
    border-top:1px solid rgba(201,161,92,0.3);
    padding-top:24px;
    margin-top:8px;
  }

  /* ---------- QUALITIES ---------- */
  .qualities-intro{
    text-align:center;
    font-family:'Amiri',serif;
    font-size:clamp(1.15rem,4vw,1.55rem);
    color:var(--ink);
    margin-bottom:46px;
    line-height:1.8;
  }
  .quality-grid{
    display:flex;flex-wrap:wrap;gap:16px;justify-content:center;
  }
  .quality-card{
    background:linear-gradient(155deg,rgba(255,255,255,0.72),rgba(255,255,255,0.4));
    backdrop-filter:blur(16px) saturate(140%);
    -webkit-backdrop-filter:blur(16px) saturate(140%);
    border:1px solid rgba(255,255,255,0.6);
    border-radius:20px;
    padding:24px 26px;
    font-family:'Amiri',serif;
    font-size:1.05rem;
    line-height:1.7;
    color:var(--ink);
    box-shadow:0 14px 34px -16px var(--shadow), inset 0 1px 0 rgba(255,255,255,0.6);
    transition:transform .45s cubic-bezier(.2,.8,.25,1), box-shadow .45s ease;
    flex:1 1 220px;
    max-width:270px;
    text-align:center;
  }
  .quality-card:hover{
    transform:translateY(-8px);
    box-shadow:0 24px 48px -18px var(--shadow);
  }
  @media(min-width:700px){
    .quality-card:nth-child(2){margin-top:30px;}
    .quality-card:nth-child(4){margin-top:14px;}
  }

  /* ---------- QUOTE SECTION ---------- */
  .quote-section{text-align:center;padding-top:min(16vw,120px);padding-bottom:min(16vw,120px);}
  .quote-mark{
    font-family:'Amiri',serif;
    font-size:3.5rem;color:var(--gold-light);
    line-height:0;position:relative;top:20px;
  }
  blockquote{
    font-family:'Amiri',serif;
    font-size:clamp(1.3rem,5vw,2.1rem);
    line-height:1.85;
    color:var(--ink);
    font-weight:400;
  }
  blockquote .accent{color:var(--gold-deep);font-weight:700;}

  /* ---------- FINAL SECTION ---------- */
  .final-section{
    text-align:center;
    min-height:90vh;
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    padding-top:0;padding-bottom:0;
  }
  .heart{
    position:relative;
    width:90px;height:90px;
    margin-bottom:38px;
  }
  .heart svg{width:100%;height:100%;overflow:visible;}
  .heart-glow{
    filter:drop-shadow(0 0 18px rgba(231,185,196,0.9)) drop-shadow(0 0 34px rgba(201,161,92,0.5));
    animation:heartbeat 2.4s ease-in-out infinite;
  }
  @keyframes heartbeat{
    0%,100%{transform:scale(1);}
    15%{transform:scale(1.12);}
    30%{transform:scale(1);}
    45%{transform:scale(1.08);}
    60%{transform:scale(1);}
  }
  .final-section p{
    font-family:'Amiri',serif;
    font-size:clamp(1.15rem,4vw,1.5rem);
    line-height:2;
    max-width:520px;
    margin-bottom:20px;
    color:var(--ink);
  }
  .final-proud{
    color:var(--gold-deep);
    font-weight:700;
    font-size:clamp(1.3rem,4.5vw,1.7rem);
    margin-top:10px;
  }
  .final-en{
    margin-top:48px;
    font-family:'Amiri',serif;
    font-style:italic;
    font-size:clamp(1rem,3.2vw,1.25rem);
    color:var(--ink-soft);
    letter-spacing:.3px;
  }
  .final-en b{color:var(--gold-deep);font-weight:700;}

  .share-hint{
    margin-top:56px;
    font-size:.82rem;
    color:var(--ink-soft);
    opacity:.75;
    letter-spacing:.5px;
    display:flex;align-items:center;gap:8px;
  }

  footer{
    text-align:center;
    padding:40px 6vw 60px;
    font-size:.75rem;
    color:var(--ink-soft);
    opacity:.6;
    letter-spacing:1px;
  }

  /* ---------- MUSIC TOGGLE ---------- */
  #music-toggle{
    position:fixed;
    bottom:22px;
    left:22px;
    z-index:50;
    width:48px;height:48px;
    border-radius:50%;
    border:1px solid rgba(255,255,255,0.7);
    background:linear-gradient(155deg,rgba(255,255,255,0.75),rgba(255,255,255,0.45));
    backdrop-filter:blur(10px);
    box-shadow:0 10px 26px -10px var(--shadow);
    display:flex;align-items:center;justify-content:center;
    font-size:1.1rem;
    cursor:pointer;
    transition:transform .3s ease, box-shadow .3s ease;
    color:var(--gold-deep);
  }
  #music-toggle:hover{transform:translateY(-3px) scale(1.05);box-shadow:0 14px 30px -10px var(--shadow);}
  #music-toggle[aria-pressed="true"]{color:#fff;background:linear-gradient(155deg,var(--gold-light),var(--gold-deep));}

  /* ---------- RESPONSIVE ---------- */
  @media(min-width:820px){
    section{max-width:820px;}
    .letter-card{padding:64px 70px;}
    .achieve-card{padding:64px 60px;}
  }

  @media(prefers-reduced-motion: reduce){
    *{animation-duration:.001ms !important;animation-iteration-count:1 !important;transition-duration:.001ms !important;}
  }

  /* focus visibility */
  button:focus-visible{outline:2px solid var(--gold-deep);outline-offset:3px;}
</style>
</head>
<body>

<div id="loader">
  <div class="loader-icon">🤍</div>
</div>

<canvas id="particles-canvas"></canvas>
<canvas id="confetti-canvas"></canvas>

<button id="music-toggle" aria-pressed="false" title="موسيقى خلفية (غير مفعّلة)">🎵</button>

<main>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-cap">🎓</div>
    <h1><span class="type-wrap" id="hero-title"></span></h1>
    <p class="subtitle">انتهت رحلة كانت من أصعب رحلات حياتك... واليوم بدأ فصل جديد.</p>
    <div class="scroll-cue"><span class="line"></span></div>
  </section>

  <!-- LETTER -->
  <section class="letter-wrap">
    <div class="glass letter-card reveal">
      <div class="seal">💌</div>
      <p class="reveal reveal-delay-1">يمكن النتيجة مش كانت الرقم اللي كنتي بتحلمي بيه، لكن عمرك ما كنتي مجرد رقم.</p>
      <p class="reveal reveal-delay-1">أنا شفت تعبك... شفت السهر... شفت الأيام اللي كنتي فيها تعبانة ولسه بتكملي.</p>
      <p class="reveal reveal-delay-2">87% مش هي اللي عرفتني بيكي... أنا عرفتك من عزيمتك، وصبرك، وإصرارك.</p>
      <p class="reveal reveal-delay-2">أنتِ خلصتي سنة كانت مليانة ضغط وخوف وتعب... ومع ذلك وصلتي للنهاية. وده بالنسبة ليا أكبر إنجاز.</p>
      <p class="reveal reveal-delay-3">أنا فخور بيكي جدًا... وفخور إني كنت معاكي في الرحلة دي.</p>
      <p class="reveal reveal-delay-3">ودي مجرد بداية... وأنا مؤمن إن اللي جاي هيكون أجمل بكتير.</p>
      <div class="signature reveal reveal-delay-3">🤍</div>
    </div>
  </section>

  <!-- ACHIEVEMENT -->
  <section>
    <div class="glass achieve-card reveal">
      <div class="achieve-row"><span>🎓</span><span>الثانوية العامة</span><span class="achieve-check">✅</span></div>
      <div class="achieve-score">87<span class="percent">%</span></div>
      <div class="achieve-label">النتيجة</div>
      <p class="achieve-quote">"النجاح الحقيقي مش إنك ما تتعبيش... النجاح الحقيقي إنك تفضلي واقفة رغم كل التعب."</p>
    </div>
  </section>

  <!-- QUALITIES -->
  <section class="qualities-section">
    <p class="qualities-intro reveal">فيه حاجات فيكي أكبر من أي رقم في أي شهادة</p>
    <div class="quality-grid">
      <div class="quality-card reveal">صبرك اللي ما خانك</div>
      <div class="quality-card reveal reveal-delay-1">إصرارك وقت ما كنتي عايزة توقفي</div>
      <div class="quality-card reveal reveal-delay-2">قلبك اللي فضل طيب حتى وانتِ تعبانة</div>
      <div class="quality-card reveal reveal-delay-3">قوتك اللي ما حد شافها غيري</div>
    </div>
  </section>

  <!-- QUOTE -->
  <section class="quote-section">
    <div class="quote-mark reveal">"</div>
    <blockquote class="reveal">مش كل الأحلام بتبدأ بالرقم اللي كنا عايزينه... لكن الأحلام الكبيرة بتبدأ بـ<span class="accent">الشخص اللي عمره ما استسلم</span>.</blockquote>
  </section>

  <!-- FINAL -->
  <section class="final-section">
    <div class="heart">
      <svg viewBox="0 0 32 29" class="heart-glow">
        <path d="M16 28.6C16 28.6 1.6 19.8 1.6 9.9C1.6 4.9 5.4 1 10.2 1C13.1 1 15.3 2.5 16 4.6C16.7 2.5 18.9 1 21.8 1C26.6 1 30.4 4.9 30.4 9.9C30.4 19.8 16 28.6 16 28.6Z"
          fill="url(#heartGrad)" />
        <defs>
          <linearGradient id="heartGrad" x1="0" y1="0" x2="32" y2="29" gradientUnits="userSpaceOnUse">
            <stop offset="0" stop-color="#E7B9C4"/>
            <stop offset="1" stop-color="#C9A15C"/>
          </linearGradient>
        </defs>
      </svg>
    </div>
    <p class="reveal">بحب أشوفك مبسوطة... وده اليوم اللي كنت مستنيه معاكي من زمان.</p>
    <p class="final-proud reveal">أنا فخور بيكي جدًا يا حبيبتي 🤍</p>
    <p class="final-en reveal">The journey isn't over… <br><b>It's only the beginning. ✨</b></p>
  </section>

  <footer>🤍</footer>

</main>

<script>
(function(){
  "use strict";

  /* ---------------- LOADER ---------------- */
  window.addEventListener('load', () => {
    setTimeout(()=>{
      document.getElementById('loader').classList.add('hide');
      burstConfetti();
    }, 1400);
  });

  /* ---------------- HERO TYPEWRITER ---------------- */
  const titleText = "🎓 مبروك يا بطلتي 🤍";
  const goldWord = "بطلتي";
  const titleEl = document.getElementById('hero-title');
  const words = titleText.split(' ');
  words.forEach((word, wi) => {
    const isGold = word === goldWord;
    const span = document.createElement('span');
    span.className = 'char' + (isGold ? ' gold-word' : '');
    span.textContent = word;
    span.style.animationDelay = isGold ? (0.5 + wi*0.16) + 's, 1.4s' : (0.5 + wi*0.16) + 's';
    titleEl.appendChild(span);
    if(wi !== words.length-1) titleEl.appendChild(document.createTextNode('\u00A0'));
  });

  /* ---------------- SCROLL REVEAL ---------------- */
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){
        e.target.classList.add('in');
        io.unobserve(e.target);
      }
    });
  }, {threshold:0.18, rootMargin:'0px 0px -40px 0px'});
  document.querySelectorAll('.reveal').forEach(el=>io.observe(el));

  /* ---------------- AMBIENT PARTICLES ---------------- */
  const pCanvas = document.getElementById('particles-canvas');
  const pCtx = pCanvas.getContext('2d');
  let W, H, particles=[];
  const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  function resize(){
    W = pCanvas.width = window.innerWidth;
    H = pCanvas.height = document.documentElement.scrollHeight;
  }
  window.addEventListener('resize', ()=>{ resize(); });
  resize();

  function initParticles(){
    const count = Math.min(60, Math.floor(window.innerWidth/18));
    particles = Array.from({length:count}, ()=>({
      x: Math.random()*W,
      y: Math.random()*H,
      r: Math.random()*2 + 0.6,
      speedY: Math.random()*0.25 + 0.05,
      speedX: (Math.random()-0.5)*0.15,
      alpha: Math.random()*0.5 + 0.15,
      pulse: Math.random()*Math.PI*2
    }));
  }
  initParticles();

  function drawParticles(){
    pCtx.clearRect(0,0,W,H);
    const scrollY = window.scrollY;
    particles.forEach(p=>{
      p.pulse += 0.02;
      const alpha = p.alpha * (0.6 + 0.4*Math.sin(p.pulse));
      pCtx.beginPath();
      pCtx.fillStyle = `rgba(201,161,92,${alpha})`;
      pCtx.arc(p.x, (p.y - scrollY*0.15 + H*3)%H, p.r, 0, Math.PI*2);
      pCtx.fill();
      p.y -= p.speedY;
      p.x += p.speedX;
      if(p.y < -10) p.y = H + 10;
      if(p.x < -10) p.x = W+10;
      if(p.x > W+10) p.x = -10;
    });
    if(!reduceMotion) requestAnimationFrame(drawParticles);
  }
  if(!reduceMotion) requestAnimationFrame(drawParticles);
  else drawParticles();

  window.addEventListener('load', ()=> setTimeout(()=>{ resize(); initParticles(); }, 1600));

  /* ---------------- CONFETTI BURST ---------------- */
  const cCanvas = document.getElementById('confetti-canvas');
  const cCtx = cCanvas.getContext('2d');
  function sizeConfettiCanvas(){
    cCanvas.width = window.innerWidth;
    cCanvas.height = window.innerHeight;
  }
  sizeConfettiCanvas();
  window.addEventListener('resize', sizeConfettiCanvas);

  const confettiColors = ['#C9A15C','#EAD2A0','#E7B9C4','#F5DEE3','#FFFDFB'];

  function burstConfetti(){
    if(reduceMotion) return;
    sizeConfettiCanvas();
    const pieces = Array.from({length:90}, ()=>({
      x: cCanvas.width/2 + (Math.random()-0.5)*120,
      y: cCanvas.height*0.25,
      vx: (Math.random()-0.5)*10,
      vy: Math.random()*-8 - 3,
      size: Math.random()*7+4,
      color: confettiColors[Math.floor(Math.random()*confettiColors.length)],
      rot: Math.random()*Math.PI,
      vrot: (Math.random()-0.5)*0.3,
      gravity: 0.22 + Math.random()*0.08,
      life: 0
    }));
    let frame=0;
    function animate(){
      frame++;
      cCtx.clearRect(0,0,cCanvas.width,cCanvas.height);
      let alive=false;
      pieces.forEach(p=>{
        p.vy += p.gravity;
        p.x += p.vx;
        p.y += p.vy;
        p.rot += p.vrot;
        p.life++;
        if(p.y < cCanvas.height+20) alive = true;
        const fade = Math.max(0, 1 - p.life/140);
        cCtx.save();
        cCtx.globalAlpha = fade;
        cCtx.translate(p.x,p.y);
        cCtx.rotate(p.rot);
        cCtx.fillStyle = p.color;
        cCtx.fillRect(-p.size/2,-p.size/2,p.size,p.size*0.6);
        cCtx.restore();
      });
      if(alive && frame < 160) requestAnimationFrame(animate);
      else cCtx.clearRect(0,0,cCanvas.width,cCanvas.height);
    }
    animate();
  }

  /* ---------------- FLOATING HEARTS ---------------- */
  function spawnHeart(){
    const h = document.createElement('div');
    h.className = 'floating-heart';
    h.textContent = Math.random() > 0.5 ? '🤍' : '💛';
    h.style.left = (Math.random()*90 + 3) + 'vw';
    h.style.setProperty('--drift', (Math.random()*80-40)+'px');
    const duration = 9 + Math.random()*6;
    h.style.animationDuration = duration + 's';
    document.body.appendChild(h);
    setTimeout(()=> h.remove(), duration*1000 + 200);
  }
  if(!reduceMotion){
    setInterval(spawnHeart, 3600);
    setTimeout(spawnHeart, 2200);
  }

  /* ---------------- MUSIC TOGGLE (visual only — no audio asset attached) ---------------- */
  const musicBtn = document.getElementById('music-toggle');
  let musicOn = false;
  musicBtn.addEventListener('click', ()=>{
    musicOn = !musicOn;
    musicBtn.setAttribute('aria-pressed', musicOn);
    musicBtn.textContent = musicOn ? '🎶' : '🎵';
    musicBtn.title = musicOn ? 'الموسيقى مفعّلة (أضف ملف صوت للتفعيل الفعلي)' : 'موسيقى خلفية (غير مفعّلة)';
  });

})();
</script>

</body>
</html>

