<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Operation Epic Dolomites - Dolomites & South Tyrol</title>
<meta name="description" content="Six hike options around Bolzano - alpine lakes, Dolomite walls, panoramic ridges and low-key viewpoints.">
<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Manrope:wght@400;600;700;800&display=swap');

:root {
  --bg: #0b0d0c;
  --ink: #f1f0e9;
  --muted: #a9aaa3;
  --line: #2b2e2b;
  --acid: #d7ff43;
  --card: #121513;
}

* { box-sizing: border-box; }
html { scroll-behavior: smooth; }
body {
  margin: 0;
  background: var(--bg);
  color: var(--ink);
  font-family: Manrope, system-ui, sans-serif;
  overflow-x: hidden;
}

/* Initial subtle noise overlay */
body:before {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;
  opacity: 0.07;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.45'/%3E%3C/svg%3E");
  z-index: 20;
}

a { color: inherit; text-decoration: none; }
.mono {
  font: 400 11px/1.4 "DM Mono", monospace;
  letter-spacing: .08em;
  text-transform: uppercase;
}

nav {
  position: fixed;
  z-index: 10;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: flex-end;
  padding: 22px 4vw;
  background: linear-gradient(to bottom, rgba(11, 13, 12, 0.85), transparent);
  backdrop-filter: blur(8px);
  color: #fff;
}
.nav-right { display: flex; gap: 28px; }
.nav-right a { transition: color 0.25s ease; }
.nav-right a:hover { color: var(--acid); }

.hero {
  min-height: 100vh;
  display: grid;
  place-items: center;
  position: relative;
  padding: 100px 5vw 60px;
  overflow: hidden;
}

