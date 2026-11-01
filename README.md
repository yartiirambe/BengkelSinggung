# BengkelSinggung
<!doctype html><html><head><meta charset=utf8><meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"><style>:root{color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}html{scroll-padding-top:env(safe-area-inset-top,0px)}body{margin:0;padding:0;font:14px -apple-system,BlinkMacSystemFont,sans-serif;background:#fff;color:#000}img{max-width:100%}[hidden]:not([hidden=until-found i]){display:none!important}</style></head><body>
<title>Bengkel Garis Singgung</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@500;600;700&family=Source+Sans+3:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap">
<style>
/* Layout: gambar kerja teknik. Header sticky, 3 misi (gambar kerja) berisi 6 tahap sintaks Discovery Learning, tiap tahap = panel dengan simulasi SVG di kiri dan kontrol di kanan. */
:root{
 --bg:#EAF0ED; --paper:#F8FBF9; --ink:#10302B; --muted:#4A675F; --line:#BCCFC8; --grid:#D6E3DE;
 --green:#0E6B57; --green-soft:#D3EBE3; --amber:#F2B01E; --amber-ink:#5E3B00; --amber-soft:#FBE9B8;
 --tan:#D96F00; --ok:#1B7F46; --ok-soft:#D5F0DF; --bad:#B7311F; --bad-soft:#F8DAD4; --belt:#E9B949;
 --fd:'Barlow Condensed','Arial Narrow',sans-serif; --fb:'Source Sans 3',system-ui,sans-serif; --fm:'IBM Plex Mono',ui-monospace,monospace;
}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){
 --bg:#08181B; --paper:#102529; --ink:#E4F1ED; --muted:#98B6AF; --line:#29484B; --grid:#18343A;
 --green:#46C9A6; --green-soft:#12413A; --amber:#F2B01E; --amber-ink:#FFE3A1; --amber-soft:#4A3809;
 --tan:#FF9A3D; --ok:#5DD28D; --ok-soft:#133D27; --bad:#FF8A78; --bad-soft:#4A1E18; --belt:#C99A2C; color-scheme:dark}}
:root[data-theme="dark"]{
 --bg:#08181B; --paper:#102529; --ink:#E4F1ED; --muted:#98B6AF; --line:#29484B; --grid:#18343A;
 --green:#46C9A6; --green-soft:#12413A; --amber:#F2B01E; --amber-ink:#FFE3A1; --amber-soft:#4A3809;
 --tan:#FF9A3D; --ok:#5DD28D; --ok-soft:#133D27; --bad:#FF8A78; --bad-soft:#4A1E18; --belt:#C99A2C; color-scheme:dark}
*{box-sizing:border-box}
body{background:var(--bg);color:var(--ink);font:400 17px/1.55 var(--fb);
 background-image:linear-gradient(var(--grid) 1px,transparent 1px),linear-gradient(90deg,var(--grid) 1px,transparent 1px);background-size:28px 28px;
 padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px));padding-block:0 64px}
