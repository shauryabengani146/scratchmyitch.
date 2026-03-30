<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scratch The Itch — India's Biggest Problems. Your Next Big Startup.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,600;1,9..40,300&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<style>
:root{--bg:#09090b;--surf:#111114;--surf2:#18181c;--bdr:#27272f;--acc:#e4ff3d;--acc2:#ff4d1c;--acc3:#3dffd8;--txt:#efefef;--mut:#6b6b7a;--glow:rgba(228,255,61,.045)}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--txt);font-family:'DM Sans',sans-serif;overflow-x:hidden;cursor:none}

.cur{width:10px;height:10px;background:var(--acc);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .18s,height .18s}
.cur-r{width:34px;height:34px;border:1.5px solid rgba(228,255,61,.3);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:left .1s,top .1s,width .2s,height .2s,border-color .2s}
.cur.h{width:18px;height:18px}.cur-r.h{width:50px;height:50px;border-color:var(--acc)}

nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:18px 48px;transition:background .3s,border-color .3s;border-bottom:1px solid transparent}
nav.sc{background:rgba(9,9,11,.9);backdrop-filter:blur(14px);border-bottom-color:var(--bdr)}
.nl{font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:3px;color:var(--acc)}
.nr{display:flex;gap:28px}
.nr a{color:var(--mut);text-decoration:none;font-size:12px;letter-spacing:1.5px;text-transform:uppercase;font-weight:600;transition:color .2s}
.nr a:hover{color:var(--txt)}

.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:flex-end;padding:0 48px 64px;position:relative;overflow:hidden}
.hbg{position:absolute;inset:0;background:radial-gradient(ellipse 55% 55% at 72% 38%,rgba(228,255,61,.09) 0%,transparent 68%),radial-gradient(ellipse 35% 35% at 18% 78%,rgba(255,77,28,.06) 0%,transparent 55%)}
.hnz{position:absolute;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.025'/%3E%3C/svg%3E");pointer-events:none}

.twrap{position:absolute;top:96px;left:0;right:0;overflow:hidden;border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr);padding:11px 0}
.tinner{display:flex;gap:56px;animation:tick 28s linear infinite;white-space:nowrap}
.ti{font-family:'Bebas Neue',sans-serif;font-size:12px;letter-spacing:3px;color:var(--mut)}
.ti span{color:var(--acc);margin-right:8px}
@keyframes tick{from{transform:translateX(0)}to{transform:translateX(-50%)}}

.ho{font-size:10px;letter-spacing:5px;text-transform:uppercase;color:var(--acc);font-weight:700;margin-bottom:20px;opacity:0;animation:fu .7s .3s forwards}
.ht{font-family:'Bebas Neue',sans-serif;font-size:clamp(68px,11.5vw,172px);line-height:.88;opacity:0;animation:fu .7s .5s forwards}
.ht .ac{color:var(--acc)}.ht .it{font-family:'Instrument Serif',serif;font-style:italic;color:var(--mut)}
.hsub{max-width:460px;font-size:15px;line-height:1.65;color:var(--mut);margin-top:28px;font-weight:300;opacity:0;animation:fu .7s .7s forwards}
.hst{display:flex;gap:44px;margin-top:44px;opacity:0;animation:fu .7s .9s forwards}
.sn{font-family:'Bebas Neue',sans-serif;font-size:38px;color:var(--acc);line-height:1}
.sl{font-size:11px;color:var(--mut);letter-spacing:1px;text-transform:uppercase;margin-top:3px}
.hscr{position:absolute;right:48px;bottom:64px;display:flex;flex-direction:column;align-items:center;gap:10px;opacity:0;animation:fu .7s 1.1s forwards}
.hscr span{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--mut);writing-mode:vertical-rl}
.sln{width:1px;height:56px;background:linear-gradient(to bottom,var(--acc),transparent);animation:sp 2s ease-in-out infinite}
@keyframes sp{0%,100%{opacity:.3}50%{opacity:1}}
@keyframes fu{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}

.mq{overflow:hidden;border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr);padding:18px 0}
.mq-i{display:flex;gap:44px;animation:tick 18s linear infinite;white-space:nowrap}
.mw{font-family:'Bebas Neue',sans-serif;font-size:30px;letter-spacing:4px;color:transparent;-webkit-text-stroke:1px var(--bdr)}
.mw.f{color:var(--txt);-webkit-text-stroke:none}

.intro{padding:72px 48px;border-top:1px solid var(--bdr);display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}
.intro h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(38px,5.5vw,72px);line-height:.92}
.intro h2 em{font-family:'Instrument Serif',serif;font-style:italic;color:var(--mut)}
.intro p{font-size:15px;line-height:1.85;color:var(--mut);font-weight:300}
.intro strong{color:var(--txt);font-weight:600}
.slbl{font-size:9px;letter-spacing:5px;text-transform:uppercase;color:var(--acc);font-weight:700;margin-bottom:14px;display:flex;align-items:center;gap:10px}
.slbl::before{content:'';display:block;width:28px;height:1px;background:var(--acc)}

