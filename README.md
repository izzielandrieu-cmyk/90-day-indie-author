<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Self-Editing Field Guide — Izzie Writes</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400;1,600&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–bg:        #e8e4df;
–white:     #ffffff;
–ink:       #1c1c1c;
–warm-gray: #b8b0a8;
–mid-gray:  #888888;
–light:     #f2f0ed;
}

html { scroll-behavior: smooth; }

body {
font-family: ‘DM Sans’, sans-serif;
background: var(–bg);
color: var(–ink);
}

/* ─────────────────────────────────────────
OUTCOME SECTION
───────────────────────────────────────── */

.outcome {
max-width: 1100px;
margin: 0 auto;
padding: 9rem 3rem 8rem;
}

/* Opening line — large, slow, breathes */
.outcome-opener {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-weight: 300;
font-size: clamp(1.1rem, 2vw, 1.4rem);
letter-spacing: 0.04em;
color: var(–mid-gray);
text-align: center;
margin-bottom: 1.8rem;
opacity: 0;
animation: rise 1s ease forwards 0.1s;
}

/* The big payoff headline */
.outcome-headline {
font-family: ‘Cormorant Garamond’, serif;
font-weight: 300;
font-size: clamp(3rem, 7vw, 6.4rem);
line-height: 1.03;
text-align: center;
color: var(–ink);
margin-bottom: 3.5rem;
opacity: 0;
animation: rise 1s ease forwards 0.25s;
}
.outcome-headline em {
font-style: italic;
font-weight: 300;
}
.outcome-headline .underline-word {
position: relative;
display: inline-block;
}
.outcome-headline .underline-word::after {
content: ‘’;
position: absolute;
left: 0; bottom: 4px;
width: 100%; height: 1px;
background: var(–warm-gray);
transform: scaleX(0);
transform-origin: left;
animation: drawline 1s ease forwards 1.1s;
}

@keyframes drawline {
to { transform: scaleX(1); }
}

/* Three-column feeling statements */
.outcome-feelings {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 1.5px;
background: var(–warm-gray);
border: 1.5px solid var(–warm-gray);
margin-bottom: 6rem;
opacity: 0;
animation: rise 0.9s ease forwards 0.5s;
}

.feeling-cell {
background: var(–white);
padding: 2.8rem 2.2rem 2.5rem;
position: relative;
}

.feeling-num {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 4.5rem;
font-weight: 300;
line-height: 1;
color: var(–ink);
opacity: 0.07;
position: absolute;
top: 1.2rem; right: 1.5rem;
}

.feeling-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.45rem;
font-weight: 400;
font-style: italic;
line-height: 1.2;
color: var(–ink);
margin-bottom: 1rem;
}

.feeling-body {
font-size: 0.85rem;
line-height: 1.85;
color: #666;
font-weight: 300;
}

/* The journey — before/after contrast */
.journey {
display: grid;
grid-template-columns: 1fr 56px 1fr;
align-items: center;
gap: 0;
margin-bottom: 6rem;
opacity: 0;
animation: rise 0.9s ease forwards 0.65s;
}

.journey-before,
.journey-after {
padding: 2.8rem 2.8rem;
}

.journey-before {
background: var(–light);
border: 1px solid rgba(184,176,168,0.5);
}

.journey-after {
background: var(–ink);
color: var(–white);
}

.journey-label {
font-family: ‘DM Mono’, monospace;
font-size: 0.55rem;
letter-spacing: 0.22em;
text-transform: uppercase;
margin-bottom: 1.4rem;
color: var(–mid-gray);
}
.journey-after .journey-label {
color: rgba(255,255,255,0.4);
}

.journey-heading {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 1.5rem;
font-weight: 300;
line-height: 1.3;
margin-bottom: 1.2rem;
color: var(–ink);
}
.journey-after .journey-heading {
color: rgba(255,255,255,0.9);
}

.journey-list {
list-style: none;
display: flex;
flex-direction: column;
gap: 0.7rem;
}
.journey-list li {
font-size: 0.82rem;
line-height: 1.6;
color: #777;
font-weight: 300;
padding-left: 1.1rem;
position: relative;
}
.journey-list li::before {
content: ‘—’;
position: absolute;
left: 0;
color: var(–warm-gray);
}
.journey-after .journey-list li {
color: rgba(255,255,255,0.65);
}
.journey-after .journey-list li::before {
color: rgba(255,255,255,0.25);
}

.journey-arrow {
display: flex;
align-items: center;
justify-content: center;
background: var(–ink);
height: 100%;
min-height: 180px;
}
.journey-arrow-inner {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 1.6rem;
color: rgba(255,255,255,0.3);
writing-mode: vertical-rl;
transform: rotate(180deg);
letter-spacing: 0.1em;
}

/* The moment statement — full-width typographic centrepiece */
.moment {
text-align: center;
padding: 5rem 2rem 5rem;
border-top: 1px solid rgba(184,176,168,0.35);
border-bottom: 1px solid rgba(184,176,168,0.35);
margin-bottom: 0;
opacity: 0;
animation: rise 0.9s ease forwards 0.8s;
}

