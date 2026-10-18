<!DOCTYPE html>
<html data-host-mode="dark" lang="de"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1"><script>Object.defineProperty(document, "cookie", {get: function() { return ""; },set: function() {},configurable: false});</script><script type="module">(async()=>{if(typeof FileSystemFileHandle!=="undefined"&&"createWritable"in FileSystemFileHandle.prototype)return;if(!navigator.storage?.getDirectory)return;try{const{createWorker}=await import("https://esm.sh/opfs-worker");const w=await createWorker();class W{constructor(p){this.p=p;this.c=[];this.x=false}write(d){if(this.x)throw new DOMException("closed","InvalidStateError");if(typeof d==="object"&&"type"in d&&!(d instanceof Blob)&&!(d instanceof ArrayBuffer)){if(d.type==="write")this.c.push(d.data);else if(d.type==="truncate")this.c=[];return}this.c.push(d)}async close(){if(this.x)return;const b=new Blob(this.c);await w.writeFile(this.p,new Uint8Array(await b.arrayBuffer()));this.x=true;this.c=[]}abort(){this.x=true;this.c=[]}}const pF=(h,p)=>new Proxy(h,{get:(t,k)=>k==="createWritable"?async()=>new W(p):typeof t[k]==="function"?t[k].bind(t):t[k]});const pD=(h,p)=>new Proxy(h,{get:(t,k)=>{if(k==="getFileHandle")return async(n,o)=>pF(await t.getFileHandle(n,o),(p+"/"+n).replace(//+/g,"/"));if(k==="getDirectoryHandle")return async(n,o)=>pD(await t.getDirectoryHandle(n,o),(p+"/"+n).replace(//+/g,"/"));return typeof t[k]==="function"?t[k].bind(t):t[k]}});const og=navigator.storage.getDirectory.bind(navigator.storage);navigator.storage.getDirectory=async function(){return pD(await og.call(this),"/")};}catch(e){console.warn("[OPFS]",e)}})();</script><link rel="preconnect" href="https://fonts.googleapis.com"><link rel="preconnect" href="https://fonts.gstatic.com" crossorigin=""><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&amp;display=swap" rel="stylesheet"><style>:root { --host-bg: #0E1217; --host-fg: #eeede4; --host-fg-muted: #A2A6AA; --host-card: rgba(255,255,255,0.04); --host-card-fg: #eeede4; --host-input: rgba(255,255,255,0.04); --host-muted: rgba(255,255,255,0.04); --host-border: rgba(255,255,255,0.06); --host-border-hover: rgba(255,255,255,0.12); --host-primary: #125DA3; --host-secondary: rgba(255,255,255,0.04); --host-secondary-fg: #eeede4; --host-success: #5F9437; --host-error: #D73436; } * { box-sizing: border-box; margin: 0; padding: 0; } :root, html, body { width: 100%; max-width: 100%; height: auto; overflow-x: hidden; overflow-y: visible; background: transparent; font-family: Inter, system-ui, -apple-system, sans-serif; } #sandbox-content { width: 100%; } @media (max-width: 640px) { :where(#sandbox-content svg, #sandbox-content img) { max-width: 100%; height: auto; } } </style></head><body><div id="sandbox-content">