.t10{padding:72px 48px;background:var(--surf);border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr)}
.t10ttl{font-family:'Bebas Neue',sans-serif;font-size:clamp(44px,7vw,90px);line-height:.9;margin-bottom:44px}
.t10ttl .dim{color:var(--bdr)}
.t10list{display:flex;flex-direction:column}
.t10r{display:grid;grid-template-columns:60px 1fr 120px 140px;align-items:center;gap:20px;padding:24px 0;border-bottom:1px solid var(--bdr);cursor:none;transition:padding-left .25s}
.t10r:first-child{border-top:1px solid var(--bdr)}
.t10r:hover{padding-left:14px}
.t10rk{font-family:'Bebas Neue',sans-serif;font-size:44px;color:var(--bdr);line-height:1;text-align:center;transition:color .2s}
.t10r:hover .t10rk{color:var(--acc)}
.t10q{font-family:'Instrument Serif',serif;font-size:18px;font-style:italic;line-height:1.45}
.t10cat{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--mut);font-weight:600;text-align:center}
.t10sc{text-align:right}.t10sc .n{font-family:'Bebas Neue',sans-serif;font-size:34px;color:var(--acc);line-height:1}
.t10sc .l{font-size:9px;letter-spacing:2px;color:var(--mut);text-transform:uppercase}

.fsec{padding:0 48px 36px}
.fbar{display:flex;gap:8px;flex-wrap:wrap;padding:18px 0;border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr);margin-bottom:44px}
.fb{background:transparent;border:1px solid var(--bdr);color:var(--mut);padding:7px 18px;border-radius:100px;font-size:11px;font-family:'DM Sans',sans-serif;letter-spacing:.5px;font-weight:600;cursor:none;transition:all .2s}
.fb:hover,.fb.on{background:var(--acc);color:var(--bg);border-color:var(--acc)}

.gsec{padding:0 48px 100px}
.gh{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:40px}
.ghttl{font-family:'Bebas Neue',sans-serif;font-size:clamp(44px,7vw,90px);line-height:.9}
.ghttl .dim{color:var(--bdr)}
.pcnt{font-family:'Bebas Neue',sans-serif;font-size:13px;letter-spacing:3px;color:var(--mut)}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(350px,1fr));gap:2px}

.card{background:var(--surf);border:1px solid var(--bdr);padding:28px;position:relative;overflow:hidden;transition:transform .28s,border-color .28s;cursor:none}
.card::before{content:'';position:absolute;inset:0;background:var(--glow);opacity:0;transition:opacity .28s;pointer-events:none}
.card:hover{border-color:var(--acc);transform:translateY(-3px);z-index:2}
.card:hover::before{opacity:1}
.card.hidden{display:none}

.ctop{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:16px}
.ccat{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--mut);font-weight:700}
.isc{display:flex;flex-direction:column;align-items:flex-end;gap:3px}
.isc-n{font-family:'Bebas Neue',sans-serif;font-size:32px;line-height:1;color:var(--acc)}
.isc-l{font-size:8px;letter-spacing:2px;text-transform:uppercase;color:var(--mut)}
.isc-bar{width:56px;height:2px;background:var(--bdr);border-radius:2px;overflow:hidden;margin-top:3px}
.isc-fill{height:100%;background:var(--acc);border-radius:2px}

.cq{font-family:'Instrument Serif',serif;font-size:18px;font-style:italic;line-height:1.45;color:var(--txt);margin-bottom:18px}

.xbtn{background:transparent;border:none;color:var(--acc);font-size:10px;letter-spacing:2px;text-transform:uppercase;font-family:'DM Sans',sans-serif;font-weight:700;cursor:none;padding:0;display:flex;align-items:center;gap:8px;transition:gap .2s}
.xbtn:hover{gap:13px}.xbtn svg{transition:transform .3s}.xbtn.open svg{transform:rotate(45deg)}

.det{max-height:0;overflow:hidden;transition:max-height .5s cubic-bezier(.4,0,.2,1),opacity .35s;opacity:0}
.det.open{max-height:700px;opacity:1}
.det-in{padding-top:20px;border-top:1px solid var(--bdr);margin-top:16px}

.dbl{margin-bottom:14px}
.dbl-lbl{font-size:8px;letter-spacing:3px;text-transform:uppercase;color:var(--acc2);font-weight:700;margin-bottom:7px}
.dbl p{font-size:13px;line-height:1.72;color:var(--mut);font-weight:300}

.ai-area{background:var(--surf2);border:1px solid var(--bdr);border-radius:4px;padding:14px;margin-top:8px;min-height:52px}
.ai-load{display:none;align-items:center;gap:8px;font-size:12px;color:var(--mut)}
.dots span{display:inline-block;width:5px;height:5px;background:var(--acc);border-radius:50%;margin-right:3px;animation:blink 1.2s ease-in-out infinite}
.dots span:nth-child(2){animation-delay:.2s}.dots span:nth-child(3){animation-delay:.4s}
@keyframes blink{0%,80%,100%{opacity:.2}40%{opacity:1}}
.ai-out{font-size:13px;line-height:1.72;color:var(--txt);font-weight:300;display:none}
.ai-hint{font-size:12px;color:var(--mut)}
.ai-badge{display:inline-flex;align-items:center;gap:5px;font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--acc3);font-weight:700;margin-bottom:8px}
.ai-badge::before{content:'';width:6px;height:6px;background:var(--acc3);border-radius:50%;animation:pulse 2s infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}
.stag{display:inline-block;background:rgba(61,255,216,.07);border:1px solid rgba(61,255,216,.18);color:var(--acc3);font-size:10px;padding:3px 10px;border-radius:3px;margin:3px 3px 3px 0;font-weight:600}
.mkt{display:inline-flex;align-items:center;gap:5px;font-size:11px;color:var(--txt);font-weight:600;margin-top:10px}
.mkt .dot{width:5px;height:5px;background:var(--acc);border-radius:50%;flex-shrink:0}

