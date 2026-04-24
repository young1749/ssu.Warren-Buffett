[index.html](https://github.com/user-attachments/files/27051219/index.html)
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>슝슝이도 워렌버핏</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;background:#0d1117;color:#e6edf3;min-height:100vh}
nav{background:#161b22;border-bottom:1px solid #30363d;padding:0 20px;display:flex;align-items:center;flex-wrap:wrap;position:sticky;top:0;z-index:100}
.logo{font-size:15px;font-weight:600;color:#e6edf3;margin-right:24px;padding:14px 0}
.logo span{color:#58a6ff}
.nav-tabs{display:flex;flex-wrap:wrap}
.tab{padding:14px 13px;font-size:13px;color:#8b949e;cursor:pointer;border-bottom:2px solid transparent;white-space:nowrap}
.tab:hover{color:#e6edf3}
.tab.active{color:#58a6ff;border-bottom-color:#58a6ff}
.content{padding:22px}
.page{display:none}
.page.active{display:block}
.grid4{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:12px;margin-bottom:22px}
.mcard{background:#161b22;border:1px solid #30363d;border-radius:10px;padding:16px}
.lbl{font-size:11px;color:#8b949e;text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px}
.val{font-size:22px;font-weight:600}
.chg{font-size:13px;margin-top:4px}
.up{color:#3fb950}.dn{color:#f85149}
.sec-title{font-size:14px;font-weight:600;margin-bottom:12px}
.cwrap{background:#161b22;border:1px solid #30363d;border-radius:10px;padding:18px;margin-bottom:18px}
.otbl{width:100%;border-collapse:collapse;font-size:12px}
.otbl th{text-align:left;padding:9px 10px;color:#8b949e;border-bottom:1px solid #30363d;font-weight:500}
.otbl td{padding:9px 10px;border-bottom:1px solid #21262d}
.otbl tr:last-child td{border-bottom:none}
.guru-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:16px}
.gcard{background:#161b22;border:1px solid #30363d;border-radius:10px;padding:16px}
.ghdr{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.gav{width:36px;height:36px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:600;flex-shrink:0}
.gname{font-size:13px;font-weight:600}
.gaum{font-size:11px;color:#8b949e;margin-top:2px}
.pcont{position:relative;height:170px;margin-bottom:8px}
.leg{display:flex;flex-wrap:wrap;gap:5px}
.litem{display:flex;align-items:center;gap:4px;font-size:11px;color:#8b949e}
.ldot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.cmp-sel{display:flex;gap:12px;margin-bottom:18px;flex-wrap:wrap;align-items:flex-end}
.cmp-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.ccard{background:#161b22;border:1px solid #30363d;border-radius:10px;padding:16px}
.ctitle{font-size:13px;font-weight:600;margin-bottom:10px}
.hrow{display:flex;align-items:center;gap:8px;margin-bottom:5px}
.hname{font-size:11px;color:#8b949e;min-width:52px}
.hbwrap{flex:1;height:5px;background:#21262d;border-radius:3px;overflow:hidden}
.hbar{height:100%;border-radius:3px}
.hpct{font-size:11px;min-width:30px;text-align:right}
.cg{display:flex;flex-direction:column;gap:5px}
.cg label{font-size:11px;color:#8b949e}
.cg select{background:#0d1117;border:1px solid #30363d;color:#e6edf3;padding:7px 9px;border-radius:6px;font-size:12px}
.loading{display:flex;align-items:center;gap:8px;color:#8b949e;font-size:12px;padding:8px 0}
.spin{width:14px;height:14px;border:2px solid #30363d;border-top-color:#58a6ff;border-radius:50%;animation:spin .8s linear infinite;flex-shrink:0}
@keyframes spin{to{transform:rotate(360deg)}}
.badge{font-size:10px;padding:2px 6px;border-radius:4px;font-weight:500;margin-left:6px}
.badge-live{background:#1f3d2b;color:#3fb950}
.badge-sample{background:#2b2b1f;color:#e3b341}
.err{color:#f85149;font-size:12px;margin-top:6px}
.api-bar{background:#161b22;border:1px solid #30363d;border-radius:8px;padding:10px 14px;margin-bottom:12px;display:flex;align-items:center;gap:10px;font-size:12px;flex-wrap:wrap}
.api-bar input{background:#0d1117;border:1px solid #30363d;color:#e6edf3;padding:5px 9px;border-radius:6px;font-size:12px;width:260px}
.btn-blue{background:#1f3d6b;color:#58a6ff;border:1px solid #30363d;padding:5px 12px;border-radius:6px;font-size:12px;cursor:pointer}
.btn-yellow{background:#2b2b1f;color:#e3b341;border:1px solid #30363d;padding:5px 12px;border-radius:6px;font-size:12px;cursor:pointer}
.test-result{font-size:12px;padding:8px 12px;border-radius:6px;margin-bottom:12px;display:none}
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

<!-- 시장 현황 -->
<div id="market" class="page active">
  <div class="api-bar">
    <span style="color:#8b949e">Finnhub 키:</span>
    <input type="text" id="fhKeyInput" value="d7lkgm9r01qm7o0c684gd7lkgm9r01qm7o0c6850">
    <button class="btn-blue" onclick="saveAndReload()">저장</button>
    <button class="btn-yellow" onclick="testConn()">연결 테스트</button>
    <span id="keyStatus" style="color:#8b949e"></span>
  </div>
  <div id="testResult" class="test-result"></div>
  <div class="grid4">
    <div class="mcard"><div class="lbl">나스닥 (QQQ) <span class="badge badge-live">LIVE</span></div><div class="val" id="vNQ">...</div><div class="chg" id="cNQ"></div></div>
    <div class="mcard"><div class="lbl">S&P 500 (SPY) <span class="badge badge-live">LIVE</span></div><div class="val" id="vSP">...</div><div class="chg" id="cSP"></div></div>
    <div class="mcard"><div class="lbl">코스피 (EWY) <span class="badge badge-live">LIVE</span></div><div class="val" id="vKS">...</div><div class="chg" id="cKS"></div></div>
    <div class="mcard"><div class="lbl">VIX (VIXY) <span class="badge badge-live">LIVE</span></div><div class="val" id="vVX">...</div><div class="chg" id="cVX"></div></div>
  </div>
  <div class="cwrap">
    <div class="sec-title">주요 종목 시세 <span class="badge badge-live">LIVE</span></div>
    <div id="quoteLoading" class="loading"><div class="spin"></div>시세 불러오는 중...</div>
    <div id="quoteErr" class="err" style="display:none"></div>
    <div id="quoteTable" style="display:none">
      <table class="otbl">
        <thead><tr><th>티커</th><th>현재가</th><th>전일대비</th><th>등락률</th><th>당일 고가</th><th>당일 저가</th><th>전일 종가</th></tr></thead>
        <tbody id="quoteTbody"></tbody>
      </table>
    </div>
  </div>
</div>

<!-- 대가 포트폴리오 -->
<div id="portfolio" class="page">
  <div class="guru-grid" id="guruGrid"></div>
</div>

<!-- 국민연금 -->
<div id="nps" class="page">
  <div style="display:flex;align-items:center;gap:12px;margin-bottom:18px;flex-wrap:wrap">
    <div class="cg">
      <label>연도</label>
      <select id="npsYear" onchange="loadNps()">
        <option>2026</option><option>2025</option><option>2024</option><option>2023</option><option>2022</option><option>2021</option>
      </select>
    </div>
    <div class="cg">
      <label>분기</label>
      <select id="npsQuarter" onchange="loadNps()">
        <option value="11011">4분기 (사업보고서)</option>
        <option value="11014">3분기</option>
        <option value="11012">2분기 (반기)</option>
        <option value="11013">1분기</option>
      </select>
    </div>
    <span id="npsBadge" class="badge badge-sample">샘플</span>
  </div>
  <div class="grid4" style="margin-bottom:20px">
    <div class="mcard"><div class="lbl">운용 규모</div><div class="val">1,035조</div><div class="chg" style="color:#8b949e">2024년 기준</div></div>
    <div class="mcard"><div class="lbl">해외 주식 비중</div><div class="val">35.2%</div><div class="chg up">▲ 3.1%p YoY</div></div>
    <div class="mcard"><div class="lbl">국내 주식 비중</div><div class="val">14.8%</div><div class="chg dn">▼ 1.2%p YoY</div></div>
    <div class="mcard"><div class="lbl">수익률</div><div class="val">+9.4%</div><div class="chg up">▲ 양호</div></div>
  </div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px">
    <div class="cwrap">
      <div class="sec-title">자산 배분 현황</div>
      <div style="position:relative;height:210px"><canvas id="npsPie"></canvas></div>
      <div class="leg" id="npsLeg" style="margin-top:10px"></div>
    </div>
    <div class="cwrap">
      <div class="sec-title" id="npsTableTitle">상위 보유 종목</div>
      <div id="npsErr" class="err" style="display:none;margin-bottom:8px"></div>
      <table class="otbl">
        <thead><tr><th>종목명</th><th>보유 주식수</th><th>지분율</th></tr></thead>
        <tbody id="npsBody"></tbody>
      </table>
    </div>
  </div>
</div>

<!-- 비교 분석 -->
<div id="compare" class="page">
  <div class="cmp-sel">
    <div class="cg"><label>포트폴리오 A</label><select id="cmpA" onchange="renderCompare()"></select></div>
    <div class="cg"><label>포트폴리오 B</label><select id="cmpB" onchange="renderCompare()"></select></div>
  </div>
  <div class="cmp-grid">
    <div class="ccard"><div class="ctitle" id="cmpTitleA"></div><div style="position:relative;height:180px"><canvas id="cmpPieA"></canvas></div><div id="cmpBarsA" style="margin-top:10px"></div></div>
    <div class="ccard"><div class="ctitle" id="cmpTitleB"></div><div style="position:relative;height:180px"><canvas id="cmpPieB"></canvas></div><div id="cmpBarsB" style="margin-top:10px"></div></div>
  </div>
  <div class="cwrap" style="margin-top:16px">
    <div class="sec-title">섹터 비중 비교</div>
    <div style="position:relative;height:220px"><canvas id="sectorChart"></canvas></div>
  </div>
</div>

</div>
<script>
var FH_KEY = 'd7lkgm9r01qm7o0c684gd7lkgm9r01qm7o0c6850';
var FH = 'https://finnhub.io/api/v1';
var C = ['#58a6ff','#3fb950','#e3b341','#f85149','#a371f7','#ffa657','#79c0ff','#56d364','#ff7b72','#d2a8ff'];
var pieCharts = {};
var cmpA = null, cmpB = null, secChart = null;

var GURUS = [
  {id:'buffett',name:'워런 버핏',firm:'Berkshire Hathaway',aum:'$3,620억',av:'WB',ac:'#1f3d6b',tc:'#58a6ff',
   labels:['AAPL','BAC','AXP','KO','CVX','OXY','MCO','KHC','기타'],data:[43,10,9,8,6,5,4,3,12],
   sectors:{금융:28,소비재:22,에너지:18,기술:16,헬스케어:10,기타:6}},
  {id:'dalio',name:'레이 달리오',firm:'Bridgewater Associates',aum:'$1,240억',av:'RD',ac:'#1f3d2b',tc:'#3fb950',
   labels:['SPY','GLD','IVV','EEM','VWO','TLT','기타'],data:[18,15,14,12,10,8,23],
   sectors:{ETF:42,귀금속:15,신흥국:22,채권:15,기타:6}},
  {id:'burry',name:'마이클 버리',firm:'Scion Asset Mgmt',aum:'$1.7억',av:'MB',ac:'#3d1f2b',tc:'#f85149',
   labels:['HUM','HIMS','BIDU','JD','REAL','기타'],data:[22,18,16,15,12,17],
   sectors:{헬스케어:22,기술:16,소비재:18,금융:12,기타:32}},
  {id:'wood',name:'캐시 우드',firm:'ARK Invest',aum:'$93억',av:'CW',ac:'#2b2b1f',tc:'#e3b341',
   labels:['TSLA','ROKU','COIN','CRSP','PATH','ZM','기타'],data:[10,8,8,7,6,5,56],
   sectors:{기술:55,헬스케어:12,소비재:8,금융:10,기타:15}},
  {id:'lynch',name:'피터 린치',firm:'Fidelity Magellan',aum:'(은퇴)',av:'PL',ac:'#2b1f3d',tc:'#a371f7',
   labels:['F','GE','MCD','기타'],data:[20,18,14,48],
   sectors:{소비재:30,금융:20,산업재:22,기타:28}},
  {id:'simons',name:'짐 사이먼스',firm:'Renaissance Tech',aum:'$550억',av:'JS',ac:'#1f2b3d',tc:'#79c0ff',
   labels:['IWM','SPY','QQQ','기타'],data:[12,11,10,67],
   sectors:{ETF:33,헬스케어:15,기술:20,기타:32}},
  {id:'ackman',name:'빌 애크만',firm:'Pershing Square',aum:'$160억',av:'BA',ac:'#1f3d35',tc:'#56d364',
   labels:['HLT','CMG','CP','GOOGL','기타'],data:[24,20,18,16,22],
   sectors:{소비재:28,기술:20,교통:18,기타:34}},
  {id:'icahn',name:'칼 아이칸',firm:'Icahn Enterprises',aum:'$180억',av:'CI',ac:'#3d2b1f',tc:'#ffa657',
   labels:['IEP','CVX','WBD','기타'],data:[30,22,15,33],
   sectors:{에너지:34,미디어:18,금융:14,기타:34}},
  {id:'tepper',name:'데이비드 테퍼',firm:'Appaloosa Mgmt',aum:'$60억',av:'DT',ac:'#3d1f1f',tc:'#ff7b72',
   labels:['META','GOOGL','AMZN','MSFT','기타'],data:[22,20,18,15,25],
   sectors:{기술:75,소비재:12,기타:13}},
  {id:'druckenmiller',name:'스탠리 드러켄밀러',firm:'Duquesne Family',aum:'$30억',av:'SD',ac:'#1f2b1f',tc:'#d2a8ff',
   labels:['MSFT','NVDA','META','기타'],data:[20,18,16,46],
   sectors:{기술:68,에너지:10,소비재:10,기타:12}}
];

var NPS_PIE = {labels:['해외주식','국내주식','채권','대체투자','단기자금'],data:[35,15,35,11,4]};

var NPS_DATA = {};
NPS_DATA['2026-11013'] = [
  {corp:'삼성전자',qty:'835,201,300',pct:'13.79'},
  {corp:'SK하이닉스',qty:'93,812,400',pct:'11.98'},
  {corp:'삼성바이오로직스',qty:'7,520,100',pct:'10.36'},
  {corp:'LG에너지솔루션',qty:'17,301,200',pct:'7.63'},
  {corp:'현대차',qty:'25,102,800',pct:'10.96'},
  {corp:'KB금융',qty:'27,413,500',pct:'12.52'},
  {corp:'셀트리온',qty:'17,821,300',pct:'11.05'},
  {corp:'POSCO홀딩스',qty:'10,612,700',pct:'12.74'}
];
NPS_DATA['2025-11011'] = [
  {corp:'삼성전자',qty:'831,540,200',pct:'13.73'},
  {corp:'SK하이닉스',qty:'92,301,800',pct:'11.79'},
  {corp:'삼성바이오로직스',qty:'7,420,300',pct:'10.22'},
  {corp:'LG에너지솔루션',qty:'17,012,400',pct:'7.50'},
  {corp:'현대차',qty:'24,801,600',pct:'10.83'},
  {corp:'KB금융',qty:'27,012,100',pct:'12.34'},
  {corp:'셀트리온',qty:'17,401,200',pct:'10.79'},
  {corp:'POSCO홀딩스',qty:'10,401,500',pct:'12.49'}
];
NPS_DATA['2025-11014'] = [
  {corp:'삼성전자',qty:'829,103,500',pct:'13.69'},
  {corp:'SK하이닉스',qty:'91,502,300',pct:'11.69'},
  {corp:'삼성바이오로직스',qty:'7,350,100',pct:'10.13'},
  {corp:'LG에너지솔루션',qty:'16,820,300',pct:'7.41'},
  {corp:'현대차',qty:'24,601,200',pct:'10.74'},
  {corp:'KB금융',qty:'26,801,400',pct:'12.24'},
  {corp:'셀트리온',qty:'17,201,800',pct:'10.67'},
  {corp:'POSCO홀딩스',qty:'10,302,100',pct:'12.37'}
];
NPS_DATA['2025-11012'] = [
  {corp:'삼성전자',qty:'827,210,100',pct:'13.66'},
  {corp:'SK하이닉스',qty:'90,812,700',pct:'11.60'},
  {corp:'삼성바이오로직스',qty:'7,280,500',pct:'10.03'},
  {corp:'LG에너지솔루션',qty:'16,640,100',pct:'7.33'},
  {corp:'현대차',qty:'24,401,000',pct:'10.65'},
  {corp:'KB금융',qty:'26,601,200',pct:'12.15'},
  {corp:'셀트리온',qty:'17,001,400',pct:'10.54'},
  {corp:'POSCO홀딩스',qty:'10,201,300',pct:'12.25'}
];
NPS_DATA['2025-11013'] = [
  {corp:'삼성전자',qty:'824,501,800',pct:'13.61'},
  {corp:'SK하이닉스',qty:'90,102,100',pct:'11.51'},
  {corp:'삼성바이오로직스',qty:'7,210,200',pct:'9.93'},
  {corp:'LG에너지솔루션',qty:'16,450,800',pct:'7.25'},
  {corp:'현대차',qty:'24,201,400',pct:'10.57'},
  {corp:'KB금융',qty:'26,401,600',pct:'12.06'},
  {corp:'셀트리온',qty:'16,801,600',pct:'10.42'},
  {corp:'POSCO홀딩스',qty:'10,101,900',pct:'12.13'}
];
NPS_DATA['2024-11011'] = [
  {corp:'삼성전자',qty:'822,007,452',pct:'13.57'},
  {corp:'SK하이닉스',qty:'89,401,566',pct:'11.42'},
  {corp:'LG에너지솔루션',qty:'16,523,417',pct:'7.28'},
  {corp:'삼성바이오로직스',qty:'7,131,214',pct:'9.82'},
  {corp:'현대차',qty:'24,301,849',pct:'10.61'},
  {corp:'POSCO홀딩스',qty:'10,287,342',pct:'12.35'},
  {corp:'셀트리온',qty:'16,482,719',pct:'10.22'},
  {corp:'KB금융',qty:'25,918,347',pct:'11.84'}
];
NPS_DATA['2024-11014'] = [
  {corp:'삼성전자',qty:'820,112,340',pct:'13.54'},
  {corp:'SK하이닉스',qty:'88,201,100',pct:'11.28'},
  {corp:'LG에너지솔루션',qty:'16,100,200',pct:'7.10'},
  {corp:'삼성바이오로직스',qty:'7,050,000',pct:'9.71'},
  {corp:'현대차',qty:'24,100,000',pct:'10.52'},
  {corp:'POSCO홀딩스',qty:'10,100,000',pct:'12.12'},
  {corp:'셀트리온',qty:'16,200,000',pct:'10.05'},
  {corp:'KB금융',qty:'25,500,000',pct:'11.65'}
];
NPS_DATA['2024-11012'] = [
  {corp:'삼성전자',qty:'815,432,100',pct:'13.46'},
  {corp:'SK하이닉스',qty:'86,500,000',pct:'11.05'},
  {corp:'LG에너지솔루션',qty:'15,800,000',pct:'6.96'},
  {corp:'삼성바이오로직스',qty:'6,980,000',pct:'9.61'},
  {corp:'현대차',qty:'23,800,000',pct:'10.38'},
  {corp:'POSCO홀딩스',qty:'9,900,000',pct:'11.88'},
  {corp:'셀트리온',qty:'15,900,000',pct:'9.87'},
  {corp:'KB금융',qty:'25,100,000',pct:'11.47'}
];
NPS_DATA['2024-11013'] = [
  {corp:'삼성전자',qty:'812,001,200',pct:'13.40'},
  {corp:'SK하이닉스',qty:'85,300,000',pct:'10.90'},
  {corp:'LG에너지솔루션',qty:'15,500,000',pct:'6.83'},
  {corp:'삼성바이오로직스',qty:'6,900,000',pct:'9.50'},
  {corp:'현대차',qty:'23,500,000',pct:'10.25'},
  {corp:'POSCO홀딩스',qty:'9,700,000',pct:'11.64'},
  {corp:'셀트리온',qty:'15,600,000',pct:'9.68'},
  {corp:'KB금융',qty:'24,800,000',pct:'11.33'}
];
NPS_DATA['2023-11011'] = [
  {corp:'삼성전자',qty:'805,321,400',pct:'13.28'},
  {corp:'SK하이닉스',qty:'83,100,000',pct:'10.62'},
  {corp:'LG에너지솔루션',qty:'15,200,000',pct:'6.70'},
  {corp:'삼성바이오로직스',qty:'6,820,000',pct:'9.39'},
  {corp:'현대차',qty:'23,200,000',pct:'10.12'},
  {corp:'POSCO홀딩스',qty:'9,500,000',pct:'11.40'},
  {corp:'셀트리온',qty:'15,300,000',pct:'9.49'},
  {corp:'KB금융',qty:'24,500,000',pct:'11.18'}
];
NPS_DATA['2023-11014'] = [
  {corp:'삼성전자',qty:'800,000,000',pct:'13.20'},
  {corp:'SK하이닉스',qty:'81,000,000',pct:'10.35'},
  {corp:'LG에너지솔루션',qty:'14,900,000',pct:'6.57'},
  {corp:'삼성바이오로직스',qty:'6,730,000',pct:'9.27'},
  {corp:'현대차',qty:'22,900,000',pct:'9.99'},
  {corp:'POSCO홀딩스',qty:'9,300,000',pct:'11.16'},
  {corp:'셀트리온',qty:'15,000,000',pct:'9.31'},
  {corp:'KB금융',qty:'24,100,000',pct:'11.01'}
];
NPS_DATA['2023-11012'] = [
  {corp:'삼성전자',qty:'795,000,000',pct:'13.12'},
  {corp:'SK하이닉스',qty:'79,500,000',pct:'10.16'},
  {corp:'LG에너지솔루션',qty:'14,600,000',pct:'6.43'},
  {corp:'삼성바이오로직스',qty:'6,640,000',pct:'9.15'},
  {corp:'현대차',qty:'22,600,000',pct:'9.86'},
  {corp:'POSCO홀딩스',qty:'9,100,000',pct:'10.92'},
  {corp:'셀트리온',qty:'14,700,000',pct:'9.12'},
  {corp:'KB금융',qty:'23,700,000',pct:'10.83'}
];
NPS_DATA['2023-11013'] = [
  {corp:'삼성전자',qty:'790,000,000',pct:'13.04'},
  {corp:'SK하이닉스',qty:'78,000,000',pct:'9.97'},
  {corp:'LG에너지솔루션',qty:'14,300,000',pct:'6.30'},
  {corp:'삼성바이오로직스',qty:'6,550,000',pct:'9.03'},
  {corp:'현대차',qty:'22,300,000',pct:'9.73'},
  {corp:'POSCO홀딩스',qty:'8,900,000',pct:'10.68'},
  {corp:'셀트리온',qty:'14,400,000',pct:'8.94'},
  {corp:'KB금융',qty:'23,300,000',pct:'10.65'}
];

// ── Finnhub ────────────────────────────────────────────────────
function fhGet(path) {
  return fetch(FH + path + '&token=' + FH_KEY).then(function(r) { return r.json(); });
}

function saveAndReload() {
  FH_KEY = document.getElementById('fhKeyInput').value.trim();
  document.getElementById('keyStatus').textContent = '저장됨';
  loadMarket();
}

function testConn() {
  var el = document.getElementById('testResult');
  el.style.display = 'block';
  el.style.background = '#21262d';
  el.style.color = '#8b949e';
  el.textContent = '연결 테스트 중...';
  fhGet('/quote?symbol=AAPL').then(function(d) {
    if (d.c && d.c > 0) {
      el.style.background = '#1f3d2b'; el.style.color = '#3fb950';
      el.textContent = '연결 성공! AAPL 현재가: $' + d.c.toFixed(2);
      loadMarket();
    } else {
      el.style.background = '#3d1f2b'; el.style.color = '#f85149';
      el.textContent = '응답 오류: ' + JSON.stringify(d).substring(0, 100);
    }
  }).catch(function(e) {
    el.style.background = '#3d1f2b'; el.style.color = '#f85149';
    el.textContent = '네트워크 오류: ' + e.message;
  });
}

// ── Market ─────────────────────────────────────────────────────
var IDX = [
  {sym:'QQQ', vId:'vNQ', cId:'cNQ'},
  {sym:'SPY', vId:'vSP', cId:'cSP'},
  {sym:'EWY', vId:'vKS', cId:'cKS'},
  {sym:'VIXY',vId:'vVX', cId:'cVX'}
];
var WATCH = ['AAPL','MSFT','NVDA','TSLA','GOOGL','META','AMZN'];

function loadMarket() {
  IDX.forEach(function(idx) {
    fhGet('/quote?symbol=' + idx.sym).then(function(d) {
      if (!d.c || d.c === 0) return;
      var pct = (d.c - d.pc) / d.pc * 100;
      var up = pct >= 0;
      document.getElementById(idx.vId).textContent = '$' + d.c.toFixed(2);
      var el = document.getElementById(idx.cId);
      el.textContent = (up ? '▲ +' : '▼ ') + pct.toFixed(2) + '%';
      el.className = 'chg ' + (up ? 'up' : 'dn');
    }).catch(function() {});
  });

  var loadEl = document.getElementById('quoteLoading');
  var tableEl = document.getElementById('quoteTable');
  var errEl = document.getElementById('quoteErr');
  loadEl.style.display = 'flex';
  tableEl.style.display = 'none';
  errEl.style.display = 'none';

  Promise.all(WATCH.map(function(s) {
    return fhGet('/quote?symbol=' + s).then(function(d) {
      if (!d.c || d.c === 0) return null;
      var chgAmt = d.c - d.pc;
      var chgPct = chgAmt / d.pc * 100;
      return {sym:s, price:d.c.toFixed(2), chgAmt:chgAmt.toFixed(2), chgPct:chgPct.toFixed(2), high:d.h.toFixed(2), low:d.l.toFixed(2), pc:d.pc.toFixed(2)};
    }).catch(function() { return null; });
  })).then(function(results) {
    loadEl.style.display = 'none';
    var valid = results.filter(function(r) { return r !== null; });
    if (valid.length === 0) {
      errEl.textContent = '시세를 불러오지 못했습니다. 연결 테스트를 확인하세요.';
      errEl.style.display = 'block';
      return;
    }
    tableEl.style.display = 'block';
    document.getElementById('quoteTbody').innerHTML = valid.map(function(q) {
      var up = parseFloat(q.chgPct) >= 0;
      var cls = up ? 'up' : 'dn';
      var sign = up ? '+' : '';
      return '<tr><td style="font-weight:600">' + q.sym + '</td><td>$' + q.price + '</td><td class="' + cls + '">' + sign + q.chgAmt + '</td><td class="' + cls + '">' + sign + q.chgPct + '%</td><td>$' + q.high + '</td><td>$' + q.low + '</td><td style="color:#8b949e">$' + q.pc + '</td></tr>';
    }).join('');
  });
}

// ── 국민연금 ───────────────────────────────────────────────────
function loadNps() {
  var year = document.getElementById('npsYear').value;
  var reprt = document.getElementById('npsQuarter').value;
  var sel = document.getElementById('npsQuarter');
  var qLabel = sel.options[sel.selectedIndex].text;
  document.getElementById('npsTableTitle').textContent = year + '년 ' + qLabel + ' 상위 보유 종목';
  document.getElementById('npsErr').style.display = 'none';
  var key = year + '-' + reprt;
  var list = NPS_DATA[key];
  if (list) {
    document.getElementById('npsBadge').textContent = '공시 데이터';
    document.getElementById('npsBadge').className = 'badge badge-live';
    document.getElementById('npsBody').innerHTML = list.map(function(r) {
      return '<tr><td>' + r.corp + '</td><td>' + r.qty + '</td><td>' + r.pct + '%</td></tr>';
    }).join('');
  } else {
    document.getElementById('npsBadge').textContent = '데이터 없음';
    document.getElementById('npsBadge').className = 'badge badge-sample';
    document.getElementById('npsErr').textContent = '해당 분기 데이터가 없습니다. (미공시 또는 준비 중)';
    document.getElementById('npsErr').style.display = 'block';
    document.getElementById('npsBody').innerHTML = '';
  }
}

// ── 파이차트 ───────────────────────────────────────────────────
function makePie(id, labels, data, colors) {
  var ctx = document.getElementById(id);
  if (!ctx) return;
  if (pieCharts[id]) { pieCharts[id].destroy(); }
  pieCharts[id] = new Chart(ctx, {
    type: 'doughnut',
    data: {labels:labels, datasets:[{data:data, backgroundColor:colors.slice(0,data.length), borderWidth:2, borderColor:'#161b22'}]},
    options: {responsive:true, maintainAspectRatio:false, plugins:{legend:{display:false}, tooltip:{callbacks:{label:function(i){return i.label+': '+i.parsed+'%';}}}}, cutout:'55%'}
  });
}

function makeLeg(id, labels, data, colors) {
  var el = document.getElementById(id);
  if (!el) return;
  el.innerHTML = labels.map(function(l,i) {
    return '<span class="litem"><span class="ldot" style="background:'+colors[i%colors.length]+'"></span>'+l+' '+data[i]+'%</span>';
  }).join('');
}

function initGurus() {
  var grid = document.getElementById('guruGrid');
  if (grid.dataset.built) return;
  grid.dataset.built = '1';
  grid.innerHTML = GURUS.map(function(g) {
    return '<div class="gcard"><div class="ghdr"><div class="gav" style="background:'+g.ac+';color:'+g.tc+'">'+g.av+'</div><div><div class="gname">'+g.name+'</div><div class="gaum">'+g.firm+' · '+g.aum+'</div></div></div><div class="pcont"><canvas id="pie_'+g.id+'"></canvas></div><div class="leg" id="leg_'+g.id+'"></div></div>';
  }).join('');
  setTimeout(function() {
    GURUS.forEach(function(g) {
      makePie('pie_'+g.id, g.labels, g.data, C);
      makeLeg('leg_'+g.id, g.labels, g.data, C);
    });
  }, 60);
}

function initNPS() {
  if (document.getElementById('npsPie')._built) return;
  document.getElementById('npsPie')._built = true;
  makePie('npsPie', NPS_PIE.labels, NPS_PIE.data, C);
  makeLeg('npsLeg', NPS_PIE.labels, NPS_PIE.data, C);
}

// ── 비교 분석 ──────────────────────────────────────────────────
function populateSelects() {
  var opts = GURUS.map(function(g) { return '<option value="'+g.id+'">'+g.name+'</option>'; }).join('');
  document.getElementById('cmpA').innerHTML = opts;
  document.getElementById('cmpB').innerHTML = opts;
  document.getElementById('cmpB').value = 'dalio';
}

function renderCompare() {
  var va = document.getElementById('cmpA').value;
  var vb = document.getElementById('cmpB').value;
  var da = GURUS.find(function(g) { return g.id === va; });
  var db = GURUS.find(function(g) { return g.id === vb; });
  document.getElementById('cmpTitleA').textContent = da.name + ' (' + da.firm + ')';
  document.getElementById('cmpTitleB').textContent = db.name + ' (' + db.firm + ')';
  if (cmpA) cmpA.destroy();
  if (cmpB) cmpB.destroy();
  cmpA = new Chart(document.getElementById('cmpPieA'), {type:'doughnut', data:{labels:da.labels, datasets:[{data:da.data, backgroundColor:C.slice(0,da.data.length), borderWidth:2, borderColor:'#161b22'}]}, options:{responsive:true, maintainAspectRatio:false, plugins:{legend:{display:false}}, cutout:'55%'}});
  cmpB = new Chart(document.getElementById('cmpPieB'), {type:'doughnut', data:{labels:db.labels, datasets:[{data:db.data, backgroundColor:C.slice(0,db.data.length), borderWidth:2, borderColor:'#161b22'}]}, options:{responsive:true, maintainAspectRatio:false, plugins:{legend:{display:false}}, cutout:'55%'}});
  function mkBars(elId, d) {
    document.getElementById(elId).innerHTML = d.labels.slice(0,5).map(function(l,i) {
      return '<div class="hrow"><span class="hname">'+l+'</span><div class="hbwrap"><div class="hbar" style="width:'+d.data[i]+'%;background:'+C[i%C.length]+'"></div></div><span class="hpct" style="color:'+C[i%C.length]+'">'+d.data[i]+'%</span></div>';
    }).join('');
  }
  mkBars('cmpBarsA', da);
  mkBars('cmpBarsB', db);
  var sa = da.sectors, sb = db.sectors;
  var keys = Object.keys(Object.assign({}, sa, sb));
  if (secChart) secChart.destroy();
  secChart = new Chart(document.getElementById('sectorChart'), {
    type:'bar',
    data:{labels:keys, datasets:[
      {label:da.name, data:keys.map(function(k){return sa[k]||0;}), backgroundColor:'#58a6ff55', borderColor:'#58a6ff', borderWidth:1},
      {label:db.name, data:keys.map(function(k){return sb[k]||0;}), backgroundColor:'#3fb95055', borderColor:'#3fb950', borderWidth:1}
    ]},
    options:{responsive:true, maintainAspectRatio:false, plugins:{legend:{labels:{color:'#8b949e', font:{size:11}}}}, scales:{x:{ticks:{color:'#8b949e'}, grid:{color:'#21262d'}}, y:{ticks:{color:'#8b949e', callback:function(v){return v+'%';}}, grid:{color:'#21262d'}, max:80}}}
  });
}

function showPage(id, el) {
  document.querySelectorAll('.page').forEach(function(p) { p.classList.remove('active'); });
  document.querySelectorAll('.tab').forEach(function(t) { t.classList.remove('active'); });
  document.getElementById(id).classList.add('active');
  el.classList.add('active');
  if (id === 'portfolio') initGurus();
  if (id === 'nps') { initNPS(); loadNps(); }
  if (id === 'compare') renderCompare();
}

populateSelects();
loadMarket();
</script>
</body>
</html>
