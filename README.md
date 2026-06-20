[index.html](https://github.com/user-attachments/files/29156191/index.html)
# zig-catalogo<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZIG Locações — Catálogo de Equipamentos</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0}
  body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;background:#f8f8f6;color:#1a1a1a;-webkit-font-smoothing:antialiased}
  .wrap{max-width:480px;margin:0 auto;padding-bottom:120px}

  /* HEADER */
  .hdr{background:white;padding:1rem 1rem 0.75rem;border-bottom:1px solid #e8e8e4;position:sticky;top:0;z-index:20}
  .hdr-top{display:flex;align-items:center;justify-content:space-between}
  .logo{font-size:18px;font-weight:600;color:#1a1a1a;letter-spacing:-0.3px}
  .logo span{color:#1D9E75}
  .wpp-topo{display:flex;align-items:center;gap:4px;font-size:12px;color:#1D9E75;text-decoration:none;font-weight:500}
  .sub{font-size:12px;color:#888;margin-top:3px}

  /* FILTROS */
  .filtros{background:white;display:flex;gap:6px;padding:0.6rem 1rem;overflow-x:auto;scrollbar-width:none;border-bottom:1px solid #e8e8e4}
  .filtros::-webkit-scrollbar{display:none}
  .fb{flex-shrink:0;font-size:11px;padding:5px 12px;border-radius:20px;border:1px solid #ddd;background:white;color:#666;cursor:pointer;font-family:inherit;white-space:nowrap;transition:all 0.15s}
  .fb:hover{border-color:#1D9E75;color:#1D9E75}
  .fb.on{background:#085041;border-color:#085041;color:white}

  /* LISTA */
  .lista{padding:0.75rem 0.75rem}

  /* CARD */
  .card{background:white;border:1px solid #e8e8e4;border-radius:12px;margin-bottom:8px;overflow:hidden;transition:border-color 0.15s,box-shadow 0.15s}
  .card:active{transform:scale(0.99)}
  .card.sel{border-color:#1D9E75;box-shadow:0 0 0 3px rgba(29,158,117,0.1)}
  .card-top{display:flex;align-items:center;gap:10px;padding:12px 12px 10px;cursor:pointer;-webkit-tap-highlight-color:transparent}
  .icn-wrap{width:44px;height:44px;border-radius:10px;background:#f3f3f0;display:flex;align-items:center;justify-content:center;flex-shrink:0;overflow:hidden}
  .card.sel .icn-wrap{background:#E1F5EE}
  .icn-wrap img{width:44px;height:44px;object-fit:cover}
  .icn-wrap svg{width:22px;height:22px;stroke:#999;fill:none;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round}
  .card.sel .icn-wrap svg{stroke:#1D9E75}
  .eq-info{flex:1;min-width:0}
  .eq-nome{font-size:13px;font-weight:600;color:#1a1a1a;line-height:1.3}
  .eq-grp{font-size:11px;color:#aaa;margin-top:1px;text-transform:capitalize}
  .chk{width:22px;height:22px;border-radius:50%;border:1.5px solid #ddd;background:white;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all 0.15s}
  .card.sel .chk{background:#1D9E75;border-color:#1D9E75}
  .chk svg{width:12px;height:12px;stroke:white;fill:none;stroke-width:2.5;opacity:0;transition:opacity 0.15s}
  .card.sel .chk svg{opacity:1}

  /* PERÍODOS */
  .periodos{display:flex;border-top:1px solid #f0f0ec}
  .card.sel .periodos{border-top-color:#b2e8d5}
  .po{flex:1;display:flex;flex-direction:column;align-items:center;padding:8px 2px;border-right:1px solid #f0f0ec;gap:2px;cursor:pointer;position:relative;-webkit-tap-highlight-color:transparent;transition:background 0.1s}
  .po:hover{background:#fafaf8}
  .card.sel .po{border-right-color:#b2e8d5}
  .po:last-child{border-right:none}
  .po.on{background:#f0fdf8}
  .po.on::after{content:'';position:absolute;bottom:0;left:20%;right:20%;height:2px;background:#1D9E75;border-radius:2px 2px 0 0}
  .pl{font-size:10px;color:#aaa;text-transform:uppercase;letter-spacing:0.5px;font-weight:500}
  .pv{font-size:13px;font-weight:600;color:#1a1a1a}
  .card.sel .po.on .pv{color:#085041}

  /* RODAPÉ */
  .rodape{position:fixed;bottom:0;left:0;right:0;background:white;border-top:1px solid #e8e8e4;padding:0.75rem 1rem;display:flex;align-items:center;justify-content:space-between;gap:12px;z-index:30;box-shadow:0 -4px 20px rgba(0,0,0,0.06)}
  .r-lbl{font-size:10px;color:#aaa;text-transform:uppercase;letter-spacing:0.5px}
  .r-total{font-size:18px;font-weight:700;color:#1a1a1a;letter-spacing:-0.3px}
  .r-qtd{font-size:11px;color:#888}
  .btn-w{display:flex;align-items:center;gap:6px;background:#1D9E75;color:white;border:none;border-radius:10px;padding:10px 16px;font-size:13px;font-weight:600;cursor:pointer;font-family:inherit;white-space:nowrap;text-decoration:none;opacity:0.35;pointer-events:none;transition:all 0.15s}
  .btn-w.on{opacity:1;pointer-events:auto}
  .btn-w:hover.on{background:#0F6E56}
  .btn-w svg{width:17px;height:17px;fill:white}

  /* ESTADOS */
  .loading{text-align:center;padding:4rem 1rem;color:#aaa;font-size:14px}
  .loading-dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:#1D9E75;margin:0 2px;animation:pulse 1.2s ease-in-out infinite}
  .loading-dot:nth-child(2){animation-delay:0.2s}
  .loading-dot:nth-child(3){animation-delay:0.4s}
  @keyframes pulse{0%,80%,100%{opacity:0.2}40%{opacity:1}}
  .erro{text-align:center;padding:3rem 1rem;color:#888;font-size:13px;line-height:1.7}
</style>
</head>
<body>

<div class="wrap">
  <div class="hdr">
    <div class="hdr-top">
      <div class="logo">ZIG <span>Locações</span></div>
      <a class="wpp-topo" href="https://wa.me/5531975758250">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="#1D9E75"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.122.554 4.122 1.527 5.855L.057 23.882l6.195-1.624A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.794 9.794 0 01-5.007-1.374l-.359-.214-3.718.975.993-3.625-.234-.372A9.794 9.794 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182c5.43 0 9.818 4.388 9.818 9.818 0 5.43-4.388 9.818-9.818 9.818z"/></svg>
        (31) 97575-8250
      </a>
    </div>
    <div class="sub">Selecione os equipamentos e solicite orçamento</div>
  </div>

  <div class="filtros" id="filtros"></div>

  <div class="lista" id="lista">
    <div class="loading">
      <div style="margin-bottom:12px">
        <span class="loading-dot"></span>
        <span class="loading-dot"></span>
        <span class="loading-dot"></span>
      </div>
      Carregando equipamentos...
    </div>
  </div>
</div>

<div class="rodape">
  <div>
    <div class="r-lbl">total estimado</div>
    <div class="r-total" id="r-total">R$ 0</div>
    <div class="r-qtd" id="r-qtd">Nenhum selecionado</div>
  </div>
  <a id="btn-w" class="btn-w" href="#">
    <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.122.554 4.122 1.527 5.855L.057 23.882l6.195-1.624A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.794 9.794 0 01-5.007-1.374l-.359-.214-3.718.975.993-3.625-.234-.372A9.794 9.794 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182c5.43 0 9.818 4.388 9.818 9.818 0 5.43-4.388 9.818-9.818 9.818z"/></svg>
    Pedir orçamento
  </a>
</div>

<script>
const API = "https://script.google.com/macros/s/AKfycbxR2rX9BJ5YrskpdVZwFBVmkIJkteI-QIP9NRHTPeizBBSp8KdE4zbgIst6mdWgdRHN/exec";
const WPP = "5531975758250";
const PL = {d:"Diária",s:"Semanal",m:"Mensal"};

const ICOS = {
  "acessorio":'<path d="M12 2a2 2 0 0 1 2 2v1h3a1 1 0 0 1 1 1v14a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1V6a1 1 0 0 1 1-1h3V4a2 2 0 0 1 2-2zm0 2v1H9V4h6v1h-3z"/>',
  "altura":'<path d="M3 20h18M8 20V8l4-4 4 4v12M10 20v-5h4v5"/>',
  "compactação":'<path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>',
  "compactacao":'<path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>',
  "concretagem":'<path d="M3 21h18M5 21V7l7-4 7 4v14M9 21V13h6v8"/>',
  "demolição":'<path d="M15 12l-8.5 8.5a1.5 1.5 0 0 1-2-2L13 10M18 9l.9-.9a2 2 0 0 0 0-2.8l-1.2-1.2a2 2 0 0 0-2.8 0L14 5M17 12l4 4M9 7l4 4"/>',
  "demolicao":'<path d="M15 12l-8.5 8.5a1.5 1.5 0 0 1-2-2L13 10M18 9l.9-.9a2 2 0 0 0 0-2.8l-1.2-1.2a2 2 0 0 0-2.8 0L14 5M17 12l4 4M9 7l4 4"/>',
  "escoramento":'<path d="M3 21h18M5 5v16M19 5v16M5 8h14M5 13h14"/>',
  "ferramentas eletricas":'<path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>',
  "ferramentas elétricas":'<path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>',
};

function getIco(grupo){
  const k=(grupo||"").toLowerCase();
  const d=ICOS[k]||'<path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>';
  return`<svg viewBox="0 0 24 24" width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">${d}</svg>`;
}

let equips=[],filtro="Todos",sel={};

function fmt(n){return"R$ "+Math.round(n).toLocaleString("pt-BR");}

async function load(){
  try{
    const r=await fetch(API);
    if(!r.ok)throw new Error();
    equips=await r.json();
    if(!Array.isArray(equips)||!equips.length)throw new Error("vazio");
  }catch(e){
    document.getElementById("lista").innerHTML=
      '<div class="erro">Não foi possível carregar os equipamentos.<br>Verifique a conexão e tente novamente.<br><br><a href="https://wa.me/5531975758250" style="color:#1D9E75;font-weight:600">Fale diretamente no WhatsApp →</a></div>';
    return;
  }
  renderFiltros();
  renderLista();
}

function renderFiltros(){
  const grupos=["Todos",...new Set(equips.map(e=>(e.grupo||"").toLowerCase()))];
  document.getElementById("filtros").innerHTML=grupos.map(g=>{
    const label=g==="Todos"?"Todos":g.charAt(0).toUpperCase()+g.slice(1);
    return`<button class="fb${filtro===g?" on":""}" onclick="setF('${g}')">${label}</button>`;
  }).join("");
}

function setF(g){filtro=g;renderFiltros();renderLista();}

function renderLista(){
  const itens=filtro==="Todos"?equips:equips.filter(e=>(e.grupo||"").toLowerCase()===filtro);
  if(!itens.length){document.getElementById("lista").innerHTML='<div class="loading">Nenhum equipamento encontrado</div>';return;}
  document.getElementById("lista").innerHTML=itens.map(eq=>{
    const s=sel[eq.nome],p=s?.periodo||"d";
    const grpKey=(eq.grupo||"").toLowerCase();
    const nm=eq.nome.replace(/'/g,"\\'");
    const imgHtml=eq.foto&&eq.foto.startsWith("http")
      ?`<img src="${eq.foto}" alt="${eq.nome}" onerror="this.parentNode.innerHTML='${getIco(grpKey).replace(/'/g,"\\'")}'"/>`
      :getIco(grpKey);
    return`<div class="card${s?" sel":""}">
      <div class="card-top" onclick="tog('${nm}')">
        <div class="icn-wrap">${imgHtml}</div>
        <div class="eq-info">
          <div class="eq-nome">${eq.nome}</div>
          <div class="eq-grp">${eq.grupo||""}</div>
        </div>
        <div class="chk"><svg viewBox="0 0 24 24"><polyline points="20 6 9 17 4 12"/></svg></div>
      </div>
      <div class="periodos">
        ${[["d","Diária"],["s","Semanal"],["m","Mensal"]].map(([k,l])=>
          `<div class="po${s&&p===k?" on":""}" onclick="setPer('${nm}','${k}')">
            <span class="pl">${l}</span>
            <span class="pv">${fmt(eq[k])}</span>
          </div>`
        ).join("")}
      </div>
    </div>`;
  }).join("");
}

function tog(nome){
  if(sel[nome])delete sel[nome];else sel[nome]={periodo:"d"};
  renderLista();upd();
}

function setPer(nome,p){
  if(!sel[nome])sel[nome]={};
  sel[nome].periodo=p;
  renderLista();upd();
}

function upd(){
  const ns=Object.keys(sel);
  const tot=ns.reduce((a,n)=>{const e=equips.find(x=>x.nome===n),p=sel[n].periodo;return a+(e?e[p]:0);},0);
  document.getElementById("r-total").textContent=fmt(tot);
  document.getElementById("r-qtd").textContent=ns.length===0
    ?"Nenhum selecionado"
    :`${ns.length} equipamento${ns.length>1?"s":""} selecionado${ns.length>1?"s":""}`;
  const btn=document.getElementById("btn-w");
  if(ns.length===0){btn.classList.remove("on");btn.removeAttribute("href");}
  else{
    btn.classList.add("on");
    let msg="Olá, gostaria de solicitar uma cotação.\n\nEquipamentos selecionados:\n";
    ns.forEach((n,i)=>{const e=equips.find(x=>x.nome===n),p=sel[n].periodo;msg+=`${i+1}- ${n} (${PL[p]}): ${fmt(e[p])}\n`;});
    msg+=`\nTotal estimado: ${fmt(tot)}\n\nAguardo confirmação de disponibilidade e valores de entrega. Obrigado!`;
    btn.href=`https://wa.me/${WPP}?text=${encodeURIComponent(msg)}`;
    btn.target="_blank";
  }
}

load();
</script>
</body>
</html>
