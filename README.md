[index.html](https://github.com/user-attachments/files/29156832/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZIG Locações — Catálogo</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;background:#f8f8f6;color:#1a1a1a;-webkit-font-smoothing:antialiased}
.wrap{max-width:480px;margin:0 auto;padding-bottom:120px}

.hdr{background:white;padding:1rem 1rem 0.75rem;border-bottom:1px solid #e8e8e4;position:sticky;top:0;z-index:20}
.hdr-top{display:flex;align-items:center;justify-content:space-between}
.logo{font-size:18px;font-weight:600;color:#1a1a1a;letter-spacing:-0.3px}
.logo span{color:#1D9E75}
.wpp-topo{display:flex;align-items:center;gap:4px;font-size:12px;color:#1D9E75;text-decoration:none;font-weight:500}
.sub{font-size:12px;color:#888;margin-top:3px}

.filtros{background:white;display:flex;gap:6px;padding:0.6rem 1rem;overflow-x:auto;scrollbar-width:none;border-bottom:1px solid #e8e8e4}
.filtros::-webkit-scrollbar{display:none}
.fb{flex-shrink:0;font-size:11px;padding:5px 12px;border-radius:20px;border:1px solid #ddd;background:white;color:#666;cursor:pointer;font-family:inherit;white-space:nowrap;transition:all 0.15s}
.fb:hover{border-color:#1D9E75;color:#1D9E75}
.fb.on{background:#085041;border-color:#085041;color:white}

.lista{padding:0.75rem}

.card{display:flex;align-items:center;gap:10px;background:white;border:1px solid #e8e8e4;border-radius:10px;padding:10px;margin-bottom:6px;transition:border-color 0.15s,box-shadow 0.15s;position:relative}
.card.sel{border-color:#1D9E75;box-shadow:0 0 0 3px rgba(29,158,117,0.1)}
.card:active{transform:scale(0.99)}

.btn-x{position:absolute;top:6px;right:6px;width:18px;height:18px;border-radius:50%;background:#1D9E75;border:none;cursor:pointer;display:none;align-items:center;justify-content:center;padding:0;line-height:1}
.card.sel .btn-x{display:flex}
.btn-x svg{width:10px;height:10px;stroke:white;fill:none;stroke-width:2.5;stroke-linecap:round}

.foto{width:44px;height:44px;border-radius:8px;background:#f3f3f0;flex-shrink:0;overflow:hidden;display:flex;align-items:center;justify-content:center;cursor:pointer}
.card.sel .foto{background:#E1F5EE}
.foto svg{transition:stroke 0.15s}
.card.sel .foto svg{stroke:#1D9E75}

.info{flex:1;min-width:0;cursor:pointer}
.nome{font-size:13px;font-weight:600;color:#1a1a1a;line-height:1.3;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;padding-right:20px}
.grp{font-size:10px;color:#aaa;margin-top:2px;text-transform:capitalize}

.btns{display:flex;gap:4px;flex-shrink:0}
.pb{display:flex;flex-direction:column;align-items:center;border:1px solid #e0e0dc;border-radius:7px;padding:5px 6px;cursor:pointer;min-width:64px;width:64px;text-align:center ;transition:all 0.15s;background:white;-webkit-tap-highlight-color:transparent}
.pb:hover{border-color:#1D9E75}
.pb.on{background:#1D9E75;border-color:#1D9E75}
.pl{font-size:9px;color:#aaa;text-transform:uppercase;letter-spacing:0.3px;font-weight:500}
.pv{font-size:11px;font-weight:700;color:#1a1a1a;margin-top:1px;font-variant-numeric:tabular-nums;min-width:36px;text-align:center}
.pb.on .pl{color:rgba(255,255,255,0.75)}
.pb.on .pv{color:white}.pv-r{font-size:9px;color:#aaa;margin-top:1px}.pb.on .pv-r{color:rgba(255,255,255,0.75)}
.rodape{position:fixed;bottom:0;left:0;right:0;background:white;border-top:1px solid #e8e8e4;padding:0.75rem 1rem;display:flex;align-items:center;justify-content:space-between;gap:12px;z-index:30;box-shadow:0 -4px 20px rgba(0,0,0,0.06)}
.r-lbl{font-size:10px;color:#aaa;text-transform:uppercase;letter-spacing:0.5px}
.r-total{font-size:18px;font-weight:700;color:#1a1a1a;letter-spacing:-0.3px}
.r-qtd{font-size:11px;color:#888}
.btn-w{display:flex;align-items:center;gap:6px;background:#1D9E75;color:white;border:none;border-radius:10px;padding:10px 16px;font-size:13px;font-weight:600;cursor:pointer;font-family:inherit;white-space:nowrap;text-decoration:none;opacity:0.35;pointer-events:none;transition:all 0.15s}
.btn-w.on{opacity:1;pointer-events:auto}
.btn-w:hover.on{background:#0F6E56}

.loading{text-align:center;padding:4rem 1rem;color:#aaa;font-size:14px}
.dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:#1D9E75;margin:0 2px;animation:p 1.2s ease-in-out infinite}
.dot:nth-child(2){animation-delay:.2s}.dot:nth-child(3){animation-delay:.4s}
@keyframes p{0%,80%,100%{opacity:.2}40%{opacity:1}}
.erro{text-align:center;padding:3rem 1rem;color:#888;font-size:13px;line-height:1.7}
</style>
</head>
<body>
<div class="wrap">
  <div class="hdr">
    <div class="hdr-top">
      <div class="logo">ZIG <span>Locações</span></div>
      <a class="wpp-topo" href="https://wa.me/5531975758250">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="#1D9E75"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.122.554 4.122 1.527 5.855L.057 23.882l6.195-1.624A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.794 9.794 0 01-5.007-1.374l-.359-.214-3.718.975.993-3.625-.234-.372A9.794 9.794 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182c5.43 0 9.818 4.388 9.818 9.818 0 5.43-4.388 9.818-9.818 9.818z"/></svg>
        (31) 97575-8250
      </a>
    </div>
    <div class="sub">Selecione os equipamentos e solicite orçamento</div>
  </div>
  <div class="filtros" id="filtros"></div>
  <div class="lista" id="lista">
    <div class="loading"><div style="margin-bottom:12px"><span class="dot"></span><span class="dot"></span><span class="dot"></span></div>Carregando equipamentos...</div>
  </div>
</div>

<div class="rodape">
  <div>
    <div class="r-lbl">total estimado</div>
    <div class="r-total" id="r-total">R$ 0</div>
    <div class="r-qtd" id="r-qtd">Nenhum selecionado</div>
  </div>
  <a id="btn-w" class="btn-w" href="#">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.122.554 4.122 1.527 5.855L.057 23.882l6.195-1.624A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.794 9.794 0 01-5.007-1.374l-.359-.214-3.718.975.993-3.625-.234-.372A9.794 9.794 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182c5.43 0 9.818 4.388 9.818 9.818 0 5.43-4.388 9.818-9.818 9.818z"/></svg>
    Pedir orçamento
  </a>
</div>

<script>
  
const API="https://script.google.com/macros/s/AKfycbx0KiXvHQm5R19E9AqE7gXiz-sNfvorl4pA4rkYYq_XjaO4leVtyAU6c3M7qAvj_ZxA/exec";
const WPP="5531975758250";
const PL={d:"Diária",s:"Semanal",m:"Mensal"};

const ICOS={
  "demolicao":`<svg width="24" height="31" viewBox="0 0 52 68" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><line x1="2" y1="16" x2="12" y2="16"/><line x1="2" y1="20" x2="12" y2="20"/><line x1="40" y1="16" x2="50" y2="16"/><line x1="40" y1="20" x2="50" y2="20"/><rect x="12" y="8" width="28" height="20" rx="3"/><line x1="18" y1="8" x2="18" y2="11"/><line x1="22" y1="8" x2="22" y2="11"/><line x1="26" y1="8" x2="26" y2="11"/><line x1="30" y1="8" x2="30" y2="11"/><line x1="34" y1="8" x2="34" y2="11"/><rect x="18" y="13" width="16" height="7" rx="1.5"/><rect x="19" y="28" width="14" height="8" rx="1"/><rect x="17" y="36" width="18" height="14" rx="2"/><line x1="17" y1="41" x2="35" y2="41"/><path d="M20 50h12l-2 5H22l-2-5z"/><rect x="23" y="55" width="6" height="8" rx="1"/><path d="M23 63h6v2l-2 3h-2l-2-3v-2z"/></svg>`,
  "concretagem":`<svg width="30" height="30" viewBox="0 0 56 56" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><ellipse cx="22" cy="20" rx="13" ry="9" transform="rotate(-25 22 20)"/><ellipse cx="13" cy="12" rx="5" ry="3.5" transform="rotate(-25 13 12)"/><rect x="32" y="16" width="9" height="14" rx="2"/><circle cx="36" cy="12" r="4"/><line x1="36" y1="8" x2="36" y2="16"/><line x1="32" y1="12" x2="40" y2="12"/><circle cx="36" cy="12" r="1.5"/><line x1="14" y1="36" x2="34" y2="36"/><line x1="14" y1="33" x2="14" y2="42"/><circle cx="18" cy="41" r="3.5"/><circle cx="18" cy="41" r="1.2"/><circle cx="36" cy="41" r="2.5"/><circle cx="36" cy="41" r="0.8"/></svg>`,
  "compactacao":`<svg width="24" height="31" viewBox="0 0 48 64" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="12" y="2" width="24" height="14" rx="3"/><circle cx="36" cy="9" r="3"/><line x1="39" y1="9" x2="46" y2="9"/><circle cx="46" cy="9" r="1.5"/><line x1="16" y1="7" x2="16" y2="12"/><line x1="20" y1="7" x2="20" y2="12"/><rect x="18" y="16" width="12" height="5" rx="1"/><line x1="15" y1="21" x2="33" y2="21"/><line x1="13" y1="24" x2="35" y2="24"/><line x1="15" y1="27" x2="33" y2="27"/><line x1="13" y1="30" x2="35" y2="30"/><line x1="15" y1="33" x2="33" y2="33"/><line x1="13" y1="36" x2="35" y2="36"/><rect x="14" y="39" width="20" height="7" rx="1"/><path d="M12 46h8a2 2 0 0 1 0 4H10a2 2 0 0 1-2-2"/><path d="M28 46h8a2 2 0 0 1 2 2v0a2 2 0 0 1-2 2H28"/></svg>`,
  "ferramentas eletricas":`<svg width="34" height="24" viewBox="0 0 64 44" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="44" cy="22" r="16"/><circle cx="44" cy="22" r="5"/><path d="M30 12a16 16 0 0 1 14-6"/><rect x="6" y="14" width="20" height="16" rx="3"/><path d="M6 16V9a3 3 0 0 0-3-3H2"/><path d="M6 28v7a3 3 0 0 0 3 3h2"/><line x1="10" y1="16" x2="10" y2="30"/><line x1="14" y1="16" x2="14" y2="30"/></svg>`,
  "equipamentos":`<svg width="26" height="32" viewBox="0 0 48 60" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="18" y="2" width="12" height="5" rx="1"/><rect x="20" y="7" width="8" height="10" rx="1"/><circle cx="24" cy="32" r="16"/><circle cx="24" cy="32" r="6"/><path d="M24 26c-2-2-5-2-6 1s0 5 2 6"/><path d="M24 26c2-2 5-1 6 2s0 5-2 6"/><path d="M18 32c-2 2-2 5 1 6s5 0 6-2"/><path d="M30 32c2 2 1 5-2 6s-5 0-6-2"/><path d="M40 32h6M40 29h6"/><rect x="10" y="48" width="28" height="5" rx="1"/><line x1="16" y1="48" x2="16" y2="44"/><line x1="32" y1="48" x2="32" y2="44"/></svg>`,
  "escoramento":`<svg width="20" height="32" viewBox="0 0 36 64" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="32" height="5" rx="1"/><rect x="14" y="7" width="8" height="18" rx="1"/><rect x="11" y="25" width="14" height="6" rx="1"/><line x1="11" y1="27" x2="25" y2="27"/><line x1="11" y1="29" x2="25" y2="29"/><rect x="15" y="31" width="6" height="20" rx="1"/><rect x="2" y="51" width="32" height="5" rx="1"/><line x1="18" y1="2" x2="18" y2="0"/><line x1="15" y1="0" x2="21" y2="0"/></svg>`,
  "altura":`<svg width="24" height="32" viewBox="0 0 44 64" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><line x1="8" y1="4" x2="8" y2="60"/><line x1="36" y1="4" x2="36" y2="60"/><line x1="8" y1="14" x2="36" y2="14"/><line x1="8" y1="26" x2="36" y2="26"/><line x1="8" y1="38" x2="36" y2="38"/><line x1="8" y1="50" x2="36" y2="50"/><path d="M4 60h8M32 60h8"/><path d="M4 4h8M32 4h8"/></svg>`,
  "acessorio":`<svg width="28" height="28" viewBox="0 0 52 52" fill="none" stroke="#888" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="12" y="8" width="28" height="28" rx="4"/><line x1="20" y1="2" x2="20" y2="12"/><line x1="32" y1="2" x2="32" y2="12"/><rect x="19" y="18" width="4" height="8" rx="1"/><rect x="29" y="18" width="4" height="8" rx="1"/><circle cx="26" cy="30" r="2"/><path d="M26 36v8M20 44h12"/></svg>`,
};

function getIco(grupo,sel){
  const k=normalizeGrp(grupo);
  const svg=ICOS[k]||ICOS["acessorio"];
  const color=sel?"#1D9E75":"#888";
  return svg.replace(/stroke="#888"/g,`stroke="${color}"`);
}

function normalizeGrp(g){
  return(g||"").toLowerCase().trim()
    .replace("demolição","demolicao")
    .replace("compactação","compactacao")
    .replace("é","e").replace("ç","c").replace("ã","a").replace("â","a").replace("ê","e");
}

let equips=[],filtro="Todos",sel={};
function fmt(n){return"R$"+Math.round(n).toLocaleString("pt-BR");}

async function load(){
  try{
    const r=await fetch(API,{redirect:"follow"});
    if(!r.ok)throw new Error();
    equips=await r.json();
    if(!Array.isArray(equips)||!equips.length)throw new Error();
  }catch(e){
    document.getElementById("lista").innerHTML='<div class="erro">Não foi possível carregar os equipamentos.<br><br><a href="https://wa.me/5531975758250" style="color:#1D9E75;font-weight:600">Fale no WhatsApp →</a></div>';
    return;
  }
  renderFiltros();renderLista();
}

function renderFiltros(){
  const grupos=["Todos",...new Set(equips.map(e=>(e.grupo||"").toLowerCase().trim()))];
  document.getElementById("filtros").innerHTML=grupos.map(g=>{
    const l=g==="Todos"?"Todos":g.charAt(0).toUpperCase()+g.slice(1);
    return`<button class="fb${filtro===g?" on":""}" onclick="setF('${g}')">${l}</button>`;
  }).join("");
}

function setF(g){filtro=g;renderFiltros();renderLista();}

function renderLista(){
  const itens=filtro==="Todos"?equips:equips.filter(e=>(e.grupo||"").toLowerCase().trim()===filtro);
  if(!itens.length){document.getElementById("lista").innerHTML='<div class="loading">Nenhum equipamento</div>';return;}
  document.getElementById("lista").innerHTML=itens.map(eq=>{
    const s=sel[eq.nome],p=s?.periodo||"d";
    const nm=eq.nome.replace(/\\/g,"\\\\").replace(/'/g,"\\'");
    return`<div class="card${s?" sel":""}">
      ${s?`<button class="btn-x" onclick="event.stopPropagation();desel('${nm}')" aria-label="Remover"><svg viewBox="0 0 12 12"><line x1="2" y1="2" x2="10" y2="10"/><line x1="10" y1="2" x2="2" y2="10"/></svg></button>`:""}
      <div class="foto" onclick="tog('${nm}')">${getIco(eq.grupo,!!s)}</div>
      <div class="info" onclick="tog('${nm}')">
        <div class="nome">${eq.nome}</div>
        <div class="grp">${eq.grupo||""}</div>
      </div>
      <div class="btns">
        ${[["d","Dia"],["s","Sem"],["m","Mês"]].map(([k,l])=>
          `<div class="pb${s&&p===k?" on":""}" onclick="setPer('${nm}','${k}')">
          <span class="pl">${l}</span>
            <span class="pv-r">R$</span><span class="pv">${Math.round(eq[k]).toLocaleString("pt-BR")}</span>
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
function desel(nome){delete sel[nome];renderLista();upd();}
function setPer(nome,p){
  if(!sel[nome])sel[nome]={};
  sel[nome].periodo=p;
  renderLista();upd();
}

function upd(){
  const ns=Object.keys(sel);
  const tot=ns.reduce((a,n)=>{const e=equips.find(x=>x.nome===n),p=sel[n].periodo;return a+(e?e[p]:0);},0);
  document.getElementById("r-total").textContent=fmt(tot);
  document.getElementById("r-qtd").textContent=ns.length===0?"Nenhum selecionado":`${ns.length} equipamento${ns.length>1?"s":""} selecionado${ns.length>1?"s":""}`;
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