.miss{padding:100px 48px;text-align:center;position:relative;overflow:hidden}
.miss-bg{position:absolute;inset:0;background:radial-gradient(ellipse 45% 55% at 50% 50%,rgba(228,255,61,.04) 0%,transparent 65%)}
.miss h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(44px,8.5vw,110px);line-height:.9;position:relative}
.miss h2 .gh{color:transparent;-webkit-text-stroke:1px var(--bdr)}
.miss-body{max-width:600px;margin:36px auto 0;font-size:17px;line-height:1.82;color:var(--mut);font-weight:300;position:relative}
.miss-body strong{color:var(--txt);font-weight:600}
.ctabtn{display:inline-flex;align-items:center;gap:10px;margin-top:44px;padding:16px 36px;background:var(--acc);color:var(--bg);font-size:12px;font-weight:700;letter-spacing:2px;text-transform:uppercase;text-decoration:none;font-family:'DM Sans',sans-serif;transition:background .2s,transform .2s;cursor:none}
.ctabtn:hover{background:var(--txt);transform:translateY(-2px)}
.ctabtn svg{transition:transform .2s}.ctabtn:hover svg{transform:translateX(4px)}

footer{border-top:1px solid var(--bdr);padding:36px 48px;display:flex;justify-content:space-between;align-items:center}
.fl{font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:2px;color:var(--mut)}
.fn{font-size:11px;color:var(--mut);font-weight:300}.fn strong{color:var(--acc)}

.rv{opacity:0;transform:translateY(28px);transition:opacity .6s,transform .6s}.rv.vis{opacity:1;transform:translateY(0)}

