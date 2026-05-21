[index.html](https://github.com/user-attachments/files/28079644/index.html)
<!DOCTYPE html>
<!-- saved from url=(0046)file:///C:/Users/dleft/Downloads/bass-log.html -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Bass Log">
<meta name="theme-color" content="#0a1628">
<title>Bass Log</title>
<link rel="stylesheet" href="./Bass Log_files/leaflet.min.css">
<style>
:root{--bg:#0a1628;--bg2:#0d2040;--bg3:#0f2035;--acc:#7dd3fc;--acc2:#1d6fa8;--acc3:#1d3a5c;--txt:#e8f4fd;--txt2:#c9e8ff;--muted:#4a7a9a;--border:rgba(56,140,220,0.2);}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent;}
html,body{height:100%;background:#000;font-family:-apple-system,BlinkMacSystemFont,'SF Pro Text',sans-serif;}
body{display:flex;justify-content:center;align-items:flex-start;}
.app{width:100%;max-width:430px;min-height:100dvh;background:var(--bg);color:var(--txt);display:flex;flex-direction:column;position:relative;overflow:hidden;}
/* HEADER */
.hdr{background:var(--bg2);padding:env(safe-area-inset-top,12px) 16px 12px;border-bottom:0.5px solid var(--border);flex-shrink:0;}
.hdr-row{display:flex;align-items:center;justify-content:space-between;}
.app-title{font-size:20px;font-weight:700;color:var(--acc);letter-spacing:-0.5px;}
.app-sub{font-size:11px;color:var(--muted);margin-top:1px;}
.add-btn{background:var(--acc2);color:#e0f2ff;border:none;border-radius:50%;width:34px;height:34px;font-size:20px;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;}
/* TABS */
.tabs{display:flex;gap:3px;padding:8px 12px;background:var(--bg);border-bottom:0.5px solid rgba(56,140,220,0.1);flex-shrink:0;}
.tab{flex:1;text-align:center;padding:7px 3px;border-radius:8px;font-size:12px;cursor:pointer;color:var(--muted);border:none;background:none;font-family:inherit;}
.tab.active{background:var(--acc3);color:var(--acc);font-weight:600;}
/* SCROLL AREA */
.scroll{flex:1;overflow-y:auto;-webkit-overflow-scrolling:touch;padding:12px 14px 80px;}
.screen{display:none;}
.screen.on{display:block;}
.slabel{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:0.08em;margin:12px 0 6px;}
/* CARDS */
.card{background:var(--bg3);border:0.5px solid var(--border);border-radius:14px;padding:12px;margin-bottom:8px;}
.fish-row{display:flex;gap:10px;align-items:flex-start;}
.fish-ico{width:38px;height:38px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0;}
.fish-name{font-size:14px;font-weight:600;color:var(--txt2);}
.fish-meta{font-size:11px;color:var(--muted);margin-top:2px;}
.tag-row{display:flex;flex-wrap:wrap;gap:3px;margin-top:5px;}
.tag{font-size:10px;padding:2px 7px;border-radius:20px;}
.tb{background:#1d3a5c;color:#7dd3fc;}
.tg{background:#1a3320;color:#6ee7b7;}
.ta{background:#2d2010;color:#fcd34d;}
.tr{background:#3a1520;color:#f87171;}
/* STATS GRID */
.stat2{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:10px;}
.stat-cell{background:var(--bg3);border:0.5px solid var(--border);border-radius:12px;padding:12px;}
.stat-v{font-size:22px;font-weight:700;color:var(--acc);}
.stat-l{font-size:11px;color:var(--muted);margin-top:2px;}
/* MAP */
#map{height:260px;width:100%;border-radius:12px;}
.map-wrap{border-radius:12px;overflow:hidden;border:0.5px solid var(--border);position:relative;}
.map-row{display:flex;gap:5px;margin-bottom:8px;}
.mBtn{flex:1;padding:8px 4px;border-radius:9px;border:0.5px solid rgba(56,140,220,0.3);background:var(--bg3);color:#7aafcc;font-size:11px;cursor:pointer;text-align:center;font-family:inherit;}
.mBtn.on{background:var(--acc3);color:var(--acc);border-color:var(--acc2);}
.place-banner{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);z-index:1000;background:rgba(29,111,168,0.95);color:white;padding:10px 18px;border-radius:20px;font-size:12px;text-align:center;line-height:1.6;pointer-events:none;}
.leaflet-popup-content-wrapper{background:var(--bg3);border:0.5px solid rgba(125,211,252,0.4);border-radius:10px;color:var(--txt);box-shadow:0 4px 20px rgba(0,0,0,0.6);}
.leaflet-popup-tip{background:var(--bg3);}
.leaflet-popup-content{margin:10px 13px;font-size:12px;line-height:1.6;min-width:150px;font-family:-apple-system,sans-serif;}
.pname{font-size:13px;font-weight:600;color:var(--acc);margin-bottom:5px;}
.prow{display:flex;justify-content:space-between;margin-bottom:2px;}
.pm{color:var(--muted);}
/* MOON */
.moon-panel{display:flex;gap:14px;align-items:center;background:var(--bg3);border:0.5px solid var(--border);border-radius:14px;padding:16px;margin-bottom:10px;}
.moon-info h3{font-size:16px;font-weight:600;color:var(--txt2);}
.moon-info p{font-size:12px;color:var(--muted);margin-top:2px;}
.rating-pill{display:inline-block;font-size:12px;padding:4px 12px;border-radius:20px;margin-top:7px;font-weight:500;}
.sol-row{display:flex;align-items:center;gap:8px;padding:9px 12px;background:var(--bg3);border:0.5px solid var(--border);border-radius:11px;margin-bottom:5px;}
.sol-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0;}
.sol-type{font-size:12px;font-weight:600;min-width:46px;color:var(--txt2);}
.sol-t{font-size:12px;color:var(--acc);flex:1;}
.sol-str{font-size:10px;color:var(--muted);}
.timeline-wrap{background:var(--bg3);border:0.5px solid var(--border);border-radius:11px;padding:11px;margin-bottom:8px;}
.tl-labels{display:flex;justify-content:space-between;font-size:9px;color:var(--muted);margin-bottom:5px;}
/* SESSIONS */
.sess-card{background:var(--bg3);border:0.5px solid var(--border);border-radius:14px;padding:12px;margin-bottom:8px;}
.sess-hdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
.sess-date{font-size:13px;font-weight:600;color:var(--txt2);}
.best-badge{font-size:10px;padding:2px 8px;border-radius:20px;background:#2d2010;color:#fcd34d;}
.stat3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:5px;}
.sc{text-align:center;background:var(--bg);border-radius:8px;padding:7px 4px;}
.sv{font-size:15px;font-weight:700;color:var(--acc);}
.sl{font-size:9px;color:var(--muted);margin-top:1px;}
.bar-wrap{height:4px;background:var(--bg);border-radius:4px;overflow:hidden;margin-top:2px;}
.bar-fill{height:100%;border-radius:4px;}
/* OVERLAYS */
.overlay{position:absolute;inset:0;background:#070f1e;overflow-y:auto;-webkit-overflow-scrolling:touch;padding:env(safe-area-inset-top,12px) 14px 40px;z-index:60;display:none;}
.overlay.on{display:block;}
.ov-hdr{display:flex;align-items:center;gap:10px;margin-bottom:18px;}
.back{background:var(--acc3);border:none;color:var(--acc);border-radius:9px;width:34px;height:34px;font-size:16px;cursor:pointer;display:flex;align-items:center;justify-content:center;font-family:inherit;}
.ov-title{font-size:17px;font-weight:600;color:var(--txt2);}
.fg{margin-bottom:12px;}
.fl{font-size:11px;color:var(--muted);margin-bottom:4px;display:block;}
.fi{width:100%;background:var(--bg3);border:0.5px solid rgba(56,140,220,0.35);border-radius:11px;padding:11px 13px;color:var(--txt);font-size:14px;font-family:inherit;outline:none;-webkit-appearance:none;appearance:none;}
.fi:focus{border-color:var(--acc2);}
.fi::placeholder{color:#3a5570;}
.r2{display:grid;grid-template-columns:1fr 1fr;gap:9px;}
.spec-grid{display:grid;grid-template-columns:1fr 1fr;gap:6px;}
.spec-btn{background:var(--bg3);border:0.5px solid rgba(56,140,220,0.2);border-radius:11px;padding:14px 5px;text-align:center;cursor:pointer;font-size:13px;font-weight:600;color:#7aafcc;font-family:inherit;}
.spec-btn.on{background:var(--acc3);border-color:var(--acc2);color:var(--acc);}
.chips{display:flex;flex-wrap:wrap;gap:5px;}
.chip{background:var(--bg3);border:0.5px solid rgba(56,140,220,0.25);border-radius:20px;padding:5px 11px;font-size:12px;color:#7aafcc;cursor:pointer;font-family:inherit;}
.chip.on{background:var(--acc3);border-color:var(--acc2);color:var(--acc);}
.save-btn{width:100%;background:var(--acc2);color:#e0f2ff;border:none;border-radius:13px;padding:14px;font-size:15px;font-weight:600;cursor:pointer;margin-top:8px;font-family:inherit;}
.save-btn.sec{background:var(--acc3);}
/* EMPTY */
.empty{text-align:center;padding:36px 16px;color:var(--muted);font-size:13px;line-height:1.7;}
/* INSTALL BANNER */
.install-bar{background:linear-gradient(135deg,#1d3a5c,#0d2a4a);border:0.5px solid rgba(125,211,252,0.3);border-radius:13px;padding:13px;margin-bottom:12px;}
.install-bar h4{font-size:13px;font-weight:600;color:var(--acc);margin-bottom:4px;}
.install-bar p{font-size:11px;color:var(--muted);line-height:1.6;}
.install-steps{margin-top:8px;display:flex;flex-direction:column;gap:4px;}
.install-step{font-size:11px;color:var(--txt2);display:flex;align-items:center;gap:6px;}
</style>
</head>
<body>
<div class="app" id="app">
  <div class="hdr">
    <div class="hdr-row">
      <div>
        <div class="app-title">🎣 Bass Log</div>
        <div class="app-sub">Largemouth · Smallmouth · Tournament Ready</div>
      </div>
      <button class="add-btn" id="openLogBtn">+</button>
    </div>
  </div>
  <div class="tabs">
    <button class="tab active" onclick="switchTab(&#39;log&#39;,this)">Log</button>
    <button class="tab" onclick="switchTab(&#39;lakes&#39;,this)">Lakes</button>
    <button class="tab" onclick="switchTab(&#39;moon&#39;,this)">Moon</button>
    <button class="tab" onclick="switchTab(&#39;sessions&#39;,this)">Sessions</button>
  </div>
  <div class="scroll" id="scrollArea">
    <!-- LOG -->
    <div class="screen on" id="tabLog">
      <div class="slabel">Your catches</div>
      <div id="catchList"><div class="empty">No catches yet.<br>Tap + to log your first bass!</div></div>
    </div>
    <!-- LAKES -->
    <div class="screen" id="tabLakes">
      <div class="map-row">
        <button class="mBtn on" id="btnMarkers" onclick="setMapMode(&#39;markers&#39;)">📍 Markers</button>
        <button class="mBtn" id="btnHeat" onclick="setMapMode(&#39;heat&#39;)">🔥 Heat map</button>
        <button class="mBtn" onclick="openForm(&#39;lakeForm&#39;)">+ Lake</button>
      </div>
      <div class="map-wrap">
        <div id="map"></div>
        <div class="place-banner" id="placeBanner" style="display:none">Tap the map to place<br><strong id="placeLabel"></strong></div>
      </div>
      <div id="lakeList" style="margin-top:10px;"></div>
    </div>
    <!-- MOON -->
    <div class="screen" id="tabMoon">
      <div class="fg"><span class="fl">Check any date</span><input class="fi" type="date" id="moonDate" onchange="renderMoon()"></div>
      <div id="moonPanel"></div>
      <div class="slabel">Solunar feeding windows</div>
      <div id="solTimeline"></div>
      <div id="solList"></div>
    </div>
    <!-- SESSIONS -->
    <div class="screen" id="tabSessions">
      <div class="slabel">Best session</div>
      <div id="bestSession"></div>
      <div class="slabel">All sessions</div>
      <div id="sessionList"></div>
      <div style="margin-top:12px;" id="installBanner"></div>
    </div>
  </div>

  <!-- LOG FORM -->
  <div class="overlay" id="logForm">
    <div class="ov-hdr"><button class="back" onclick="closeForm(&#39;logForm&#39;)">←</button><div class="ov-title">Log a bass</div></div>
    <div class="fg">
      <span class="fl">Species</span>
      <div class="spec-grid">
        <div class="spec-btn on" id="spLM" onclick="selSp(&#39;Largemouth Bass&#39;)">🐟 Largemouth</div>
        <div class="spec-btn" id="spSM" onclick="selSp(&#39;Smallmouth Bass&#39;)">🎣 Smallmouth</div>
      </div>
    </div>
    <div class="r2">
      <div class="fg"><span class="fl">Weight (lb)</span><input class="fi" id="fWt" type="number" step="0.01" placeholder="3.45" inputmode="decimal"></div>
      <div class="fg"><span class="fl">Length (in)</span><input class="fi" id="fLen" type="number" step="0.5" placeholder="17.5" inputmode="decimal"></div>
    </div>
    <div class="fg">
      <span class="fl">Lake</span>
      <select class="fi" id="fLake"><option value="">— Select lake —</option></select>
    </div>
    <div class="fg"><span class="fl">Spot / area</span><input class="fi" id="fSpot" placeholder="e.g. north dock, creek mouth..."></div>
    <div class="fg">
      <span class="fl">Lure / presentation</span>
      <div class="chips" id="lureChips">
        <div class="chip on" onclick="this.classList.toggle(&#39;on&#39;)">Jig</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Crankbait</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Spinnerbait</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Topwater</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Swimbait</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Drop Shot</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Texas Rig</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Chatterbait</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Frog</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Finesse</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Blade bait</div>
      </div>
    </div>
    <div class="r2">
      <div class="fg"><span class="fl">Depth (ft)</span><input class="fi" id="fDep" type="number" placeholder="8" inputmode="numeric"></div>
      <div class="fg"><span class="fl">Water temp (°F)</span><input class="fi" id="fTemp" type="number" placeholder="64" inputmode="numeric"></div>
    </div>
    <div class="fg">
      <span class="fl">Water clarity</span>
      <div class="chips" id="clarityChips">
        <div class="chip on" onclick="selChipGroup(&#39;clarityChips&#39;,this)">Clear</div>
        <div class="chip" onclick="selChipGroup(&#39;clarityChips&#39;,this)">Stained</div>
        <div class="chip" onclick="selChipGroup(&#39;clarityChips&#39;,this)">Muddy</div>
      </div>
    </div>
    <div class="fg">
      <span class="fl">Structure</span>
      <div class="chips">
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Dock</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Rock</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Weedline</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Creek mouth</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Point</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Laydown</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Bridge</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Flats</div>
        <div class="chip" onclick="this.classList.toggle(&#39;on&#39;)">Open water</div>
      </div>
    </div>
    <div class="r2">
      <div class="fg"><span class="fl">Date</span><input class="fi" id="fDate" type="date"></div>
      <div class="fg"><span class="fl">Time</span><input class="fi" id="fTime" type="time"></div>
    </div>
    <div class="fg">
      <span class="fl">Weather</span>
      <div class="chips" id="wxChips">
        <div class="chip on" onclick="selChipGroup(&#39;wxChips&#39;,this)">☀️ Sunny</div>
        <div class="chip" onclick="selChipGroup(&#39;wxChips&#39;,this)">⛅ Cloudy</div>
        <div class="chip" onclick="selChipGroup(&#39;wxChips&#39;,this)">🌧 Rainy</div>
        <div class="chip" onclick="selChipGroup(&#39;wxChips&#39;,this)">💨 Windy</div>
        <div class="chip" onclick="selChipGroup(&#39;wxChips&#39;,this)">🌫 Overcast</div>
      </div>
    </div>
    <div class="fg"><span class="fl">Notes</span><textarea class="fi" id="fNotes" rows="3" placeholder="Color, retrieve speed, anything special..."></textarea></div>
    <button class="save-btn" onclick="saveCatch()">Save catch 🎣</button>
  </div>

  <!-- LAKE FORM -->
  <div class="overlay" id="lakeForm">
    <div class="ov-hdr"><button class="back" onclick="closeForm(&#39;lakeForm&#39;)">←</button><div class="ov-title">Add a lake</div></div>
    <div class="fg"><span class="fl">Lake name</span><input class="fi" id="lName" placeholder="e.g. Lake Champlain"></div>
    <div class="fg"><span class="fl">State / region</span><input class="fi" id="lState" placeholder="e.g. Vermont"></div>
    <div style="display:flex;gap:8px;">
      <button class="save-btn sec" style="margin-top:0;" onclick="placeOnMap()">📍 Tap map to place</button>
      <button class="save-btn sec" style="margin-top:0;" onclick="useGPS()">📡 Use GPS</button>
    </div>
    <div style="font-size:11px;color:var(--muted);margin:10px 0 8px;text-align:center;">Or enter coordinates manually</div>
    <div class="r2">
      <div class="fg"><span class="fl">Latitude</span><input class="fi" id="lLat" type="number" step="0.0001" placeholder="42.5612" inputmode="decimal"></div>
      <div class="fg"><span class="fl">Longitude</span><input class="fi" id="lLng" type="number" step="0.0001" placeholder="-72.3498" inputmode="decimal"></div>
    </div>
    <button class="save-btn" onclick="saveLake()">Add lake</button>
  </div>
</div>

<script src="./Bass Log_files/leaflet.min.js.download"></script>
<script src="./Bass Log_files/leaflet-heat.js.download"></script>
<script>
// ── STORAGE (localStorage — private per device) ──
const DB = {
  get(k){try{const v=localStorage.getItem(k);return v?JSON.parse(v):null;}catch(e){return null;}},
  set(k,v){try{localStorage.setItem(k,JSON.stringify(v));}catch(e){}},
};

// ── STATE ──
let catches = DB.get('catches')||[];
let lakes   = DB.get('lakes')||[];
let nextId  = catches.length ? Math.max(...catches.map(c=>c.id))+1 : 1;
let selSpecies='Largemouth Bass', placingLake=false, pendingLake={};
let leafletMap=null, markers=[], heatLayer=null, mapMode='markers';

const COLORS=['#2587c8','#22c98a','#e89c3a','#e05a9a','#a87df8','#e05a5a','#5ac8e0','#f59e0b','#34d399','#fb923c'];
function lakeColor(name){const i=lakes.findIndex(l=>l.name===name);return COLORS[Math.max(i,0)%COLORS.length];}
function fmtDate(d){if(!d)return'';const dt=new Date(d+'T12:00');return dt.toLocaleDateString('en-US',{weekday:'short',month:'short',day:'numeric'});}
function fmtTime(t){if(!t)return'';const[h,m]=t.split(':');return`${(+h%12)||12}:${m}${+h>=12?'pm':'am'}`;}

// ── LOG ──
function renderLog(){
  const el=document.getElementById('catchList');
  const list=[...catches].sort((a,b)=>b.date.localeCompare(a.date)||(b.time||'').localeCompare(a.time||''));
  if(!list.length){el.innerHTML='<div class="empty">No catches yet.<br>Tap + to log your first bass!</div>';return;}
  el.innerHTML=list.map(c=>{
    const col=lakeColor(c.lake||'');
    return`<div class="card"><div class="fish-row">
      <div class="fish-ico" style="background:${col}22;">${c.species==='Largemouth Bass'?'🐟':'🎣'}</div>
      <div style="flex:1;min-width:0;">
        <div class="fish-name">${c.species}</div>
        <div class="fish-meta">${c.lake||'Unknown lake'}${c.spot?' · '+c.spot:''} · ${fmtDate(c.date)} ${fmtTime(c.time)}</div>
        <div class="tag-row">
          ${c.lure?`<span class="tag tb">${c.lure}</span>`:''}
          ${c.depth?`<span class="tag tg">${c.depth}ft</span>`:''}
          ${c.clarity?`<span class="tag ta">${c.clarity}</span>`:''}
          ${c.wx?`<span class="tag tr">${c.wx}</span>`:''}
        </div>
      </div>
      <div style="text-align:right;flex-shrink:0;">
        <div style="font-size:18px;font-weight:700;color:var(--acc);">${c.weight?c.weight.toFixed(2):'-'}<span style="font-size:10px;color:var(--muted);"> lb</span></div>
        <div style="font-size:11px;color:var(--muted);">${c.length?c.length+'"':''}</div>
      </div>
    </div></div>`;
  }).join('');
}

// ── MOON ──
function julianDay(date){
  const y=date.getFullYear(),m=date.getMonth()+1,d=date.getDate();
  const a=Math.floor((14-m)/12),Y=y+4800-a,M=m+12*a-3;
  return d+Math.floor((153*M+2)/5)+365*Y+Math.floor(Y/4)-Math.floor(Y/100)+Math.floor(Y/400)-32045-0.5;
}
function moonAge(date){let a=(julianDay(date)-2451549.5)%29.53058853;return a<0?a+29.53058853:a;}
function moonInfo(age){
  const p=age/29.53,ill=Math.round((1-Math.cos(p*2*Math.PI))/2*100);
  const ns=['New Moon','Waxing Crescent','First Quarter','Waxing Gibbous','Full Moon','Waning Gibbous','Last Quarter','Waning Crescent'];
  const ts=[0.034,0.234,0.284,0.484,0.534,0.734,0.784,0.966];
  let name=ns[ns.length-1];for(let i=0;i<ts.length;i++){if(p<ts[i]){name=ns[i];break;}}
  const d=Math.min(Math.min(p,1-p),Math.abs(p-0.5));
  const [rating,rc]=d<0.05?['Excellent 🔥','#22c98a']:d<0.12?['Good 👍','#7dd3fc']:d<0.22?['Fair','#e89c3a']:['Slow','#5a8aaa'];
  return{name,ill,rating,rc,p};
}
function moonSVG(age){
  const p=age/29.53,r=52;
  const ill=(1-Math.cos(p*2*Math.PI))/2;
  if(ill<0.01)return`<circle r="${r}" fill="#1d2d3d" stroke="#2a4a6a" stroke-width="1.5"/>`;
  if(ill>0.99)return`<circle r="${r}" fill="#c9e8ff" stroke="#7dd3fc" stroke-width="1.5"/>`;
  const wax=p<0.5,tx=(Math.abs(Math.cos(p*2*Math.PI))*r).toFixed(1);
  let dp;
  if(wax){dp=ill<=0.5?`M 0 -${r} A ${r} ${r} 0 0 0 0 ${r} A ${tx} ${r} 0 0 1 0 -${r} Z`:`M 0 -${r} A ${tx} ${r} 0 0 0 0 ${r} A ${r} ${r} 0 0 1 0 -${r} Z`;}
  else{dp=ill<=0.5?`M 0 -${r} A ${r} ${r} 0 0 1 0 ${r} A ${tx} ${r} 0 0 0 0 -${r} Z`:`M 0 -${r} A ${tx} ${r} 0 0 1 0 ${r} A ${r} ${r} 0 0 0 0 -${r} Z`;}
  return`<circle r="${r}" fill="#c9e8ff"/><path d="${dp}" fill="#1d2d3d"/><circle r="${r}" fill="none" stroke="#7dd3fc" stroke-width="1.5"/>`;
}
function solunarTimes(age){
  const off=(age*50)%(24*60),up=(12*60+off)%(24*60),lo=(up+720)%(24*60);
  function f(m){const h=Math.floor(((m%1440)+1440)%1440/60),mn=Math.floor(((m%1440)+1440)%1440%60);return`${(h%12)||12}:${mn.toString().padStart(2,'0')}${h>=12?'pm':'am'}`;}
  return[
    {type:'Major',color:'#22c98a',s:(up-60+1440)%1440,dur:120,str:`${f(up-60)} – ${f(up+60)}`},
    {type:'Minor',color:'#7dd3fc',s:(up+330+1440)%1440,dur:60,str:`${f(up+330)} – ${f(up+390)}`},
    {type:'Major',color:'#22c98a',s:(lo-60+1440)%1440,dur:120,str:`${f(lo-60)} – ${f(lo+60)}`},
    {type:'Minor',color:'#7dd3fc',s:(lo+330+1440)%1440,dur:60,str:`${f(lo+330)} – ${f(lo+390)}`},
  ].sort((a,b)=>a.s-b.s);
}
function renderMoon(){
  const ds=document.getElementById('moonDate').value||new Date().toISOString().split('T')[0];
  const date=new Date(ds+'T12:00:00'),age=moonAge(date),info=moonInfo(age),times=solunarTimes(age);
  document.getElementById('moonPanel').innerHTML=`
    <div class="moon-panel">
      <svg viewBox="-60 -60 120 120" width="110" height="110">${moonSVG(age)}</svg>
      <div class="moon-info">
        <h3>${info.name}</h3>
        <p>${info.ill}% illuminated · Day ${Math.round(age)} of 29.5</p>
        <div class="rating-pill" style="background:${info.rc}22;color:${info.rc};border:0.5px solid ${info.rc}55;">Bass activity: ${info.rating}</div>
      </div>
    </div>`;
  const W=330;
  let segs=times.map(t=>`<rect x="${Math.round(t.s/1440*W)}" y="0" width="${Math.round(t.dur/1440*W)}" height="14" rx="3" fill="${t.color}" opacity="0.85"/>`).join('');
  const now=new Date(),nx=Math.round((now.getHours()*60+now.getMinutes())/1440*W);
  segs+=`<line x1="${nx}" y1="-2" x2="${nx}" y2="16" stroke="white" stroke-width="2" opacity="0.8"/>`;
  document.getElementById('solTimeline').innerHTML=`
    <div class="timeline-wrap">
      <div class="tl-labels"><span>12am</span><span>6am</span><span>12pm</span><span>6pm</span><span>12am</span></div>
      <div style="height:14px;background:#0a1628;border-radius:7px;overflow:hidden;">
        <svg width="100%" height="14" viewBox="0 0 ${W} 14" preserveAspectRatio="none">${segs}</svg>
      </div>
      <div style="font-size:9px;color:var(--muted);margin-top:5px;text-align:center;">White line = now · 🟢 Major · 🔵 Minor</div>
    </div>`;
  document.getElementById('solList').innerHTML=times.map(t=>`
    <div class="sol-row">
      <div class="sol-dot" style="background:${t.color};"></div>
      <div class="sol-type" style="color:${t.color};">${t.type}</div>
      <div class="sol-t">${t.str}</div>
      <div class="sol-str">${t.type==='Major'?'🔥 Peak bite':'Active'}</div>
    </div>`).join('');
}

// ── SESSIONS ──
function renderSessions(){
  const groups={};
  catches.forEach(c=>{groups[c.date]=groups[c.date]||[];groups[c.date].push(c);});
  const dates=Object.keys(groups).sort((a,b)=>b.localeCompare(a));
  if(!dates.length){
    document.getElementById('bestSession').innerHTML='';
    document.getElementById('sessionList').innerHTML='<div class="empty">No sessions yet.</div>';
    renderInstallBanner();return;
  }
  const sessions=dates.map(d=>{
    const arr=groups[d];
    const tw=arr.reduce((s,c)=>s+(c.weight||0),0);
    const big=Math.max(...arr.map(c=>c.weight||0));
    const bag=[...arr].sort((a,b)=>(b.weight||0)-(a.weight||0)).slice(0,5);
    const bagW=bag.reduce((s,c)=>s+(c.weight||0),0);
    const lures={};arr.forEach(c=>{if(c.lure)lures[c.lure]=(lures[c.lure]||0)+1;});
    const bestLure=Object.entries(lures).sort((a,b)=>b[1]-a[1])[0]?.[0]||'—';
    return{date:d,arr,tw,big,bagW,bestLure,spots:[...new Set(arr.map(c=>c.location))].length};
  });
  const maxW=Math.max(...sessions.map(s=>s.tw));
  const bestIdx=sessions.reduce((bi,s,i)=>s.tw>sessions[bi].tw?i:bi,0);
  const b=sessions[bestIdx];
  document.getElementById('bestSession').innerHTML=`
    <div class="sess-card" style="border-color:rgba(250,196,75,0.4);background:#0d1e10;">
      <div class="sess-hdr"><div class="sess-date">${fmtDate(b.date)}</div><span class="best-badge">🏆 Best session</span></div>
      <div class="stat3">
        <div class="sc"><div class="sv">${b.arr.length}</div><div class="sl">caught</div></div>
        <div class="sc"><div class="sv">${b.tw.toFixed(2)}</div><div class="sl">total lb</div></div>
        <div class="sc"><div class="sv">${b.big.toFixed(2)}</div><div class="sl">biggest lb</div></div>
      </div>
      <div style="font-size:11px;color:var(--muted);margin-top:7px;">🎣 ${b.bestLure} · 5-fish bag: ${b.bagW.toFixed(2)} lb</div>
    </div>`;
  document.getElementById('sessionList').innerHTML=sessions.map((s,i)=>{
    const pct=Math.round(s.tw/maxW*100);
    return`<div class="sess-card${i===bestIdx?' ':" "}">
      <div class="sess-hdr">
        <div class="sess-date">${fmtDate(s.date)}</div>
        ${i===bestIdx?'<span class="best-badge">🏆 Best</span>':''}
      </div>
      <div class="stat3">
        <div class="sc"><div class="sv">${s.arr.length}</div><div class="sl">bass</div></div>
        <div class="sc"><div class="sv">${s.tw.toFixed(2)}</div><div class="sl">total lb</div></div>
        <div class="sc"><div class="sv">${s.big.toFixed(2)}</div><div class="sl">biggest lb</div></div>
      </div>
      <div style="margin-top:8px;">
        <div style="font-size:9px;color:var(--muted);margin-bottom:3px;">Weight vs best session</div>
        <div class="bar-wrap"><div class="bar-fill" style="width:${pct}%;background:${pct===100?'#fcd34d':'#2587c8'};"></div></div>
      </div>
      <div style="font-size:11px;color:var(--muted);margin-top:6px;">🎣 ${s.bestLure} · bag: ${s.bagW.toFixed(2)} lb</div>
    </div>`;
  }).join('');
  renderInstallBanner();
}

function renderInstallBanner(){
  const isInstalled=window.matchMedia('(display-mode: standalone)').matches||window.navigator.standalone;
  if(isInstalled){document.getElementById('installBanner').innerHTML='';return;}
  document.getElementById('installBanner').innerHTML=`
    <div class="install-bar">
      <h4>📱 Install on your iPhone</h4>
      <p>Add this to your home screen for a real app experience — works offline too.</p>
      <div class="install-steps">
        <div class="install-step"><span>1.</span>Open this page in <strong>Safari</strong></div>
        <div class="install-step"><span>2.</span>Tap the <strong>Share</strong> button (box with arrow)</div>
        <div class="install-step"><span>3.</span>Tap <strong>"Add to Home Screen"</strong></div>
        <div class="install-step"><span>4.</span>Tap <strong>Add</strong> — done! 🎣</div>
      </div>
    </div>`;
}

// ── MAP ──
function buildSpotMap(){const m={};catches.forEach(c=>{const k=c.lake||'?';m[k]=m[k]||[];m[k].push(c);});return m;}
function makeIcon(col,n){
  const s=n?Math.min(26+n*2,44):20;
  return L.divIcon({html:`<svg xmlns="http://www.w3.org/2000/svg" width="${s}" height="${s}" viewBox="0 0 40 40"><circle cx="20" cy="20" r="18" fill="${col}" fill-opacity="0.18" stroke="${col}" stroke-width="1.5"/><circle cx="20" cy="20" r="11" fill="${col}" stroke="white" stroke-width="2"/>${n?`<text x="20" y="25" text-anchor="middle" font-size="12" fill="white" font-weight="700" font-family="sans-serif">${n}</text>`:''}</svg>`,className:'',iconSize:[s,s],iconAnchor:[s/2,s/2],popupAnchor:[0,-s/2]});
}
function initMap(){
  if(leafletMap){leafletMap.invalidateSize();rebuildMarkers();return;}
  const center=lakes.length?[lakes[0].lat,lakes[0].lng]:[39,-96];
  const zoom=lakes.length?12:4;
  leafletMap=L.map('map',{zoomControl:true,attributionControl:false}).setView(center,zoom);
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',{maxZoom:18}).addTo(leafletMap);
  L.control.attribution({prefix:'© OpenStreetMap'}).addTo(leafletMap);
  leafletMap.on('click',onMapClick);
  rebuildMarkers();
}
function onMapClick(e){
  if(!placingLake)return;
  const{lat,lng}=e.latlng;
  lakes.push({name:pendingLake.name,state:pendingLake.state,lat:+lat.toFixed(5),lng:+lng.toFixed(5),date:new Date().toISOString().split('T')[0]});
  DB.set('lakes',lakes);
  placingLake=false;
  document.getElementById('placeBanner').style.display='none';
  rebuildMarkers();renderLakeList();
}
function rebuildMarkers(){
  if(!leafletMap)return;
  markers.forEach(m=>m.remove());markers=[];
  if(heatLayer){heatLayer.remove();heatLayer=null;}
  const sm=buildSpotMap();
  if(mapMode==='markers'){
    lakes.forEach((lake,i)=>{
      const arr=sm[lake.name]||[];
      const col=COLORS[i%COLORS.length];
      const tw=arr.reduce((a,c)=>a+(c.weight||0),0).toFixed(2);
      const big=arr.length?Math.max(...arr.map(c=>c.weight||0)).toFixed(2):'—';
      const sp=[...new Set(arr.map(c=>c.species))];
      const mk=L.marker([lake.lat,lake.lng],{icon:makeIcon(col,arr.length)})
        .addTo(leafletMap)
        .bindPopup(`<div class="pname">🏞 ${lake.name}${lake.state?', '+lake.state:''}</div>
          <div class="prow"><span class="pm">Catches</span><span>${arr.length}</span></div>
          <div class="prow"><span class="pm">Total wt</span><span>${tw} lb</span></div>
          <div class="prow"><span class="pm">Biggest</span><span>${big} lb</span></div>
          <div style="margin-top:5px;">${sp.map(s=>`<span style="font-size:10px;padding:2px 6px;border-radius:20px;background:#1d3a5c;color:#7dd3fc;display:inline-block;margin:1px;">${s}</span>`).join('')}</div>`,{maxWidth:210});
      markers.push(mk);
    });
  } else {
    const pts=[];
    catches.forEach(c=>{const l=lakes.find(k=>k.name===c.lake);if(l)pts.push([l.lat+(Math.random()-.5)*.004,l.lng+(Math.random()-.5)*.004,(c.weight||1)/6]);});
    if(typeof L.heatLayer==='function'&&pts.length)heatLayer=L.heatLayer(pts,{radius:35,blur:25,gradient:{0.2:'#1e6fa8',0.5:'#22c98a',0.8:'#e89c3a',1:'#e05a5a'}}).addTo(leafletMap);
    lakes.forEach((lake,i)=>{
      const arr=sm[lake.name]||[];if(!arr.length)return;
      const mk=L.marker([lake.lat,lake.lng],{icon:L.divIcon({html:`<div style="background:#0f2035cc;color:#7dd3fc;font-size:10px;padding:2px 8px;border-radius:8px;border:0.5px solid rgba(125,211,252,0.4);white-space:nowrap;">📍 ${lake.name}</div>`,className:'',iconAnchor:[0,10]})}).addTo(leafletMap);
      markers.push(mk);
    });
  }
}
function setMapMode(m){
  mapMode=m;
  document.getElementById('btnMarkers').classList.toggle('on',m==='markers');
  document.getElementById('btnHeat').classList.toggle('on',m==='heat');
  rebuildMarkers();
}
function renderLakeList(){
  const sm=buildSpotMap();
  const el=document.getElementById('lakeList');
  if(!lakes.length){el.innerHTML='<div class="empty">No lakes added yet.<br>Tap "+ Lake" to add your waters.</div>';return;}
  el.innerHTML=lakes.map((lake,i)=>{
    const arr=sm[lake.name]||[];
    const tw=arr.reduce((a,c)=>a+(c.weight||0),0).toFixed(2);
    const big=arr.length?Math.max(...arr.map(c=>c.weight||0)).toFixed(2):'—';
    const col=COLORS[i%COLORS.length];
    return`<div class="card" style="border-color:${col}33;">
      <div style="display:flex;justify-content:space-between;align-items:center;">
        <div>
          <div style="font-size:14px;font-weight:600;color:var(--txt2);">🏞 ${lake.name}${lake.state?', '+lake.state:''}</div>
          <div style="font-size:11px;color:var(--muted);margin-top:2px;">${arr.length} catches · ${tw} lb total · biggest ${big} lb</div>
        </div>
        <div style="font-size:22px;font-weight:700;color:${col};">${arr.length}</div>
      </div>
    </div>`;
  }).join('');
}

// ── FORM HELPERS ──
function selSp(s){selSpecies=s;document.getElementById('spLM').classList.toggle('on',s==='Largemouth Bass');document.getElementById('spSM').classList.toggle('on',s==='Smallmouth Bass');}
function selChipGroup(groupId,el){document.querySelectorAll('#'+groupId+' .chip').forEach(c=>c.classList.remove('on'));el.classList.add('on');}
function openForm(id){document.getElementById(id).classList.add('on');document.getElementById(id).scrollTop=0;}
function closeForm(id){document.getElementById(id).classList.remove('on');}

function openLogForm(){
  const now=new Date();
  document.getElementById('fDate').value=now.toISOString().split('T')[0];
  document.getElementById('fTime').value=now.toTimeString().slice(0,5);
  document.getElementById('fWt').value='';document.getElementById('fLen').value='';
  document.getElementById('fSpot').value='';document.getElementById('fNotes').value='';
  document.getElementById('fDep').value='';document.getElementById('fTemp').value='';
  const sel=document.getElementById('fLake');
  sel.innerHTML='<option value="">— Select lake —</option>'+lakes.map(l=>`<option value="${l.name}">${l.name}${l.state?', '+l.state:''}</option>`).join('');
  openForm('logForm');
}

function saveCatch(){
  const lure=[...document.querySelectorAll('#lureChips .chip.on')].map(c=>c.textContent).join(', ');
  const struc=[...document.querySelectorAll('.fg .chips:not(#lureChips):not(#clarityChips):not(#wxChips) .chip.on')].map(c=>c.textContent).join(', ');
  const wx=document.querySelector('#wxChips .chip.on');
  const clarity=document.querySelector('#clarityChips .chip.on');
  const wt=parseFloat(document.getElementById('fWt').value)||0;
  if(!wt){alert('Enter a weight to log this catch.');return;}
  catches.push({
    id:nextId++,species:selSpecies,
    weight:wt,length:parseFloat(document.getElementById('fLen').value)||0,
    lure:lure||'',depth:parseFloat(document.getElementById('fDep').value)||0,
    temp:parseFloat(document.getElementById('fTemp').value)||0,
    lake:document.getElementById('fLake').value,
    spot:document.getElementById('fSpot').value,
    clarity:clarity?clarity.textContent:'',
    structure:struc,wx:wx?wx.textContent:'',
    date:document.getElementById('fDate').value,
    time:document.getElementById('fTime').value,
    notes:document.getElementById('fNotes').value
  });
  DB.set('catches',catches);
  closeForm('logForm');
  renderLog();
}

function placeOnMap(){
  const name=document.getElementById('lName').value.trim();
  if(!name){alert('Enter a lake name first.');return;}
  pendingLake={name,state:document.getElementById('lState').value.trim()};
  closeForm('lakeForm');
  placingLake=true;
  document.getElementById('placeBanner').style.display='flex';
  document.getElementById('placeLabel').textContent=name;
  switchTab('lakes',document.querySelectorAll('.tab')[1]);
}
function useGPS(){
  if(!navigator.geolocation){alert('GPS not available in this browser.');return;}
  navigator.geolocation.getCurrentPosition(pos=>{
    document.getElementById('lLat').value=pos.coords.latitude.toFixed(5);
    document.getElementById('lLng').value=pos.coords.longitude.toFixed(5);
  },()=>alert('Could not get GPS position. Try entering coordinates manually.'));
}
function saveLake(){
  const name=document.getElementById('lName').value.trim();
  const state=document.getElementById('lState').value.trim();
  const lat=parseFloat(document.getElementById('lLat').value);
  const lng=parseFloat(document.getElementById('lLng').value);
  if(!name||!lat||!lng){alert('Enter a lake name and location (GPS, tap map, or coordinates).');return;}
  if(!lakes.find(l=>l.name===name)){
    lakes.push({name,state,lat,lng,date:new Date().toISOString().split('T')[0]});
    DB.set('lakes',lakes);
  }
  closeForm('lakeForm');
  rebuildMarkers();renderLakeList();
}

// ── TABS ──
function switchTab(tab,btn){
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  btn.classList.add('active');
  document.getElementById('scrollArea').scrollTop=0;
  ['log','lakes','moon','sessions'].forEach(t=>{
    document.getElementById('tab'+t.charAt(0).toUpperCase()+t.slice(1)).classList.toggle('on',t===tab);
  });
  if(tab==='lakes')setTimeout(()=>{initMap();renderLakeList();},60);
  if(tab==='moon'){document.getElementById('moonDate').value=new Date().toISOString().split('T')[0];renderMoon();}
  if(tab==='sessions')renderSessions();
}

document.getElementById('openLogBtn').onclick=openLogForm;
renderLog();
</script>


</body></html>