body::before{content:"";position:fixed;inset:0 0 auto;height:env(safe-area-inset-top,0px);z-index:30;background:var(--ink)}
.wrap{max-width:1060px;margin:0 auto}
h1,h2,h3,h4{font-family:var(--fd);font-weight:700;line-height:1.1;margin:0;text-wrap:balance;letter-spacing:.01em}
h2{font-size:2.1rem} h3{font-size:1.45rem} h4{font-size:1.1rem;text-transform:uppercase;letter-spacing:.07em;color:var(--green)}
p{margin:0 0 .7em;max-width:68ch} .mono{font-family:var(--fm);font-variant-numeric:tabular-nums}
.mut{color:var(--muted)} .sm{font-size:.9rem}
.rad{white-space:nowrap}.rad .ov{border-top:1.6px solid currentColor;padding:0 .18em 0 .12em;margin-left:-.04em}
.fx{font-family:var(--fm);font-size:1.05em;white-space:nowrap}
/* header */
.top{position:sticky;top:env(safe-area-inset-top,0px);z-index:20;background:var(--ink);color:var(--paper);margin-inline:calc(50% - 50vw);padding-inline:max(16px,calc(50vw - 530px))}
.top .in{display:flex;align-items:center;gap:14px;padding:8px 0;flex-wrap:wrap}
.brand{font-family:var(--fd);font-weight:700;font-size:1.25rem;letter-spacing:.04em;color:var(--amber);white-space:nowrap}
.top nav{display:flex;gap:2px;flex-wrap:wrap;flex:1;min-width:0}
.top nav a{color:#DCEBE6;text-decoration:none;font:600 .85rem var(--fb);padding:6px 10px;border-radius:3px;white-space:nowrap}
.top nav a:hover,.top nav a:focus-visible{background:rgba(255,255,255,.14);outline:none}
.prog{display:flex;align-items:center;gap:8px;font:500 .78rem var(--fm);color:#DCEBE6}
.prog i{display:block;width:96px;height:7px;background:rgba(255,255,255,.2);border-radius:2px;overflow:hidden}
.prog b{display:block;height:100%;background:var(--amber);width:0;transition:width .4s}
.thm{background:transparent;border:1px solid rgba(255,255,255,.4);color:#fff;border-radius:3px;padding:3px 9px;font:600 .8rem var(--fb);cursor:pointer}
/* hero */
.hero{padding:44px 0 28px;display:grid;grid-template-columns:1.25fr 1fr;gap:28px;align-items:start}
.hero h1{font-size:clamp(2.8rem,7vw,5rem);text-transform:uppercase;color:var(--ink)}
.hero h1 em{font-style:normal;color:var(--green)}
.tb{border:2px solid var(--ink);background:var(--paper);display:grid;grid-template-columns:1fr 1fr;font-size:.82rem}
.tb div{padding:7px 10px;border:1px solid var(--ink);margin:-1px 0 0 -1px;min-width:0}
.tb small{display:block;font:500 .66rem var(--fm);text-transform:uppercase;letter-spacing:.08em;color:var(--muted)}
.tb .w2{grid-column:span 2}
.lead{font-size:1.15rem;margin-top:14px}
.chips{display:flex;gap:6px;flex-wrap:wrap;margin-top:10px}
.chip{font:600 .72rem var(--fm);text-transform:uppercase;letter-spacing:.06em;padding:3px 8px;border:1.5px solid var(--green);color:var(--green);border-radius:2px;background:var(--paper)}
.chip.a{border-color:var(--tan);color:var(--tan)} .chip.m{border-color:var(--ink);color:var(--ink)}
/* sections */
section.blk{margin-top:34px;scroll-margin-top:70px}
.sechd{display:flex;align-items:baseline;gap:14px;flex-wrap:wrap;border-bottom:3px solid var(--ink);padding-bottom:8px;margin-bottom:16px}
.sechd .no{font:600 .8rem var(--fm);background:var(--ink);color:var(--paper);padding:3px 9px;letter-spacing:.08em;white-space:nowrap}
.card{background:var(--paper);border:1.5px solid var(--ink);padding:16px 18px;min-width:0}
.card.soft{border-color:var(--line)}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:16px}.grid3{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.grid2>*,.grid3>*{min-width:0}
/* tp tracker */
.tp{display:flex;gap:10px;align-items:flex-start;padding:9px 0;border-top:1px dashed var(--line)}
.tp:first-of-type{border-top:0}
input[type=checkbox],input[type=radio]{accent-color:var(--green);width:19px;height:19px;flex:none;margin-top:3px}
/* stage tabs */
.tabs{display:flex;gap:0;overflow-x:auto;border:1.5px solid var(--ink);border-bottom:0;background:var(--paper);scrollbar-width:thin}
.tab{flex:1 0 auto;min-width:128px;text-align:left;border:0;border-right:1px solid var(--line);background:transparent;color:var(--ink);padding:9px 12px;cursor:pointer;font:600 .92rem/1.2 var(--fb)}
.tab small{display:block;font:500 .64rem var(--fm);text-transform:uppercase;letter-spacing:.08em;color:var(--muted);margin-bottom:2px}
.tab[aria-selected=true]{background:var(--ink);color:var(--paper)} .tab[aria-selected=true] small{color:var(--amber)}
.tab.done::after{content:" ✓";color:var(--ok)} .tab[aria-selected=true].done::after{color:var(--amber)}
.tab:focus-visible,button:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid var(--amber);outline-offset:1px}
.panel{border:1.5px solid var(--ink);background:var(--paper);padding:20px;display:flex;flex-direction:column;gap:18px;min-width:0}
.panel>*{min-width:0}
.ph{display:flex;gap:10px;align-items:baseline;flex-wrap:wrap}
.sim{display:grid;grid-template-columns:minmax(0,1.55fr) minmax(0,1fr);gap:18px;align-items:start}
.fig{border:1px solid var(--line);background:var(--bg);background-image:linear-gradient(var(--grid) 1px,transparent 1px),linear-gradient(90deg,var(--grid) 1px,transparent 1px);background-size:20px 20px;touch-action:none;line-height:0}
.fig svg{width:100%;height:auto;display:block;max-height:420px}
.ctl{display:flex;flex-direction:column;gap:12px}
.sl label{display:flex;justify-content:space-between;font:600 .92rem var(--fb)} .sl output{font-family:var(--fm);color:var(--green);font-weight:600}
input[type=range]{width:100%;accent-color:var(--green);height:28px}
.ro{background:var(--ink);color:var(--paper);padding:10px 12px;font:500 .95rem/1.5 var(--fm)} .ro b{color:var(--amber)}
.seg{display:flex;border:1.5px solid var(--ink)} .seg button{flex:1;border:0;background:var(--paper);color:var(--ink);padding:7px 8px;font:600 .88rem var(--fb);cursor:pointer}
.seg button[aria-pressed=true]{background:var(--green);color:#fff}
.btn{font:700 .95rem var(--fb);padding:9px 16px;border:1.5px solid var(--ink);background:var(--amber);color:#2B1B00;cursor:pointer;border-radius:3px;box-shadow:2px 2px 0 var(--ink)}
.btn:active{transform:translate(1px,1px);box-shadow:1px 1px 0 var(--ink)}
.btn.g{background:var(--paper);color:var(--ink)} .btn.s{padding:5px 10px;font-size:.85rem}
.navb{display:flex;justify-content:space-between;gap:10px;flex-wrap:wrap;border-top:1px dashed var(--line);padding-top:14px}
.tbl{overflow-x:auto;border:1px solid var(--line)} table{border-collapse:collapse;width:100%;font:500 .86rem var(--fm);font-variant-numeric:tabular-nums}
th,td{padding:5px 9px;border-bottom:1px solid var(--line);text-align:right;white-space:nowrap} th{background:var(--green-soft);color:var(--ink);font-weight:600;position:sticky;top:0} th:first-child,td:first-child{text-align:left}
tr.hl td{background:var(--amber-soft)}
.note{border-left:5px solid var(--amber);background:var(--amber-soft);color:var(--ink);padding:10px 14px}
.note.ok{border-color:var(--ok);background:var(--ok-soft)} .note.bad{border-color:var(--bad);background:var(--bad-soft)}
.fb{min-height:1.4em;margin-top:8px;font-weight:600} .fb.ok{color:var(--ok)} .fb.bad{color:var(--bad)}
.opt{display:flex;gap:10px;align-items:flex-start;padding:9px 12px;border:1.5px solid var(--line);margin-bottom:7px;cursor:pointer;background:var(--paper)}
.opt:hover{border-color:var(--green)} .opt.ok{border-color:var(--ok);background:var(--ok-soft)} .opt.bad{border-color:var(--bad);background:var(--bad-soft)}
textarea,input[type=text],input.num,select{font:inherit;color:var(--ink);background:var(--paper);border:1.5px solid var(--ink);padding:8px 10px;border-radius:2px;max-width:100%}
textarea{width:100%;min-height:74px;resize:vertical} input.num{width:9ch;font-family:var(--fm);text-align:right}
select{padding:2px 6px;font-weight:600}
.pb{border:1.5px solid var(--line);padding:14px;display:flex;flex-direction:column;gap:10px}
.pb .q{font-weight:600}
.pb.ok{border-color:var(--ok)} .row{display:flex;gap:10px;align-items:center;flex-wrap:wrap}
.hint{background:var(--green-soft);padding:8px 12px;font-size:.95rem;border-left:5px solid var(--green)}
.sol{background:var(--bg);border:1px dashed var(--ink);padding:10px 14px}
.sol .st{padding:3px 0} .st[hidden]{display:none}
.big{font:600 1.6rem var(--fm);text-align:center;padding:14px;background:var(--ink);color:var(--amber);overflow-x:auto}
.cloze select{margin:0 3px}
.gear{position:absolute;opacity:.08;pointer-events:none}
details.card summary{cursor:pointer;font:700 1.1rem var(--fd);letter-spacing:.04em;text-transform:uppercase}
.pts{font:600 .75rem var(--fm);color:var(--muted)}
.score{display:flex;gap:18px;align-items:center;flex-wrap:wrap}
.score .n{font:700 3.4rem var(--fd);color:var(--green);line-height:1}
@media (max-width:820px){
 .hero,.sim,.grid2,.grid3{grid-template-columns:1fr}
 .prog i{width:60px} .top nav{order:3;flex:1 0 100%;overflow-x:auto;flex-wrap:nowrap}
 .panel{padding:14px} body{font-size:16px}
}
@media (prefers-reduced-motion:reduce){*{transition:none!important;animation:none!important}}
svg text{font-family:'IBM Plex Mono',monospace;font-size:13px;fill:var(--ink);paint-order:stroke;stroke:var(--bg);stroke-width:3px;stroke-linejoin:round}
svg .tx2{fill:var(--tan);font-weight:600} svg .txg{fill:var(--green);font-weight:600} svg .txr{fill:var(--bad);font-weight:600}
svg{}.lk>*{display:none!important}.lk::before{content:attr(data-msg);display:block;padding:18px;border:2px dashed var(--ink);background:var(--amber-soft);color:var(--ink);font-weight:700}</style>
<header class="top"><div class="in">
 <span class="brand">⚙ BENGKEL SINGGUNG</span>
 <nav aria-label="Navigasi">
  <a href="#mulai">Mulai</a><a href="#diagnostik">Cek Awal</a><a href="#m1">Misi 1</a><a href="#m2">Misi 2</a><a href="#m3">Misi 3</a><a href="#akhir">Tantangan &amp; Refleksi</a><a href="#kirim">Kirim</a>
 </nav>
 <div class="prog" title="Tahap yang sudah kamu selesaikan"><span id="pgt">0/18</span><i><b id="pgb"></b></i></div>
 <a class="chip" id="sdot" href="#kirim" style="text-decoration:none">…</a><button class="thm" id="thm" type="button" aria-label="Ganti tema terang atau gelap">Tema</button>
</div></header>

<main class="wrap">
<section class="hero blk" id="mulai">
 <div>
  <div class="chips"><span class="chip">Matematika · Fase F · Kelas XI</span><span class="chip a">Pembelajaran Mendalam</span><span class="chip m">Discovery Learning</span></div>
  <h1 style="margin-top:14px">Bengkel <em>Garis</em> Singgung</h1>
  <p class="lead">Kamu montir muda di bengkel roda, rantai, dan sabuk. Tiga gambar kerja menunggumu. Setiap rumus kamu temukan sendiri dari data yang kamu ukur, lalu kamu uji pada soal nyata.</p>
  <div class="tb" aria-label="Kepala gambar">
   <div class="w2"><small>Satuan pendidikan</small>SMA Muhammadiyah 01 Medan</div>
   <div><small>Materi</small>Lingkaran · Garis Singgung</div><div><small>Alokasi</small>3 pertemuan × 3 JP</div>
   <div><small>Penyusun</small>Yarti Melvina Rambe, Maysaroh Pos Pos</div><div><small>Skala</small>1 kotak = 1 cm</div>
  </div>
 </div>
 <div class="card">
  <h4>Pelacak tujuan (berkesadaran)</h4>
  <p class="sm mut">Kamu dinyatakan mencapai tujuan bila skor latihan minimal 3 dari 4 (kategori Cakap). Centang saat kamu yakin bisa menjelaskan sendiri.</p>
  <div id="tps"></div>
 </div>
</section>

<section class="blk" id="identitas"><style>#identitas input{padding:8px 10px;border:1.5px solid var(--ink);background:var(--paper);color:var(--ink);font:inherit;border-radius:3px}</style><div class="card"><h4>Identitas siswa</h4><p class="sm mut">Wajib diisi agar hasilmu terekam dan bisa dikirim ke guru.</p><div class="row" style="flex-wrap:wrap;gap:10px"><input id="idn" placeholder="Nama lengkap" autocomplete="name" style="flex:2;min-width:180px"><input id="idk" placeholder="Kelas (mis. XI-1)" style="flex:1;min-width:110px"><input id="ida" placeholder="No. absen" inputmode="numeric" style="width:110px"></div></div></section>
<section class="blk" id="diagnostik">
 <div class="sechd"><span class="no">CEK AWAL</span><h2>Siapkan perkakasmu</h2></div>
 <p>Lima pertanyaan singkat untuk memetakan bekal yang kamu bawa. Ini bukan nilai akhir.</p>
 <div class="grid2"><div id="diag" class="card"></div>
  <div class="card soft"><h4>Kartu bantu Pythagoras</h4>
   <p class="sm mut">Tripel yang sering muncul. Hafal pola ini untuk memeriksa hasil hitunganmu.</p>
   <svg viewBox="0 0 300 130" role="img" aria-label="Segitiga siku-siku 5, 12, 13" style="width:100%;max-width:340px">
    <polygon points="20,110 220,110 220,22" fill="var(--green-soft)" stroke="var(--ink)" stroke-width="2"/>
    <rect x="204" y="94" width="16" height="16" fill="none" stroke="var(--bad)" stroke-width="2"/>
    <text x="110" y="126">12</text><text x="228" y="70">5</text><text x="100" y="56" class="tx2">13</text></svg>
   <p class="fx">3-4-5 · 5-12-13 · 8-15-17 · 7-24-25</p>
   <p class="sm">Contoh: sisi miring 13, satu sisi 5, maka sisi lain = <span class="rad"><span>√</span><span class="ov">13² − 5²</span></span> = 12.</p>
  </div></div>
</section>

<section class="blk" id="m1"></section>
<section class="blk" id="m2"></section>
<section class="blk" id="m3"></section>

<section class="blk" id="akhir">
 <div class="sechd"><span class="no">AKHIR</span><h2>Tantangan, nilai, dan refleksi</h2></div>
 <div class="grid2">
  <div class="card" id="chal"></div>
  <div class="card" id="final"></div>
 </div>
 <div class="card" id="kirim" style="margin-top:16px"></div>
 <details class="card soft" style="margin-top:16px"><summary>Glosarium</summary><div id="glos" style="margin-top:10px"></div></details>
</section>
<p class="sm mut" style="margin-top:30px">Media ajar interaktif untuk Modul Ajar Kurikulum Merdeka, Matematika Kelas XI. Catatan dan skor tersimpan otomatis di perangkat ini dan dikirim ke guru lewat bagian Kirim hasil.</p>
</main>
<script>
const $=(s,r=document)=>r.querySelector(s),$$=(s,r=document)=>[...r.querySelectorAll(s)];
let ST={},OKS=true;try{ST=JSON.parse(localStorage.getItem('bgs1'))||{}}catch(e){OKS=false}
['diag','done','pts','note','tp','stage','cb','ans','mc','cz','rows','chal','nq','profile','sync'].forEach(k=>ST[k]=ST[k]||{});
const save=()=>{try{localStorage.setItem('bgs1',JSON.stringify(ST));OKS=true}catch(e){OKS=false}onSaved()};
const f=(x,d=2)=>(+x).toFixed(d).replace(/\.?0+$/,'').replace('.',',');
const rt=x=>`<span class="rad">√<span class="ov">${x}</span></span>`;
const RT={rows:ST.rows};let CUR={};const txt=h=>String(h).replace(/<[^>]+>/g,'').slice(0,90),hs=s=>{let h=0;for(const c of s)h=(h*31+c.charCodeAt(0))|0;return h.toString(36)};
const D2R=Math.PI/180;
const sub=(a,b)=>[a[0]-b[0],a[1]-b[1]], nrm=v=>{const l=Math.hypot(v[0],v[1])||1;return[v[0]/l,v[1]/l]};
const PT=(o,l,a)=>[o[0]+l*Math.cos(a),o[1]-l*Math.sin(a)];
const ln=(a,b,c,w=2,x='')=>`<line x1="${a[0].toFixed(1)}" y1="${a[1].toFixed(1)}" x2="${b[0].toFixed(1)}" y2="${b[1].toFixed(1)}" stroke="${c}" stroke-width="${w}" stroke-linecap="round" ${x}/>`;
const tx=(p,t,c='')=>`<text x="${p[0].toFixed(1)}" y="${p[1].toFixed(1)}" text-anchor="middle" dominant-baseline="middle" class="${c}">${t}</text>`;
const dot=(p,c='var(--ink)',r=4.5)=>`<circle cx="${p[0].toFixed(1)}" cy="${p[1].toFixed(1)}" r="${r}" fill="${c}"/>`;
const circ=(o,r,fill,st,w=2.5)=>`<circle cx="${o[0].toFixed(1)}" cy="${o[1].toFixed(1)}" r="${r.toFixed(1)}" fill="${fill}" stroke="${st}" stroke-width="${w}"/>`;
function sqm(V,a,b,s=11){const u=nrm(sub(a,V)),v=nrm(sub(b,V));const p=[[V[0]+u[0]*s,V[1]+u[1]*s],[V[0]+(u[0]+v[0])*s,V[1]+(u[1]+v[1])*s],[V[0]+v[0]*s,V[1]+v[1]*s]];
 return `<polyline points="${p.map(q=>q.map(z=>z.toFixed(1)).join(',')).join(' ')}" fill="none" stroke="var(--bad)" stroke-width="2"/>`}
function lab(a,b,c,t,cls,off=16){const m=[(a[0]+b[0])/2,(a[1]+b[1])/2],g=[(a[0]+b[0]+c[0])/3,(a[1]+b[1]+c[1])/3],d=nrm(sub(m,g));return tx([m[0]+d[0]*off,m[1]+d[1]*off],t,cls)}
function ptl(p,c,t,off=15){const d=nrm(sub(p,c));return tx([p[0]+d[0]*off,p[1]+d[1]*off],t,'txg')}
const SVG=(w,h,inner,al)=>`<svg viewBox="0 0 ${w} ${h}" role="img" aria-label="${al}">${inner}</svg>`;

/* ---------- gambar: roda dan jalan (h = jarak jalan ke pusat) ---------- */
function lineLab(S){const s=20,r=5,O=[300,110],h=S.h,y=O[1]+h*s,rr=r*s;
 let g=`<rect x="10" y="${y}" width="580" height="${290-y}" fill="var(--line)" opacity=".7"/>`;
 g+=ln([10,y],[590,y],'var(--ink)',4);
 g+=circ(O,rr,'var(--paper)','var(--ink)',6);
 for(let i=0;i<8;i++)g+=ln(O,PT(O,rr-3,i*Math.PI/4+S.h),'var(--muted)',1.5);
 g+=dot(O,'var(--ink)',7)+tx([O[0]+16,O[1]-14],'O');
 g+=ln(O,[O[0],y],'var(--tan)',2,'stroke-dasharray="6 4"')+tx([O[0]+54,O[1]+h*s/2+(h?0:-20)],`h = ${f(h,1)} cm`,'tx2');
 g+=tx([O[0]-70,O[1]-40],'r = 5 cm','txg')+ln(O,PT(O,rr,2.4),'var(--green)',2);
 if(h<r){const dx=Math.sqrt(r*r-h*h)*s;g+=dot([O[0]-dx,y],'var(--bad)',6)+dot([O[0]+dx,y],'var(--bad)',6)}
 else if(h===r){g+=dot([O[0],y],'var(--ok)',7)+tx([O[0]+22,y-14],'titik singgung','txg')}
 return SVG(600,300,g,'Roda berjari-jari 5 cm dan jalan pada jarak h dari pusat')}
const lineSt=h=>h<5?['bad',`Jalan <b>memotong</b> roda di 2 titik (roda "tenggelam" ke jalan).`]:h===5?['ok',`Jalan <b>menyinggung</b> roda di tepat 1 titik. Jarak pusat ke jalan = jari-jari.`]:['bad',`Jalan <b>tidak menyentuh</b> roda (roda melayang).`];

/* ---------- gambar: laboratorium sudut (garis melalui T diputar) ---------- */
function rotLab(S){const s=20,r=5,O=[300,150],rr=r*s,T=PT(O,rr,S.T*D2R),b=Math.atan2(O[1]-T[1],O[0]-T[0])+S.phi*D2R,dv=[Math.cos(b),Math.sin(b)];
 const tan=S.phi===90,c=tan?'var(--ok)':'var(--tan)';
 let g=circ(O,rr,'var(--paper)','var(--ink)',3)+ln([T[0]-dv[0]*260,T[1]-dv[1]*260],[T[0]+dv[0]*260,T[1]+dv[1]*260],c,4);
 g+=ln(T,O,'var(--green)',2.5,'stroke-dasharray="6 4"')+dot(O)+tx([O[0]+14,O[1]+14],'O')+dot(T,'var(--ink)',5.5)+ptl(T,O,'T',16);
 if(!tan){const q=[T[0]+dv[0]*2*rr*Math.cos(S.phi*D2R),T[1]+dv[1]*2*rr*Math.cos(S.phi*D2R)];g+=dot(q,'var(--bad)',6)}
 const u=nrm(sub(O,T)),m=nrm([u[0]+dv[0],u[1]+dv[1]]);
 g+=tan?sqm(T,O,[T[0]+dv[0],T[1]+dv[1]],13):'';
 g+=tx([T[0]+m[0]*(tan?34:40),T[1]+m[1]*(tan?34:40)],`${S.phi}°`,tan?'txg':'tx2');
 return SVG(600,300,g,'Lingkaran dan garis melalui titik T yang dapat diputar')}

/* ---------- gambar: titik A di luar lingkaran ---------- */
function pyth(o){const {r,d,ang=0,q,drag,tri=true}=o,s=9,O=[300,180],a=ang*D2R,A=PT(O,d*s,a),al=Math.acos(r/d),T1=PT(O,r*s,a+al),T2=PT(O,r*s,a-al),t=Math.sqrt(d*d-r*r);
 let g=circ(O,r*s,'var(--paper)','var(--ink)',3);
 if(tri)g+=`<polygon points="${[O,T1,A].map(p=>p.map(z=>z.toFixed(1)).join(',')).join(' ')}" fill="var(--green-soft)" opacity=".85"/>`;
 g+=ln(A,T2,'var(--tan)',3.5)+ln(A,T1,'var(--tan)',4.5)+ln(O,T2,'var(--green)',1.5,'stroke-dasharray="5 4"')+ln(O,T1,'var(--green)',2.5,'stroke-dasharray="6 4"')+ln(O,A,'var(--muted)',2,'stroke-dasharray="3 4"');
 g+=sqm(T1,O,A)+dot(O)+dot(T1)+dot(T2)+dot(A,'var(--ink)',5);
 const c=[(O[0]+T1[0]+A[0])/3,(O[1]+T1[1]+A[1])/3];
 g+=tx([O[0]-16,O[1]+(O[1]>c[1]?16:-16)],'O')+ptl(T1,c,'T')+ptl(T2,O,"T'",15)+ptl(A,c,'A',18);
 const L=(k,v,u='cm')=>q===k?'?':f(v)+' '+u;
 g+=lab(O,T1,A,'r = '+L('r',r),'txg')+lab(T1,A,O,'t = '+L('t',t),'tx2')+lab(O,A,T1,'d = '+L('d',d),'');
 if(drag)g+=`<circle data-drag="A" cx="${A[0].toFixed(1)}" cy="${A[1].toFixed(1)}" r="16" fill="var(--amber)" opacity=".35" stroke="var(--ink)" stroke-dasharray="3 3" style="cursor:grab"/>`;
 return SVG(600,360,g,`Lingkaran berpusat O dengan titik A di luar, jarak d dan jari-jari r`)}

/* ---------- gambar: dua lingkaran ---------- */
function twoC(o){const {mode,R,r,d,tri,belt,q,lower=true}=o,luar=mode==='luar',cs=luar?(R-r)/d:(R+r)/d,th=Math.acos(cs),
 s=Math.min(540/(R+d+r),135/Math.max(R,r)),left=(600-s*(R+d+r))/2,O=[left+R*s,170],Pp=[O[0]+d*s,170];
 const n=a=>[Math.cos(a),Math.sin(a)];
 const A=PT(O,R*s,th),B=luar?PT(Pp,r*s,th):PT(Pp,r*s,th+Math.PI),A2=PT(O,R*s,-th),B2=luar?PT(Pp,r*s,-th):PT(Pp,r*s,Math.PI-th);
 const S_=luar?PT(O,(R-r)*s,th):PT(O,(R+r)*s,th),L=Math.hypot(A[0]-B[0],A[1]-B[1])/s;
 let g='';
 if(belt){const p=x=>x.map(z=>z.toFixed(1)).join(' ');
  const path=luar?`M${p(A)} L${p(B)} A${r*s} ${r*s} 0 0 1 ${p(B2)} L${p(A2)} A${R*s} ${R*s} 0 1 1 ${p(A)}Z`
  :`M${p(A)} L${p(B)} A${r*s} ${r*s} 0 1 0 ${p(B2)} L${p(A2)} A${R*s} ${R*s} 0 1 1 ${p(A)}Z`;
  g+=`<path d="${path}" fill="var(--amber-soft)" stroke="var(--belt)" stroke-width="7" stroke-linejoin="round" opacity=".95"/>`}
 g+=circ(O,R*s,belt?'var(--paper)':'none','var(--ink)',3)+circ(Pp,r*s,belt?'var(--paper)':'none','var(--ink)',3);
 if(belt){for(let i=0;i<6;i++){g+=ln(O,PT(O,R*s-3,i*Math.PI/3),'var(--muted)',1.2)+ln(Pp,PT(Pp,r*s-3,i*Math.PI/3),'var(--muted)',1.2)}}
 if(lower&&!belt)g+=ln(A2,B2,'var(--tan)',2,'stroke-dasharray="7 5" opacity=".55"');
 if(tri&&!belt)g+=`<polygon points="${[O,S_,Pp].map(p=>p.map(z=>z.toFixed(1)).join(',')).join(' ')}" fill="var(--green-soft)" opacity=".9"/>`;
 g+=ln(O,Pp,'var(--muted)',2,'stroke-dasharray="3 4"');
 g+=ln(A,B,'var(--tan)',belt?2:4.5)+ln(O,A,'var(--green)',2,'stroke-dasharray="6 4"')+ln(Pp,B,'var(--green)',2,'stroke-dasharray="6 4"');
 if(!belt){if(tri){g+=ln(Pp,S_,'var(--tan)',2.5,'stroke-dasharray="2 4"');if(!luar)g+=ln(A,S_,'var(--green)',2.5,'stroke-dasharray="6 4"');g+=sqm(S_,O,Pp,10)+dot(S_,'var(--bad)',4)}
  g+=sqm(A,O,B,10)+sqm(B,Pp,A,10)}
 g+=dot(O)+dot(Pp)+dot(A)+dot(B);
 const cen=[(O[0]+Pp[0]+A[0])/3,(O[1]+Pp[1]+A[1])/3],lb=(k,v)=>q===k?'?':f(v);
 g+=tx([O[0]-14,O[1]+16],'O')+tx([Pp[0]+14,Pp[1]+16],'P')+ptl(A,O,luar?'A':'C',16)+ptl(B,Pp,luar?'B':'D',16);
 if(tri&&!belt)g+=ptl(S_,[(O[0]+S_[0]+Pp[0])/3,(O[1]+S_[1]+Pp[1])/3],'S',14);
 g+=lab(O,A,Pp,'R='+lb('R',R),'txg',18)+lab(Pp,B,O,'r='+lb('r',r),'txg',18);
 g+=tx([(O[0]+Pp[0])/2,O[1]+16],'d='+lb('d',d));
 const mid=[(A[0]+B[0])/2,(A[1]+B[1])/2];g+=tx([mid[0],mid[1]-16],(luar?'L = ':'L = ')+lb('L',L),'tx2');
 if(tri&&!belt)g+=lab(O,S_,Pp,luar?'R−r':'R+r','txr',16);
 return SVG(600,340,g,'Dua lingkaran berpusat O dan P dengan garis singgung persekutuan '+mode)}
const twoL=o=>{const c=o.mode==='luar'?(o.R-o.r):(o.R+o.r);return Math.sqrt(o.d*o.d-c*c)};

/* ---------- laboratorium generik ---------- */
let UID=0;
function mkLab(root,cfg){
 const id='lb'+(++UID),S={...cfg.init},rows=cfg.key?(RT.rows[cfg.key]=RT.rows[cfg.key]||[]):[];
 const sl=cfg.sliders.map((k,i)=>`<div class="sl"><label for="${id}s${i}">${k.l}<output id="${id}o${i}"></output></label><input type="range" id="${id}s${i}" min="${k.min}" max="${k.max}" step="${k.step||1}"></div>`).join('');
 const tg=cfg.toggle?`<div class="seg" role="group" aria-label="${cfg.toggle.l}">${cfg.toggle.o.map(([v,t])=>`<button type="button" data-tg="${v}">${t}</button>`).join('')}</div>`:'';
 root.innerHTML=`<div class="sim"><div><div class="fig"></div><div class="ro" aria-live="polite"></div></div><div class="ctl">${tg}${sl}${cfg.note?`<p class="sm mut" style="margin:0">${cfg.note}</p>`:''}${cfg.cols?'<div class="row"><button class="btn rec" type="button">＋ Catat data</button><button class="btn g s clr" type="button">Hapus</button></div>':''}</div></div>${cfg.cols?'<div class="tbl" style="margin-top:12px"></div>':''}`;
 const fig=$('.fig',root),ro=$('.ro',root),tb=$('.tbl',root);
 function table(){if(!tb)return;tb.innerHTML=`<table><thead><tr><th>#</th>${cfg.cols.map(c=>`<th>${c.h}</th>`).join('')}</tr></thead><tbody>${rows.length?rows.map((r,i)=>`<tr><td>${i+1}</td>${cfg.cols.map(c=>`<td>${c.f(r)}</td>`).join('')}</tr>`).join(''):`<tr><td colspan="${cfg.cols.length+1}" style="text-align:left;font-family:var(--fb)">Belum ada data. Atur gambar lalu tekan "Catat data".</td></tr>`}</tbody></table>`;cfg.onrows&&cfg.onrows(rows,root)}
 function upd(){const L=cfg.limits?cfg.limits(S):{};
  cfg.sliders.forEach((k,i)=>{const e=$('#'+id+'s'+i,root);const lo=L[k.k]?.min??k.min,hi=L[k.k]?.max??k.max;e.min=lo;e.max=hi;S[k.k]=Math.min(hi,Math.max(lo,S[k.k]));e.value=S[k.k];$('#'+id+'o'+i,root).textContent=' '+f(S[k.k],1)+(k.u||'')});
  $$('[data-tg]',root).forEach(b=>b.setAttribute('aria-pressed',S[cfg.toggle.k]===b.dataset.tg));
  fig.innerHTML=cfg.draw(S);ro.innerHTML=cfg.ro(S)}
 cfg.sliders.forEach((k,i)=>$('#'+id+'s'+i,root).addEventListener('input',e=>{S[k.k]=+e.target.value;upd()}));
 $$('[data-tg]',root).forEach(b=>b.onclick=()=>{S[cfg.toggle.k]=b.dataset.tg;upd()});
 if(cfg.cols){$('.rec',root).onclick=()=>{rows.push({...S,...cfg.measure(S)});if(rows.length>12)rows.shift();table();save()};$('.clr',root).onclick=()=>{rows.length=0;table();save()}}
 if(cfg.drag){let dg=false;fig.addEventListener('pointerdown',e=>{if(e.target.closest('[data-drag]')){dg=true;e.preventDefault()}});
  window.addEventListener('pointermove',e=>{if(!dg||!root.isConnected)return;const sv=fig.querySelector('svg');const p=new DOMPoint(e.clientX,e.clientY).matrixTransform(sv.getScreenCTM().inverse());cfg.drag(S,p.x,p.y);upd()});
  window.addEventListener('pointerup',()=>dg=false)}
 upd();table();return S}
/* ---------- komponen umum ---------- */
function mc(host,list,ci,expl,onOk){let done=false;const mk=(CUR.m||'')+(CUR.k||'')+':'+hs(list.join('|'));
 host.innerHTML=list.map((t,i)=>`<div class="opt" role="button" tabindex="0" data-i="${i}">${t}</div>`).join('')+'<div class="fb" aria-live="polite"></div>';
 const fb=$('.fb',host);
 $$('.opt',host).forEach(o=>{const go=()=>{if(done)return;const good=+o.dataset.i===ci,rc=ST.mc[mk]=ST.mc[mk]||{n:0,ok:false,q:txt(list[ci]),sel:[]};rc.n++;rc.ok=rc.ok||good;rc.sel.push(txt(list[+o.dataset.i]));save();if(good){done=true;o.classList.add('ok');fb.className='fb ok';fb.innerHTML='Tepat. '+expl;onOk&&onOk()}else{o.classList.add('bad');fb.className='fb bad';fb.textContent='Belum tepat. Baca ulang pilihannya, lalu coba yang lain.'}};
  o.onclick=go;o.onkeydown=e=>{if(e.key==='Enter'||e.key===' '){e.preventDefault();go()}}})}
const stepper=steps=>`<div class="sol" data-sp>${steps.map((s,i)=>`<div class="st" ${i?'hidden':''}>${s}</div>`).join('')}<div class="row" style="margin-top:8px"><button class="btn s" type="button" data-nx>Langkah berikutnya</button><span class="pts">1/${steps.length}</span></div></div>`;
function wire(root){
 $$('[data-sp]',root).forEach(sp=>{const b=$('[data-nx]',sp),st=$$('.st',sp),c=$('.pts',sp);let n=1;b.onclick=()=>{if(n<st.length){st[n].hidden=false;n++;c.textContent=n+'/'+st.length;if(n===st.length)b.hidden=true}}});
 $$('textarea[data-note]',root).forEach(t=>{const k=t.dataset.note,qq=()=>ST.nq[k]=(t.previousElementSibling?.textContent||t.getAttribute('aria-label')||k).trim();t.value=ST.note[k]||'';if(t.value)qq();t.oninput=()=>{ST.note[k]=t.value;qq();save()}})}
const sel=(list,ok)=>`<select data-a="${ok}" aria-label="pilih jawaban"><option value="">pilih…</option>${list.map(x=>`<option>${x}</option>`).join('')}</select>`;
function cloze(host,lines,formula,onOk){const ck=(CUR.m||'')+(CUR.k||'')+':cz';
 host.innerHTML=`<div class="cloze">${lines.map(l=>`<p>${l}</p>`).join('')}</div><div class="row"><button class="btn" type="button">Periksa kesimpulan</button></div><div class="fb" aria-live="polite"></div><div class="big" hidden>${formula}</div>`;
 $('.btn',host).onclick=()=>{let ok=true;$$('select',host).forEach(s=>{const g=s.value===s.dataset.a;s.style.borderColor=g?'var(--ok)':'var(--bad)';if(!g)ok=false});
  const cr=ST.cz[ck]=ST.cz[ck]||{n:0,ok:false};cr.n++;cr.ok=cr.ok||ok;cr.v=$$('select',host).map(s=>s.value).join(' | ');save();const fb=$('.fb',host);fb.className='fb '+(ok?'ok':'bad');fb.textContent=ok?'Kesimpulanmu tepat. Ini rumus yang kamu temukan sendiri:':'Masih ada yang keliru (kotak merah). Lihat lagi tabel data dan gambar segitiga.';$('.big',host).hidden=!ok;if(ok)onOk&&onOk()}}
function reflect(qs,m){return `<h4>Refleksi</h4>`+qs.map((q,i)=>`<p style="margin:10px 0 4px"><b>${i+1}.</b> ${q}</p><textarea data-note="${m}r${i}" aria-label="Jawaban refleksi ${i+1}" placeholder="Tulis dengan kata-katamu sendiri"></textarea>`).join('')}

/* ---------- soal latihan dengan bantuan bertahap ---------- */
RT.lvl={};
function problems(host,m,list,onAll){
 const lv=RT.lvl[m]=RT.lvl[m]||'full',N={full:['Lengkap',2],key:['Kunci',3],self:['Mandiri',4]};
 host.innerHTML=`<div class="note"><b>Bantuan bertahap.</b> Pilih seberapa banyak bantuan yang kamu butuhkan. Lengkap menghasilkan skor 2, Kunci skor 3, Mandiri skor 4. Skor 3 ke atas berarti Cakap.</div>
 <div class="seg" role="group" aria-label="Tingkat bantuan" style="max-width:420px">${Object.entries(N).map(([k,v])=>`<button type="button" data-l="${k}" aria-pressed="${k===lv}">${v[0]}</button>`).join('')}</div>
 <div class="pl" style="display:flex;flex-direction:column;gap:14px">${list.map((p,i)=>`<div class="pb" id="pb-${p.id}"><div class="q"><span class="chip">Soal ${i+1}</span> ${p.q}</div>${p.fig?`<div class="fig" style="max-width:480px">${p.fig}</div>`:''}<div class="hint"></div>
 <div class="row"><input class="num" type="text" inputmode="decimal" aria-label="Jawaban soal ${i+1}" placeholder="…"> <span>${p.unit||''}</span><button class="btn s ck" type="button">Periksa</button><button class="btn g s sh" type="button" hidden>Lihat penyelesaian</button><span class="pts"></span></div><div class="fb" aria-live="polite"></div><div class="sol" hidden>${p.sol.map(s=>`<div class="st">${s}</div>`).join('')}</div></div>`).join('')}</div>`;
 const hints=()=>{const l=RT.lvl[m];list.forEach(p=>{const h=$('#pb-'+p.id+' .hint',host);h.hidden=l==='self';h.innerHTML=l==='full'?'<b>Petunjuk lengkap:</b> '+p.full:'<b>Langkah kunci:</b> '+p.key});$$('[data-l]',host).forEach(b=>b.setAttribute('aria-pressed',b.dataset.l===l))};
 $$('[data-l]',host).forEach(b=>b.onclick=()=>{RT.lvl[m]=b.dataset.l;hints()});
 const chk=()=>{if(list.every(p=>ST.pts[p.id])){onAll&&onAll()}};
 list.forEach(p=>{const box=$('#pb-'+p.id,host),inp=$('input',box),fb=$('.fb',box),sh=$('.sh',box),so=$('.sol',box);let wrong=0;if(ST.ans[p.id])inp.value=ST.ans[p.id].v;
  const show=()=>{so.hidden=false};
  const upd=()=>{if(ST.pts[p.id]){box.classList.add('ok');$('.pts',box).textContent='skor '+ST.pts[p.id]}};upd();
  $('.ck',box).onclick=()=>{const v=parseFloat(inp.value.replace(',','.'));if(isNaN(v)){fb.className='fb bad';fb.textContent='Isi dulu jawabanmu dengan angka.';return}
   const okA=Math.abs(v-p.ans)<=(p.tol??0.011),pr=ST.ans[p.id]||{n:0};ST.ans[p.id]={v:inp.value,n:pr.n+1,ok:okA||!!pr.ok,lvl:RT.lvl[m],t:Date.now()};save();if(okA){const sc=N[RT.lvl[m]][1];ST.pts[p.id]=Math.max(ST.pts[p.id]||0,sc);save();fb.className='fb ok';fb.textContent='Benar. Penyelesaian di bawah dapat kamu cocokkan dengan caramu.';show();upd();chk();refresh()}
   else{wrong++;fb.className='fb bad';fb.textContent=wrong>1?'Belum tepat. Periksa pemilihan rumus dan tanda hitungnya.':'Belum tepat. Cek lagi: sisi mana yang miring, dan sisi mana yang tegak?';if(wrong>1)sh.hidden=false}};
  inp.onkeydown=e=>{if(e.key==='Enter')$('.ck',box).click()};sh.onclick=show});
 hints()}
const FIX=(a,b)=>`${a}`;

/* ---------- cek awal ---------- */
const DQ=[['Apa yang dimaksud jari-jari lingkaran?',['Ruas garis dari pusat ke titik pada lingkaran','Garis yang menyentuh lingkaran di satu titik','Dua kali panjang diameter'],0,'unsur lingkaran','Jari-jari menghubungkan pusat dengan titik pada lingkaran.'],
 ['Berapa sudut antara dua garis yang saling tegak lurus?',['45°','90°','180°'],1,'garis tegak lurus','Tegak lurus berarti membentuk sudut siku-siku 90°.'],
 ['Sisi siku-siku sebuah segitiga 3 cm dan 4 cm. Berapa sisi miringnya?',['5 cm','7 cm','12 cm'],0,'Pythagoras','3² + 4² = 25, akar 25 = 5.'],
 [`Hitung ${rt('13² − 5²')}.`,['8','12','18'],1,'Pythagoras dan pangkat','169 − 25 = 144, akar 144 = 12.'],
 [`Sederhanakan ${rt('72')}.`,['8√3','36','6√2'],2,'bentuk akar','72 = 36 × 2, jadi akar 72 = 6√2.']];
function diag(){const h=$('#diag');h.innerHTML=DQ.map((q,i)=>`<div style="margin-bottom:14px"><p style="margin:0 0 6px"><b>${i+1}.</b> ${q[0]}</p><div data-q="${i}"></div></div>`).join('')+'<div id="dsum"></div>';
 DQ.forEach((q,i)=>{const host=$(`[data-q="${i}"]`);const o=q[1].map((t,j)=>`<div class="opt" role="button" tabindex="0" data-i="${j}">${t}</div>`).join('');host.innerHTML=o+'<div class="fb"></div>';
  const mark=(j)=>{const ok=j===q[2];$$('.opt',host).forEach(e=>{if(+e.dataset.i===q[2])e.classList.add('ok');else if(+e.dataset.i===j)e.classList.add('bad')});$('.fb',host).className='fb '+(ok?'ok':'bad');$('.fb',host).textContent=(ok?'Tepat. ':'Belum tepat. ')+q[4]};
  if(ST.diag[i]!==undefined)mark(ST.diag[i]);
  $$('.opt',host).forEach(e=>{const go=()=>{if(ST.diag[i]!==undefined)return;ST.diag[i]=+e.dataset.i;save();mark(+e.dataset.i);dsum()};e.onclick=go;e.onkeydown=k=>{if(k.key==='Enter'||k.key===' '){k.preventDefault();go()}}})});
 function dsum(){if(Object.keys(ST.diag).length<DQ.length){$('#dsum').innerHTML='';return}
  const bad=DQ.filter((q,i)=>ST.diag[i]!==q[2]),n=DQ.length-bad.length;
  $('#dsum').innerHTML=`<div class="note ${bad.length?'':'ok'}"><b>${n} dari ${DQ.length} tepat.</b> ${bad.length?`Perkuat dulu: ${bad.map(q=>q[3]).join(', ')}. Di setiap soal latihan, mulai dengan Bantuan Lengkap dan pakai kartu bantu di samping.`:'Bekalmu lengkap. Kamu boleh memilih Bantuan Mandiri sejak awal.'}</div>`}
 dsum()}

/* ---------- kerangka misi ---------- */
const STG=[['stim','Stimulation','Memahami'],['prob','Problem Statement','Memahami'],['data','Data Collection','Memahami'],['proc','Data Processing','Memahami'],['ver','Verification','Mengaplikasi'],['gen','Generalization','Merefleksi']];
const MS=[];
function refresh(){if(window.kirimOn&&MS.length>2)locks();let n=0;MS.forEach(M=>STG.forEach(([k])=>{if(ST.done[M.id+k])n++}));$('#pgt').textContent=n+'/18';$('#pgb').style.width=(n/18*100)+'%';
 $$('.tab').forEach(t=>{t.classList.toggle('done',!!ST.done[t.dataset.m+t.dataset.k]);const fi=STG.findIndex(s=>!ST.done[t.dataset.m+s[0]]);t.style.opacity=fi>=0&&STG.findIndex(s=>s[0]===t.dataset.k)>fi?.45:1});
 const ids=[...M1P,...M2P,...M3P].map(p=>p.id),got=ids.filter(i=>ST.pts[i]),avg=got.length?got.reduce((s,i)=>s+ST.pts[i],0)/got.length:0;
 const cat=avg>=3.5?'Mahir':avg>=3?'Cakap':avg>=2?'Berkembang':'Perlu bimbingan';
 $('#final').innerHTML=`<h3>Rekap belajarmu</h3><div class="score" style="margin:10px 0"><div class="n">${got.length?Math.round(avg/4*100):'–'}</div><div><b>${got.length?cat:'Belum ada soal'}</b><br><span class="sm mut">Nilai = skor perolehan ÷ skor maksimal × 100, dari ${got.length} dari ${ids.length} soal latihan yang kamu selesaikan.</span></div></div>
 <div class="note ${avg>=3?'ok':''}">${!got.length?'Selesaikan soal di tahap Verification tiap misi.':avg>=3?'Kamu mencapai tujuan pembelajaran. Lanjutkan ke tantangan pengayaan.':'Skor rata-rata belum 3. Ulangi soal dengan Bantuan Kunci atau Mandiri, atau tinjau data dan segitiga di Data Processing.'}</div>
 <h4 style="margin-top:14px">Refleksi akhir</h4>`+['Konsep apa yang telah saya pahami?','Bagian materi apa yang masih sulit?','Apakah saya dapat membedakan garis singgung persekutuan luar dan dalam?'].map((q,i)=>`<p style="margin:10px 0 4px"><b>${i+1}.</b> ${q}</p><textarea data-note="fin${i}" aria-label="Refleksi akhir ${i+1}"></textarea>`).join('')+'<div class="row" style="margin-top:12px"><a class="btn" href="#kirim" style="text-decoration:none">Kirim hasil ke guru →</a></div>';wire($('#final'))}
function goStage(M,k){{const ti=STG.findIndex(s=>s[0]===k),fi=STG.findIndex(s=>!ST.done[M.id+s[0]]);if(fi>=0&&ti>fi)k=STG[fi][0]}CUR={m:M.id,k};ST.stage[M.id]=k;save();const host=$('#'+M.id),pn=$('.panel',host);
 $$('.tab',host).forEach(t=>t.setAttribute('aria-selected',t.dataset.k===k));
 const i=STG.findIndex(s=>s[0]===k),g=STG[i];
 pn.innerHTML=`<div class="ph"><span class="chip ${g[2]==='Mengaplikasi'?'a':g[2]==='Merefleksi'?'m':''}">${g[2]}</span><h3>${g[1]}</h3></div><div class="body" style="display:flex;flex-direction:column;gap:16px"></div><div class="navb"><button class="btn g" type="button" id="pv" ${i?'':'disabled'}>← Tahap sebelumnya</button><button class="btn" type="button" id="nx">${i<5?'Lanjut ke '+STG[i+1][1]+' →':'Selesai, lanjut misi berikutnya →'}</button></div><p class="sm" id="gmsg" style="margin:0;color:var(--bad)"></p>`;
 const b=$('.body',pn),nx=$('#nx',pn),need=()=>(k==='prob'||k==='gen')?$$('textarea[data-note]',b).every(t=>t.value.trim()):true,chk=()=>{if(ST.cb[M.id+k]&&need()&&!ST.done[M.id+k]){ST.done[M.id+k]=1;save();refresh()}const d=ST.done[M.id+k];nx.disabled=!d;$('#gmsg',pn).textContent=d?'':ST.cb[M.id+k]?'Isi semua kolom dugaan/refleksi dulu untuk lanjut.':'Jawab dulu kegiatan di tahap ini dengan benar untuk lanjut.'};M.st[k](b,()=>{ST.cb[M.id+k]=1;save();chk()});wire(b);b.addEventListener('input',chk);chk();
 $('#pv',pn).onclick=()=>goStage(M,STG[i-1][0]);
 $('#nx',pn).onclick=()=>{if(!ST.done[M.id+k])return;if(i<5){goStage(M,STG[i+1][0]);host.scrollIntoView({behavior:'smooth'})}else{const nx=document.getElementById(M.id==='m3'?'akhir':'m'+(M.no+1));nx&&nx.scrollIntoView({behavior:'smooth'})}};
 refresh()}
function mission(M){MS.push(M);const h=$('#'+M.id);
 h.innerHTML=`<div class="sechd"><span class="no">GAMBAR KERJA ${M.no}</span><h2>${M.title}</h2><span class="mut">Pertemuan ${M.no} · 3 JP</span></div>
 <div class="grid2" style="margin-bottom:16px"><div class="card soft"><h4>Tujuan misi</h4><p style="margin:6px 0 0">${M.tp}</p></div><div class="card soft"><h4>Konteks nyata</h4><p style="margin:6px 0 0">${M.ctx}</p></div></div>
 <div class="tabs" role="tablist" aria-label="Tahap belajar">${STG.map(([k,t,g])=>`<button class="tab" role="tab" type="button" data-m="${M.id}" data-k="${k}"><small>${g}</small>${t}</button>`).join('')}</div><div class="panel" role="tabpanel"></div>`;
 $$('.tab',h).forEach(t=>t.onclick=()=>goStage(M,t.dataset.k));goStage(M,ST.stage[M.id]||'stim')}
const measT=S=>{const s=9,O=[300,180],a=(S.ang||0)*D2R,A=PT(O,S.d*s,a),T1=PT(O,S.r*s,a+Math.acos(S.r/S.d));return{t:Math.hypot(A[0]-T1[0],A[1]-T1[1])/s}};
const measL=S=>({L:twoL(S)});
const THEME=()=>{const r=document.documentElement,c=r.dataset.theme||(matchMedia('(prefers-color-scheme:dark)').matches?'dark':'light');r.dataset.theme=c==='dark'?'light':'dark'};
/* ---------- bank soal ---------- */
const pf=(r,d,q)=>pyth({r,d,q,tri:true}), tf=(mode,R,r,d,q)=>twoC({mode,R,r,d,q,tri:true});
const M1P=[
 {id:'m1p1',q:'Garis PT menyinggung lingkaran di titik T, dan O adalah pusat lingkaran. Berapa besar ∠OTP?',ans:90,unit:'°',full:'OT adalah jari-jari dan PT garis singgung. Ingat temuanmu di Data Collection A.',key:'Hubungan jari-jari ke titik singgung dengan garis singgung.',sol:['OT jari-jari, PT garis singgung, keduanya bertemu di T.','Jari-jari ke titik singgung tegak lurus garis singgung.','Jadi ∠OTP = 90°.']},
 {id:'m1p2',q:'Jari-jari lingkaran 5 cm. Titik A berjarak 13 cm dari pusat. Tentukan panjang garis singgung t dari A.',fig:pf(5,13,'t'),ans:12,unit:'cm',full:'Segitiga OTA siku-siku di T, sisi miringnya d. Hitung t² = d² − r² = 13² − 5², lalu tarik akar.',key:'Gunakan t = √(d² − r²).',sol:[`t = ${rt('13² − 5²')}`,`t = ${rt('169 − 25')} = ${rt('144')} = 12 cm`]},
 {id:'m1p3',q:'Jari-jari lingkaran 8 cm dan panjang garis singgung dari titik A adalah 15 cm. Tentukan jarak titik A ke pusat.',fig:pf(8,17,'d'),ans:17,unit:'cm',full:'Sekarang yang dicari sisi miring. d² = r² + t² = 8² + 15². Hitung lalu tarik akar.',key:'Sisi miring: d = √(r² + t²).',sol:[`d = ${rt('8² + 15²')}`,`d = ${rt('64 + 225')} = ${rt('289')} = 17 cm`]},
 {id:'m1p4',q:'Sebuah taman berbentuk lingkaran berjari-jari 9 m. Titik di jalan berjarak 15 m dari pusat taman. Berapa panjang garis singgung dari titik itu ke taman?',fig:pf(9,15,'t'),ans:12,unit:'m',full:'Jari-jari 9 m, jarak ke pusat 15 m. t² = 15² − 9². Hitung lalu tarik akar.',key:'Jarak ke pusat adalah sisi miring. t = √(d² − r²).',sol:[`t = ${rt('15² − 9²')} = ${rt('225 − 81')} = ${rt('144')} = 12 m`]}];
const M2P=[
 {id:'m2p1',q:'Dua lingkaran berjari-jari 8 cm dan 3 cm dengan jarak pusat 13 cm. Tentukan panjang garis singgung persekutuan luar.',fig:tf('luar',8,3,13,'L'),ans:12,unit:'cm',full:'Sisi tegak segitiga = R − r = 8 − 3 = 5. L² = d² − 5² = 169 − 25. Hitung lalu tarik akar.',key:'Garis singgung luar memakai selisih jari-jari: L = √(d² − (R − r)²).',sol:[`L = ${rt('13² − (8 − 3)²')} = ${rt('169 − 25')} = ${rt('144')} = 12 cm`]},
 {id:'m2p2',q:'Dua lingkaran berjari-jari 10 cm dan 4 cm. Panjang garis singgung persekutuan luarnya 8 cm. Tentukan jarak kedua pusat.',fig:tf('luar',10,4,10,'d'),ans:10,unit:'cm',full:'Sekarang d yang dicari: d² = L² + (R − r)² = 8² + 6². Hitung lalu tarik akar.',key:'d = √(L² + (R − r)²).',sol:[`d = ${rt('8² + (10 − 4)²')} = ${rt('64 + 36')} = ${rt('100')} = 10 cm`]},
 {id:'m2p3',q:'Jarak kedua pusat 25 cm, jari-jari 13 cm dan 8 cm. Tentukan panjang garis singgung persekutuan luar (dua angka desimal).',fig:tf('luar',13,8,25,'L'),ans:24.49,tol:.02,unit:'cm',full:'R − r = 5. L² = 25² − 5² = 625 − 25 = 600. L = √600 = 10√6.',key:'L = √(d² − (R − r)²), lalu hampiri akarnya.',sol:[`L = ${rt('25² − (13 − 8)²')} = ${rt('600')} = 10${rt('6')} ≈ 24,49 cm`]},
 {id:'m2p4',q:'Dua gir berjari-jari 7 cm dan 2 cm dipasang dengan jarak pusat 13 cm. Rantai dipasang tanpa menyilang. Berapa panjang bagian rantai yang lurus pada sisi atas?',fig:twoC({mode:'luar',R:7,r:2,d:13,belt:true,q:'L'}),ans:12,unit:'cm',full:'Rantai tanpa menyilang adalah garis singgung persekutuan luar. R − r = 5, d = 13.',key:'L = √(d² − (R − r)²).',sol:[`L = ${rt('13² − (7 − 2)²')} = ${rt('169 − 25')} = ${rt('144')} = 12 cm`]}];
const M3P=[
 {id:'m3p1',q:'Dua lingkaran berjari-jari 3 cm dan 2 cm dengan jarak pusat 13 cm. Tentukan panjang garis singgung persekutuan dalam.',fig:tf('dalam',3,2,13,'L'),ans:12,unit:'cm',full:'Sisi tegak segitiga = R + r = 3 + 2 = 5. L² = 13² − 5². Hitung lalu tarik akar.',key:'Garis singgung dalam memakai jumlah jari-jari: L = √(d² − (R + r)²).',sol:[`L = ${rt('13² − (3 + 2)²')} = ${rt('169 − 25')} = ${rt('144')} = 12 cm`]},
 {id:'m3p2',q:'Jarak kedua pusat 17 cm dan panjang garis singgung persekutuan dalam 15 cm. Jari-jari lingkaran besar 6 cm. Tentukan jari-jari lingkaran kecil.',fig:tf('dalam',6,2,17,'r'),ans:2,unit:'cm',full:'Cari R + r dulu: (R + r)² = d² − L² = 289 − 225 = 64, jadi R + r = 8. Lalu r = 8 − 6.',key:'(R + r)² = d² − L². Setelah R + r ketemu, kurangi dengan R.',sol:[`(R + r)² = 17² − 15² = 289 − 225 = 64`,`R + r = 8, sehingga r = 8 − 6 = 2 cm`]},
 {id:'m3p3',q:'Dua lingkaran berjari-jari 7 cm dan 5 cm dengan jarak pusat 20 cm. Tentukan panjang garis singgung persekutuan dalam.',fig:tf('dalam',7,5,20,'L'),ans:16,unit:'cm',full:'R + r = 12. L² = 20² − 12² = 400 − 144. Hitung lalu tarik akar.',key:'L = √(d² − (R + r)²).',sol:[`L = ${rt('20² − (7 + 5)²')} = ${rt('400 − 144')} = ${rt('256')} = 16 cm`]},
 {id:'m3p4',q:'Dua katrol berjari-jari 6 cm dan 2 cm berjarak pusat 17 cm. Sabuk dipasang menyilang. Berapa panjang bagian sabuk yang lurus?',fig:twoC({mode:'dalam',R:6,r:2,d:17,belt:true,q:'L'}),ans:15,unit:'cm',full:'Sabuk menyilang adalah garis singgung persekutuan dalam. R + r = 8, d = 17.',key:'L = √(d² − (R + r)²).',sol:[`L = ${rt('17² − (6 + 2)²')} = ${rt('289 − 64')} = ${rt('225')} = 15 cm`]}];

/* ---------- tahap generik ---------- */
const probSt=(m,list,ci,expl,ph)=>(b,done)=>{b.innerHTML=`<p>Dari pengamatanmu, rumuskan masalah yang akan kamu selidiki.</p><div class="mcq"></div><h4>Dugaanmu</h4><textarea data-note="${m}d" aria-label="Dugaanmu" placeholder="${ph}"></textarea><div class="note ok">Dugaan tidak harus benar. Kamu mengujinya dengan data di tahap berikutnya.</div>`;mc($('.mcq',b),list,ci,expl,done)};
const SAMPLE={m1:[{r:5,d:13},{r:8,d:17},{r:3,d:5}],m2:[{mode:'luar',R:9,r:3,d:10},{mode:'luar',R:8,r:3,d:13},{mode:'luar',R:12,r:5,d:25}],m3:[{mode:'dalam',R:3,r:2,d:13},{mode:'dalam',R:6,r:2,d:17},{mode:'dalam',R:7,r:5,d:20}]};
const procSt=c=>(b,done)=>{const real=(RT.rows[c.key]||[]).length>0,rows=real?RT.rows[c.key]:SAMPLE[c.m].map(s=>({...s,...c.meas(s)})),val=r=>r.t??r.L;
 b.innerHTML=`<h4>Langkah 1 · Cocokkan dengan datamu</h4><p>${real?'Tabel memakai data yang kamu catat.':'Kamu belum mencatat data, jadi tabel memakai <b>data contoh</b>.'} Kolom mana yang nilainya selalu sama dengan <b>${c.tg}</b>?</p>
 <div class="tbl"><table><thead><tr><th>#</th>${c.vars.map(v=>`<th>${v}</th>`).join('')}<th>${c.tg}</th>${c.cands.map(x=>`<th>${x[0]}</th>`).join('')}</tr></thead><tbody>${rows.map((r,i)=>`<tr><td>${i+1}</td>${c.vars.map(v=>`<td>${f(r[v])}</td>`).join('')}<td><b>${f(val(r)**2)}</b></td>${c.cands.map(x=>`<td>${f(x[1](r))}</td>`).join('')}</tr>`).join('')}</tbody></table></div><div class="mcq"></div>
 <h4>Langkah 2 · Mengapa cocok? Turunkan dari segitiga siku-siku</h4><div class="sim"><div class="fig">${c.fig}</div><div>${stepper(c.derive)}</div></div>
 <h4>Langkah 3 · Contoh terbimbing</h4><div class="sim"><div class="fig">${c.ex.fig}</div><div><p>${c.ex.q}</p>${stepper(c.ex.steps)}</div></div>`;
 mc($('.mcq',b),c.cands.map(x=>x[0]),c.ok,c.why,done)};
const genSt=(m,lines,formula,qs,extra)=>(b,done)=>{b.innerHTML=`<p>Lengkapi kesimpulan dengan memilih kata yang tepat. Gunakan temuan dari data dan segitiganya.</p><div class="cz"></div><div class="ex"></div><div class="card soft">${reflect(qs,m)}</div>`;cloze($('.cz',b),lines,formula,done);extra&&extra($('.ex',b))};
const verSt=(m,list)=>(b,done)=>{b.innerHTML='<div class="pr"></div><div class="ex"></div>';problems($('.pr',b),m,list,done);return b};

/* ---------- misi 1 ---------- */
const M1={id:'m1',no:1,title:'Teorema Garis Singgung',tp:'Memakai sifat jari-jari tegak lurus garis singgung dan Teorema Pythagoras untuk menentukan sudut dan panjang garis singgung dari titik di luar lingkaran.',ctx:'Roda sepeda menyentuh jalan hanya di satu titik. Jalan lurus yang menyinggung taman berbentuk lingkaran.',st:{
 stim:(b,done)=>{b.innerHTML=`<p>Roda sepeda berjari-jari <b>5 cm</b> menyentuh jalan. Geser jalan naik-turun dan amati berapa titik yang tersentuh.</p><div class="l"></div><div class="card soft"><h4>Prediksi</h4><p>Saat roda <b>hanya menyentuh jalan di satu titik</b>, apa yang berlaku?</p><div class="q"></div></div><div class="note"><b>Pertanyaan pemantik.</b> Di titik sentuh, jari-jari ke titik itu membentuk sudut berapa terhadap jalan? Apakah selalu begitu, di titik sentuh mana pun?</div>`;
  mkLab($('.l',b),{init:{h:7},sliders:[{k:'h',l:'Jarak jalan ke pusat roda',min:0,max:8,step:.5,u:' cm'}],draw:lineLab,ro:S=>lineSt(S.h)[1]});
  mc($('.q',b),['Jarak pusat roda ke jalan lebih kecil dari jari-jari','Jarak pusat roda ke jalan sama dengan jari-jari','Jarak pusat roda ke jalan lebih besar dari jari-jari'],1,'Jalan menyinggung roda tepat saat jarak pusat ke jalan sama dengan jari-jari, yaitu 5 cm.',done)},
 prob:probSt('m1',['Berapa sudut antara jari-jari dan garis singgung di titik singgung, dan bagaimana menghitung panjang garis singgung dari titik di luar lingkaran bila r dan d diketahui?','Berapa keliling roda sepeda yang berjari-jari 5 cm?','Mengapa jalan raya dibuat datar?'],0,'Dua hal inilah yang akan kamu temukan: sudutnya dan rumus panjangnya.','Menurutku sudut antara jari-jari dan garis singgung adalah … dan panjang t dapat dihitung dengan …'),
 data:(b,done)=>{b.innerHTML=`<div class="card soft"><h4>Data A · Sudut jari-jari dan garis</h4><p class="sm">Garis selalu melalui titik T. Putar garis dengan penggeser sudut. Titik merah adalah titik potong kedua. Catat beberapa data, termasuk saat garis hanya menyentuh lingkaran di satu titik.</p><div class="la"></div><div class="note disc" hidden></div></div>
  <div class="card soft"><h4>Data B · Panjang garis singgung dari titik A</h4><p class="sm">Seret titik amber A atau pakai penggeser. Catat minimal 3 data dengan r dan d berbeda.</p><div class="lb"></div></div>`;
  const dc=$('.disc',b);
  mkLab($('.la',b),{init:{T:130,phi:60},key:'m1A',sliders:[{k:'T',l:'Posisi titik T',min:10,max:350,step:10,u:'°'},{k:'phi',l:'Sudut garis terhadap jari-jari OT',min:20,max:160,step:1,u:'°'}],draw:rotLab,ro:S=>`Garis memotong lingkaran di <b>${S.phi===90?1:2}</b> titik. Sudut = <b>${S.phi}°</b>`,
   cols:[{h:'posisi T',f:r=>r.T+'°'},{h:'sudut',f:r=>r.phi+'°'},{h:'titik sentuh',f:r=>r.N},{h:'status',f:r=>r.N===1?'singgung':'memotong'}],measure:S=>({N:S.phi===90?1:2}),
   onrows:rows=>{const t=rows.filter(r=>r.N===1);dc.hidden=rows.length<3;dc.className='note disc'+(t.length>=2?' ok':'');dc.innerHTML=t.length>=2?'<b>Temuanmu.</b> Setiap kali garis hanya menyentuh lingkaran di satu titik, sudutnya <b>90°</b>, di posisi T mana pun.':'Belum ada pola. Putar sudut sampai garis hanya menyentuh lingkaran di satu titik, catat, lalu ganti posisi T dan ulangi.';if(t.length>=2)done()}});
  mkLab($('.lb',b),{init:{r:5,d:13,ang:0},key:'m1B',sliders:[{k:'r',l:'Jari-jari r',min:2,max:8,u:' cm'},{k:'d',l:'Jarak A ke pusat O (d)',min:3,max:16,u:' cm'}],limits:S=>({d:{min:S.r+1,max:16}}),draw:S=>pyth({...S,drag:true,tri:false}),ro:S=>`Panjang garis singgung terukur: <b>t = ${f(measT(S).t)} cm</b>`,
   drag:(S,x,y)=>{const dx=(x-300)/9,dy=(180-y)/9;S.d=Math.max(S.r+1,Math.min(16,Math.round(Math.hypot(dx,dy)*2)/2));S.ang=Math.atan2(dy,dx)/D2R},
   cols:[{h:'r',f:r=>f(r.r)},{h:'d',f:r=>f(r.d)},{h:'t (ukur)',f:r=>f(r.t)},{h:'t²',f:r=>f(r.t*r.t)},{h:'d²−r²',f:r=>f(r.d*r.d-r.r*r.r)},{h:'d²+r²',f:r=>f(r.d*r.d+r.r*r.r)},{h:'(d−r)²',f:r=>f((r.d-r.r)**2)}],measure:measT})},
 proc:procSt({m:'m1',key:'m1B',meas:measT,vars:['r','d'],tg:'t²',cands:[['d² − r²',r=>r.d**2-r.r**2],['d² + r²',r=>r.d**2+r.r**2],['(d − r)²',r=>(r.d-r.r)**2]],ok:0,why:'Semua baris cocok persis dengan d² − r². Berarti t² + r² = d², yaitu Teorema Pythagoras. Langkah 2 menjelaskan alasannya.',fig:pyth({r:5,d:13,tri:true}),
  derive:['Garis singgung AT tegak lurus jari-jari OT di titik T. Maka segitiga OTA siku-siku di T.','Sisi miringnya OA = d. Sisi tegaknya OT = r dan TA = t.','Pythagoras: OT² + TA² = OA², yaitu r² + t² = d².','Pindahkan r²: t² = d² − r².',`Tarik akar: t = ${rt('d² − r²')}. Dari persamaan yang sama: d = ${rt('t² + r²')} dan r = ${rt('d² − t²')}.`],
  ex:{fig:pyth({r:7,d:25,tri:true}),q:'Titik A berjarak 25 cm dari pusat O, jari-jari 7 cm. Tentukan panjang garis singgung AB.',steps:['<b>Diketahui:</b> AO = d = 25 cm, BO = r = 7 cm.','<b>Ditanyakan:</b> panjang garis singgung AB.',`<b>Rumus:</b> segitiga ABO siku-siku di B, sehingga AB = ${rt('AO² − BO²')}.`,`<b>Substitusi:</b> AB = ${rt('25² − 7²')}.`,`<b>Hitung:</b> AB = ${rt('625 − 49')} = ${rt('576')} = 24.`,'<b>Kesimpulan:</b> AB = 24 cm. Garis singgung kedua dari A juga 24 cm, sebab dua garis singgung dari satu titik luar sama panjang.']}}),
 ver:verSt('m1',M1P),
 gen:genSt('m1',[`Garis singgung lingkaran selalu ${sel(['sejajar','tegak lurus','berimpit'],'tegak lurus')} dengan jari-jari di titik singgung, sehingga sudutnya ${sel(['45°','90°','180°'],'90°')}.`,`Dari satu titik di luar lingkaran dapat ditarik ${sel(['1','2','3'],'2')} garis singgung, dan panjangnya ${sel(['sama','berbeda'],'sama')}.`,`Rumus: t = ${rt('d² '+sel(['−','+'],'−')+' r²')}, karena OA = d adalah ${sel(['sisi miring','sisi tegak'],'sisi miring')} segitiga OTA.`],`t = ${rt('d² − r²')}`,['Apa sifat utama garis singgung lingkaran?','Mengapa jari-jari tegak lurus terhadap garis singgung?','Bagaimana menentukan panjang garis singgung dari titik di luar lingkaran?','Bagian mana yang masih sulit dipahami?'])}};

/* ---------- laboratorium dua lingkaran ---------- */
const twoLab=(key,mode,init,view)=>({init:{mode,...init},key,sliders:[{k:'R',l:'Jari-jari R',min:2,max:12,u:' cm'},{k:'r',l:'Jari-jari r',min:1,max:12,u:' cm'},{k:'d',l:'Jarak pusat d',min:2,max:28,u:' cm'}],
 limits:S=>({r:{max:S.R},d:{min:S.mode==='luar'?S.R-S.r+1:S.R+S.r+1,max:28}}),draw:S=>twoC({...S,tri:true}),ro:S=>`Panjang garis singgung terukur: <b>L = ${f(twoL(S))} cm</b>`,
 cols:[{h:'R',f:r=>r.R},{h:'r',f:r=>r.r},{h:'d',f:r=>r.d},{h:'L (ukur)',f:r=>f(r.L)},{h:'L²',f:r=>f(r.L*r.L)},{h:'d²−(R−r)²',f:r=>f(r.d**2-(r.R-r.r)**2)},{h:'d²−(R+r)²',f:r=>f(r.d**2-(r.R+r.r)**2)},{h:'d²−R²−r²',f:r=>f(r.d**2-r.R**2-r.r**2)}],measure:measL});
const beltLab=(mode,init)=>({init:{mode,view:'belt',...init},sliders:[{k:'R',l:'Jari-jari gir/katrol besar R',min:4,max:10,u:' cm'},{k:'r',l:'Jari-jari kecil r',min:2,max:10,u:' cm'},{k:'d',l:'Jarak pusat d',min:2,max:26,u:' cm'}],toggle:{k:'view',l:'Tampilan',o:[['belt','Rantai/sabuk'],['geo','Garis singgung']]},
 limits:S=>({r:{max:S.R},d:{min:mode==='luar'?S.R-S.r+1:S.R+S.r+1,max:26}}),draw:S=>twoC({...S,belt:S.view==='belt',tri:false}),ro:S=>`Bagian lurus rantai/sabuk: <b>${f(twoL(S))} cm</b>`});
const cmpTable=`<div class="tbl"><table><thead><tr><th>Ciri</th><th>Persekutuan luar</th><th>Persekutuan dalam</th></tr></thead><tbody><tr><td>Posisi kedua pusat</td><td style="text-align:left">sisi yang sama</td><td style="text-align:left">sisi berlawanan</td></tr><tr><td>Ruas penghubung pusat</td><td style="text-align:left">tidak dipotong</td><td style="text-align:left">dipotong</td></tr><tr><td>Sisi tegak segitiga</td><td class="fx">R − r</td><td class="fx">R + r</td></tr><tr><td>Rumus</td><td class="fx">${rt('d² − (R − r)²')}</td><td class="fx">${rt('d² − (R + r)²')}</td></tr><tr><td>Contoh nyata</td><td style="text-align:left">rantai tanpa menyilang</td><td style="text-align:left">sabuk menyilang</td></tr></tbody></table></div>`;
const exM=(mode,R,r,d,L)=>twoC({mode,R,r,d,tri:true});

/* ---------- misi 2 ---------- */
const M2={id:'m2',no:2,title:'Garis Singgung Persekutuan Luar',tp:'Menentukan panjang garis singgung persekutuan luar dua lingkaran dan menjelaskan mengapa rumusnya memakai selisih jari-jari.',ctx:'Rantai yang menghubungkan dua gir tanpa menyilang. Sabuk lurus di sisi atas dan bawah dua katrol.',st:{
 stim:(b,done)=>{b.innerHTML=`<p>Rantai menghubungkan dua gir tanpa menyilang. Ubah ukuran gir, lalu pindah ke tampilan <b>Garis singgung</b> untuk melihat kerangka geometrinya.</p><div class="l"></div><div class="card soft"><h4>Prediksi</h4><p>Bagian lurus rantai di sisi atas menyinggung kedua gir. Di mana pusat kedua gir terhadap bagian lurus itu?</p><div class="q"></div></div>`;
  mkLab($('.l',b),beltLab('luar',{R:9,r:3,d:14}));mc($('.q',b),['Di sisi yang sama, yaitu di bawah bagian lurus itu','Di sisi yang berlawanan','Tepat di atas garis rantai'],0,'Kedua pusat berada pada sisi yang sama. Garis seperti ini disebut garis singgung persekutuan luar.',done)},
 prob:probSt('m2',['Bagaimana menghitung panjang bagian lurus rantai (garis singgung persekutuan luar) bila d, R, dan r diketahui, dan mengapa rumusnya memakai selisih jari-jari?','Berapa banyak gigi yang dimiliki sebuah gir?','Berapa panjang seluruh rantai dalam satu putaran?'],0,'Tepat. Panjang seluruh rantai memuat busur, sedangkan kamu menyelidiki bagian lurusnya saja.','Menurutku panjang bagian lurusnya dihitung dengan … karena …'),
 data:(b,done)=>{b.innerHTML=`<p class="sm">Atur R, r, d lalu catat. Perhatikan kolom L² dan tiga kolom kandidat di sebelah kanannya. Catat minimal 3 data berbeda.</p><div class="l"></div>`;mkLab($('.l',b),{...twoLab('m2B','luar',{R:9,r:3,d:10}),onrows:rows=>{if(rows.length>=3)done()}})},
 proc:procSt({m:'m2',key:'m2B',meas:measL,vars:['R','r','d'],tg:'L²',cands:[['d² − (R − r)²',r=>r.d**2-(r.R-r.r)**2],['d² − (R + r)²',r=>r.d**2-(r.R+r.r)**2],['d² − R² − r²',r=>r.d**2-r.R**2-r.r**2]],ok:0,why:'Kolom d² − (R − r)² selalu sama dengan L². Langkah 2 menunjukkan mengapa sisi tegaknya R − r.',fig:twoC({mode:'luar',R:9,r:3,d:10,tri:true}),
  derive:['AB menyinggung kedua lingkaran, sehingga OA ⟂ AB dan PB ⟂ AB.','Dari P tarik garis PS sejajar AB dengan S pada OA. ABPS persegi panjang, jadi SP = AB = L dan AS = BP = r.','Maka OS = OA − AS = R − r. Segitiga OSP siku-siku di S, dengan OP = d.','Pythagoras: OP² = OS² + SP², yaitu d² = (R − r)² + L².','Pindahkan: L² = d² − (R − r)².',`Jadi L = ${rt('d² − (R − r)²')}. Sisi tegaknya selisih jari-jari karena S berada pada OA di antara O dan A.`],
  ex:{fig:twoC({mode:'luar',R:9,r:3,d:10,tri:true,q:'L'}),q:'Hitung panjang garis singgung persekutuan luar dua lingkaran berjari-jari 9 cm dan 3 cm, jarak pusat 10 cm.',steps:['<b>Diketahui:</b> R = 9 cm, r = 3 cm, d = 10 cm.','<b>Ditanyakan:</b> panjang garis singgung persekutuan luar L.',`<b>Rumus:</b> L = ${rt('d² − (R − r)²')}.`,`<b>Substitusi:</b> L = ${rt('10² − (9 − 3)²')}.`,`<b>Hitung:</b> L = ${rt('100 − 36')} = ${rt('64')} = 8.`,'<b>Kesimpulan:</b> panjang garis singgung persekutuan luar adalah 8 cm.']}}),
 ver:verSt('m2',M2P),
 gen:genSt('m2',[`Pada garis singgung persekutuan luar, kedua pusat berada pada sisi yang ${sel(['sama','berlawanan'],'sama')} dan garis singgungnya ${sel(['memotong','tidak memotong'],'tidak memotong')} ruas penghubung kedua pusat.`,`Sisi tegak segitiga siku-siku OSP adalah ${sel(['selisih','jumlah'],'selisih')} jari-jari, yaitu R ${sel(['−','+'],'−')} r.`,`Rumus: L = ${rt('d² − (R '+sel(['−','+'],'−')+' r)²')}.`],`L = ${rt('d² − (R − r)²')}`,['Apa ciri garis singgung persekutuan luar?','Mengapa rumusnya memakai selisih jari-jari?','Bagaimana kamu memastikan memakai R − r, bukan R + r?','Bagian mana yang masih sulit dipahami?'])}};

/* ---------- misi 3 ---------- */
const M3={id:'m3',no:3,title:'Garis Singgung Persekutuan Dalam',tp:'Menentukan panjang garis singgung persekutuan dalam, menjelaskan mengapa rumusnya memakai jumlah jari-jari, dan membedakannya dari garis singgung persekutuan luar.',ctx:'Sabuk yang menyilang di antara dua katrol. Dua roda gila yang diputar berlawanan arah.',st:{
 stim:(b,done)=>{b.innerHTML=`<p>Kali ini sabuk dipasang <b>menyilang</b>. Ubah ukuran katrol dan bandingkan dengan rantai tanpa menyilang di Misi 2.</p><div class="l"></div><div class="card soft"><h4>Prediksi</h4><p>Pada bagian lurus sabuk yang menyilang, di mana pusat kedua katrol berada?</p><div class="q"></div></div>`;
  mkLab($('.l',b),beltLab('dalam',{R:6,r:2,d:17}));mc($('.q',b),['Di sisi yang sama terhadap sabuk','Di sisi yang berlawanan, sehingga sabuk memotong garis penghubung kedua pusat','Pusat katrol berada pada sabuk'],1,'Pusat O dan P berada di sisi berlawanan. Garis seperti ini disebut garis singgung persekutuan dalam.',done)},
 prob:probSt('m3',['Bagaimana menghitung panjang bagian lurus sabuk menyilang (garis singgung persekutuan dalam), mengapa memakai jumlah jari-jari, dan apa bedanya dengan yang luar?','Berapa panjang sabuk seluruhnya?','Mengapa sabuk menyilang lebih jarang dipakai?'],0,'Tepat. Fokusmu: rumus L, alasan jumlah jari-jari, dan perbandingannya dengan garis singgung luar.','Menurutku garis singgung dalam berbeda dari yang luar karena …'),
 data:(b,done)=>{b.innerHTML=`<p class="sm">Pusat berada di sisi berlawanan, sehingga d harus lebih besar dari R + r. Catat minimal 3 data dan bandingkan kolom kandidatnya.</p><div class="l"></div>`;mkLab($('.l',b),{...twoLab('m3B','dalam',{R:3,r:2,d:13}),onrows:rows=>{if(rows.length>=3)done()}})},
 proc:procSt({m:'m3',key:'m3B',meas:measL,vars:['R','r','d'],tg:'L²',cands:[['d² − (R − r)²',r=>r.d**2-(r.R-r.r)**2],['d² − (R + r)²',r=>r.d**2-(r.R+r.r)**2],['d² − R² − r²',r=>r.d**2-r.R**2-r.r**2]],ok:1,why:'Kali ini kolom d² − (R + r)² yang selalu sama dengan L². Jumlah, bukan selisih. Langkah 2 menjelaskan alasannya.',fig:twoC({mode:'dalam',R:3,r:2,d:13,tri:true}),
  derive:['CD menyinggung kedua lingkaran: OC ⟂ CD dan PD ⟂ CD. Pusat O dan P berada di sisi berlawanan, sehingga CD memotong OP.','Perpanjang OC melewati C sampai S dengan CS = DP = r, lalu hubungkan P ke S. CDPS persegi panjang, jadi SP = CD = L.','Maka OS = OC + CS = R + r. Segitiga OSP siku-siku di S, dengan OP = d.','Pythagoras: d² = (R + r)² + L².','Pindahkan: L² = d² − (R + r)².',`Jadi L = ${rt('d² − (R + r)²')}. Sisi tegaknya jumlah jari-jari karena S berada di perpanjangan OC, di luar lingkaran pertama.`],
  ex:{fig:twoC({mode:'dalam',R:3,r:2,d:13,tri:true,q:'L'}),q:'Hitung panjang garis singgung persekutuan dalam dua lingkaran berjari-jari 3 cm dan 2 cm, jarak pusat 13 cm.',steps:['<b>Diketahui:</b> R = 3 cm, r = 2 cm, d = 13 cm.','<b>Ditanyakan:</b> panjang garis singgung persekutuan dalam L.',`<b>Rumus:</b> L = ${rt('d² − (R + r)²')}.`,`<b>Substitusi:</b> L = ${rt('13² − (3 + 2)²')}.`,`<b>Hitung:</b> L = ${rt('169 − 25')} = ${rt('144')} = 12.`,'<b>Kesimpulan:</b> panjang garis singgung persekutuan dalam adalah 12 cm.']}}),
 ver:(b,done)=>{b.innerHTML='<div class="pr"></div><div class="ex"></div>';problems($('.pr',b),'m3',M3P,done);
  $('.ex',b).innerHTML=`<div class="card soft"><h4>Analisis kesalahan</h4><p>Seorang teman mengerjakan soal: dua lingkaran R = 7 cm, r = 3 cm, d = 13 cm. Tentukan panjang garis singgung persekutuan <b>dalam</b>.</p><div class="sol"><div class="st"><b>Baris 1.</b> Diketahui R = 7, r = 3, d = 13.</div><div class="st"><b>Baris 2.</b> L = ${rt('d² − (R − r)²')}</div><div class="st"><b>Baris 3.</b> L = ${rt('13² − 4²')} = ${rt('169 − 16')} = ${rt('153')}</div><div class="st"><b>Baris 4.</b> L ≈ 12,37 cm</div></div><p style="margin-top:10px"><b>Pada baris berapa kesalahan pertama?</b></p><div class="eq"></div></div>`;
  mc($('.eq',b),['Baris 1','Baris 2','Baris 3','Baris 4'],1,`Garis singgung dalam memakai R + r, bukan R − r. Yang benar: L = ${rt('13² − (7 + 3)²')} = ${rt('69')} ≈ 8,31 cm. Baris berikutnya ikut salah karena baris 2.`)},
 gen:genSt('m3',[`Garis singgung persekutuan dalam ${sel(['memotong','tidak memotong'],'memotong')} ruas penghubung kedua pusat, dan kedua pusat berada pada sisi yang ${sel(['sama','berlawanan'],'berlawanan')}.`,`Sisi tegak segitiga siku-siku OSP adalah ${sel(['selisih','jumlah'],'jumlah')} jari-jari, yaitu R ${sel(['−','+'],'+')} r.`,`Rumus: L = ${rt('d² − (R '+sel(['−','+'],'+')+' r)²')}.`],`L = ${rt('d² − (R + r)²')}`,['Apa ciri garis singgung persekutuan dalam?','Mengapa rumusnya menggunakan jumlah jari-jari?','Bagaimana membedakan rumus garis singgung luar dan dalam?','Apakah kamu dapat memilih rumus tanpa melihat contoh?'],ex=>{
  ex.innerHTML=`<div class="card soft" style="margin-bottom:16px"><h4>Bandingkan luar dan dalam</h4><p class="sm">Ganti jenisnya dan gerakkan penggeser. Pada R, r, d yang sama, mana yang lebih panjang? Mengapa?</p><div class="cp"></div>${cmpTable}</div><div class="card soft" style="margin-bottom:16px"><h4>Uji bedakan</h4><div class="uq"></div></div>`;
  mkLab($('.cp',ex),{init:{mode:'dalam',R:7,r:4,d:16},sliders:[{k:'R',l:'Jari-jari R',min:3,max:12,u:' cm'},{k:'r',l:'Jari-jari r',min:1,max:12,u:' cm'},{k:'d',l:'Jarak pusat d',min:2,max:28,u:' cm'}],toggle:{k:'mode',l:'Jenis',o:[['luar','Persekutuan luar'],['dalam','Persekutuan dalam']]},limits:S=>({r:{max:S.R},d:{min:S.mode==='luar'?S.R-S.r+1:S.R+S.r+1,max:28}}),draw:S=>twoC({...S,tri:true}),
   ro:S=>`L luar = <b>${f(twoL({...S,mode:'luar'}))} cm</b><br>L dalam = <b>${S.d>S.R+S.r?f(twoL({...S,mode:'dalam'}))+' cm':'tidak ada'}</b>`});
  const Q=[['Rantai menghubungkan dua gir tanpa menyilang.',0],['Sabuk menghubungkan dua katrol dan menyilang di tengah.',1],['Kedua pusat lingkaran berada pada sisi yang sama terhadap garis singgung.',0],['Garis singgung memotong ruas garis penghubung kedua pusat.',1]];
  $('.uq',ex).innerHTML=Q.map((q,i)=>`<p style="margin:10px 0 6px"><b>${i+1}.</b> ${q[0]}</p><div class="u${i}"></div>`).join('');
  Q.forEach((q,i)=>mc($('.u'+i,ex),['Persekutuan luar, sisi tegak R − r','Persekutuan dalam, sisi tegak R + r'],q[1],q[1]?'Ciri dalam: pusat di sisi berlawanan, garis memotong penghubung pusat.':'Ciri luar: pusat di sisi yang sama, garis tidak memotong penghubung pusat.'))})}};

/* ---------- bagian akhir ---------- */
const TPS=['Saya dapat memakai sifat jari-jari tegak lurus garis singgung dan Pythagoras untuk mencari panjang garis singgung dari titik di luar lingkaran.','Saya dapat menentukan panjang garis singgung persekutuan luar dan menjelaskan mengapa memakai selisih jari-jari.','Saya dapat menentukan panjang garis singgung persekutuan dalam, menjelaskan mengapa memakai jumlah jari-jari, dan membedakannya dari yang luar.'];
function tps(){$('#tps').innerHTML=TPS.map((t,i)=>`<label class="tp"><input type="checkbox" id="tp${i}" ${ST.tp[i]?'checked':''}><span><b>TP ${i+1}.</b> ${t}</span></label>`).join('');TPS.forEach((t,i)=>$('#tp'+i).onchange=e=>{ST.tp[i]=e.target.checked;save()})}
function chal(){const h=$('#chal');h.innerHTML=`<h3>Tantangan pengayaan</h3><p>Dua lingkaran bersinggungan luar, artinya d = R + r. Jika R = 9 cm dan r = 4 cm, berapa panjang garis singgung persekutuan luarnya?</p><div class="row"><input class="num" id="chin" type="text" inputmode="decimal" aria-label="Jawaban tantangan"> <span>cm</span><button class="btn s" id="chbtn" type="button">Periksa</button></div><div class="fb" id="chfb" aria-live="polite"></div><div id="chpf" hidden><p><b>Buktikan bahwa L = 2√(Rr):</b></p>${stepper(['Garis singgung persekutuan luar: L² = d² − (R − r)².','Bersinggungan luar berarti d = R + r.','L² = (R + r)² − (R − r)² = 4Rr.','Jadi L = 2√(Rr). Uji: 2√(9 × 4) = 2 × 6 = 12 cm. Cocok dengan hasil hitunganmu.'])}</div><h4 style="margin-top:14px">Buat soal kontekstualmu</h4><textarea data-note="mysoal" aria-label="Soal buatanmu" placeholder="Tulis satu soal tentang roda, gir, sabuk, atau taman, lengkap dengan penyelesaiannya."></textarea>`;
 $('#chbtn').onclick=()=>{const v=parseFloat($('#chin').value.replace(',','.')),fb=$('#chfb'),okc=Math.abs(v-12)<.011;ST.chal={v:$('#chin').value,n:(ST.chal.n||0)+1,ok:okc||!!ST.chal.ok,t:Date.now()};save();if(okc){fb.className='fb ok';fb.textContent='Benar. Sekarang buktikan pola umumnya.';$('#chpf').hidden=false}else{fb.className='fb bad';fb.textContent='Belum tepat. Hitung d = R + r lebih dulu, lalu pakai rumus garis singgung luar.'}};const ci=$('#chin');if(ST.chal.v)ci.value=ST.chal.v;if(ST.chal.ok){$('#chpf').hidden=false;$('#chfb').className='fb ok';$('#chfb').textContent='Benar. Sekarang buktikan pola umumnya.'}ci.oninput=()=>{ST.chal.v=ci.value;save()};wire(h)}
const GL=[['Garis singgung lingkaran','Garis yang menyentuh lingkaran tepat di satu titik.'],['Garis potong (sekan)','Garis yang memotong lingkaran di dua titik.'],['Jari-jari','Ruas garis dari titik pusat ke suatu titik pada lingkaran.'],['Jarak antarpusat','Panjang ruas garis yang menghubungkan pusat dua lingkaran.'],['Garis singgung persekutuan','Garis yang menyinggung dua lingkaran sekaligus.'],['Persekutuan luar','Pusat di sisi yang sama terhadap garis; tidak memotong ruas penghubung pusat.'],['Persekutuan dalam','Pusat di sisi berlawanan terhadap garis; memotong ruas penghubung pusat.'],['Ruas garis','Bagian garis yang dibatasi oleh dua titik ujung.']];
$('#glos').innerHTML='<dl style="margin:0;display:grid;gap:8px">'+GL.map(g=>`<div><dt><b>${g[0]}</b></dt><dd style="margin:0" class="mut">${g[1]}</dd></div>`).join('')+'</dl>';
/* ---------- identitas, laporan, dan pengiriman ke guru ---------- */
const CFG={endpoint:'https://script.google.com/macros/s/AKfycbzqV2xCrfgUcOSAxEowhnCNrOhMIWDxoja5KALUuxO-lakM1wF23-to2kaYYV1vU2I5_Q/exec',/* URL Web App Google Apps Script (lihat Code.gs) */ guru:'Bapak/Ibu Guru'};
const PF=()=>ST.profile,okP=()=>!!(PF().nama&&PF().kelas);
[['idn','nama'],['idk','kelas'],['ida','absen']].forEach(([i,k])=>{const e=$('#'+i);e.value=PF()[k]||'';e.oninput=()=>{PF()[k]=e.value.trim();save()}});
function score(){const ids=[...M1P,...M2P,...M3P].map(p=>p.id),g=ids.filter(i=>ST.pts[i]),a=g.length?g.reduce((s,i)=>s+ST.pts[i],0)/g.length:0;return{ids,got:g.length,nilai:g.length?Math.round(a/4*100):0,cat:a>=3.5?'Mahir':a>=3?'Cakap':a>=2?'Berkembang':'Perlu bimbingan'}}
function report(){const s=score(),p=PF(),P=[...M1P,...M2P,...M3P],nq=k=>ST.nq[k]||k,L=[];let n=0;MS.forEach(M=>STG.forEach(([k])=>{if(ST.done[M.id+k])n++}));
 L.push('LAPORAN BENGKEL GARIS SINGGUNG','Nama: '+(p.nama||'-'),'Kelas: '+(p.kelas||'-')+' | No. absen: '+(p.absen||'-'),'Nilai: '+s.nilai+' ('+s.cat+') | soal selesai '+s.got+'/'+s.ids.length+' | tahap selesai '+n+'/18','','== TANTANGAN PENGAYAAN ==','Jawaban: '+(ST.chal.v||'(kosong)')+(ST.chal.ok?' (benar)':' (belum benar)')+' | percobaan '+(ST.chal.n||0),'Soal buatan: '+(ST.note.mysoal||'(kosong)'),'','== REFLEKSI AKHIR ==');
 [0,1,2].forEach(i=>L.push((i+1)+'. '+(ST.nq['fin'+i]||'Refleksi akhir '+(i+1))+' -> '+(ST.note['fin'+i]||'(kosong)')));
 L.push('','== DUGAAN & REFLEKSI PER MISI ==');Object.keys(ST.note).filter(k=>!/^(fin|mysoal)/.test(k)&&ST.note[k]).forEach(k=>L.push('['+k+'] '+nq(k)+' -> '+ST.note[k]));
 L.push('','== SOAL LATIHAN ==');P.forEach(q=>{const a=ST.ans[q.id];L.push(q.id+': '+(a?a.v+(a.ok?' (benar':' (belum benar')+', '+a.n+'x coba, bantuan '+a.lvl+', skor '+(ST.pts[q.id]||0)+')':'(belum dikerjakan)'))});
 L.push('','== LAINNYA ==','Cek awal: '+DQ.map((q,i)=>ST.diag[i]===undefined?'-':ST.diag[i]===q[2]?'benar':'salah').join(', '),'Pelacak TP: '+[0,1,2].map(i=>ST.tp[i]?'ya':'belum').join(', '),'Pilihan ganda: '+(Object.entries(ST.mc).map(([k,v])=>k.split(':')[0]+' '+(v.ok?'benar':'salah')+' x'+v.n).join('; ')||'-'),'Kesimpulan isian: '+(Object.entries(ST.cz).map(([k,v])=>k.split(':')[0]+' '+(v.ok?'benar':'salah')+' x'+v.n).join('; ')||'-'),'Data tabel: '+(Object.entries(ST.rows).map(([k,r])=>k+' '+r.length+' data').join('; ')||'-'));
 const text=L.join('\n');return{text,data:{id:((p.nama||'')+'|'+(p.kelas||'')+'|'+(p.absen||'')).toLowerCase(),nama:p.nama,kelas:p.kelas,absen:p.absen,nilai:s.nilai,kategori:s.cat,tahap:n,tantangan:ST.chal.v||'',tantanganBenar:!!ST.chal.ok,soalBuatan:ST.note.mysoal||'',refleksi:[0,1,2].map(i=>ST.note['fin'+i]||''),laporan:text,state:ST}}}
const sig=()=>{const r=report();return hs(r.text+JSON.stringify(ST.rows)+JSON.stringify(ST.mc))};
let tmr,busy=false,KM='';
const raw=()=>{try{localStorage.setItem('bgs1',JSON.stringify(ST))}catch(e){}};
function onSaved(){if(!window.kirimOn)return;if(MS.length>2)locks();clearTimeout(tmr);ui();if(CFG.endpoint&&okP())tmr=setTimeout(()=>sendNow(false),5000)}
function ui(){const d=ST.sync.h!==sig();$('#sdot').textContent=!CFG.endpoint?(OKS?'Tersimpan ✓':'⚠ Tidak tersimpan'):d?'Belum terkirim':'Terkirim ✓';
 const k=$('#kst');if(!k)return;k.className='note'+(CFG.endpoint&&!d?' ok':'');
 k.innerHTML='<b>Di perangkat:</b> '+(OKS?'tersimpan otomatis ✓':'⚠ peramban menolak penyimpanan, unduh laporan sebelum menutup halaman')+'<br><b>Identitas:</b> '+(okP()?'lengkap ✓':'isi nama dan kelas di bagian Identitas')+'<br><b>Ke guru:</b> '+(KM||(CFG.endpoint?(d?'belum terkirim (terkirim otomatis beberapa detik setelah kamu berhenti mengisi)':'terkirim ✓ '+(ST.sync.ts||'')):'pengiriman online belum diaktifkan guru'));
 const r=$('#krp');if(r)r.value=report().text}
function fin(h,m){ST.sync={h,ts:new Date().toLocaleString('id-ID')};raw();KM=m+' '+ST.sync.ts;ui()}
async function sendNow(man){if(busy)return;if(!okP()){if(man){alert('Isi nama dan kelas dulu di bagian Identitas.');$('#idn').scrollIntoView();$('#idn').focus()}return}
 if(!CFG.endpoint){KM='';ui();return}
 busy=true;const r=report(),h=sig(),body=JSON.stringify(r.data);KM='mengirim…';ui();
 try{const res=await fetch(CFG.endpoint,{method:'POST',body});const j=await res.json();if(!j.ok)throw 0;fin(h,'terkirim ✓')}
 catch(e){try{await fetch(CFG.endpoint,{method:'POST',mode:'no-cors',body});fin(h,'terkirim (belum terkonfirmasi) ')}catch(e2){KM='gagal terkirim, cek internet. Dicoba lagi otomatis.';ui();tmr=setTimeout(()=>sendNow(false),20000)}}
 busy=false}
const kn=()=>(PF().kelas||'').toLowerCase().replace(/\s+/g,'');
async function getAcc(){if(!CFG.endpoint||!kn())return;try{const j=await(await fetch(CFG.endpoint+'?aksi=akses&kelas='+encodeURIComponent(kn()))).json();if(j.ok){ST.acc=j.akses;raw()}}catch(e){}if(MS.length>2)locks()}
function locks(){MS.forEach((M,i)=>{const h=$('#'+M.id);let m='';if(!i){if(!okP())m='🔒 Isi identitas (nama dan kelas) dulu.';else if(Object.keys(ST.diag).length<DQ.length)m='🔒 Jawab dulu 5 soal Cek Awal.'}if(i){const pm=MS[i-1];if(!STG.every(([k])=>ST.done[pm.id+k]))m='🔒 Misi '+M.no+' terkunci. Selesaikan semua tahap Misi '+pm.no+' dulu.';else if(CFG.endpoint&&ST.acc&&ST.acc[M.id]!==true)m='🔒 Misi '+M.no+' belum dibuka guru. Tunggu pertemuan berikutnya.'}h.classList.toggle('lk',!!m);h.dataset.msg=m});const c=$('#chal'),ok=STG.every(([k])=>ST.done[MS[2].id+k]);c.classList.toggle('lk',!ok);c.dataset.msg='🔒 Tantangan terbuka setelah Misi 3 selesai.'}
$('#idk').addEventListener('change',getAcc);setInterval(getAcc,60000);
window.kirimOn=1;
$('#kirim').innerHTML=`<h3>Kirim hasil ke guru</h3><p class="sm mut">Jawaban soal, tantangan, dan refleksi tersimpan otomatis. Pastikan statusnya terkirim, atau unduh cadangan lalu serahkan ke guru.</p><div id="kst"></div><div class="row" style="margin-top:10px;flex-wrap:wrap;gap:8px">${CFG.endpoint?'<button class="btn" id="ksd" type="button">Kirim ke guru sekarang</button>':''}<button class="btn g" id="kdl" type="button">Unduh cadangan</button></div>`;
const need=()=>{if(okP())return true;alert('Isi nama dan kelas dulu di bagian Identitas.');$('#idn').scrollIntoView();$('#idn').focus();return false};
if($('#ksd'))$('#ksd').onclick=()=>sendNow(true);
$('#kdl').onclick=()=>{if(!need())return;const a=document.createElement('a');a.href=URL.createObjectURL(new Blob([report().text],{type:'text/plain;charset=utf-8'}));a.download=('Singgung_'+PF().kelas+'_'+PF().nama).replace(/[^\w\-]+/g,'_')+'.txt';document.body.appendChild(a);a.click();a.remove()};

$('#thm').onclick=THEME;
diag();tps();[M1,M2,M3].forEach(mission);chal();refresh();ui();getAcc();setTimeout(()=>{if(CFG.endpoint&&okP()&&ST.sync.h!==sig())sendNow(false)},2500);
</script>

</body></html>
