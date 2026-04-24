<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>슝슝이도 워렌버핏</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
/* 1. 모바일/시스템 다크모드 강제 고정 */
:root {
  color-scheme: dark;
}

*{box-sizing:border-box;margin:0;padding:0}

/* 2. 배경 및 기본 폰트 설정 */
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  background: #010409 !important; /* 배경을 더 깊은 검정으로 고정 */
  color: #e6edf3 !important;
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
}

/* 네비게이션 */
nav {
  background: #0d1117 !important;
  border-bottom: 1px solid #30363d;
  padding: 0 20px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo{font-size:15px;font-weight:600;color:#e6edf3;margin-right:24px;padding:14px 0}
.logo span{color:#58a6ff}
.nav-tabs{display:flex;flex-wrap:wrap}
.tab{padding:14px 13px;font-size:13px;color:#8b949e;cursor:pointer;border-bottom:2px solid transparent;white-space:nowrap}
.tab:hover{color:#e6edf3}
.tab.active{color:#58a6ff;border-bottom-color:#58a6ff;font-weight:600}

.content{padding:22px; max-width: 1200px; margin: 0 auto;}
.page{display:none}
.page.active{display:block}

/* 카드 공통 스타일 */
.mcard, .cwrap, .gcard, .ccard {
  background: #0d1117 !important;
  border: 1px solid #30363d !important;
  border-radius: 10px;
  padding: 18px;
  margin-bottom: 18px;
}

.grid4{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:12px;margin-bottom:22px}
.lbl{font-size:11px;color:#8b949e;text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px}
.val{font-size:22px;font-weight:600}
.chg{font-size:13px;margin-top:4px}
.up{color:#3fb950 !important}.dn{color:#f85149 !important}

/* 3. 문제의 표(Table) 스타일 - !important로 강력 고정 */
.otbl {
  width: 100%;
  border-collapse: collapse;
  font-size: 12px;
  background-color: #0d1117 !important; /* 배경색 강제 */
  color: #e6edf3 !important;           /* 글자색 강제 */
}

.otbl th {
  text-align: left;
  padding: 12px 10px;
  color: #8b949e !important;
  border-bottom: 1px solid #30363d;
  background-color: #161b22 !important;
}

.otbl td {
  padding: 12px 10px;
  border-bottom: 1px solid #21262d;
  background-color: #0d1117 !important; /* 각 칸의 배경도 강제 */
  color: #e6edf3 !important;
}

.otbl tr:last-child td{border-bottom:none}

/* 모바일 가로 스크롤 대응 */
.cwrap {
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}

/* 버튼 및 입력창 스타일 */
.cg select {
  background: #161b22 !important;
  color: #e6edf3 !important;
  border: 1px solid #30363d;
  padding: 7px 9px;
  border-radius: 6px;
  font-size: 12px;
  -webkit-appearance: none; /* 아이폰 스타일 제거 */
}

.btn-blue{background:#1f3d6b;color:#58a6ff;border:1px solid #30363d;padding:6px 12px;border-radius:6px;font-size:12px;cursor:pointer}
.btn-yellow{background:#2b2b1f;color:#e3b341;border:1px solid #30363d;padding:6px 12px;border-radius:6px;font-size:12px;cursor:pointer}

/* 차트 컨테이너 */
.pcont{position:relative;height:170px;margin-bottom:8px}

@media (max-width:600px){
  .tab{padding:10px 8px;font-size:12px}
  .grid4{grid-template-columns: 1fr 1fr;}
}
</style>
</head>
<body>
<nav>
  <div class="logo">슝슝이도<span>워렌버핏</span></div>
  <div class="nav-tabs">
    <div class="tab active" onclick="showPage('market',this)">시장 현황</div>
    <div class="tab" onclick="showPage('portfolio',this)">대가 포트폴리오</div>
    <div class="tab" onclick="showPage('nps',this)">국민연금</div>
    <div class="tab" onclick="showPage('compare',this)">비교 분석</div>
  </div>
</nav>

<div class="content">
  <div id="market" class="page active">
    <div class="mcard" style="display:flex;gap:10px;align-items:center;flex-wrap:wrap">
      <span style="color:#8b949e;font-size:12px">Finnhub 키:</span>
      <input type="text" id="fhKeyInput" value="d7lkgm9r01qm7o0c684gd7lkgm9r01qm7o0c6850" style="background:#010409;border:1px solid #30363d;color:#e6edf3;padding:5px 8px;border-radius:4px;font-size:12px;flex:1;min-width:200px">
      <button class="btn-blue" onclick="saveAndReload()">저장</button>
      <button class="btn-yellow" onclick="testConn()">테스트</button>
    </div>

    <div class="grid4">
      <div class="mcard"><div class="lbl">나스닥 (QQQ)</div><div class="val" id="vNQ">...</div><div class="chg" id="cNQ"></div></div>
      <div class="mcard"><div class="lbl">S&P 500 (SPY)</div><div class="val" id="vSP">...</div><div class="chg" id="cSP"></div></div>
      <div class="mcard"><div class="lbl">코스피 (EWY)</div><div class="val" id="vKS">...</div><div class="chg" id="cKS"></div></div>
      <div class="mcard"><div class="lbl">VIX (VIXY)</div><div class="val" id="vVX">...</div><div class="chg" id="cVX"></div></div>
    </div>

    <div class="cwrap">
      <h3 style="font-size:14px;margin-bottom:12px">주요 종목 시세 (LIVE)</h3>
      <table class="otbl">
        <thead>
          <tr><th>티커</th><th>현재가</th><th>전일대비</th><th>등락률</th><th>고가</th><th>저가</th></tr>
        </thead>
        <tbody id="quoteTbody"></tbody>
      </table>
    </div>
  </div>

  <div id="portfolio" class="page">
    <div class="guru-grid" id="guruGrid"></div>
  </div>
  <div id="nps" class="page">
    <div class="cwrap">국민연금 데이터를 불러오는 중...</div>
  </div>
  <div id="compare" class="page">
    <div class="cwrap">비교 분석 준비 중...</div>
  </div>
</div>

<script>
var FH_KEY = 'd7lkgm9r01qm7o0c684gd7lkgm9r01qm7o0c6850';
var FH = 'https://finnhub.io/api/v1';

function fhGet(path) {
  return fetch(FH + path + '&token=' + FH_KEY).then(r => r.json());
}

function saveAndReload() {
  FH_KEY = document.getElementById('fhKeyInput').value.trim();
  loadMarket();
}

function testConn() {
  fhGet('/quote?symbol=AAPL').then(d => {
    alert(d.c ? '연결 성공! AAPL: $' + d.c : '키를 확인해주세요.');
    if(d.c) loadMarket();
  });
}

function loadMarket() {
  const symbols = [{s:'QQQ',v:'vNQ',c:'cNQ'}, {s:'SPY',v:'vSP',c:'cSP'}, {s:'EWY',v:'vKS',c:'cKS'}, {s:'VIXY',v:'vVX',c:'cVX'}];
  symbols.forEach(idx => {
    fhGet('/quote?symbol=' + idx.s).then(d => {
      if(!d.c) return;
      let pct = (d.c - d.pc) / d.pc * 100;
      document.getElementById(idx.v).textContent = '$' + d.c.toFixed(2);
      let el = document.getElementById(idx.c);
      el.textContent = (pct>=0?'▲ +':'▼ ') + pct.toFixed(2) + '%';
      el.className = 'chg ' + (pct>=0?'up':'dn');
    });
  });

  const watch = ['AAPL','MSFT','NVDA','TSLA','GOOGL','META','AMZN'];
  Promise.all(watch.map(s => fhGet('/quote?symbol='+s))).then(results => {
    let html = results.map((d, i) => {
      if(!d.c) return '';
      let pct = (d.c - d.pc) / d.pc * 100;
      let cls = pct>=0?'up':'dn';
      return `<tr><td style="font-weight:600">${watch[i]}</td><td>$${d.c}</td><td class="${cls}">${(d.c-d.pc).toFixed(2)}</td><td class="${cls}">${pct.toFixed(2)}%</td><td>$${d.h}</td><td>$${d.l}</td></tr>`;
    }).join('');
    document.getElementById('quoteTbody').innerHTML = html;
  });
}

function showPage(id, el) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  el.classList.add('active');
}

window.onload = loadMarket;
</script>
</body>
</html>
