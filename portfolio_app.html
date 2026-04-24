<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>슝슝이도 워렌버핏</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
/* 1. 모바일 다크모드 및 시스템 색상 고정 */
:root {
  color-scheme: dark;
}

*{box-sizing:border-box;margin:0;padding:0}

/* 2. 배경과 카드의 대비를 높여 색상 차이 명확화 */
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  background: #010409; /* 더 깊은 검정으로 변경 */
  color: #e6edf3;
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
}

/* 네비게이션 및 카드 배경색 통일 및 테두리 강화 */
nav {
  background: #0d1117;
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
.tab.active{color:#e6edf3;border-bottom-color:#f78166;font-weight:600}

.container{max-width:1100px;margin:0 auto;padding:24px 16px}
.page{display:none}
.page.active{display:block}

/* 카드 디자인 개선 */
.mcard, .cwrap, .gcard, .ccard {
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 16px;
  margin-bottom: 16px;
}

h2{font-size:18px;margin-bottom:12px;font-weight:600}
.desc{font-size:13px;color:#8b949e;margin-bottom:20px;line-height:1.5}

/* 모바일 입력창(Select) 스타일 최적화 */
.cg{display:flex;gap:12px;margin-bottom:20px;flex-wrap:wrap}
.cg select{
  background:#161b22;
  color:#e6edf3;
  border:1px solid #30363d;
  padding:6px 12px;
  border-radius:6px;
  font-size:14px;
  outline:none;
  -webkit-appearance: none; /* 아이폰 기본 스타일 제거 */
  min-width: 120px;
}

.btn-blue{background:#238636;color:#fff;border:1px solid rgba(240,246,252,0.1);padding:6px 12px;border-radius:6px;font-size:14px;font-weight:500;cursor:pointer}
.btn-blue:hover{background:#2ea043}
.btn-yellow{background:#afb8c11f;color:#e6edf3;border:1px solid #30363d;padding:6px 12px;border-radius:6px;font-size:14px;cursor:pointer;margin-left:8px}

/* 비교 바 디자인 */
.comp-row{display:flex;align-items:center;margin-bottom:10px}
.cname{width:100px;font-size:12px;color:#8b949e;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.cbar-bg{flex:1;height:8px;background:#21262d;border-radius:4px;margin:0 10px;overflow:hidden}
.cbar-fill{height:100%;border-radius:4px;transition:width 0.4s ease}
.hpct{width:40px;font-size:11px;font-weight:600;text-align:right}

.chart-h{height:280px;margin-top:10px}
@media (max-width:600px){
  .tab{padding:10px 8px;font-size:12px}
  .logo{margin-right:12px}
  .chart-h{height:220px}
}
</style>
</head>
<body>

<nav>
  <div class="logo">슝슝이<span>워렌버핏</span></div>
  <div class="nav-tabs">
    <div class="tab active" onclick="showPage('compare', this)">포트폴리오 비교</div>
    <div class="tab" onclick="showPage('guide', this)">투자 가이드</div>
  </div>
</nav>

<div class="container">
  <div id="compare" class="page active">
    <div class="mcard">
      <h2>두 포트폴리오 비교</h2>
      <p class="desc">슝슝이가 분석한 워렌 버핏과 한국 고배당 전략의 차이를 확인해보세요.</p>
      <div class="cg">
        <select id="selA">
          <option value="buffett">워렌 버핏 (Berkshire)</option>
          <option value="k-high">한국 고배당주</option>
          <option value="nasdaq">나스닥 100</option>
        </select>
        <span style="align-self:center;color:#8b949e;font-size:14px">VS</span>
        <select id="selB">
          <option value="k-high">한국 고배당주</option>
          <option value="buffett">워렌 버핏 (Berkshire)</option>
          <option value="nasdaq">나스닥 100</option>
        </select>
        <button class="btn-blue" onclick="runCompare()">분석하기</button>
      </div>
    </div>

    <div class="cwrap">
      <h3 style="font-size:14px;margin-bottom:15px">상위 보유 종목 비중 (%)</h3>
      <div id="compBarsA"></div>
      <div style="height:1px;background:#30363d;margin:20px 0"></div>
      <div id="compBarsB"></div>
    </div>

    <div class="gcard">
      <h3 style="font-size:14px;margin-bottom:10px">산업 섹터 분포</h3>
      <div class="chart-h">
        <canvas id="sectorChart"></canvas>
      </div>
    </div>
  </div>

  <div id="guide" class="page">
    <div class="ccard">
      <h2>워렌 버핏의 투자 원칙</h2>
      <p class="desc" style="margin-bottom:10px">1. 절대로 돈을 잃지 마라.<br>2. 첫 번째 규칙을 절대 잊지 마라.</p>
      <p style="font-size:13px;line-height:1.6;color:#8b949e">
        슝슝이가 추천하는 초보 투자자 가이드입니다. 복리의 마법을 믿고 우량한 자산에 장기 투자하세요.
      </p>
    </div>
  </div>
</div>

<script>
var data = {
  'buffett': { name:'버핏', stocks:['Apple','BofA','Amex','CocaCola','Chevron'], data:[42,10,9,7,6], sectors:{'IT':45, '금융':25, '에너지':12, '소비재':18} },
  'k-high': { name:'K-고배당', stocks:['삼성전자','현대차','KB금융','신한지주','POSCO'], data:[25,15,12,10,8], sectors:{'IT':25, '제조':30, '금융':35, '철강':10} },
  'nasdaq': { name:'나스닥', stocks:['MSFT','Apple','Nvidia','Amazon','Meta'], data:[12,11,8,6,5], sectors:{'IT':60, '통신':15, '소비재':15, '기타':10} }
};

var C = ['#58a6ff', '#3fb950', '#d29922', '#bc8cff', '#f85149'];
var secChart = null;

function runCompare() {
  var a = document.getElementById('selA').value;
  var b = document.getElementById('selB').value;
  var da = data[a], db = data[b];

  function mkBars(id, d) {
    var h = '<div style="font-size:12px;font-weight:600;margin-bottom:8px;color:#e6edf3">'+d.name+'</div>';
    document.getElementById(id).innerHTML = h + d.stocks.map(function(s,i){
      return '<div class="comp-row"><div class="cname">'+s+'</div><div class="cbar-bg"><div class="cbar-fill" style="width:'+d.data[i]+'%;background:'+C[i%C.length]+'"></div></div><span class="hpct" style="color:'+C[i%C.length]+'">'+d.data[i]+'%</span></div>';
    }).join('');
  }
  mkBars('compBarsA', da);
  mkBars('compBarsB', db);

  var sa = da.sectors, sb = db.sectors;
  var keys = Object.keys(Object.assign({}, sa, sb));
  if (secChart) secChart.destroy();
  secChart = new Chart(document.getElementById('sectorChart'), {
    type:'bar',
    data:{labels:keys, datasets:[
      {label:da.name, data:keys.map(function(k){return sa[k]||0;}), backgroundColor:'#58a6ff55', borderColor:'#58a6ff', borderWidth:1},
      {label:db.name, data:keys.map(function(k){return sb[k]||0;}), backgroundColor:'#3fb95055', borderColor:'#3fb950', borderWidth:1}
    ]},
    options:{
      responsive:true, 
      maintainAspectRatio:false, 
      plugins:{legend:{labels:{color:'#8b949e', font:{size:11}}}}, 
      scales:{
        x:{ticks:{color:'#8b949e'}, grid:{color:'#21262d'}}, 
        y:{ticks:{color:'#8b949e', callback:function(v){return v+'%';}}, grid:{color:'#21262d'}, max:80}
      }
    }
  });
}

function showPage(id, el) {
  document.querySelectorAll('.page').forEach(function(p){p.classList.remove('active')});
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.tab').forEach(function(t){t.classList.remove('active')});
  el.classList.add('active');
  if(id==='compare') runCompare();
}

window.onload = function(){ runCompare(); };
</script>

</body>
</html>
