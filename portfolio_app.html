<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>슝슝이도 워렌버핏 | Premium Dashboard</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
/* 1. 프리미엄 다크 테마 컬러 팔레트 */
:root {
  --bg-main: #0b0e14;
  --bg-card: #161b22;
  --accent-purple: #a855f7;
  --accent-cyan: #06b6d4;
  --accent-gold: #f59e0b;
  --text-main: #f0f6fc;
  --text-dim: #8b949e;
  --border: #30363d;
  --up-color: #22c55e;
  --dn-color: #ef4444;
}

*{box-sizing:border-box;margin:0;padding:0}

body {
  font-family: 'Inter', -apple-system, sans-serif;
  background: var(--bg-main);
  color: var(--text-main);
  min-height: 100vh;
  line-height: 1.6;
}

/* 네비게이션 스타일 - 그라데이션 포인트 */
nav {
  background: rgba(22, 27, 34, 0.8);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
  padding: 0 24px;
  display: flex;
  align-items: center;
  position: sticky;
  top: 0;
  z-index: 1000;
}

.logo {
  font-size: 18px;
  font-weight: 800;
  letter-spacing: -0.5px;
  padding: 18px 0;
  margin-right: 40px;
}
.logo span {
  background: linear-gradient(90deg, var(--accent-purple), var(--accent-cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.nav-tabs { display: flex; gap: 8px; }
.tab {
  padding: 20px 16px;
  font-size: 14px;
  color: var(--text-dim);
  cursor: pointer;
  transition: 0.2s;
  position: relative;
}
.tab:hover { color: var(--text-main); }
.tab.active { color: var(--accent-cyan); font-weight: 600; }
.tab.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: var(--accent-cyan);
  box-shadow: 0 -2px 10px var(--accent-cyan);
}

.content { padding: 32px 24px; max-width: 1300px; margin: 0 auto; }
.page { display: none; }
.page.active { display: block; }

/* 세련된 카드 디자인 (Glow 효과) */
.mcard {
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 24px;
  margin-bottom: 24px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.3);
}

/* 상단 요약 지표 (Grid) */
.summary-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
  margin-bottom: 32px;
}
.s-card {
  background: linear-gradient(145deg, #1c2128, #161b22);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 20px;
  transition: transform 0.2s;
}
.s-card:hover { transform: translateY(-5px); border-color: var(--accent-purple); }
.s-lbl { font-size: 12px; color: var(--text-dim); margin-bottom: 8px; font-weight: 600; }
.s-val { font-size: 26px; font-weight: 700; display: flex; align-items: baseline; gap: 8px; }
.s-chg { font-size: 14px; font-weight: 500; }

/* 스크린샷 스타일의 테이블 */
.table-container {
  overflow-x: auto;
  border-radius: 16px;
  border: 1px solid var(--border);
  background: var(--bg-card);
}
.otbl {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
}
.otbl th {
  background: #1c2128;
  padding: 16px;
  font-size: 12px;
  color: var(--text-dim);
  text-transform: uppercase;
  border-bottom: 1px solid var(--border);
}
.otbl td {
  padding: 16px;
  font-size: 14px;
  border-bottom: 1px solid #21262d;
}
.otbl tr:hover td { background: rgba(255,255,255,0.03); }

/* 시각화 도구 */
.chart-box {
  height: 300px;
  margin-top: 20px;
}

/* 업다운 컬러 강조 */
.up { color: var(--up-color) !important; }
.dn { color: var(--dn-color) !important; }

@media (max-width: 768px) {
  .summary-grid { grid-template-columns: 1fr 1fr; }
  .logo { margin-right: 10px; }
}
</style>
</head>
<body>

<nav>
  <div class="logo">슝슝이<span>버핏 대시보드</span></div>
  <div class="nav-tabs">
    <div class="tab active" onclick="showPage('market',this)">시장 분석</div>
    <div class="tab" onclick="showPage('portfolio',this)">포트폴리오</div>
    <div class="tab" onclick="showPage('compare',this)">비교 엔진</div>
  </div>
</nav>

<div class="content">
  <div id="market" class="page active">
    <div class="summary-grid">
      <div class="s-card">
        <div class="s-lbl">NASDAQ 100</div>
        <div class="s-val" id="vNQ">----</div>
        <div class="s-chg" id="cNQ">--%</div>
      </div>
      <div class="s-card">
        <div class="s-lbl">S&P 500</div>
        <div class="s-val" id="vSP">----</div>
        <div class="s-chg" id="cSP">--%</div>
      </div>
      <div class="s-card">
        <div class="s-lbl">KOSPI 200</div>
        <div class="s-val" id="vKS">----</div>
        <div class="s-chg" id="cKS">--%</div>
      </div>
      <div class="s-card">
        <div class="s-lbl">FEAR & GREED</div>
        <div class="s-val" style="color:var(--accent-gold)">Neutral</div>
        <div class="s-chg" style="color:var(--text-dim)">Index: 52</div>
      </div>
    </div>

    <div class="mcard">
      <h2 style="font-size:18px; margin-bottom:20px;">글로벌 주요 자산 실시간 시세</h2>
      <div class="table-container">
        <table class="otbl">
          <thead>
            <tr>
              <th>자산명</th>
              <th>현재가</th>
              <th>변동($)</th>
              <th>변동률(%)</th>
              <th>24H 차트</th>
            </tr>
          </thead>
          <tbody id="quoteTbody">
            <tr><td colspan="5" style="text-align:center; padding:40px; color:var(--text-dim);">데이터를 불러오는 중...</td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="mcard">
      <h2 style="font-size:18px; margin-bottom:10px;">자산군 분포 (Asset Allocation)</h2>
      <div class="chart-box">
        <canvas id="mainChart"></canvas>
      </div>
    </div>
  </div>
</div>

<script>
// Finnhub API 설정
const FH_KEY = 'd7lkgm9r01qm7o0c684gd7lkgm9r01qm7o0c6850';
const FH = 'https://finnhub.io/api/v1';

async function fetchQuote(symbol) {
  const r = await fetch(`${FH}/quote?symbol=${symbol}&token=${FH_KEY}`);
  return r.json();
}

async function initDashboard() {
  // 상단 요약 데이터
  const indices = [
    {s:'QQQ', v:'vNQ', c:'cNQ'},
    {s:'SPY', v:'vSP', c:'cSP'},
    {s:'EWY', v:'vKS', c:'cKS'}
  ];

  for (const idx of indices) {
    const d = await fetchQuote(idx.s);
    if(d.c) {
      const pct = ((d.c - d.pc) / d.pc * 100).toFixed(2);
      document.getElementById(idx.v).innerText = `$${d.c.toLocaleString()}`;
      const el = document.getElementById(idx.c);
      el.innerText = (pct >= 0 ? '+' : '') + pct + '%';
      el.className = 's-chg ' + (pct >= 0 ? 'up' : 'dn');
    }
  }

  // 실시간 테이블 데이터
  const watch = ['AAPL', 'TSLA', 'NVDA', 'MSFT', 'AMZN', 'GOOGL'];
  let html = '';
  for (const s of watch) {
    const d = await fetchQuote(s);
    const pct = ((d.c - d.pc) / d.pc * 100).toFixed(2);
    const cls = pct >= 0 ? 'up' : 'dn';
    html += `
      <tr>
        <td style="font-weight:600; color:var(--accent-cyan)">${s}</td>
        <td style="font-weight:600">$${d.c}</td>
        <td class="${cls}">${(d.c - d.pc).toFixed(2)}</td>
        <td class="${cls}">${pct}%</td>
        <td style="color:var(--text-dim); font-size:11px;">데이터 준비중</td>
      </tr>
    `;
  }
  document.getElementById('quoteTbody').innerHTML = html;

  // 차트 생성 (그라데이션 효과)
  const ctx = document.getElementById('mainChart').getContext('2d');
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['1월', '2월', '3월', '4월', '5월', '6월'],
      datasets: [{
        label: '버핏 포트폴리오 수익률',
        data: [10, 15, 12, 18, 25, 22],
        borderColor: '#a855f7',
        backgroundColor: 'rgba(168, 85, 247, 0.1)',
        fill: true,
        tension: 0.4
      }]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: { legend: { display: false } },
      scales: {
        x: { grid: { display: false }, ticks: { color: '#8b949e' } },
        y: { grid: { color: '#30363d' }, ticks: { color: '#8b949e' } }
      }
    }
  });
}

function showPage(id, el) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  el.classList.add('active');
}

window.onload = initDashboard;
</script>

</body>
</html>