@media(max-width:768px){
  nav{padding:14px 20px}.nr{display:none}
  .hero,.intro,.t10,.fsec,.gsec,.miss,footer{padding-left:20px;padding-right:20px}
  .intro{grid-template-columns:1fr;gap:28px}
  .t10r{grid-template-columns:44px 1fr}.t10cat,.t10sc{display:none}
  .hst{gap:24px;flex-wrap:wrap}.grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<div class="cur" id="cur"></div>
<div class="cur-r" id="curR"></div>

<nav id="nav">
  <div class="nl">SCRATCH THE ITCH</div>
  <div class="nr">
    <a href="#top10">Top 10</a>
    <a href="#problems">All Problems</a>
    <a href="#mission">Mission</a>
  </div>
</nav>

<section class="hero">
  <div class="hbg"></div><div class="hnz"></div>
  <div class="twrap"><div class="tinner">
    <span class="ti"><span>✦</span>94.5 — REAL ESTATE</span>
    <span class="ti"><span>✦</span>92.4 — SAAS</span>
    <span class="ti"><span>✦</span>92.1 — LOGISTICS</span>
    <span class="ti"><span>✦</span>90.5 — FINTECH</span>
    <span class="ti"><span>✦</span>10,000+ VERIFIED PROBLEMS</span>
    <span class="ti"><span>✦</span>50K+ CONTRIBUTORS</span>
    <span class="ti"><span>✦</span>AI-POWERED SOLUTIONS BY CLAUDE</span>
    <span class="ti"><span>✦</span>94.5 — REAL ESTATE</span>
    <span class="ti"><span>✦</span>92.4 — SAAS</span>
    <span class="ti"><span>✦</span>92.1 — LOGISTICS</span>
    <span class="ti"><span>✦</span>90.5 — FINTECH</span>
    <span class="ti"><span>✦</span>10,000+ VERIFIED PROBLEMS</span>
    <span class="ti"><span>✦</span>50K+ CONTRIBUTORS</span>
    <span class="ti"><span>✦</span>AI-POWERED SOLUTIONS BY CLAUDE</span>
  </div></div>
  <div class="ho">India's Problem Wishlist for Founders</div>
  <h1 class="ht">INDIA<br><span class="ac">ITCHES.</span><br><span class="it">Do you dare</span><br>SCRATCH IT?</h1>
  <p class="hsub">50,000 Indians told us exactly where it hurts. Every problem here is real, ranked by Itch Score. Click any card to generate a live AI startup blueprint powered by Claude.</p>
  <div class="hst">
    <div><div class="sn">10K+</div><div class="sl">Verified Problems</div></div>
    <div><div class="sn">50K+</div><div class="sl">Contributors</div></div>
    <div><div class="sn">17</div><div class="sl">Industries</div></div>
    <div><div class="sn">94.5</div><div class="sl">Highest Score</div></div>
  </div>
  <div class="hscr"><div class="sln"></div><span>Scroll</span></div>
</section>

<div class="mq"><div class="mq-i">
  <span class="mw f">BUILD</span><span class="mw">SOLVE</span><span class="mw f">SCRATCH</span><span class="mw">DISRUPT</span>
  <span class="mw f">FOUND</span><span class="mw">ITERATE</span><span class="mw f">GROW</span><span class="mw">LAUNCH</span>
  <span class="mw f">BUILD</span><span class="mw">SOLVE</span><span class="mw f">SCRATCH</span><span class="mw">DISRUPT</span>
  <span class="mw f">FOUND</span><span class="mw">ITERATE</span><span class="mw f">GROW</span><span class="mw">LAUNCH</span>
</div></div>

<section class="intro rv">
  <div>
    <div class="slbl">The Context</div>
    <h2>WHAT IS<br><em>THIS</em><br>ALL ABOUT?</h2>
  </div>
  <div>
    <p>India is a country of <strong>1.4 billion people</strong> with an almost infinite number of unsolved problems. Over <strong>50,000 real Indians</strong> submitted their biggest daily frustrations across health, business, finance, housing, logistics, and more.</p>
    <br>
    <p>Each problem received an <strong>Itch Score</strong> — measuring severity, frequency, and market readiness. We show only the <strong>highest-scoring problem per category</strong>. Click <strong>"Generate AI Solution"</strong> on any card to get a live startup blueprint by Claude AI — with product ideas, revenue model, and India-specific strategy.</p>
  </div>
</section>

<section class="t10" id="top10">
  <div class="slbl rv">Hall of Pain</div>
  <div class="t10ttl rv">TOP <span class="dim">10</span><br>ITCHES</div>
  <div class="t10list">
    <div class="t10r rv"><div class="t10rk">01</div><div class="t10q">Why don't homebuyers have standardized neighborhood quality data reports?</div><div class="t10cat">Real Estate</div><div class="t10sc"><div class="n">94.5</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">02</div><div class="t10q">Why can't shop owners create websites without coding knowledge?</div><div class="t10cat">SaaS</div><div class="t10sc"><div class="n">92.4</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">03</div><div class="t10q">Why is booking cargo vehicles harder than booking passenger transport?</div><div class="t10cat">Logistics</div><div class="t10sc"><div class="n">92.1</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">04</div><div class="t10q">Why do people struggle to track where their money goes each month?</div><div class="t10cat">FinTech</div><div class="t10sc"><div class="n">90.5</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">05</div><div class="t10q">Why can't first-time used car buyers verify car histories, conditions and future maintenance costs?</div><div class="t10cat">Automotive</div><div class="t10sc"><div class="n">89.2</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">06</div><div class="t10q">Why can't renters access verified mold, pest or hazard data before signing leases?</div><div class="t10cat">Housing</div><div class="t10sc"><div class="n">88.7</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">07</div><div class="t10q">Why is caring for aging parents for sole earners across cities still fragmented and stressful?</div><div class="t10cat">Healthcare</div><div class="t10sc"><div class="n">87.3</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">08</div><div class="t10q">Why do teachers lack real-time mental health support at work?</div><div class="t10cat">Healthcare</div><div class="t10sc"><div class="n">85.8</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">09</div><div class="t10q">Why do STEM students face education loan anxiety from unclear costs?</div><div class="t10cat">Career</div><div class="t10sc"><div class="n">84.1</div><div class="l">Itch Score</div></div></div>
    <div class="t10r rv"><div class="t10rk">10</div><div class="t10q">Why can't consumers see verified kitchen safety standards on food delivery apps?</div><div class="t10cat">Consumer</div><div class="t10sc"><div class="n">82.9</div><div class="l">Itch Score</div></div></div>
  </div>
</section>

<div class="mq"><div class="mq-i" style="animation-direction:reverse">
  <span class="mw">REAL ESTATE</span><span class="mw f">FINTECH</span><span class="mw">SAAS</span><span class="mw f">LOGISTICS</span>
  <span class="mw">HEALTHCARE</span><span class="mw f">EDTECH</span><span class="mw">B2B</span><span class="mw f">CONSUMER</span>
  <span class="mw">REAL ESTATE</span><span class="mw f">FINTECH</span><span class="mw">SAAS</span><span class="mw f">LOGISTICS</span>
  <span class="mw">HEALTHCARE</span><span class="mw f">EDTECH</span><span class="mw">B2B</span><span class="mw f">CONSUMER</span>
</div></div>

<section class="fsec" id="problems">
  <div class="fbar">
    <button class="fb on" data-f="all">All Industries</button>
    <button class="fb" data-f="realestate">Real Estate</button>
    <button class="fb" data-f="saas">SaaS</button>
    <button class="fb" data-f="logistics">Logistics</button>
    <button class="fb" data-f="fintech">FinTech</button>
    <button class="fb" data-f="automotive">Automotive</button>
    <button class="fb" data-f="housing">Housing</button>
    <button class="fb" data-f="healthcare">Healthcare</button>
    <button class="fb" data-f="edtech">EdTech</button>
    <button class="fb" data-f="consumer">Consumer</button>
    <button class="fb" data-f="b2b">B2B</button>
    <button class="fb" data-f="food">Food & Bev</button>
    <button class="fb" data-f="beauty">Beauty</button>
  </div>
</section>

<section class="gsec">
  <div class="gh rv">
    <div class="ghttl">ALL <span class="dim">ITCHES</span></div>
    <div class="pcnt" id="pcnt">SHOWING 20 PROBLEMS</div>
  </div>
  <div class="grid" id="grid">

    <!-- card macro: cat, score, label, question, pain, market -->
    <!-- REAL ESTATE 94.5 -->
    <div class="card rv" data-cat="realestate">
      <div class="ctop"><div class="ccat">Real Estate</div><div class="isc"><div class="isc-n">94.5</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:94.5%"></div></div></div></div>
      <div class="cq">Why don't homebuyers have standardized neighborhood quality data reports?</div>
      <button class="xbtn" data-cat="Real Estate" data-q="Why don't homebuyers have standardized neighborhood quality data reports?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Homebuyers spend ₹50–100L on a flat without knowing if the neighbourhood floods, has poor air quality, unreliable water supply, rising crime, or failing schools nearby. All this data exists scattered across 15 government websites nobody visits.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India housing market: ₹13+ Lakh Cr/year</div>
      </div></div>
    </div>

    <!-- SAAS 92.4 -->
    <div class="card rv" data-cat="saas">
      <div class="ctop"><div class="ccat">SaaS</div><div class="isc"><div class="isc-n">92.4</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:92.4%"></div></div></div></div>
      <div class="cq">Why can't shop owners create websites without coding knowledge?</div>
      <button class="xbtn" data-cat="SaaS / No-Code" data-q="Why can't shop owners create websites without coding knowledge?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>India has 63M+ small businesses. Most can't afford a ₹30,000 website or a developer who ghosts after payment. Shopify and Wix are too expensive and English-only. These shop owners are losing customers to rivals who got lucky with a nephew who codes.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>63M+ MSMEs in India, &lt;5% have an online presence</div>
      </div></div>
    </div>

    <!-- LOGISTICS 92.1 -->
    <div class="card rv" data-cat="logistics">
      <div class="ctop"><div class="ccat">Logistics</div><div class="isc"><div class="isc-n">92.1</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:92.1%"></div></div></div></div>
      <div class="cq">Why is booking cargo vehicles harder than booking passenger transport?</div>
      <button class="xbtn" data-cat="Logistics" data-q="Why is booking cargo vehicles harder than booking passenger transport?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>A small business needing a tempo to move goods calls 5 brokers, haggles blind on price, has no GPS tracking, and prays the driver shows up. Booking an Ola takes 30 seconds. Booking a truck still takes 3 days and a miracle.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India's freight market: $350B+ by 2030</div>
      </div></div>
    </div>

    <!-- FINTECH 90.5 -->
    <div class="card rv" data-cat="fintech">
      <div class="ctop"><div class="ccat">FinTech</div><div class="isc"><div class="isc-n">90.5</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:90.5%"></div></div></div></div>
      <div class="cq">Why do people struggle to track where their money goes each month?</div>
      <button class="xbtn" data-cat="FinTech / Personal Finance" data-q="Why do people struggle to track where their money goes each month?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>UPI has made payments invisible — which means spending is invisible too. Indians get 40+ transaction SMS/month across 4+ bank accounts and 2 wallets. Nobody knows their actual monthly spend until they're broke. Existing apps require manual entry nobody does.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>500M+ UPI users with zero spending visibility</div>
      </div></div>
    </div>

    <!-- AUTOMOTIVE 89.2 -->
    <div class="card rv" data-cat="automotive">
      <div class="ctop"><div class="ccat">Automotive</div><div class="isc"><div class="isc-n">89.2</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:89.2%"></div></div></div></div>
      <div class="cq">Why can't first-time used car buyers verify car histories, conditions and future maintenance costs?</div>
      <button class="xbtn" data-cat="Automotive / Consumer Tech" data-q="Why can't first-time used car buyers verify car histories, conditions and future maintenance costs?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>The used car market is rife with odometer fraud, flood-damaged vehicles sold as excellent condition, and undisclosed accident histories. First-time buyers with no mechanical knowledge are routinely exploited. You can spend ₹5L and discover it's a lemon in week two.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>Used car market: ₹2+ Lakh Cr/year in India</div>
      </div></div>
    </div>

    <!-- HOUSING 88.7 -->
    <div class="card rv" data-cat="housing">
      <div class="ctop"><div class="ccat">Housing</div><div class="isc"><div class="isc-n">88.7</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:88.7%"></div></div></div></div>
      <div class="cq">Why can't renters access verified mold, pest or hazard data before signing leases?</div>
      <button class="xbtn" data-cat="Housing / PropTech" data-q="Why can't renters access verified mold, pest or hazard data before signing leases?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Renters discover black mold, cockroach infestations, and faulty wiring — always after signing a 11-month lease with 2 months advance. There's no inspection standard, no disclosure law, and brokers show flats only in bright afternoon light for a reason.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>72M+ renter households in India, zero inspection standards</div>
      </div></div>
    </div>

    <!-- HEALTHCARE — Aging 87.3 -->
    <div class="card rv" data-cat="healthcare">
      <div class="ctop"><div class="ccat">Healthcare</div><div class="isc"><div class="isc-n">87.3</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:87.3%"></div></div></div></div>
      <div class="cq">Why is caring for aging parents for sole earners across cities still fragmented and stressful?</div>
      <button class="xbtn" data-cat="Healthcare / Elder Care" data-q="Why is caring for aging parents for sole earners across cities still fragmented and stressful?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>A software engineer in Bangalore with aging parents in Lucknow manages their health via panicked phone calls. Every doctor visit is a logistical crisis — finding a cab, someone to accompany them, knowing which specialist, carrying paper files. The guilt is constant and the system offers nothing.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>138M Indians above 60 — fastest growing demographic</div>
      </div></div>
    </div>

    <!-- HEALTHCARE — Teachers 85.8 -->
    <div class="card rv" data-cat="healthcare">
      <div class="ctop"><div class="ccat">Healthcare / EdTech</div><div class="isc"><div class="isc-n">85.8</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:85.8%"></div></div></div></div>
      <div class="cq">Why do teachers lack real-time mental health support at work?</div>
      <button class="xbtn" data-cat="Healthcare / EdTech" data-q="Why do teachers lack real-time mental health support at work?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Teachers handle 40+ children per class, admin workload, and parent pressure — while being expected to be emotionally available 100% of the time. India has 9M+ school teachers with zero workplace mental health infrastructure. Burnout is endemic. Schools don't even have a counsellor for teachers.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>9M+ school teachers in India, near-zero mental health coverage</div>
      </div></div>
    </div>

    <!-- EDTECH 84.1 -->
    <div class="card rv" data-cat="edtech">
      <div class="ctop"><div class="ccat">EdTech / Career</div><div class="isc"><div class="isc-n">84.1</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:84.1%"></div></div></div></div>
      <div class="cq">Why do STEM students face education loan anxiety from unclear costs in 2026?</div>
      <button class="xbtn" data-cat="EdTech / FinTech" data-q="Why do STEM students face education loan anxiety from unclear costs in 2026?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Students take ₹15–25L loans without understanding actual placement rates, real salaries (not the average package fiction), or how long repayment takes. The commitment happens at 18 with zero financial literacy. Many spend a decade repaying a degree that never paid off.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>Education loans outstanding: ₹1.07 Lakh Cr in India</div>
      </div></div>
    </div>

    <!-- CONSUMER 82.9 -->
    <div class="card rv" data-cat="consumer">
      <div class="ctop"><div class="ccat">Consumer Services</div><div class="isc"><div class="isc-n">82.9</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:82.9%"></div></div></div></div>
      <div class="cq">Why can't consumers see verified kitchen safety standards on food delivery apps?</div>
      <button class="xbtn" data-cat="Consumer Services / FoodTech" data-q="Why can't consumers see verified kitchen safety standards on food delivery apps?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Swiggy and Zomato show beautiful food photos. Nobody shows you the kitchen they came from. FSSAI licenses are impossible to look up. Food safety incidents are rising. Every person ordering delivery is choosing to trust a stranger's kitchen hygiene — blindly.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India food delivery market: ₹1.5 Lakh Cr by 2030</div>
      </div></div>
    </div>

    <!-- B2B 82.8 -->
    <div class="card rv" data-cat="b2b">
      <div class="ctop"><div class="ccat">B2B Services</div><div class="isc"><div class="isc-n">82.8</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:82.8%"></div></div></div></div>
      <div class="cq">Why can't SMEs negotiate favorable payment terms with large buyers?</div>
      <button class="xbtn" data-cat="B2B Services / FinTech" data-q="Why can't SMEs negotiate favorable payment terms with large buyers?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Small businesses supplying large corporates face 60–90 day payment cycles with zero negotiating power. This forces them into high-interest debt just to survive the gap between delivering and getting paid. A startup founder's entire cash flow depends on when a corporate feels like approving an invoice.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>₹45–60 Lakh Cr of SME receivables locked annually</div>
      </div></div>
    </div>

    <!-- HEALTHCARE Sleep 81.7 -->
    <div class="card rv" data-cat="healthcare">
      <div class="ctop"><div class="ccat">Healthcare / Wellness</div><div class="isc"><div class="isc-n">81.7</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:81.7%"></div></div></div></div>
      <div class="cq">Why can't anxious people find trustworthy non-prescription sleep solutions easily?</div>
      <button class="xbtn" data-cat="Healthcare / Wellness" data-q="Why can't anxious people find trustworthy non-prescription sleep solutions easily?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Sleep disorders affect 33% of urban Indians. Getting a prescription involves doctor visits, stigma, and dependency risk. Non-prescription options are a minefield of unregulated supplements and wellness grift. Anxious people don't know what actually works and is safe for long-term use.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India sleep disorder market: ₹8,000+ Cr and growing</div>
      </div></div>
    </div>

    <!-- HARDWARE 80.4 -->
    <div class="card rv" data-cat="consumer">
      <div class="ctop"><div class="ccat">Hardware / Consumer</div><div class="isc"><div class="isc-n">80.4</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:80.4%"></div></div></div></div>
      <div class="cq">Why is connecting specialized hardware to laptops still unreliable and frustrating?</div>
      <button class="xbtn" data-cat="Hardware / Consumer Tech" data-q="Why is connecting specialized hardware to laptops still unreliable and frustrating?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Medical devices, lab instruments, MIDI controllers, industrial sensors — connecting these to modern laptops means driver hell, USB-C incompatibility, and hours on forums. SMEs and research labs in India lose real productivity to hardware connectivity issues with zero customer support.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India hardware market: $300B+ by 2026</div>
      </div></div>
    </div>

    <!-- CAREER 79.6 -->
    <div class="card rv" data-cat="edtech">
      <div class="ctop"><div class="ccat">Career / EdTech</div><div class="isc"><div class="isc-n">79.6</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:79.6%"></div></div></div></div>
      <div class="cq">Why do people leaving formal education lack structure, mentorship and clear career guidance?</div>
      <button class="xbtn" data-cat="EdTech / Career Guidance" data-q="Why do people leaving formal education lack structure, mentorship and clear career guidance?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Dropouts, career changers, and non-traditional learners have no roadmap. Society brands them as failures. Every coaching center sells the same stale courses. Mentorship is a luxury for IIT graduates. Everyone else navigates career decisions with YouTube and peer pressure.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>30M+ students exit education without a clear path annually</div>
      </div></div>
    </div>

    <!-- FOOD 79.0 -->
    <div class="card rv" data-cat="food">
      <div class="ctop"><div class="ccat">Food & Beverage</div><div class="isc"><div class="isc-n">79.0</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:79%"></div></div></div></div>
      <div class="cq">Why can't small restaurants access wholesale ingredient pricing without large minimum orders?</div>
      <button class="xbtn" data-cat="Food & Beverage / B2B" data-q="Why can't small restaurants access wholesale ingredient pricing without large minimum orders?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>A small dhaba ordering 10kg of onions pays retail price while hotel chains pay 60% less. Distributors ignore small restaurants. Large minimum order quantities are impossible for a 20-seat place. The price disparity destroys margins and makes it impossible to compete with cloud kitchens.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>7.5M+ restaurants in India — majority are small format</div>
      </div></div>
    </div>

    <!-- BEAUTY 78.1 -->
    <div class="card rv" data-cat="beauty">
      <div class="ctop"><div class="ccat">Beauty & Personal Care</div><div class="isc"><div class="isc-n">78.1</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:78.1%"></div></div></div></div>
      <div class="cq">Why do Indian consumers buy skincare blind without knowing if products are safe for their skin type and climate?</div>
      <button class="xbtn" data-cat="Beauty & Personal Care" data-q="Why do Indian consumers buy skincare blind without knowing if products are safe for their skin type and climate?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Influencer skincare advice ignores India's diversity — a dark-skinned consumer in Chennai's humidity has radically different needs from someone in Rajasthan's dry heat. Ingredient labels are incomprehensible jargon. Allergic reactions are common, and returns aren't accepted after opening.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India beauty market: ₹1.8 Lakh Cr, growing at 11% CAGR</div>
      </div></div>
    </div>

    <!-- FINTECH 2 77.6 -->
    <div class="card rv" data-cat="fintech">
      <div class="ctop"><div class="ccat">FinTech</div><div class="isc"><div class="isc-n">77.6</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:77.6%"></div></div></div></div>
      <div class="cq">Why can't blue-collar workers build financial credit history to access affordable loans?</div>
      <button class="xbtn" data-cat="FinTech / Credit" data-q="Why can't blue-collar workers build financial credit history to access affordable loans?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Construction workers, domestic helpers, and gig drivers are paid in cash, have no formal income proof, and are invisible to credit bureaus. Banks auto-reject them. Moneylenders charge 40–80% interest. 400M Indians are locked out of the credit system by design.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>400M+ informal workers — massively underserved credit market</div>
      </div></div>
    </div>

    <!-- B2B FREELANCER 76.0 -->
    <div class="card rv" data-cat="b2b">
      <div class="ctop"><div class="ccat">B2B / Marketplace</div><div class="isc"><div class="isc-n">76.0</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:76%"></div></div></div></div>
      <div class="cq">Why do freelancers ghost projects after partial payments without any accountability?</div>
      <button class="xbtn" data-cat="B2B Services / Freelance Marketplace" data-q="Why do freelancers ghost projects after partial payments without any accountability?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Businesses hiring Indian freelancers face a recurring nightmare: pay 40–50% upfront, wait weeks for silence, then get ghosted with no legal recourse. No platform creates true accountability. Most Indian freelance transactions happen over WhatsApp with zero protection for either side.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>India freelance market: $20B+ and entirely unstructured</div>
      </div></div>
    </div>

    <!-- LOGISTICS 2 75.8 -->
    <div class="card rv" data-cat="logistics">
      <div class="ctop"><div class="ccat">Logistics / B2B</div><div class="isc"><div class="isc-n">75.8</div><div class="isc-l">Itch Score</div><div class="isc-bar"><div class="isc-fill" style="width:75.8%"></div></div></div></div>
      <div class="cq">Why can't manufacturers rely on guaranteed, accountable pickup logistics for outbound deliveries?</div>
      <button class="xbtn" data-cat="Logistics / Manufacturing B2B" data-q="Why can't manufacturers rely on guaranteed, accountable pickup logistics for outbound deliveries?">Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg></button>
      <div class="det"><div class="det-in">
        <div class="dbl"><div class="dbl-lbl">The Pain</div><p>Small manufacturers experience last-minute courier no-shows, zero accountability for missed pickups, and total loss of visibility once goods leave the factory gate. They negotiate with 4–5 vendors per week just to ship daily output. Every no-show is a broken customer promise.</p></div>
        <div class="dbl"><div class="dbl-lbl">AI-Generated Solution</div><div class="ai-area"><div class="ai-load"><div class="dots"><span></span><span></span><span></span></div><span>Claude is thinking...</span></div><div class="ai-out"></div><p class="ai-hint">Click "Generate AI Solution" above to get a live startup blueprint</p></div></div>
        <div class="mkt"><span class="dot"></span>450K+ registered factories in India with unreliable outbound logistics</div>
      </div></div>
    </div>

  </div>
</section>

<div class="mq"><div class="mq-i">
  <span class="mw f">THE</span><span class="mw">MISSION</span><span class="mw f">IS</span><span class="mw">SIMPLE</span>
  <span class="mw f">BUILD</span><span class="mw">WHAT</span><span class="mw f">INDIA</span><span class="mw">NEEDS</span>
  <span class="mw f">THE</span><span class="mw">MISSION</span><span class="mw f">IS</span><span class="mw">SIMPLE</span>
  <span class="mw f">BUILD</span><span class="mw">WHAT</span><span class="mw f">INDIA</span><span class="mw">NEEDS</span>
</div></div>

<section class="miss" id="mission">
  <div class="miss-bg"></div>
  <div class="slbl rv" style="justify-content:center">Our Mission</div>
  <h2 class="rv">START<br><span class="gh">WHERE</span><br>INDIA ITCHES</h2>
  <p class="miss-body rv">These aren't abstract market reports. These are <strong>real people's real pains</strong> — verified, ranked, and handed to you. Every problem here scores above 75. Every solution is generated live by <strong>Claude AI</strong>. The only question is: <strong>who's brave enough to scratch it?</strong></p>
  <a href="#problems" class="ctabtn rv">Explore All Problems <svg width="15" height="15" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg></a>
</section>

<footer>
  <div class="fl">SCRATCH THE ITCH</div>
  <div class="fn">Problems sourced from <strong>Razorpay Fix My Itch</strong> · 50K+ real Indians · AI solutions by <strong>Claude</strong></div>
</footer>

<script>
// CURSOR
const cur=document.getElementById('cur'),curR=document.getElementById('curR');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px'});
(function loop(){rx+=(mx-rx)*.11;ry+=(my-ry)*.11;curR.style.left=rx+'px';curR.style.top=ry+'px';requestAnimationFrame(loop)})();
document.querySelectorAll('a,button,.card,.t10r,.fb').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur.classList.add('h');curR.classList.add('h')});
  el.addEventListener('mouseleave',()=>{cur.classList.remove('h');curR.classList.remove('h')});
});

