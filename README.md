<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>ZAYO Embroidery — فن التطريز اليدوي</title>
<meta name="description" content="ZAYO Embroidery — Handmade embroidery hoops, personalised gifts and tote bags."/>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500;600&family=Amiri:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
<style>
:root{
  --cream:#f9f5ef;--warm:#f0e8d8;--blush:#e8c4b0;--rose:#c4826a;
  --deep:#3d2b1f;--olive:#7a7a5a;--gold:#b8964e;--text:#2a1f17;--muted:#8a7060;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'Amiri',serif;background:var(--cream);color:var(--text);overflow-x:hidden}

/* ===================== NAV ===================== */
nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  padding:0 40px;height:64px;
  display:flex;justify-content:space-between;align-items:center;
  background:rgba(249,245,239,0.96);backdrop-filter:blur(12px);
  border-bottom:1px solid rgba(196,130,106,0.18);
  transition:transform 0.4s ease;
}
nav.nav-hidden{transform:translateY(-100%)}
.nav-logo{
  font-family:'Cormorant Garamond',serif;font-size:1.5rem;font-weight:600;
  color:var(--deep);letter-spacing:0.06em;text-decoration:none;
}
.nav-logo span{color:var(--rose)}
.nav-center{display:flex;gap:28px;align-items:center}
.nav-center a{
  font-size:0.95rem;color:var(--muted);text-decoration:none;
  transition:color 0.3s;font-family:'Amiri',serif;
  position:relative;
}
.nav-center a::after{
  content:'';position:absolute;bottom:-4px;left:0;right:0;
  height:1px;background:var(--rose);transform:scaleX(0);
  transition:transform 0.3s;
}
.nav-center a:hover{color:var(--rose)}
.nav-center a:hover::after{transform:scaleX(1)}

.lang-strip{display:flex;gap:6px;align-items:center}
.lang-btn{
  background:none;border:1.5px solid var(--blush);
  color:var(--muted);font-size:0.72rem;letter-spacing:0.08em;
  padding:5px 12px;cursor:pointer;border-radius:20px;
  transition:all 0.25s;font-family:'Jost',sans-serif;font-weight:500;
}
.lang-btn.active{background:var(--rose);border-color:var(--rose);color:#fff}
.lang-btn:hover:not(.active){border-color:var(--rose);color:var(--rose)}

.nav-hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px}
.nav-hamburger span{display:block;width:22px;height:1.5px;background:var(--deep);transition:all 0.3s}

/* ===================== FLOATING LOGO ===================== */
.floating-logo{
  position:fixed;top:50%;left:50%;
  transform:translate(-50%,-50%);
  z-index:100;pointer-events:none;
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(4rem,10vw,8rem);font-weight:300;
  letter-spacing:0.35em;text-transform:uppercase;
  color:rgba(61,43,31,0.04);
  white-space:nowrap;
  animation:floatLogo 20s ease-in-out infinite;
}
@keyframes floatLogo{
  0%,100%{transform:translate(-50%,-50%) rotate(-2deg) scale(1)}
  25%{transform:translate(-48%,-52%) rotate(1deg) scale(1.02)}
  50%{transform:translate(-52%,-48%) rotate(-1deg) scale(0.98)}
  75%{transform:translate(-50%,-53%) rotate(2deg) scale(1.01)}
}