.hero-grid {
  position: absolute;
  inset: 0;
  background: 
    linear-gradient(90deg, transparent 49.9%, #202420 50%, transparent 50.1%),
    linear-gradient(0deg, transparent 49.9%, #202420 50%, transparent 50.1%);
  opacity: .22;
}

.orbit {
  position: absolute;
  width: 70vw;
  height: 70vw;
  max-width: 800px;
  max-height: 800px;
  border: 1px solid #272b27;
  border-radius: 50%;
  animation: spin 45s linear infinite;
  pointer-events: none;
}

.orbit:before, .orbit:after {
  content: "";
  position: absolute;
  width: 8px;
  height: 8px;
  background: var(--acid);
  border-radius: 50%;
  top: 50%;
  left: -4px;
  box-shadow: 0 0 30px 10px rgba(215, 255, 67, 0.4);
}

.orbit:after {
  top: 20%;
  left: 86%;
  width: 4px;
  height: 4px;
}

.hero-content {
  position: relative;
  max-width: 1200px;
  width: 100%;
  text-align: center;
  z-index: 1;
}

.eyebrow { 
  color: var(--acid); 
  margin-bottom: 28px; 
}

.hero h1 {
  font-size: clamp(42px, 10.5vw, 140px);
  line-height: .78;
  letter-spacing: -.08em;
  margin: 0;
  font-weight: 800;
}
.hero h1 span { display: block; }
.hero h1 .outline {
  color: transparent;
  -webkit-text-stroke: 1.5px var(--ink);
}

.hero-sub {
  max-width: 570px;
  margin: 42px auto 0;
  color: var(--muted);
  font-size: 15px;
  line-height: 1.7;
}

.scroll {
  position: absolute;
  bottom: 28px;
  left: 50%;
  transform: translateX(-50%);
  color: var(--muted);
  animation: bob 2s ease-in-out infinite;
  z-index: 1;
}

section { padding: 100px 5vw; }

.intro {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 8vw;
  border-top: 1px solid var(--line);
  padding-top: 28px;
}
.intro h2 {
  font-size: clamp(36px, 5vw, 72px);
  letter-spacing: -.06em;
  margin: 0;
  line-height: .95;
}
.intro p {
  font-size: 18px;
  line-height: 1.7;
  max-width: 760px;
  color: #c4c6bf;
  margin: 0;
}

.routes { display: grid; gap: 2px; margin-top: 70px; }
.route {
  display: grid;
  grid-template-columns: 80px 1.6fr 1fr 180px;
  gap: 30px;
  align-items: center;
  padding: 28px 18px;
  border-top: 1px solid var(--line);
  position: relative;
  overflow: hidden;
  transition: transform .45s ease, color .45s ease;
  background: var(--card);
}
.route:last-child { border-bottom: 1px solid var(--line); }

.route:before {
  content: "";
  position: absolute;
  inset: 0;
  background: var(--acid);
  transform: translateX(-102%);
  transition: transform .45s ease;
  z-index: 0;
}

.route * { position: relative; z-index: 1; }

.route:hover { color: #0b0d0c; transform: translateX(8px); }
.route:hover:before { transform: translateX(0); }

.num { font-size: 12px; color: var(--acid); }
.route:hover .num { color: #0b0d0c; }

.name { font-size: clamp(24px, 3vw, 43px); font-weight: 700; letter-spacing: -.045em; }
.meta { color: var(--muted); font-size: 13px; line-height: 1.7; }
.route:hover .meta { color: #252a23; }

.badge {
  justify-self: end;
  border: 1px solid #41463f;
  padding: 9px 13px;
  border-radius: 999px;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: .1em;
}
.route:hover .badge { border-color: #252a23; color: #0b0d0c; }

.route-link {
  margin-top: 10px;
  display: inline-block;
  font-size: 11px;
  text-decoration: underline;
  text-underline-offset: 4px;
}

.note {
  margin-top: 80px;
  padding: 25px 0;
  border-top: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
  display: flex;
  justify-content: space-between;
  gap: 30px;
  color: var(--muted);
}
.note strong { color: var(--ink); }

footer {
  padding: 80px 5vw 35px;
  display: flex;
  justify-content: flex-end;
  color: var(--muted);
  font-size: 11px;
}

@keyframes spin { to { transform: rotate(360deg); } }
@keyframes bob { 50% { transform: translate(-50%, 8px); } }

@media(max-width: 800px) {
  nav { padding: 17px 5vw; }
  .nav-right { display: none; }
  .intro { grid-template-columns: 1fr; }
  .route { grid-template-columns: 35px 1fr; }
  .route .meta { grid-column: 2; }
  .badge { grid-column: 2; justify-self: start; }
  .note { display: block; }
  .note span { display: block; margin-top: 10px; }
}
</style>
</head>
<body>

<nav>
  <div class="nav-right mono">
    <a href="#routes">routes</a>
    <a href="#sources">sources</a>
  </div>
</nav>

<header class="hero">
  <div class="hero-grid"></div>
  <div class="orbit"></div>
  <div class="hero-content">
    <div class="mono eyebrow">BOLZANO → DOLOMITES / SOUTH TYROL</div>
    <h1><span>OPERATION</span><span class="outline">EPIC</span><span>DOLOMITES.</span></h1>
    <p class="hero-sub">Six hike options worth driving for. Alpine lakes, impossible rock walls, panoramic ridges and viewpoints - selected for scenery first, not crowds or convenience.</p>
  </div>
  <div class="scroll mono">↓ scroll the ridge</div>
</header>

<section id="routes">
  <div class="intro">
    <div>
      <div class="mono" style="color:var(--acid)">THE SHORTLIST</div>
      <h2>Six ways<br>up.</h2>
    </div>
    <p><strong>Sassongher</strong> is the summit mission. <strong>Sopranes</strong> is the alpine-lake mission. <strong>Adolf Munkel</strong> is the visual knockout with little vertical gain. <strong>Kreuzjoch</strong> is the quiet long day. <strong>Kohlern</strong> is the fast local hit. <strong>Piz Boè</strong> is the accessible 3000m giant.</p>
  </div>

  <div class="routes">
    <article class="route">
      <div class="num mono">01</div>
      <div>
        <div class="name">Laghi di Sopranes</div>
        <a class="route-link" href="https://www.alltrails.com/trail/italy/south-tyrol/laghi-di-sopranes-lago-lungo-lago-verde-lago-vizze" target="_blank">open route ↗</a>
      </div>
      <div class="meta">13.5 km · hard<br>+1,174 m · ~2,444 m high<br>Highest high-altitude lake district in Europe.</div>
      <div class="badge">ALPINE LAKES</div>
    </article>

    <article class="route">
      <div class="num mono">02</div>
      <div>
        <div class="name">Sassongher</div>
        <a class="route-link" href="https://www.alta-badia.org/it/sport-e-tempo-libero/montagne-ed-escursioni/sul-sassongher/" target="_blank">open route ↗</a>
      </div>
      <div class="meta">9.9 km · difficult<br>+1,224 m · 2,665 m summit<br>Rock, fixed ropes, Sella + Marmolada.</div>
      <div class="badge">SUMMIT</div>
    </article>

    <article class="route">
      <div class="num mono">03</div>
      <div>
        <div class="name">Grande Kreuzjochrunde</div>
        <a class="route-link" href="https://www.outdooractive.com/en/route/hiking-trail/bozen-umgebung/large-kreuzjoch-circular-route-kreuzjochrunde-/810054763/" target="_blank">open route ↗</a>
      </div>
      <div class="meta">17.3 km · moderate<br>+678 m · 2,084 m high<br>360° ridge panorama; quieter Sarntal terrain.</div>
      <div class="badge">QUIET RIDGE</div>
    </article>

    <article class="route">
      <div class="num mono">04</div>
      <div>
        <div class="name">Kohlern / Three Viewpoints</div>
        <a class="route-link" href="https://www.suedtirol.info/en/en/experiences-and-events/plp-experiences/experiences-south-tyrol/pdp-experience.smgpoid8cb7ca58b554e90756a1b2481177f8b.a-trip-to-three-viewpoints.colle-kohlern" target="_blank">open route ↗</a>
      </div>
      <div class="meta">7.6 km · easy<br>+337 m · 1,558 m high<br>Schlern, Rosengarten, Latemar + valley views.</div>
      <div class="badge">QUICK HIT</div>
    </article>

    <article class="route">
      <div class="num mono">05</div>
      <div>
        <div class="name">Adolf Munkel Trail</div>
        <a class="route-link" href="https://www.moonhoneytravel.com/hiking-adolf-munkel-trail-dolomites/" target="_blank">open route ↗</a>
      </div>
      <div class="meta">~9.5 km · easy/moderate<br>+400 m · ~2,050 m high<br>Directly beneath the Geisler / Odle walls.</div>
      <div class="badge">VISUAL HIT</div>
    </article>

    <article class="route">
      <div class="num mono">06</div>
      <div>
        <div class="name">Piz Boè</div>
        <a class="route-link" href="https://www.alta-badia.org/it/sport-e-tempo-libero/montagne-ed-escursioni/sul-piz-boe/" target="_blank">open route ↗</a>
      </div>
      <div class="meta">~6.5 km · moderate/hard<br>+460 m · 3,152 m summit<br>Lunar plateau, accessible 3000m peak & Marmolada views.</div>
      <div class="badge">3000M PEAK</div>
    </article>
  </div>

  <div class="note">
    <div><strong>Field notes:</strong> These aren't equivalent hikes.</div>
    <span>Vertical gain ranges from a 337 m viewpoint circuit to 1,224 m for a serious summit. Pick the experience, not the number.</span>
  </div>
</section>

<section id="sources">
  <div class="intro">
    <div>
      <div class="mono" style="color:var(--acid)">SOURCE CHECK</div>
      <h2>Know<br>before go.</h2>
    </div>
    <p><strong>Sopranes:</strong> AllTrails lists 13.5 km and 3,854 ft / ~1,175 m gain for the selected three-lake route. <strong>Sassongher:</strong> Alta Badia lists 9.9 km, +1,224 m and 2,665 m, and warns that the route is popular in high summer. <strong>Kreuzjoch:</strong> Outdooractive lists 17.3 km and +678 m. <strong>Kohlern:</strong> South Tyrol lists 7.6 km and +337 m. <strong>Piz Boè:</strong> Various sources list the loop from Sass Pordoi around 6.5 km and +460 m elevation to the 3,152 m summit. <strong>Adolf Munkel:</strong> recent GPS routes cluster around 9 - 10 km and ~400 m gain.</p>
  </div>
</section>

<footer>
  <span class="mono">BUILT FOR THE NEXT MOUNTAIN DAY</span>
</footer>

</body>
</html>