// NAV
window.addEventListener('scroll',()=>document.getElementById('nav').classList.toggle('sc',scrollY>50));

// FILTERS
document.querySelectorAll('.fb').forEach(btn=>{
  btn.addEventListener('click',()=>{
    document.querySelectorAll('.fb').forEach(b=>b.classList.remove('on'));
    btn.classList.add('on');
    const f=btn.dataset.f;
    let n=0;
    document.querySelectorAll('.card').forEach(c=>{
      const show=f==='all'||c.dataset.cat===f;
      c.style.display=show?'':'none';
      if(show)n++;
    });
    document.getElementById('pcnt').textContent=`SHOWING ${n} PROBLEM${n!==1?'S':''}`;
  });
});

// REVEAL
const obs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('vis');obs.unobserve(e.target)}})},{threshold:.08});
document.querySelectorAll('.rv').forEach((el,i)=>{el.style.transitionDelay=(i%4)*.055+'s';obs.observe(el)});

// AI SOLUTION — attach to all buttons
document.querySelectorAll('.xbtn').forEach(btn=>{
  btn.addEventListener('click',()=>handleCard(btn));
});

function handleCard(btn) {
  const card=btn.closest('.card');
  const det=card.querySelector('.det');
  const area=card.querySelector('.ai-area');
  const load=area.querySelector('.ai-load');
  const out=area.querySelector('.ai-out');
  const hint=area.querySelector('.ai-hint');
  const cat=btn.dataset.cat;
  const q=btn.dataset.q;

  // toggle close
  if(det.classList.contains('open')){
    det.classList.remove('open');
    btn.classList.remove('open');
    btn.innerHTML=`Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>`;
    return;
  }

  // close all others
  document.querySelectorAll('.det.open').forEach(d=>{
    d.classList.remove('open');
    const b=d.previousElementSibling;
    b.classList.remove('open');
    b.innerHTML=`Generate AI Solution <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>`;
  });

  det.classList.add('open');
  btn.classList.add('open');
  btn.innerHTML=`Close <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>`;

  // already loaded
  if(out.dataset.loaded) return;

  // fetch AI
  if(hint) hint.style.display='none';
  load.style.display='flex';
  out.style.display='none';

  fetch('https://api.anthropic.com/v1/messages',{
    method:'POST',
    headers:{
      'Content-Type':'application/json',
      'x-api-key':'',
      'anthropic-version':'2023-06-01',
      'anthropic-dangerous-direct-browser-access':'true'
    },
    body:JSON.stringify({
      model:'claude-sonnet-4-20250514',
      max_tokens:900,
      system:`You are a razor-sharp startup advisor for Indian founders. Given a problem, respond ONLY with this exact HTML (no markdown, no extra text, no code fences):

<div class="ai-badge">✦ Claude AI Blueprint</div>
<div class="dbl"><div class="dbl-lbl">The Startup Idea</div><p>[2-3 crisp sentences on what to build]</p></div>
<div class="dbl"><div class="dbl-lbl">How It Works</div><p>[2-3 sentences on mechanism]</p></div>
<div class="dbl"><div class="dbl-lbl">Solution Angles</div><div><span class="stag">[tag1]</span><span class="stag">[tag2]</span><span class="stag">[tag3]</span></div></div>
<div class="dbl"><div class="dbl-lbl">Revenue Model</div><p>[1-2 sentences on monetization]</p></div>
<div class="dbl"><div class="dbl-lbl">Why India, Why Now</div><p>[1-2 sentences on timing and India-specific advantage]</p></div>

Be concrete. Be specific. Avoid generic advice. India-first lens always.`,
      messages:[{role:'user',content:`Industry: ${cat}\nProblem: ${q}\n\nGenerate startup blueprint.`}]
    })
  })
  .then(r=>r.json())
  .then(data=>{
    const html=data.content.map(i=>i.text||'').join('');
    load.style.display='none';
    out.innerHTML=html;
    out.style.display='block';
    out.dataset.loaded='1';
  })
  .catch(()=>{
    load.style.display='none';
    out.innerHTML='<p style="color:var(--acc2);font-size:12px">⚠ API unavailable in this preview. The solution generator works when served with a valid Anthropic API key.</p>';
    out.style.display='block';
    out.dataset.loaded='1';
  });
}
</script>
</body>
</html>