/* ===================== SOCIAL SIDEBAR ===================== */
.social-sidebar{
  position:fixed;left:0;top:50%;transform:translateY(-50%);
  z-index:150;display:flex;flex-direction:column;gap:0;
  border-radius:0 12px 12px 0;overflow:hidden;
  box-shadow:4px 0 24px rgba(61,43,31,0.12);
}
[dir="ltr"] .social-sidebar{left:0;right:auto;border-radius:0 12px 12px 0}
[dir="rtl"] .social-sidebar{right:0;left:auto;border-radius:12px 0 0 12px}
.soc-btn{
  display:flex;align-items:center;gap:10px;
  padding:13px 14px;text-decoration:none;
  font-size:0.75rem;font-family:'Jost',sans-serif;
  font-weight:500;letter-spacing:0.04em;
  color:#fff;white-space:nowrap;overflow:hidden;
  max-width:46px;transition:max-width 0.35s ease,padding 0.35s ease;
}
.soc-btn:hover{max-width:180px}
.soc-btn .soc-icon{flex-shrink:0;line-height:1;display:flex;align-items:center;justify-content:center}
.soc-btn .soc-icon svg{display:block}
.soc-btn .soc-label{opacity:0;transition:opacity 0.2s 0.1s;font-size:0.78rem}
.soc-btn:hover .soc-label{opacity:1}
.soc-tiktok{background:#010101}
.soc-insta{background:linear-gradient(135deg,#f09433,#e6683c,#dc2743,#cc2366,#bc1888)}
.soc-fb{background:#1877f2}
.soc-wa{background:#25d366}
.soc-email{background:var(--rose)}

/* ===================== HERO ===================== */
.hero{
  min-height:100vh;display:flex;align-items:center;justify-content:center;
  padding:100px 40px 60px;position:relative;overflow:hidden;text-align:center;
  background:var(--cream);
}
.hero-bg{
  position:absolute;inset:0;
  background:linear-gradient(160deg,var(--cream) 0%,var(--warm) 60%,#ecdec8 100%);
}
.hero-inner{position:relative;max-width:720px;z-index:2}
.hero-brand{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(5rem,14vw,12rem);font-weight:300;
  letter-spacing:0.3em;text-transform:uppercase;
  color:var(--deep);line-height:0.95;margin-bottom:20px;
  opacity:0;animation:heroReveal 1.2s ease forwards 0.3s;
}
@keyframes heroReveal{
  from{opacity:0;transform:translateY(30px);letter-spacing:0.5em}
  to{opacity:1;transform:translateY(0);letter-spacing:0.3em}
}
.hero-tagline{
  font-family:'Amiri',serif;
  font-size:clamp(1rem,2.5vw,1.4rem);color:var(--muted);
  letter-spacing:0.08em;margin-bottom:48px;
  opacity:0;animation:fadeUp 0.8s ease forwards 0.9s;
}
@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
.hero-cta{
  display:inline-block;background:var(--deep);color:#fff;
  padding:16px 52px;font-family:'Jost',sans-serif;
  font-size:0.82rem;letter-spacing:0.18em;text-transform:uppercase;
  text-decoration:none;border:none;cursor:pointer;
  transition:all 0.4s;opacity:0;animation:fadeUp 0.8s ease forwards 1.3s;
}
.hero-cta:hover{background:var(--rose);transform:translateY(-2px);box-shadow:0 8px 30px rgba(196,130,106,0.3)}
.hero-scroll{
  position:absolute;bottom:30px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  font-size:0.65rem;letter-spacing:0.2em;text-transform:uppercase;
  color:var(--muted);font-family:'Jost',sans-serif;
  opacity:0;animation:fadeUp 0.8s ease forwards 1.8s;
}
.hero-scroll-line{width:1px;height:40px;background:var(--blush);animation:scrollDown 1.8s ease-in-out infinite}
@keyframes scrollDown{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform:scaleY(1);transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

/* ===================== SECTIONS ===================== */
section{padding:90px 40px}
.section-label{
  font-size:0.68rem;letter-spacing:0.28em;text-transform:uppercase;
  color:var(--gold);margin-bottom:12px;display:block;font-family:'Jost',sans-serif;
}
.section-title{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(2rem,4vw,3rem);font-weight:300;
  color:var(--deep);margin-bottom:16px;line-height:1.2;
}
.section-title-ar{font-family:'Amiri',serif;font-size:clamp(1.8rem,3.5vw,2.8rem)}
.section-sub{font-size:0.92rem;color:var(--muted);line-height:1.85;max-width:520px}
.section-header{text-align:center;margin-bottom:56px}
.section-header .section-sub{margin:0 auto}

/* ===================== GALLERY & PRODUCTS ===================== */
#shop{background:var(--warm);padding-bottom:120px}

.products-grid{
  display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));
  gap:24px;max-width:1400px;margin:0 auto;
}
.product-card{
  position:relative;overflow:hidden;cursor:pointer;
  background:#fff;border-radius:6px;
  transition:transform 0.3s,box-shadow 0.3s;
  display:flex;flex-direction:column;
}
.product-card:hover{transform:translateY(-8px);box-shadow:0 16px 40px rgba(61,43,31,0.2)}
.product-image{
  width:100%;aspect-ratio:1;overflow:hidden;
  position:relative;
}
.product-image img{
  width:100%;height:100%;object-fit:cover;
  transition:transform 0.7s cubic-bezier(0.25,0.46,0.45,0.94);
}
.product-card:hover .product-image img{transform:scale(1.08)}
.product-badge{
  position:absolute;top:12px;right:12px;z-index:5;
  background:var(--gold);color:#fff;
  font-family:'Jost',sans-serif;font-size:0.65rem;
  letter-spacing:0.1em;text-transform:uppercase;
  padding:5px 12px;border-radius:20px;
}
[dir="ltr"] .product-badge{left:12px;right:auto}

.product-overlay{
  position:absolute;inset:0;
  display:flex;align-items:flex-end;justify-content:center;
  padding:24px;
  background:linear-gradient(transparent 40%,rgba(61,43,31,0.7));
  opacity:0;transition:opacity 0.4s;
}
.product-card:hover .product-overlay{opacity:1}
.overlay-btn{
  font-family:'Jost',sans-serif;font-size:0.72rem;
  letter-spacing:0.2em;text-transform:uppercase;
  color:#fff;background:rgba(61,43,31,0.9);
  padding:10px 28px;border:none;cursor:pointer;
  backdrop-filter:blur(4px);transition:background 0.3s;
  border-radius:3px;
}
.overlay-btn:hover{background:var(--rose)}

.product-info{
  padding:16px;flex-grow:1;display:flex;flex-direction:column;
}
.product-name{
  font-family:'Amiri',serif;font-size:1rem;color:var(--deep);
  margin-bottom:8px;font-weight:600;line-height:1.3;
}
.product-price{
  display:flex;justify-content:space-between;align-items:center;
  padding:12px 0;border-top:1px solid rgba(196,130,106,0.2);
  margin-top:auto;
}
.price-label{font-size:0.75rem;letter-spacing:0.1em;text-transform:uppercase;
  color:var(--muted);font-family:'Jost',sans-serif;}
.price-value{font-size:1.1rem;color:var(--rose);font-weight:600;
  font-family:'Jost',sans-serif;}

.cat-tabs{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-bottom:48px}
.cat-tab{
  background:none;border:none;color:var(--muted);
  font-size:0.78rem;letter-spacing:0.15em;text-transform:uppercase;
  padding:9px 22px;cursor:pointer;transition:all 0.3s;
  font-family:'Jost',sans-serif;position:relative;
}
.cat-tab::after{
  content:'';position:absolute;bottom:0;left:50%;transform:translateX(-50%);
  width:0;height:1px;background:var(--deep);transition:width 0.3s;
}
.cat-tab.active,.cat-tab:hover{color:var(--deep)}
.cat-tab.active::after,.cat-tab:hover::after{width:100%}
.hidden{display:none!important}

/* ===================== ABOUT ===================== */
#about{background:var(--cream)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:center;max-width:1100px;margin:0 auto}
.about-img-wrap{position:relative}
.about-img-wrap img{width:100%;border-radius:4px;box-shadow:0 16px 48px rgba(61,43,31,0.15)}
.about-badge{
  position:absolute;bottom:-20px;
  background:var(--rose);color:#fff;padding:20px;border-radius:50%;
  width:90px;height:90px;display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  font-family:'Cormorant Garamond',serif;font-size:1.4rem;font-weight:600;
  line-height:1.1;box-shadow:0 8px 24px rgba(196,130,106,0.4);
}
[dir="rtl"] .about-badge{left:-20px;right:auto}
[dir="ltr"] .about-badge{right:-20px;left:auto}
.about-badge small{font-size:0.52rem;letter-spacing:0.1em;text-transform:uppercase;font-family:'Jost',sans-serif;font-weight:400}
.about-text .section-sub{max-width:100%;margin-top:18px}
.about-features{display:flex;gap:32px;margin-top:36px;flex-wrap:wrap}
.feature-item{text-align:center}
.feature-num{font-family:'Cormorant Garamond',serif;font-size:2rem;color:var(--rose);font-weight:600}
.feature-label{font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--muted);margin-top:4px;font-family:'Jost',sans-serif}

/* ===================== ORDER FORM ===================== */
#order{background:var(--warm)}
.order-inner{max-width:640px;margin:0 auto}
.order-form{display:flex;flex-direction:column;gap:18px;margin-top:36px}
.order-row{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.order-field{display:flex;flex-direction:column;gap:6px}
.order-field label{
  font-size:0.7rem;letter-spacing:0.15em;text-transform:uppercase;
  color:var(--muted);font-family:'Jost',sans-serif;
}
.order-field input,.order-field textarea,.order-field select{
  background:#fff;border:1px solid rgba(196,130,106,0.3);
  color:var(--text);padding:12px 16px;border-radius:3px;
  font-family:'Amiri',serif;font-size:1rem;outline:none;
  transition:border-color 0.3s;resize:vertical;
}
.order-field input:focus,.order-field textarea:focus,.order-field select:focus{border-color:var(--rose)}
.order-field textarea{min-height:100px}
.order-submit{
  background:var(--deep);color:#fff;border:none;padding:16px 40px;
  font-size:0.82rem;letter-spacing:0.15em;text-transform:uppercase;
  cursor:pointer;transition:all 0.3s;font-family:'Jost',sans-serif;
  align-self:center;border-radius:3px;
}
.order-submit:hover{background:var(--rose);transform:translateY(-2px)}
.order-submit:disabled{opacity:0.6;cursor:not-allowed}
.order-note{
  text-align:center;font-size:0.8rem;color:var(--muted);
  font-family:'Jost',sans-serif;margin-top:-4px;
  display:flex;align-items:center;justify-content:center;gap:6px;
}
.order-success{
  display:none;text-align:center;padding:40px 20px;
}
.order-success.show{display:block}
.order-success h3{font-family:'Cormorant Garamond',serif;font-size:1.8rem;color:var(--deep);margin-bottom:12px}
.order-success p{color:var(--muted);font-size:1rem;line-height:1.8;margin-bottom:12px}
.order-success .email-note{
  margin-top:16px;padding:14px 20px;
  background:rgba(184,150,78,0.12);border-radius:6px;
  font-size:0.85rem;color:var(--deep);font-family:'Jost',sans-serif;
  border:1px solid rgba(184,150,78,0.3);
}

/* ===================== CUSTOM ===================== */
#custom{background:var(--cream)}
.custom-inner{max-width:720px;margin:0 auto;text-align:center}
.custom-features{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;margin:48px 0}
.cf-item{padding:28px 20px;background:var(--warm);border-radius:6px;border:1px solid rgba(196,130,106,0.2)}
.cf-icon{font-size:2.8rem;margin-bottom:12px}
.cf-title{font-family:'Amiri',serif;font-size:1.15rem;color:var(--deep);margin-bottom:8px}
.cf-text{font-size:0.85rem;color:var(--muted);line-height:1.75;font-family:'Amiri',serif}

/* ===================== CONTACT ===================== */
#contact{background:var(--deep);color:#fff}
#contact .section-label{color:var(--gold)}
#contact .section-title{color:var(--cream)}
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:start;max-width:1000px;margin:0 auto}
.contact-info p{color:rgba(249,245,239,0.7);font-size:0.95rem;line-height:1.9;margin-bottom:28px;font-family:'Amiri',serif}
.contact-links{display:flex;flex-direction:column;gap:14px}
.contact-link{
  display:flex;align-items:center;gap:14px;text-decoration:none;
  color:rgba(249,245,239,0.85);font-size:0.88rem;transition:color 0.3s;
  font-family:'Jost',sans-serif;
}
[dir="rtl"] .contact-link{flex-direction:row-reverse;text-align:right}
.contact-link:hover{color:var(--blush)}
.cl-icon{
  width:44px;height:44px;border:1px solid rgba(249,245,239,0.2);
  border-radius:50%;display:flex;align-items:center;justify-content:center;
  font-size:1.3rem;flex-shrink:0;
}

/* ===================== FOOTER ===================== */
footer{
  background:#2a1f17;color:rgba(249,245,239,0.5);
  text-align:center;padding:28px 40px;
  font-size:0.78rem;letter-spacing:0.05em;font-family:'Jost',sans-serif;
}
footer span{color:var(--blush)}

/* ===================== LIGHTBOX ===================== */
.lightbox{
  display:none;position:fixed;inset:0;z-index:999;
  background:rgba(42,31,23,0.95);align-items:center;
  justify-content:center;padding:20px;
  flex-direction:column;
}
.lightbox.open{display:flex}
.lightbox img{
  max-width:90vw;max-height:80vh;object-fit:contain;
  border-radius:4px;box-shadow:0 20px 60px rgba(0,0,0,0.5);
  margin-bottom:20px;
}
.lightbox-info{
  color:#fff;text-align:center;
}
.lightbox-name{font-family:'Amiri',serif;font-size:1.4rem;margin-bottom:8px}
.lightbox-price{font-family:'Jost',sans-serif;font-size:1.2rem;color:var(--gold);margin-bottom:16px}
.lb-close{
  position:fixed;top:20px;right:24px;font-size:2rem;color:#fff;
  cursor:pointer;opacity:0.7;transition:opacity 0.2s;
  background:none;border:none;line-height:1;z-index:1000;
}
.lb-close:hover{opacity:1}
.lb-order-btn{
  background:var(--rose);color:#fff;border:none;
  padding:14px 40px;font-family:'Jost',sans-serif;
  font-size:0.8rem;letter-spacing:0.15em;text-transform:uppercase;
  cursor:pointer;z-index:1000;transition:background 0.3s;border-radius:3px;
}
.lb-order-btn:hover{background:var(--deep)}

/* ===================== MOBILE ===================== */
@media(max-width:768px){
  nav{padding:0 16px}
  .nav-center{display:none}
  .nav-hamburger{display:flex}
  .hero{padding:80px 20px 50px}
  .hero-brand{font-size:clamp(3rem,12vw,5rem);letter-spacing:0.2em}
  section{padding:60px 20px}
  .about-grid,.contact-grid{grid-template-columns:1fr}
  .custom-features{grid-template-columns:1fr}
  .products-grid{grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:16px}
  .soc-btn{padding:11px 12px}
  .about-badge{bottom:-14px;width:72px;height:72px;font-size:1.1rem}
  .order-row{grid-template-columns:1fr}
  .floating-logo{font-size:clamp(3rem,10vw,5rem)}
}
@media(max-width:480px){
  .products-grid{grid-template-columns:repeat(auto-fill,minmax(150px,1fr))}
  .story-icon{font-size:2rem}
}

/* ===================== STORY ANIMATED ICONS ===================== */
.story-section{position:relative;overflow:hidden}
.story-floating-icons{position:absolute;inset:0;pointer-events:none;z-index:0}
.story-section .about-grid{position:relative;z-index:1}
.story-icon{
  position:absolute;font-size:2.8rem;opacity:0.18;
  animation-timing-function:ease-in-out;
  animation-iteration-count:infinite;
  animation-fill-mode:both;
}
.si-1{top:8%;left:5%;animation:floatBounce1 4s infinite}
.si-2{top:68%;right:8%;animation:floatBounce2 5.5s infinite}
.si-3{bottom:15%;left:12%;animation:floatBounce3 6s infinite}
.si-4{top:25%;right:5%;animation:floatBounce1 4.8s infinite}
@keyframes floatBounce1{0%,100%{transform:translateY(0)}50%{transform:translateY(-20px)}}
@keyframes floatBounce2{0%,100%{transform:translateY(0)}50%{transform:translateY(20px)}}
@keyframes floatBounce3{0%,100%{transform:translateY(0)}50%{transform:translateY(-16px)}}
</style>
</head>
<body>

<!-- ===================== NAVIGATION ===================== -->
<nav id="mainNav">
  <a href="#hero" class="nav-logo">ZA<span>Y</span>O</a>
  <div class="nav-center" id="navCenter">
    <a href="#shop" onclick="filterCat('all',event.target.closest('a')?.nextElementSibling)">المتجر</a>
    <a href="#about">من نحن</a>
    <a href="#contact">التواصل</a>
  </div>
  <div class="lang-strip">
    <button class="lang-btn active" onclick="setLang('ar')">AR</button>
    <button class="lang-btn" onclick="setLang('fr')">FR</button>
    <button class="lang-btn" onclick="setLang('en')">EN</button>
  </div>
  <button class="nav-hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- ===================== SOCIAL SIDEBAR ===================== -->
<div class="social-sidebar">
  <a href="https://www.tiktok.com/@zayo.embroidery" class="soc-btn soc-tiktok" target="_blank">
    <span class="soc-icon">🎵</span>
    <span class="soc-label">TikTok</span>
  </a>
  <a href="https://www.instagram.com/zayo.embroidery/" class="soc-btn soc-insta" target="_blank">
    <span class="soc-icon">📸</span>
    <span class="soc-label">Instagram</span>
  </a>
  <a href="https://wa.me/212783395988" class="soc-btn soc-wa" target="_blank">
    <span class="soc-icon">💬</span>
    <span class="soc-label">WhatsApp</span>
  </a>
  <a href="mailto:zay