.moment-eyebrow {
font-family: ‘DM Mono’, monospace;
font-size: 0.56rem;
letter-spacing: 0.24em;
text-transform: uppercase;
color: var(–mid-gray);
margin-bottom: 2rem;
}

.moment-text {
font-family: ‘Cormorant Garamond’, serif;
font-weight: 300;
font-size: clamp(1.5rem, 4vw, 3rem);
line-height: 1.45;
color: var(–ink);
max-width: 780px;
margin: 0 auto 2rem;
}
.moment-text em {
font-style: italic;
}

.moment-attr {
font-family: ‘DM Mono’, monospace;
font-size: 0.56rem;
letter-spacing: 0.14em;
text-transform: uppercase;
color: var(–mid-gray);
}

/* ─────────────────────────────────────────
CTA SECTION
───────────────────────────────────────── */

.cta-wrap {
background: var(–ink);
padding: 8rem 3rem 9rem;
text-align: center;
position: relative;
overflow: hidden;
}

/* Subtle ruled-paper texture on dark bg */
.cta-wrap::before {
content: ‘’;
position: absolute;
inset: 0;
background: repeating-linear-gradient(
0deg,
transparent,
transparent 47px,
rgba(255,255,255,0.02) 47px,
rgba(255,255,255,0.02) 48px
);
pointer-events: none;
}

.cta-inner {
position: relative;
max-width: 640px;
margin: 0 auto;
}

.cta-star-row {
display: flex;
align-items: center;
justify-content: center;
gap: 1rem;
margin-bottom: 2.8rem;
opacity: 0;
}
.cta-star-row.visible { animation: rise 0.8s ease forwards; }
.star-line {
width: 48px;
height: 1px;
background: rgba(255,255,255,0.15);
}
.star-glyph {
font-size: 0.75rem;
color: rgba(255,255,255,0.35);
letter-spacing: 0.3em;
}

.cta-heading {
font-family: ‘Cormorant Garamond’, serif;
font-weight: 300;
font-size: clamp(2.8rem, 6vw, 5.2rem);
line-height: 1.05;
color: var(–white);
margin-bottom: 1rem;
opacity: 0;
}
.cta-heading.visible { animation: rise 0.85s ease forwards 0.1s; }
.cta-heading em { font-style: italic; }

.cta-sub {
font-size: 0.88rem;
line-height: 1.9;
color: rgba(255,255,255,0.5);
font-weight: 300;
margin-bottom: 3.5rem;
opacity: 0;
}
.cta-sub.visible { animation: rise 0.85s ease forwards 0.2s; }

/* The button — restrained but confident */
.cta-btn {
display: inline-block;
font-family: ‘DM Mono’, monospace;
font-size: 0.68rem;
letter-spacing: 0.18em;
text-transform: uppercase;
background: var(–white);
color: var(–ink);
padding: 1.15rem 3.2rem;
text-decoration: none;
transition: background 0.25s, color 0.25s;
margin-bottom: 1.4rem;
opacity: 0;
}
.cta-btn.visible { animation: rise 0.85s ease forwards 0.3s; }
.cta-btn:hover {
background: var(–bg);
color: var(–ink);
}

.cta-fine {
display: block;
font-family: ‘DM Mono’, monospace;
font-size: 0.52rem;
letter-spacing: 0.14em;
text-transform: uppercase;
color: rgba(255,255,255,0.25);
margin-bottom: 4rem;
opacity: 0;
}
.cta-fine.visible { animation: rise 0.85s ease forwards 0.38s; }

/* Divider row of guide labels */
.cta-guide-labels {
display: flex;
justify-content: center;
gap: 0;
border-top: 1px solid rgba(255,255,255,0.08);
padding-top: 2.8rem;
flex-wrap: wrap;
opacity: 0;
}
.cta-guide-labels.visible { animation: rise 0.85s ease forwards 0.5s; }
.cta-guide-label {
font-family: ‘DM Mono’, monospace;
font-size: 0.52rem;
letter-spacing: 0.14em;
text-transform: uppercase;
color: rgba(255,255,255,0.22);
padding: 0 1.5rem;
border-right: 1px solid rgba(255,255,255,0.08);
line-height: 1;
}
.cta-guide-label:last-child { border-right: none; }

/* Footer strip */
.page-footer {
background: var(–ink);
border-top: 1px solid rgba(255,255,255,0.06);
padding: 1.6rem 3rem;
display: flex;
justify-content: space-between;
align-items: center;
}
.page-footer span {
font-family: ‘DM Mono’, monospace;
font-size: 0.56rem;
letter-spacing: 0.18em;
text-transform: uppercase;
color: rgba(255,255,255,0.25);
}

@keyframes rise {
from { opacity: 0; transform: translateY(16px); }
to   { opacity: 1; transform: none; }
}

/* Scroll reveal */
.sr {
opacity: 0;
transform: translateY(20px);
transition: opacity 0.75s ease, transform 0.75s ease;
}
.sr.on { opacity: 1; transform: none; }

