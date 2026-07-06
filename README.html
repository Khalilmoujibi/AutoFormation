<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>AutoFormation — Deep Learning from Scratch</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Inter:wght@300;400;600;700&display=swap');

  :root {
    --bg: #050a12;
    --surface: #0d1520;
    --border: #1a2a3a;
    --cyan: #00d4ff;
    --purple: #7b61ff;
    --coral: #ff6b35;
    --green: #00ff88;
    --text: #c8d8e8;
    --muted: #5a7a9a;
    --white: #ffffff;
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    font-size: 15px;
    line-height: 1.7;
  }

  /* HERO */
  .hero {
    text-align: center;
    padding: 80px 40px 60px;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, #0a1e35 0%, var(--bg) 70%);
    border-bottom: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      repeating-linear-gradient(0deg, transparent, transparent 40px, rgba(0,212,255,0.03) 40px, rgba(0,212,255,0.03) 41px),
      repeating-linear-gradient(90deg, transparent, transparent 40px, rgba(0,212,255,0.03) 40px, rgba(0,212,255,0.03) 41px);
  }
  .hero-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 3rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--cyan) 0%, var(--purple) 50%, var(--coral) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
    position: relative;
  }
  .hero-sub {
    font-size: 1.1rem;
    color: var(--muted);
    margin-bottom: 32px;
    font-family: 'JetBrains Mono', monospace;
  }
  .badges { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; margin-bottom: 32px; }
  .badge {
    padding: 6px 16px;
    border-radius: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.04em;
    border: 1px solid;
  }
  .badge-cyan  { color: var(--cyan);   border-color: var(--cyan);   background: rgba(0,212,255,0.08); }
  .badge-purple{ color: var(--purple); border-color: var(--purple); background: rgba(123,97,255,0.08); }
  .badge-coral { color: var(--coral);  border-color: var(--coral);  background: rgba(255,107,53,0.08); }
  .badge-green { color: var(--green);  border-color: var(--green);  background: rgba(0,255,136,0.08); }
  .hero-quote {
    max-width: 600px;
    margin: 0 auto;
    font-style: italic;
    color: var(--muted);
    font-size: 0.95rem;
    border-left: 3px solid var(--purple);
    padding-left: 20px;
    text-align: left;
  }

  /* LAYOUT */
  .container { max-width: 1100px; margin: 0 auto; padding: 0 32px; }
  section { padding: 64px 0; border-bottom: 1px solid var(--border); }
  h2 {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.6rem;
    color: var(--cyan);
    margin-bottom: 40px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  h2::after { content:''; flex:1; height:1px; background: linear-gradient(90deg, var(--border), transparent); }
  h3 {
    font-size: 1.1rem;
    color: var(--white);
    margin-bottom: 20px;
    margin-top: 40px;
    font-weight: 600;
  }

  /* ROADMAP */
  .roadmap-grid { display: flex; flex-direction: column; gap: 12px; }
  .roadmap-item {
    display: grid;
    grid-template-columns: 180px 1fr 80px;
    align-items: center;
    gap: 20px;
    padding: 14px 20px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
  }
  .roadmap-item.done { border-color: rgba(0,212,255,0.3); }
  .roadmap-label { font-family: 'JetBrains Mono', monospace; font-size: 0.88rem; color: var(--text); }
  .bar-track { background: rgba(255,255,255,0.06); border-radius: 4px; height: 8px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 4px; }
  .bar-cyan   { background: linear-gradient(90deg, var(--cyan), var(--purple)); }
  .bar-purple { background: linear-gradient(90deg, var(--purple), var(--coral)); }
  .bar-muted  { background: var(--border); width: 0%; }
  .roadmap-status { font-family: 'JetBrains Mono', monospace; font-size: 0.78rem; text-align: right; }
  .status-done { color: var(--green); }
  .status-wip  { color: var(--cyan); }
  .status-soon { color: var(--muted); }

  /* CARDS */
  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    margin-bottom: 24px;
  }
  .card-header {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem;
    color: var(--cyan);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 16px;
    opacity: 0.7;
  }

  /* CODE */
  pre, code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.83rem;
  }
  pre {
    background: #060d16;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    overflow-x: auto;
    color: #a8c8e8;
    margin: 16px 0;
    line-height: 1.6;
  }
  .kw  { color: var(--purple); }
  .fn  { color: var(--cyan); }
  .num { color: var(--coral); }
  .cm  { color: var(--muted); }
  .ok  { color: var(--green); }

  /* FORMULA */
  .formula-box {
    background: rgba(123,97,255,0.08);
    border: 1px solid rgba(123,97,255,0.3);
    border-radius: 8px;
    padding: 16px 24px;
    margin: 16px 0;
    font-family: 'JetBrains Mono', monospace;
    font-size: 1rem;
    color: var(--white);
    text-align: center;
  }

  /* TABLE */
  table { width: 100%; border-collapse: collapse; margin: 20px 0; }
  th {
    background: rgba(0,212,255,0.08);
    color: var(--cyan);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    padding: 12px 16px;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }
  td {
    padding: 12px 16px;
    border-bottom: 1px solid rgba(26,42,58,0.5);
    font-size: 0.88rem;
  }
  tr:hover td { background: rgba(255,255,255,0.02); }

  /* SVG DIAGRAMS */
  .diagram-wrap {
    background: #060d16;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    margin: 20px 0;
    overflow-x: auto;
  }
  .ts { font-family:'JetBrains Mono',monospace; font-size:11px; fill:#5a7a9a; }
  .th { font-family:'JetBrains Mono',monospace; font-size:12px; fill:#c8d8e8; font-weight:700; }
  .node circle, .node rect { fill:#0d1520; stroke-width:1.5; }
  .c-gray   circle, .c-gray   rect { stroke:#5a7a9a; }
  .c-purple circle, .c-purple rect { stroke:#7b61ff; fill:rgba(123,97,255,0.15); }
  .c-cyan   circle, .c-cyan   rect { stroke:#00d4ff; fill:rgba(0,212,255,0.1); }
  .c-teal   circle, .c-teal   rect { stroke:#1d9e75; fill:rgba(29,158,117,0.15); }
  .c-coral  circle, .c-coral  rect { stroke:#ff6b35; fill:rgba(255,107,53,0.15); }
  .c-green  circle, .c-green  rect { stroke:#00ff88; fill:rgba(0,255,136,0.1); }

  /* ACTIVATION CHARTS side by side */
  .charts-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
  .chart-card {
    background: #060d16;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }
  .chart-title { font-family:'JetBrains Mono',monospace; font-size:0.8rem; color:var(--cyan); margin-bottom:8px; }
  .chart-formula { font-family:'JetBrains Mono',monospace; font-size:0.72rem; color:var(--muted); margin-top:8px; }

  /* NUMERICAL EXAMPLE */
  .example-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
  .example-block {
    background: #060d16;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
  }
  .example-block h4 {
    font-family:'JetBrains Mono',monospace;
    font-size:0.78rem;
    color:var(--cyan);
    text-transform:uppercase;
    letter-spacing:0.1em;
    margin-bottom:12px;
  }

  /* LOSS CURVE */
  .loss-curve-wrap { margin: 20px 0; }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 48px 32px;
    color: var(--muted);
    font-size: 0.88rem;
    font-family: 'JetBrains Mono', monospace;
  }
  footer span { color: var(--cyan); }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <h1 class="hero-title">Auto-Formation<br/>Deep Learning from Scratch</h1>
  <p class="hero-sub">$ numpy only &nbsp;·&nbsp; full derivations &nbsp;·&nbsp; zero shortcuts</p>
  <div class="badges">
    <span class="badge badge-cyan">PhD · ISTI / UM6P</span>
    <span class="badge badge-purple">Supervisor: Dr. Kaoutar Sefrioui</span>
    <span class="badge badge-coral">NumPy only — no frameworks</span>
    <span class="badge badge-green">● Active</span>
  </div>
  <p class="hero-quote">
    "Master every model from scratch — full mathematical derivation,
    hand-calculated verification, numpy implementation. No shortcuts."<br/>
    <small style="color:#3a5a7a">— Dr. Kaoutar Sefrioui</small>
  </p>
</div>

<div class="container">

<!-- ROADMAP -->
<section>
  <h2>📡 Roadmap</h2>
  <div class="roadmap-grid">
    <div class="roadmap-item done">
      <span class="roadmap-label">01 — Neural Networks</span>
      <div class="bar-track"><div class="bar-fill bar-cyan" style="width:100%"></div></div>
      <span class="roadmap-status status-done">✅ Done</span>
    </div>
    <div class="roadmap-item done">
      <span class="roadmap-label">02 — CNN</span>
      <div class="bar-track"><div class="bar-fill bar-cyan" style="width:85%"></div></div>
      <span class="roadmap-status status-done">✅ Done</span>
    </div>
    <div class="roadmap-item">
      <span class="roadmap-label">03 — RNN / LSTM / GRU</span>
      <div class="bar-track"><div class="bar-fill bar-purple" style="width:0%"></div></div>
      <span class="roadmap-status status-soon">⏳ Next</span>
    </div>
    <div class="roadmap-item">
      <span class="roadmap-label">04 — Transformers</span>
      <div class="bar-track"><div class="bar-fill bar-muted" style="width:0%"></div></div>
      <span class="roadmap-status status-soon">⏳ Soon</span>
    </div>
    <div class="roadmap-item">
      <span class="roadmap-label">05 — AE / VAE / GAN</span>
      <div class="bar-track"><div class="bar-fill bar-muted" style="width:0%"></div></div>
      <span class="roadmap-status status-soon">⏳ Soon</span>
    </div>
    <div class="roadmap-item">
      <span class="roadmap-label">06 — GNN Variants</span>
      <div class="bar-track"><div class="bar-fill bar-muted" style="width:0%"></div></div>
      <span class="roadmap-status status-soon">⏳ Soon</span>
    </div>
    <div class="roadmap-item">
      <span class="roadmap-label">07 — Active Learning</span>
      <div class="bar-track"><div class="bar-fill bar-muted" style="width:0%"></div></div>
      <span class="roadmap-status status-soon">⏳ Soon</span>
    </div>
  </div>
</section>

<!-- NN -->
<section>
  <h2>01 — Neural Networks</h2>

  <h3>Architecture — data flowing forward</h3>
  <div class="diagram-wrap">
    <svg width="100%" viewBox="0 0 700 320">
      <defs>
        <marker id="arr" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="#5a7a9a" stroke-width="1.5"/>
        </marker>
      </defs>
      <!-- connections -->
      <g stroke="#1a2a3a" stroke-width="1" opacity="0.6">
        <line x1="80" y1="160" x2="240" y2="80"/><line x1="80" y1="160" x2="240" y2="160"/><line x1="80" y1="160" x2="240" y2="240"/>
        <line x1="240" y1="80" x2="420" y2="100"/><line x1="240" y1="80" x2="420" y2="200"/>
        <line x1="240" y1="160" x2="420" y2="100"/><line x1="240" y1="160" x2="420" y2="200"/>
        <line x1="240" y1="240" x2="420" y2="100"/><line x1="240" y1="240" x2="420" y2="200"/>
        <line x1="420" y1="100" x2="600" y2="160"/><line x1="420" y1="200" x2="600" y2="160"/>
      </g>
      <!-- input -->
      <g class="node c-gray"><circle cx="80" cy="160" r="22"/></g>
      <text class="ts" x="80" y="198" text-anchor="middle">INPUT</text>
      <text class="th" x="80" y="164" text-anchor="middle" fill="#5a7a9a">x</text>
      <!-- hidden 1 -->
      <g class="node c-purple"><circle cx="240" cy="80" r="22"/></g>
      <g class="node c-purple"><circle cx="240" cy="160" r="22"/></g>
      <g class="node c-purple"><circle cx="240" cy="240" r="22"/></g>
      <text class="ts" x="240" y="288" text-anchor="middle">HIDDEN 1 · ReLU</text>
      <!-- hidden 2 -->
      <g class="node c-teal"><circle cx="420" cy="100" r="22"/></g>
      <g class="node c-teal"><circle cx="420" cy="200" r="22"/></g>
      <text class="ts" x="420" y="248" text-anchor="middle">HIDDEN 2 · ReLU</text>
      <!-- output -->
      <g class="node c-coral"><circle cx="600" cy="160" r="22"/></g>
      <text class="ts" x="600" y="198" text-anchor="middle">OUTPUT · σ</text>
      <!-- labels on arrows -->
      <text class="ts" x="160" y="100" text-anchor="middle" fill="#7b61ff">z=Wx+b</text>
      <text class="ts" x="330" y="80" text-anchor="middle" fill="#1d9e75">a=ReLU(z)</text>
      <text class="ts" x="520" y="120" text-anchor="middle" fill="#ff6b35">ŷ=σ(z)</text>
      <!-- forward label -->
      <text class="ts" x="350" y="20" text-anchor="middle" fill="#00d4ff">► FORWARD PASS</text>
    </svg>
  </div>

  <div class="formula-box">z<sup>[l]</sup> = W<sup>[l]</sup> · a<sup>[l-1]</sup> + b<sup>[l]</sup> &nbsp;&nbsp;&nbsp; → &nbsp;&nbsp;&nbsp; a<sup>[l]</sup> = g( z<sup>[l]</sup> )</div>

  <h3>Activation Functions</h3>
  <div class="charts-row">
    <!-- Sigmoid -->
    <div class="chart-card">
      <div class="chart-title" style="color:#7b61ff">Sigmoid</div>
      <svg viewBox="0 0 200 130" width="100%">
        <line x1="10" y1="65" x2="190" y2="65" stroke="#1a2a3a" stroke-width="1"/>
        <line x1="100" y1="10" x2="100" y2="120" stroke="#1a2a3a" stroke-width="1"/>
        <text style="font-family:monospace;font-size:9px;fill:#1a2a3a" x="12" y="62">0.5</text>
        <text style="font-family:monospace;font-size:9px;fill:#1a2a3a" x="12" y="20">1</text>
        <text style="font-family:monospace;font-size:9px;fill:#1a2a3a" x="12" y="115">0</text>
        <path d="M10,110 C20,110 30,108 40,102 C55,92 65,78 80,68 C90,62 100,58 110,55 C125,50 140,42 155,28 C165,20 175,16 190,14" fill="none" stroke="#7b61ff" stroke-width="2.5"/>
        <line x1="10" y1="14" x2="190" y2="14" stroke="#1a2a3a" stroke-width="0.5" stroke-dasharray="3"/>
      </svg>
      <div class="chart-formula">σ(z) = 1 / (1 + e⁻ᶻ)<br/>range (0, 1)</div>
    </div>
    <!-- Tanh -->
    <div class="chart-card">
      <div class="chart-title" style="color:#1d9e75">Tanh</div>
      <svg viewBox="0 0 200 130" width="100%">
        <line x1="10" y1="65" x2="190" y2="65" stroke="#1a2a3a" stroke-width="1"/>
        <line x1="100" y1="10" x2="100" y2="120" stroke="#1a2a3a" stroke-width="1"/>
        <text style="font-family:monospace;font-size:9px;fill:#1a2a3a" x="12" y="20">1</text>
        <text style="font-family:monospace;font-size:9px;fill:#1a2a3a" x="12" y="115">-1</text>
        <path d="M10,113 C20,113 35,112 50,105 C65,96 75,80 90,68 C96,63 100,61 105,59 C118,52 130,38 148,26 C163,16 178,13 190,13" fill="none" stroke="#1d9e75" stroke-width="2.5"/>
      </svg>
      <div class="chart-formula">tanh(z)<br/>range (-1, 1)</div>
    </div>
    <!-- ReLU -->
    <div class="chart-card">
      <div class="chart-title" style="color:#ff6b35">ReLU</div>
      <svg viewBox="0 0 200 130" width="100%">
        <line x1="10" y1="65" x2="190" y2="65" stroke="#1a2a3a" stroke-width="1"/>
        <line x1="100" y1="10" x2="100" y2="120" stroke="#1a2a3a" stroke-width="1"/>
        <path d="M10,65 L100,65 L190,15" fill="none" stroke="#ff6b35" stroke-width="2.5"/>
        <circle cx="100" cy="65" r="3" fill="#ff6b35"/>
      </svg>
      <div class="chart-formula">max(0, z)<br/>range [0, ∞)</div>
    </div>
  </div>

  <div class="card">
    <div class="card-header">⚠ Vanishing Gradient — why ReLU wins</div>
    At large |z|, sigmoid and tanh flatten — their derivative → 0.<br/>
    During backprop, that near-zero value gets multiplied at <em>every layer</em>.<br/>
    After L layers: gradient ≈ (0.01)ᴸ → early layers stop learning entirely.<br/><br/>
    <strong style="color:#ff6b35">ReLU fix:</strong> derivative = 1 for all z &gt; 0. No decay. No saturation.
  </div>

  <h3>Backpropagation — Chain Rule Layer by Layer</h3>
  <div class="diagram-wrap">
    <svg width="100%" viewBox="0 0 700 180">
      <defs>
        <marker id="arr2" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="#00d4ff" stroke-width="1.5"/>
        </marker>
        <marker id="arr3" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="#ff6b35" stroke-width="1.5"/>
        </marker>
      </defs>
      <!-- forward arrows -->
      <line x1="60" y1="60" x2="190" y2="60" stroke="#00d4ff" stroke-width="1.5" marker-end="url(#arr2)"/>
      <line x1="270" y1="60" x2="380" y2="60" stroke="#00d4ff" stroke-width="1.5" marker-end="url(#arr2)"/>
      <line x1="460" y1="60" x2="570" y2="60" stroke="#00d4ff" stroke-width="1.5" marker-end="url(#arr2)"/>
      <text class="ts" x="120" y="50" text-anchor="middle" fill="#00d4ff">z=Wa+b</text>
      <text class="ts" x="320" y="50" text-anchor="middle" fill="#00d4ff">a=ReLU(z)</text>
      <text class="ts" x="510" y="50" text-anchor="middle" fill="#00d4ff">L=BCE(ŷ,y)</text>
      <!-- nodes -->
      <g class="node c-gray"><circle cx="40" cy="60" r="18"/></g>
      <text class="th" x="40" y="64" text-anchor="middle" fill="#5a7a9a">x</text>
      <g class="node c-purple"><circle cx="230" cy="60" r="18"/></g>
      <text class="th" x="230" y="64" text-anchor="middle">z</text>
      <g class="node c-teal"><circle cx="420" cy="60" r="18"/></g>
      <text class="th" x="420" y="64" text-anchor="middle">a</text>
      <g class="node c-coral"><circle cx="600" cy="60" r="18"/></g>
      <text class="th" x="600" y="64" text-anchor="middle" fill="#ff6b35">L</text>
      <!-- backward arrows -->
      <line x1="570" y1="110" x2="460" y2="110" stroke="#ff6b35" stroke-width="1.5" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <line x1="390" y1="110" x2="280" y2="110" stroke="#ff6b35" stroke-width="1.5" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <line x1="200" y1="110" x2="90" y2="110" stroke="#ff6b35" stroke-width="1.5" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <text class="ts" x="510" y="102" text-anchor="middle" fill="#ff6b35">δ=a-y</text>
      <text class="ts" x="330" y="102" text-anchor="middle" fill="#ff6b35">δ·ReLU'(z)</text>
      <text class="ts" x="140" y="102" text-anchor="middle" fill="#ff6b35">dW=δ·aᵀ</text>
      <!-- labels -->
      <text class="ts" x="350" y="148" text-anchor="middle" fill="#00d4ff">► FORWARD</text>
      <text class="ts" x="350" y="165" text-anchor="middle" fill="#ff6b35">◄ BACKWARD (backprop)</text>
    </svg>
  </div>

  <pre><span class="cm"># Complete backprop algorithm</span>
<span class="cm"># Step 1 — output layer (sigmoid + BCE simplification)</span>
δ[L]  = a[L] - y

<span class="cm"># Step 2 — hidden layers (L-1 down to 1)</span>
δ[l]  = (W[l+1])ᵀ · δ[l+1]  ⊙  <span class="fn">ReLU'</span>(z[l])

<span class="cm"># Step 3 — parameter gradients</span>
dW[l] = δ[l] · (a[l-1])ᵀ
db[l] = δ[l]

<span class="cm"># Step 4 — gradient descent update</span>
W[l]  := W[l] - η · dW[l]
b[l]  := b[l] - η · db[l]</pre>

  <h3>Numerical Example — Hand-calculated & numpy-verified</h3>
  <div class="example-grid">
    <div class="example-block">
      <h4>🔵 Forward Pass</h4>
      <pre style="margin:0"><span class="cm"># x=[2,3], y=1, lr=0.1</span>
<span class="cm"># W1=[[0.5,1],[1,-0.5]]</span>
<span class="cm"># b1=[0,1], W2=[1,1], b2=-2</span>

z1 = [<span class="num">4.0</span>, <span class="num">1.5</span>]   <span class="cm"># W1·x+b1</span>
a1 = [<span class="num">4.0</span>, <span class="num">1.5</span>]   <span class="cm"># ReLU(z1)</span>
z2 = <span class="num">3.5</span>          <span class="cm"># W2·a1+b2</span>
a2 = <span class="num">0.9707</span>       <span class="cm"># σ(z2) ← ŷ</span>
L  = <span class="num">0.0297</span>       <span class="cm"># BCE loss</span></pre>
    </div>
    <div class="example-block">
      <h4>🔴 Backward Pass</h4>
      <pre style="margin:0">δ2  = <span class="num">-0.0293</span>       <span class="cm"># a2-y</span>
dW2 = [<span class="num">-0.1172</span>,<span class="num">-0.0440</span>]
δ1  = [<span class="num">-0.0293</span>,<span class="num">-0.0293</span>]
dW1 = [[<span class="num">-0.0586</span>,<span class="num">-0.0879</span>],
        [<span class="num">-0.0586</span>,<span class="num">-0.0879</span>]]

<span class="cm"># After update (η=0.1)</span>
W2 = [<span class="ok">1.0117</span>, <span class="ok">1.0044</span>]  <span class="ok">✓</span>
W1 = [[<span class="ok">0.5059</span>,<span class="ok">1.0088</span>],
      [<span class="ok">1.0059</span>,<span class="ok">-0.4912</span>]] <span class="ok">✓</span></pre>
    </div>
  </div>

  <h3>Training Loss — XOR Dataset</h3>
  <div class="diagram-wrap">
    <svg viewBox="0 0 700 200" width="100%">
      <line x1="60" y1="20" x2="60" y2="170" stroke="#1a2a3a" stroke-width="1.5"/>
      <line x1="60" y1="170" x2="680" y2="170" stroke="#1a2a3a" stroke-width="1.5"/>
      <text class="ts" x="30" y="28" text-anchor="middle" fill="#5a7a9a">0.70</text>
      <text class="ts" x="30" y="90" text-anchor="middle" fill="#5a7a9a">0.50</text>
      <text class="ts" x="30" y="165" text-anchor="middle" fill="#5a7a9a">0.40</text>
      <text class="ts" x="370" y="190" text-anchor="middle" fill="#5a7a9a">Epoch →</text>
      <text class="ts" x="80" y="185" text-anchor="middle" fill="#5a7a9a">0</text>
      <text class="ts" x="220" y="185" text-anchor="middle" fill="#5a7a9a">200</text>
      <text class="ts" x="430" y="185" text-anchor="middle" fill="#5a7a9a">500</text>
      <text class="ts" x="660" y="185" text-anchor="middle" fill="#5a7a9a">1000</text>
      <defs>
        <linearGradient id="lossGrad" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" style="stop-color:#7b61ff"/>
          <stop offset="100%" style="stop-color:#00d4ff"/>
        </linearGradient>
      </defs>
      <path d="M80,28 C100,28 130,32 160,45 C190,58 210,78 240,100 C270,118 310,138 370,150 C430,158 500,162 580,164 C620,165 650,165 670,165"
            fill="none" stroke="url(#lossGrad)" stroke-width="2.5"/>
      <path d="M80,28 C100,28 130,32 160,45 C190,58 210,78 240,100 C270,118 310,138 370,150 C430,158 500,162 580,164 C620,165 650,165 670,165 L670,170 L80,170 Z"
            fill="url(#lossGrad)" opacity="0.08"/>
      <circle cx="80" cy="28" r="4" fill="#7b61ff"/>
      <circle cx="670" cy="165" r="4" fill="#00d4ff"/>
      <text class="ts" x="90" y="22" fill="#7b61ff">0.706</text>
      <text class="ts" x="640" y="160" fill="#00d4ff">0.486</text>
    </svg>
  </div>

  <h3>Optimizers</h3>
  <table>
    <tr><th>Optimizer</th><th>Update Rule</th><th>Key Hyperparams</th><th>When to use</th></tr>
    <tr><td>SGD</td><td><code>W := W - η·g</code></td><td>η</td><td>Baseline, simple</td></tr>
    <tr><td>Momentum</td><td><code>v := βv - η·g &nbsp; W := W + v</code></td><td>η, β≈0.9</td><td>Smooths noisy gradients</td></tr>
    <tr><td><strong style="color:#00d4ff">Adam</strong></td><td><code>m̂/(√v̂+ε)</code></td><td>β₁=0.9, β₂=0.999</td><td>Default for most tasks</td></tr>
  </table>
</section>

<!-- CNN -->
<section>
  <h2>02 — Convolutional Neural Networks</h2>

  <h3>Why CNN Instead of Plain NN?</h3>
  <div class="example-grid">
    <div class="example-block">
      <h4>❌ Fully Connected (256×256 image)</h4>
      <pre style="margin:0">Pixels: 256×256×3 = <span class="num">196,608</span>
Hidden units: 1,000
Parameters: <span class="num">196,608,000</span>
→ overfits immediately
→ ignores spatial structure</pre>
    </div>
    <div class="example-block">
      <h4>✅ CNN (32 filters of 3×3)</h4>
      <pre style="margin:0">Filter: 3×3×3×32 = <span class="ok">864</span>
Weight sharing: same filter
scans the whole image
→ translation invariant
→ learns local patterns</pre>
    </div>
  </div>

  <h3>The Convolution Operation</h3>
  <div class="diagram-wrap">
    <svg viewBox="0 0 700 260" width="100%">
      <!-- INPUT grid 5x5 -->
      <text class="ts" x="120" y="20" text-anchor="middle" fill="#5a7a9a">INPUT (5×5)</text>
      <g fill="#0d1520" stroke="#1a2a3a" stroke-width="1">
        <rect x="20" y="30" width="40" height="40"/><text class="th" x="40" y="55" text-anchor="middle">1</text>
        <rect x="60" y="30" width="40" height="40"/><text class="th" x="80" y="55" text-anchor="middle">2</text>
        <rect x="100" y="30" width="40" height="40"/><text class="th" x="120" y="55" text-anchor="middle">3</text>
        <rect x="140" y="30" width="40" height="40"/><text class="th" x="160" y="55" text-anchor="middle">1</text>
        <rect x="180" y="30" width="40" height="40"/><text class="th" x="200" y="55" text-anchor="middle">0</text>

        <rect x="20" y="70" width="40" height="40"/><text class="th" x="40" y="95" text-anchor="middle">4</text>
        <rect x="60" y="70" width="40" height="40"/><text class="th" x="80" y="95" text-anchor="middle">5</text>
        <rect x="100" y="70" width="40" height="40"/><text class="th" x="120" y="95" text-anchor="middle">6</text>
        <rect x="140" y="70" width="40" height="40"/><text class="th" x="160" y="95" text-anchor="middle">2</text>
        <rect x="180" y="70" width="40" height="40"/><text class="th" x="200" y="95" text-anchor="middle">1</text>

        <rect x="20" y="110" width="40" height="40"/><text class="th" x="40" y="135" text-anchor="middle">7</text>
        <rect x="60" y="110" width="40" height="40"/><text class="th" x="80" y="135" text-anchor="middle">8</text>
        <rect x="100" y="110" width="40" height="40"/><text class="th" x="120" y="135" text-anchor="middle">9</text>
        <rect x="140" y="110" width="40" height="40"/><text class="th" x="160" y="135" text-anchor="middle">3</text>
        <rect x="180" y="110" width="40" height="40"/><text class="th" x="200" y="135" text-anchor="middle">2</text>

        <rect x="20" y="150" width="40" height="40"/><text class="th" x="40" y="175" text-anchor="middle">1</text>
        <rect x="60" y="150" width="40" height="40"/><text class="th" x="80" y="175" text-anchor="middle">2</text>
        <rect x="100" y="150" width="40" height="40"/><text class="th" x="120" y="175" text-anchor="middle">3</text>
        <rect x="140" y="150" width="40" height="40"/><text class="th" x="160" y="175" text-anchor="middle">1</text>
        <rect x="180" y="150" width="40" height="40"/><text class="th" x="200" y="175" text-anchor="middle">0</text>

        <rect x="20" y="190" width="40" height="40"/><text class="th" x="40" y="215" text-anchor="middle">0</text>
        <rect x="60" y="190" width="40" height="40"/><text class="th" x="80" y="215" text-anchor="middle">1</text>
        <rect x="100" y="190" width="40" height="40"/><text class="th" x="120" y="215" text-anchor="middle">2</text>
        <rect x="140" y="190" width="40" height="40"/><text class="th" x="160" y="215" text-anchor="middle">0</text>
        <rect x="180" y="190" width="40" height="40"/><text class="th" x="200" y="215" text-anchor="middle">1</text>
      </g>
      <!-- highlight active patch -->
      <rect x="20" y="30" width="120" height="120" fill="none" stroke="#7b61ff" stroke-width="2.5" stroke-dasharray="5 3" rx="2"/>

      <!-- × -->
      <text class="th" x="250" y="135" text-anchor="middle" fill="#5a7a9a">×</text>

      <!-- FILTER 3x3 -->
      <text class="ts" x="340" y="20" text-anchor="middle" fill="#7b61ff">FILTER (3×3)</text>
      <g fill="rgba(123,97,255,0.15)" stroke="#7b61ff" stroke-width="1">
        <rect x="280" y="70" width="40" height="40"/><text class="th" x="300" y="95" text-anchor="middle" fill="#7b61ff">1</text>
        <rect x="320" y="70" width="40" height="40"/><text class="th" x="340" y="95" text-anchor="middle" fill="#7b61ff">0</text>
        <rect x="360" y="70" width="40" height="40"/><text class="th" x="380" y="95" text-anchor="middle" fill="#7b61ff">1</text>
        <rect x="280" y="110" width="40" height="40"/><text class="th" x="300" y="135" text-anchor="middle" fill="#7b61ff">0</text>
        <rect x="320" y="110" width="40" height="40"/><text class="th" x="340" y="135" text-anchor="middle" fill="#7b61ff">1</text>
        <rect x="360" y="110" width="40" height="40"/><text class="th" x="380" y="135" text-anchor="middle" fill="#7b61ff">0</text>
        <rect x="280" y="150" width="40" height="40"/><text class="th" x="300" y="175" text-anchor="middle" fill="#7b61ff">1</text>
        <rect x="320" y="150" width="40" height="40"/><text class="th" x="340" y="175" text-anchor="middle" fill="#7b61ff">0</text>
        <rect x="360" y="150" width="40" height="40"/><text class="th" x="380" y="175" text-anchor="middle" fill="#7b61ff">1</text>
      </g>

      <!-- = -->
      <text class="th" x="435" y="135" text-anchor="middle" fill="#5a7a9a">=</text>

      <!-- OUTPUT 3x3 -->
      <text class="ts" x="575" y="20" text-anchor="middle" fill="#00d4ff">OUTPUT (3×3)</text>
      <g fill="rgba(0,212,255,0.1)" stroke="#00d4ff" stroke-width="1">
        <rect x="460" y="70" width="50" height="50"/><text class="th" x="485" y="100" text-anchor="middle" fill="#00d4ff">?</text>
        <rect x="510" y="70" width="50" height="50"/><text class="th" x="535" y="100" text-anchor="middle" fill="#00d4ff">...</text>
        <rect x="560" y="70" width="50" height="50"/>

        <rect x="460" y="120" width="50" height="50"/>
        <rect x="510" y="120" width="50" height="50"/>
        <rect x="560" y="120" width="50" height="50"/>

        <rect x="460" y="170" width="50" height="50"/>
        <rect x="510" y="170" width="50" height="50"/>
        <rect x="560" y="170" width="50" height="50"/>
      </g>

      <text class="ts" x="350" y="248" text-anchor="middle" fill="#5a7a9a">Slide filter across input → one number per position → build output map</text>
    </svg>
  </div>

  <div class="formula-box">Output size = (Input − Filter + 2 × Padding) / Stride + 1</div>

  <h3>LeNet Architecture</h3>
  <div class="diagram-wrap">
    <svg viewBox="0 0 700 120" width="100%">
      <defs>
        <marker id="arr4" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="#5a7a9a" stroke-width="1.2"/>
        </marker>
      </defs>
      <!-- boxes -->
      <g>
        <rect x="10" y="35" width="70" height="50" rx="4" fill="#0d1520" stroke="#5a7a9a" stroke-width="1"/>
        <text class="ts" x="45" y="56" text-anchor="middle" fill="#c8d8e8">32×32×1</text>
        <text class="ts" x="45" y="70" text-anchor="middle">INPUT</text>

        <line x1="80" y1="60" x2="110" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="110" y="30" width="80" height="60" rx="4" fill="rgba(123,97,255,0.15)" stroke="#7b61ff" stroke-width="1.2"/>
        <text class="ts" x="150" y="52" text-anchor="middle" fill="#7b61ff">28×28×6</text>
        <text class="ts" x="150" y="65" text-anchor="middle" fill="#7b61ff">CONV+ReLU</text>
        <text class="ts" x="150" y="78" text-anchor="middle" fill="#5a7a9a">5×5, 156p</text>

        <line x1="190" y1="60" x2="220" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="220" y="35" width="70" height="50" rx="4" fill="rgba(29,158,117,0.15)" stroke="#1d9e75" stroke-width="1.2"/>
        <text class="ts" x="255" y="56" text-anchor="middle" fill="#1d9e75">14×14×6</text>
        <text class="ts" x="255" y="70" text-anchor="middle" fill="#1d9e75">MAX POOL</text>

        <line x1="290" y1="60" x2="320" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="320" y="30" width="80" height="60" rx="4" fill="rgba(123,97,255,0.15)" stroke="#7b61ff" stroke-width="1.2"/>
        <text class="ts" x="360" y="52" text-anchor="middle" fill="#7b61ff">10×10×16</text>
        <text class="ts" x="360" y="65" text-anchor="middle" fill="#7b61ff">CONV+ReLU</text>
        <text class="ts" x="360" y="78" text-anchor="middle" fill="#5a7a9a">5×5, 2,416p</text>

        <line x1="400" y1="60" x2="430" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="430" y="35" width="70" height="50" rx="4" fill="rgba(29,158,117,0.15)" stroke="#1d9e75" stroke-width="1.2"/>
        <text class="ts" x="465" y="56" text-anchor="middle" fill="#1d9e75">5×5×16</text>
        <text class="ts" x="465" y="70" text-anchor="middle" fill="#1d9e75">MAX POOL</text>

        <line x1="500" y1="60" x2="530" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="530" y="35" width="60" height="50" rx="4" fill="rgba(0,212,255,0.1)" stroke="#00d4ff" stroke-width="1.2"/>
        <text class="ts" x="560" y="56" text-anchor="middle" fill="#00d4ff">FC 120</text>
        <text class="ts" x="560" y="70" text-anchor="middle" fill="#5a7a9a">dense</text>

        <line x1="590" y1="60" x2="620" y2="60" stroke="#5a7a9a" marker-end="url(#arr4)"/>

        <rect x="620" y="35" width="70" height="50" rx="4" fill="rgba(255,107,53,0.15)" stroke="#ff6b35" stroke-width="1.2"/>
        <text class="ts" x="655" y="56" text-anchor="middle" fill="#ff6b35">OUTPUT</text>
        <text class="ts" x="655" y="70" text-anchor="middle" fill="#ff6b35">10 classes</text>
        <text class="ts" x="655" y="83" text-anchor="middle" fill="#5a7a9a">softmax</text>
      </g>
    </svg>
  </div>

  <h3>Training Loss — MNIST Subset</h3>
  <div class="diagram-wrap">
    <svg viewBox="0 0 700 200" width="100%">
      <line x1="60" y1="20" x2="60" y2="170" stroke="#1a2a3a" stroke-width="1.5"/>
      <line x1="60" y1="170" x2="680" y2="170" stroke="#1a2a3a" stroke-width="1.5"/>
      <text class="ts" x="35" y="28" text-anchor="middle" fill="#5a7a9a">2.30</text>
      <text class="ts" x="35" y="90" text-anchor="middle" fill="#5a7a9a">1.20</text>
      <text class="ts" x="35" y="155" text-anchor="middle" fill="#5a7a9a">0.30</text>
      <text class="ts" x="370" y="190" text-anchor="middle" fill="#5a7a9a">Epoch →</text>
      <text class="ts" x="80" y="185" text-anchor="middle" fill="#5a7a9a">0</text>
      <text class="ts" x="280" y="185" text-anchor="middle" fill="#5a7a9a">10</text>
      <text class="ts" x="480" y="185" text-anchor="middle" fill="#5a7a9a">20</text>
      <text class="ts" x="660" y="185" text-anchor="middle" fill="#5a7a9a">30</text>
      <defs>
        <linearGradient id="lossGrad2" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" style="stop-color:#ff6b35"/>
          <stop offset="100%" style="stop-color:#00ff88"/>
        </linearGradient>
      </defs>
      <path d="M80,25 C120,25 150,28 180,38 C220,52 250,78 300,105 C360,130 420,148 490,158 C560,164 620,166 670,167"
            fill="none" stroke="url(#lossGrad2)" stroke-width="2.5"/>
      <path d="M80,25 C120,25 150,28 180,38 C220,52 250,78 300,105 C360,130 420,148 490,158 C560,164 620,166 670,167 L670,170 L80,170 Z"
            fill="url(#lossGrad2)" opacity="0.08"/>
      <circle cx="80" cy="25" r="4" fill="#ff6b35"/>
      <circle cx="670" cy="167" r="4" fill="#00ff88"/>
      <text class="ts" x="90" y="20" fill="#ff6b35">2.30</text>
      <text class="ts" x="630" y="162" fill="#00ff88">0.30</text>
      <text class="ts" x="350" y="100" fill="#00d4ff">~94% accuracy</text>
    </svg>
  </div>
</section>

<!-- NOTATION + RESOURCES -->
<section>
  <h2>📐 Notation Reference</h2>
  <table>
    <tr><th>Symbol</th><th>Meaning</th><th>Shape</th></tr>
    <tr><td><code>W[l]</code></td><td>Weight matrix of layer l</td><td>(n[l], n[l-1])</td></tr>
    <tr><td><code>b[l]</code></td><td>Bias vector of layer l</td><td>(n[l], 1)</td></tr>
    <tr><td><code>z[l]</code></td><td>Pre-activation: W[l]·a[l-1] + b[l]</td><td>(n[l], 1)</td></tr>
    <tr><td><code>a[l]</code></td><td>Post-activation: g(z[l])</td><td>(n[l], 1)</td></tr>
    <tr><td><code>δ[l]</code></td><td>Error signal: dL/dz[l]</td><td>(n[l], 1)</td></tr>
    <tr><td><code>η</code></td><td>Learning rate</td><td>scalar</td></tr>
    <tr><td><code>⊙</code></td><td>Element-wise (Hadamard) product</td><td>—</td></tr>
  </table>
</section>

<section style="border-bottom:none">
  <h2>📚 Resources</h2>
  <table>
    <tr><th>Resource</th><th>Used for</th></tr>
    <tr><td><a href="https://cs231n.github.io/" style="color:#00d4ff">CS231n — Stanford</a></td><td>Primary reference — full course</td></tr>
    <tr><td><a href="https://cs231n.github.io/neural-networks-1/" style="color:#00d4ff">CS231n — NN Part 1</a></td><td>Architecture, activations</td></tr>
    <tr><td><a href="https://cs231n.github.io/optimization-2/" style="color:#00d4ff">CS231n — Backpropagation</a></td><td>Chain rule, gradient flow</td></tr>
    <tr><td><a href="https://cs231n.github.io/neural-networks-case-study/" style="color:#00d4ff">CS231n — Case Study</a></td><td>Full numpy implementation</td></tr>
    <tr><td><a href="https://cs231n.github.io/convolutional-networks/" style="color:#00d4ff">CS231n — CNN</a></td><td>Convolution, pooling, architectures</td></tr>
    <tr><td>Deep Learning — Goodfellow et al.</td><td>Mathematical foundations</td></tr>
  </table>
</section>

</div>

<footer>
  <span>Khalil Moujibi</span> · PhD Researcher — AI for Chemistry · UM6P / ISTI · 2026<br/>
  <small style="opacity:0.5">HieroRetro · Transformer-based retrosynthesis prediction</small>
</footer>

</body>
</html>