<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Piratenkiste</title>
<meta name="theme-color" content="#0b0f14">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Piratenkiste">
<style>
:root{--bg:#0b0f14;--bg2:#121821;--bg3:#1a222d;--fg:#e6edf3;--mut:#8b98a5;--acc:#f0a020;--ok:#3fb950;--bad:#f85149;--br:#232c38;--r:10px}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--fg);font:15px/1.55 system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
header{padding:13px 16px;background:linear-gradient(180deg,#141b24,#0b0f14);border-bottom:1px solid var(--br);display:flex;align-items:center;gap:9px;flex-wrap:wrap}
h1{font-size:19px;margin:0;letter-spacing:.3px}
.badge{font-size:11px;color:var(--mut);border:1px solid var(--br);padding:2px 8px;border-radius:99px}
nav{display:flex;gap:6px;padding:10px 12px;flex-wrap:wrap;border-bottom:1px solid var(--br);background:var(--bg)}
nav button{background:var(--bg2);color:var(--fg);border:1px solid var(--br);padding:7px 13px;border-radius:99px;cursor:pointer;font:inherit;font-size:14px}
nav button.on{background:var(--acc);color:#141414;border-color:var(--acc);font-weight:700}
#modebar{display:flex;gap:8px;align-items:center;flex-wrap:wrap;padding:8px 12px;background:#0d131a;border-bottom:1px solid var(--br);font-size:13px}
#modebar select{background:var(--bg3);color:var(--fg);border:1px solid var(--br);border-radius:8px;padding:5px 9px;font:inherit;font-size:13px;width:auto}
main{padding:14px;max-width:1000px;margin:0 auto}
section{display:none}
section.on{display:block}
.card{background:var(--bg2);border:1px solid var(--br);border-radius:var(--r);padding:14px;margin-bottom:13px}
.card h2{font-size:15px;margin:0 0 10px}
.card h2 .n{display:inline-block;background:var(--acc);color:#141414;border-radius:99px;width:20px;height:20px;line-height:20px;text-align:center;font-size:12px;margin-right:7px}
input,select,textarea{background:var(--bg3);color:var(--fg);border:1px solid var(--br);border-radius:8px;padding:9px 11px;font:inherit;width:100%}
textarea{font-family:ui-monospace,Menlo,Consolas,monospace;font-size:12px}
.row{display:flex;gap:8px;flex-wrap:wrap;align-items:center}
.row>input,.row>select{flex:1;min-width:150px;width:auto}
button{background:var(--acc);color:#141414;border:0;border-radius:8px;padding:9px 14px;font:inherit;font-weight:600;cursor:pointer}
button.ghost{background:var(--bg3);color:var(--fg);border:1px solid var(--br);font-weight:500}
a{color:var(--acc)}
a.btn{display:inline-block;text-decoration:none;background:var(--acc);color:#141414;border-radius:8px;padding:9px 14px;font-weight:600;font-size:15px;line-height:1.2;cursor:pointer}
a.btn.ghost{background:var(--bg3);color:var(--fg);border:1px solid var(--br);font-weight:500}
small,.mut{color:var(--mut)}
.res{border:1px solid var(--br);border-radius:8px;padding:9px 11px;margin:7px 0;background:var(--bg3)}
.res b{display:block;font-size:14px;margin-bottom:2px}
.res .u{font-size:11px;color:var(--mut);word-break:break-all;display:block;margin-bottom:6px}
.pill{font-size:11px;border-radius:99px;padding:1px 8px;border:1px solid var(--br);color:var(--mut);margin-left:6px}
.pill.y{color:var(--ok);border-color:#1f6f3a}
.pill.n{color:var(--bad);border-color:#6e2a26}
pre{background:#0d131a;border:1px solid var(--br);border-radius:8px;padding:10px;overflow:auto;font-size:12px;max-height:340px;white-space:pre-wrap;word-break:break-word}
.bar{height:7px;background:var(--bg3);border-radius:99px;overflow:hidden;margin-top:6px}
.bar>i{display:block;height:100%;background:var(--acc);width:0}
.ok{color:var(--ok)}.bad{color:var(--bad)}
#lockbox{border:1px dashed var(--br)}
iframe{width:100%;height:66vh;border:1px solid var(--br);border-radius:8px;background:#000}
video{width:100%;border-radius:8px;background:#000}
code{font-family:ui-monospace,monospace;font-size:12px;background:#0d131a;padding:1px 5px;border-radius:4px}
#copyTmp{position:absolute;left:-9999px;top:0;width:10px;height:10px}
.sbox{border:1px solid var(--br);border-radius:8px;padding:10px;background:var(--bg3)}
ol.steps{margin:0;padding-left:22px}
ol.steps li{margin-bottom:10px}
.gh{border-color:#2d3a4d}
</style>


<header>
  <h1>Piratenkiste</h1>
  <span class="badge">build 25</span>
  <span class="badge">Grauzone</span>
  <span class="mut" style="margin-left:auto;font-size:12px">Streaming &amp; Download</span>
</header>

<nav id="nav">
  <button data-t="suche" class="on">Suche</button>
  <button data-t="player">Player</button>
  <button data-t="dl">Download</button>
  <button data-t="app">App</button>
  <button data-t="info">Info</button>
</nav>

<div id="modebar">
  <span class="mut">Links öffnen:</span>
  <select id="openMode">
    <option value="auto">Automatisch (empfohlen)</option>
    <option value="tab">Neuer Tab</option>
    <option value="top">Hauptfenster</option>
    <option value="self">Im Fenster</option>
  </select>
  <span id="modeMsg" class="mut" style="font-size:12px"></span>
</div>

<main>

<section id="s-suche" class="on">
  <div class="card">
    <h2>Suche</h2>
    <div class="row">
      <input id="q" placeholder="Titel eingeben, z. B. Breaking Bad, One Piece, Avatar">
      <button id="go">Suchen</button>
    </div>
    <div class="row" style="margin-top:8px">
      <label class="mut" style="font-size:13px"><input type="checkbox" id="de" style="width:auto"> deutsche Synchro bevorzugen</label>
      <button class="ghost" id="liveAll">Alle Quellen live laden</button>
    </div>
    <p class="mut" style="font-size:12px;margin:9px 0 0"><b>Ansehen</b> lädt die Seite direkt in der App – das klappt immer. <b>Öffnen</b> versucht Tab, Hauptfenster und Fenster automatisch der Reihe nach.</p>
  </div>
  <div id="srcList"></div>
  <div id="liveOut"></div>
</section>

<section id="s-player">
  <div class="card">
    <h2>Player</h2>
    <div class="row">
      <input id="pUrl" placeholder="Adresse der Folge / des Films einfügen">
      <button id="pGo">Ansehen</button>
    </div>
    <div class="row" style="margin-top:8px">
      <select id="embMode" style="max-width:300px">
        <option value="proxy">Blockierte Seiten über Proxy laden (empfohlen)</option>
        <option value="off">Direkt laden (ohne Proxy)</option>
      </select>
      <button class="ghost" id="pOpen">Öffnen</button>
    </div>
    <p class="mut" style="font-size:12px;margin:9px 0 0">Bleibt das Fenster weiß, ist die Seite nicht einbettbar – dann auf Proxy umschalten oder Öffnen benutzen.</p>
  </div>
  <div id="playerWrap"></div>
  <div class="card">
    <h2>YouTube</h2>
    <div class="row"><input id="ytQ" placeholder="YouTube-Suche"><button id="ytGo">Suchen</button></div>
    <div id="ytOut"></div>
  </div>
  <div class="card">
    <h2>Direkt-Link finden (m3u8 / mp4)</h2>
    <div class="row"><input id="resUrl" placeholder="Adresse der Folge / des Films"><button id="resGo">Suchen</button></div>
    <div id="resOut"></div>
  </div>
</section>

<section id="s-dl">
  <div class="card">
    <h2>Download</h2>
    <div class="row">
      <input id="dlUrl" placeholder="Direkte Datei-Adresse (.mp4, .m3u8, .zip ...)">
      <button id="dlAdd">Hinzufügen</button>
    </div>
    <p class="mut" style="font-size:12px;margin:9px 0 0">Die Datei wird in den Speicher geladen und danach mit mehreren Speicher-Wege angeboten.</p>
  </div>
  <div id="dlOut"></div>
</section>

<section id="s-app">
  <div class="card" id="lockbox">
    <h2>Gesperrt</h2>
    <p class="mut" style="font-size:13px;margin:0 0 10px">Kopieren, Duplizieren und Herunterladen der App sind passwortgeschützt.</p>
    <div class="row">
      <input id="pwIn" type="password" placeholder="" autocomplete="off" spellcheck="false" style="max-width:200px">
      <button class="ghost" id="pwShow">zeigen</button>
      <button id="pwGo">Entsperren</button>
    </div>
    <div id="pwMsg" class="mut" style="font-size:13px;margin-top:9px"></div>
  </div>

  <div id="exp" hidden="">

    <div class="card" style="border-color:#3a4a2a">
      <h2>Schnellstart – ohne Download</h2>
      <div class="row">
        <button id="copyLink">Website-Link kopieren</button>
        <button class="ghost" id="openTab">Öffnen versuchen</button>
        <button class="ghost" id="copyCode">App-Code kopieren</button>
      </div>
      <div id="qsMsg" class="mut" style="font-size:13px;margin-top:10px"></div>
      <p class="mut" style="font-size:12px;margin:10px 0 0">Für GitHub brauchst du nur <b>App-Code kopieren</b> – der Rest steht unten Schritt für Schritt.</p>
    </div>

    <div class="card gh">
      <h2>GitHub: App als Website veröffentlichen</h2>
      <p class="mut" style="font-size:12px;margin:0 0 12px">Einmal eingerichtet, hast du eine echte Adresse wie <code>https://deinname.github.io/piratenkiste/</code> – auf PC, Handy und iPad aufrufbar, und dort auch als App installierbar. Kein Datei-Upload nötig, alles per Einfügen.</p>

      <div class="sbox" style="margin-bottom:12px">
        <p class="mut" style="font-size:12px;margin:0 0 8px">Trag hier deinen GitHub-Namen und den gewünschten Projektnamen ein – dann bekommst du unten deine direkten Links:</p>
        <div class="row">
          <input id="ghUser" placeholder="GitHub-Benutzername" autocomplete="off" spellcheck="false" style="max-width:220px">
          <input id="ghRepo" placeholder="Projektname, z. B. piratenkiste" autocomplete="off" spellcheck="false" style="max-width:220px">
        </div>
        <div id="ghOut" style="margin-top:10px"></div>
      </div>

      <ol class="steps">
        <li><b>Konto:</b> <a class="btn ghost" href="https://github.com/signup" data-open="https://github.com/signup">github.com/signup</a> – kostenlos. Falls vorhanden: <a class="btn ghost" href="https://github.com/login" data-open="https://github.com/login">Anmelden</a></li>
        <li><b>Repository anlegen:</b> <a class="btn ghost" href="https://github.com/new?name=piratenkiste" data-open="https://github.com/new?name=piratenkiste">github.com/new</a><br>
          Name eintragen (z. B. <code>piratenkiste</code>), Sichtbarkeit <b>Public</b> wählen, dann <b>Create repository</b>. <span class="mut">Public ist nötig, damit die Seite kostenlos erreichbar ist.</span></li>
        <li><b>Datei anlegen:</b> im Repo auf <b>Add file → Create new file</b> (oder direkt deinen Link oben benutzen).<br>
          Als Dateiname exakt <code>index.html</code> eintragen. <span class="mut">Kleinschreibung, keine Leerzeichen.</span></li>
        <li><b>Code einfügen:</b> <button class="ghost" id="copyForGh">App-Code kopieren</button> → ins große Textfeld einfügen (Strg+V / ⌘V).<br>
          <span class="mut">Am Handy/iPad: im Textfeld lange drücken → Einfügen.</span></li>
        <li><b>Speichern:</b> unten auf <b>Commit changes</b> klicken, im Dialog nochmal <b>Commit changes</b>.</li>
        <li><b>Seite aktivieren:</b> <b>Settings</b> → links <b>Pages</b> → unter „Branch“: <code>main</code> auswählen, Ordner <code>/ (root)</code>, dann <b>Save</b>.</li>
        <li><b>Warten:</b> etwa eine Minute. Danach ist deine Adresse aktiv – oben im grünen Kasten.</li>
      </ol>

      <div class="row" style="margin-top:12px">
        <button class="ghost" id="copyGhGuide">Diese Anleitung kopieren</button>
        <button class="ghost" id="mkFileGh">index.html als Datei</button>
      </div>
      <div id="ghMsg" class="mut" style="font-size:13px;margin-top:10px"></div>
      <div id="ghFile" style="margin-top:11px"></div>

      <div class="sbox" style="margin-top:12px">
        <p class="mut" style="font-size:12px;margin:0 0 6px"><b>Später ändern:</b> im Repo <code>index.html</code> öffnen → Stift-Symbol → ändern → Commit.</p>
        <p class="mut" style="font-size:12px;margin:0 0 6px"><b>Voll-Editor im Browser:</b> im Repo die <b>Punkt-Taste</b> drücken – öffnet github.dev.</p>
        <p class="mut" style="font-size:12px;margin:0 0 6px"><b>Ohne Pages (Notlösung):</b> <code>https://htmlpreview.github.io/?https://raw.githubusercontent.com/BENUTZER/REPO/main/index.html</code></p>
        <p class="mut" style="font-size:12px;margin:0"><b>Als App:</b> Adresse öffnen → iPhone/iPad: Teilen → Zum Home-Bildschirm. Android/PC: Installieren.</p>
      </div>
    </div>

    <div class="card">
      <h2><span class="n">1</span>Code kopieren (Basis für alles)</h2>
      <div class="row">
        <button id="copySrc">Gesamten App-Code kopieren</button>
        <button class="ghost" id="selSrc">Alles markieren</button>
      </div>
      <div id="copyMsg" class="mut" style="font-size:13px;margin-top:9px"></div>
      <textarea id="srcBox" readonly="" spellcheck="false" style="height:150px;margin-top:10px"></textarea>
      <div class="mut" style="font-size:12px;margin-top:7px">Prüfsumme <span id="sum"></span> · Zeichen <span id="len"></span> · Ende <code id="tail"></code></div>
    </div>

    <div class="card">
      <h2><span class="n">2</span>Schnelltest in 30 Sekunden (CodePen)</h2>
      <ol class="steps">
        <li><a class="btn ghost" href="https://codepen.io/pen/" data-open="https://codepen.io/pen/">codepen.io/pen öffnen</a></li>
        <li><button class="ghost" id="copyForCp">App-Code kopieren</button> — ins <b>HTML</b>-Feld einfügen.</li>
        <li>Läuft sofort. Über <b>Change View → Full Page</b> bekommst du eine reine Seitenansicht.</li>
      </ol>
      <div id="cpMsg" class="mut" style="font-size:13px;margin-top:10px"></div>
    </div>

    <div class="card">
      <h2><span class="n">3</span>Falls Download doch geht – ZIP / Datei</h2>
      <div class="row">
        <button class="ghost" id="mkZip">ZIP-Wege erzeugen</button>
        <button class="ghost" id="mkFile">Datei-Wege erzeugen</button>
      </div>
      <div id="outZip" style="margin-top:11px"></div>
      <div id="outFile" style="margin-top:11px"></div>
    </div>

    <div class="card">
      <h2><span class="n">4</span>Notfall ohne alles</h2>
      <p class="mut" style="font-size:13px;margin:0 0 8px">App-Code kopieren → auf dem Gerät eine Datei <code>index.html</code> anlegen → einfügen → speichern → im Browser öffnen.</p>
      <p class="mut" style="font-size:13px;margin:0">Oder: Website-Link kopieren, in Notizen einfügen, Link antippen.</p>
    </div>

    <div class="card">
      <h2>Passwort</h2>
      <div class="row">
        <input id="pwNew" type="password" placeholder="neues Passwort" autocomplete="off" style="max-width:220px">
        <button class="ghost" id="pwSave">Speichern</button>
        <button class="ghost" id="pwLock">Wieder sperren</button>
      </div>
      <div id="pwMsg2" class="mut" style="font-size:13px;margin-top:9px"></div>
    </div>
  </div>
</section>

<section id="s-info">
  <div class="card">
    <h2>Selbstprüfung</h2>
    <div class="row">
      <button id="tAll">Alles prüfen</button>
      <button class="ghost" id="tOpen">Öffnen-Test</button>
      <button class="ghost" id="tDiag">Umgebungs-Diagnose</button>
      <button class="ghost" id="tInteg">Vollständigkeit prüfen</button>
      <button class="ghost" id="tZip">ZIP testen</button>
    </div>
    <pre id="testOut">bereit.</pre>
  </div>
  <div class="card">
    <h2>Speicher-Test mit Mini-Datei</h2>
    <button class="ghost" id="tFile">Testdatei erzeugen</button>
    <div id="fileOut" style="margin-top:11px"></div>
  </div>
  <div class="card"><h2>Quellen</h2><div id="srcInfo"></div></div>
  <div class="card"><h2>Anleitung</h2><pre id="howto"></pre></div>
</section>

<div class="card" id="urlbar" style="display:none">
  <h2>Zuletzt geöffnet</h2>
  <div class="row">
    <input id="lastUrl" readonly="">
    <button class="ghost" id="copyLast">Link kopieren</button>
    <button class="ghost" id="openLast">Nochmal öffnen</button>
  </div>
</div>

<textarea id="copyTmp" readonly=""></textarea>

</main>

<script>
(function(){
'use strict';
var MARK='ENDE-PIRATENKISTE-build 25';
var PRISTINE='<!DOCTYPE html>\n'+document.documentElement.outerHTML;
var ON_DATA=(location.protocol==='data:');

function $(id){return document.getElementById(id)}
var MEM={},LS_OK=true;
try{localStorage.setItem('pk_probe','1');localStorage.removeItem('pk_probe')}catch(e){LS_OK=false}
function ls(k,v){
  try{
    if(v===undefined)return LS_OK?localStorage.getItem(k):(k in MEM?MEM[k]:null);
    if(LS_OK)localStorage.setItem(k,v);else MEM[k]=v;
    return v;
  }catch(e){return v===undefined?(k in MEM?MEM[k]:null):(MEM[k]=v)}
}
function esc(s){return String(s).replace(/[&<>"]/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]})}
function cat(a){var n=0,i;for(i=0;i<a.length;i++)n+=a[i].length;var o=new Uint8Array(n),p=0;for(i=0;i<a.length;i++){o.set(a[i],p);p+=a[i].length}return o}
function b64(u8){var s='',C=0x8000,i;for(i=0;i<u8.length;i+=C){s+=String.fromCharCode.apply(null,u8.subarray(i,i+C))}return btoa(s)}
function fnv(s){var h=0x811c9dc5,i;for(i=0;i<s.length;i++){h^=s.charCodeAt(i);h=(h*0x01000193)>>>0}return ('00000000'+h.toString(16)).slice(-8)}
function fmt(n){return n<1024?n+' B':n<1048576?(n/1024).toFixed(1)+' KB':(n/1048576).toFixed(2)+' MB'}

var OPEN_MODE=ls('pk_open')||'auto';
var pendingTop=n