@media (max-width: 860px) {
.outcome-feelings { grid-template-columns: 1fr; }
.journey { grid-template-columns: 1fr; }
.journey-arrow { display: none; }
.outcome { padding: 6rem 1.5rem 5rem; }
.cta-wrap { padding: 6rem 1.5rem 7rem; }
.cta-guide-labels { gap: 0.8rem; }
.cta-guide-label { border: none; }
}
</style>

</head>
<body>

<!-- ─── OUTCOME SECTION ─── -->

<section class="outcome">

  <p class="outcome-opener">You've written the book. Now finish it.</p>

  <h2 class="outcome-headline">
    The moment you hold it<br>
    and think — <em>I made <span class="underline-word">this</span>.</em>
  </h2>

  <!-- Three feelings -->

  <div class="outcome-feelings">

```
<div class="feeling-cell sr">
  <span class="feeling-num">1</span>
  <h3 class="feeling-title">Reading it back and actually trusting it.</h3>
  <p class="feeling-body">Not cringing at chapter three. Not wondering if the editor you can't afford would have caught something you missed. Reading it the way a stranger will — and knowing it's ready.</p>
</div>

<div class="feeling-cell sr" style="transition-delay:0.1s">
  <span class="feeling-num">2</span>
  <h3 class="feeling-title">Sending it out without the knot in your stomach.</h3>
  <p class="feeling-body">To your ARC readers. To the formatter. To the printer. No more "I should probably do one more pass." You did the passes. You used the process. You're done.</p>
</div>

<div class="feeling-cell sr" style="transition-delay:0.2s">
  <span class="feeling-num">3</span>
  <h3 class="feeling-title">Knowing the work is yours — all of it.</h3>
  <p class="feeling-body">You didn't just pay someone to fix it and hope for the best. You understood every layer of the manuscript. That knowledge goes into every book you ever write.</p>
</div>
```

  </div>

  <!-- Before / After journey -->

  <div class="journey sr">
    <div class="journey-before">
      <p class="journey-label">Where you are now</p>
      <h3 class="journey-heading">A finished draft that doesn't feel finished.</h3>
      <ul class="journey-list">
        <li>You're not sure the structure actually works</li>
        <li>You've read it so many times you can't see it anymore</li>
        <li>You don't know what kind of editing it even needs</li>
        <li>You're too scared to send it out, too stuck to fix it</li>
        <li>Hiring a professional editor isn't in the budget right now</li>
      </ul>
    </div>

```
<div class="journey-arrow">
  <span class="journey-arrow-inner">→</span>
</div>

<div class="journey-after">
  <p class="journey-label">Where this takes you</p>
  <h3 class="journey-heading">A manuscript you've worked through with intention.</h3>
  <ul class="journey-list">
    <li>You know exactly which pass to do and when</li>
    <li>Every checklist item is something you've genuinely checked</li>
    <li>You caught the consistency errors before your readers did</li>
    <li>You've read it aloud, cut the dead weight, found the rhythm</li>
    <li>You're ready to hit publish — and you know why</li>
  </ul>
</div>
```

  </div>

  <!-- The moment statement -->

  <div class="moment sr">
    <p class="moment-eyebrow">The outcome</p>
    <p class="moment-text">
      A book you finished <em>properly</em> — not abandoned to "good enough." Not handed off hoping someone else catches what you missed. <em>Finished</em>. By you. On purpose.
    </p>
    <p class="moment-attr">The Self-Editing Field Guide · Izzie Writes</p>
  </div>

</section>

<!-- ─── CTA SECTION ─── -->

<div class="cta-wrap">
  <div class="cta-inner">

```
<div class="cta-star-row sr">
  <span class="star-line"></span>
  <span class="star-glyph">★ ★ ★</span>
  <span class="star-line"></span>
</div>

<h2 class="cta-heading sr">
  Your manuscript<br>deserves a<br><em>proper finish.</em>
</h2>

<p class="cta-sub sr">
  Five complete editing guides. Every checklist. Every process step. Every tool recommendation — honest, not sponsored. One printable PDF you'll come back to for every book you write.
</p>

<a href="#" class="cta-btn sr">Get the Field Guide</a>

<span class="cta-fine sr">Instant PDF download · Print every time · Izzie Writes</span>

<div class="cta-guide-labels sr">
  <span class="cta-guide-label">01 Developmental</span>
  <span class="cta-guide-label">02 Copyediting</span>
  <span class="cta-guide-label">03 Line Editing</span>
  <span class="cta-guide-label">04 Proofreading</span>
  <span class="cta-guide-label">05 Formatting ★</span>
</div>
```

  </div>
</div>

<footer class="page-footer">
  <span>Izzie Writes</span>
  <span>★</span>
  <span>The Self-Editing Field Guide</span>
</footer>

<script>
const els = document.querySelectorAll('.sr');
const obs = new IntersectionObserver(entries => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) {
      const delay = parseFloat(e.target.style.transitionDelay || 0) * 1000;
      setTimeout(() => e.target.classList.add('on'), delay);
      // CTA elements need .visible class for their animation
      e.target.classList.add('visible');
      obs.unobserve(e.target);
    }
  });
}, { threshold: 0.1 });
els.forEach(el => obs.observe(el));
</script>

</body>
</html>
