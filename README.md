<!DOCTYPE html>
<html lang="pt-BR" data-theme="light">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Clínica Veterinária</title>
  <link href="https://api.fontshare.com/v2/css?f[]=satoshi@300,400,500,700,900&display=swap" rel="stylesheet">
  <style>
    :root, [data-theme="light"] {
      --text-xs: clamp(0.75rem, 0.7rem + 0.25vw, 0.875rem);
      --text-sm: clamp(0.875rem, 0.8rem + 0.35vw, 1rem);
      --text-base: clamp(1rem, 0.95rem + 0.25vw, 1.125rem);
      --text-lg: clamp(1.125rem, 1rem + 0.75vw, 1.35rem);
      --text-xl: clamp(1.5rem, 1.2rem + 1.25vw, 2rem);
      --space-2:.5rem; --space-3:.75rem; --space-4:1rem; --space-5:1.25rem; --space-6:1.5rem; --space-8:2rem; --space-10:2.5rem;
      --radius-md:.75rem; --radius-lg:1rem; --radius-xl:1.25rem; --radius-full:9999px;
      --color-bg:#f5f6f7; --color-surface:#ffffff; --color-surface-2:#fafafb; --color-surface-offset:#eff1f3; --color-border:#dde2e7; --color-divider:#ebedf0;
      --color-text:#161a1f; --color-text-muted:#66707a; --color-text-inverse:#ffffff; --color-primary:#303942; --color-primary-hover:#1f252b; --color-primary-highlight:#dce2e8;
      --color-danger:#c63f3f; --color-danger-bg:#fdeaea; --color-warning:#b56a11; --color-warning-bg:#fff4e7; --color-success:#20744f; --color-success-bg:#e8f7ef; --color-info:#2669d6; --color-info-bg:#eaf1ff;
      --shadow-sm:0 1px 2px rgba(10,10,10,.04); --shadow-md:0 12px 30px rgba(10,10,10,.07);
      --font-body:'Satoshi',Inter,sans-serif; --sidebar-w:284px; --transition:180ms cubic-bezier(.16,1,.3,1);
    }
    [data-theme="dark"] {
      --color-bg:#0f1215; --color-surface:#171b20; --color-surface-2:#1c2127; --color-surface-offset:#21262d; --color-border:#2d353f; --color-divider:#252a30;
      --color-text:#f0f2f5; --color-text-muted:#adb5bf; --color-text-inverse:#15181c; --color-primary:#edf0f3; --color-primary-hover:#d8dee4; --color-primary-highlight:#272e36;
      --color-danger:#ff8484; --color-danger-bg:rgba(198,63,63,.14); --color-warning:#ffc270; --color-warning-bg:rgba(181,106,17,.18); --color-success:#73d4a4; --color-success-bg:rgba(32,116,79,.18); --color-info:#80adff; --color-info-bg:rgba(38,105,214,.18);
      --shadow-sm:0 1px 2px rgba(0,0,0,.25); --shadow-md:0 12px 30px rgba(0,0,0,.35);
    }
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%;overflow:hidden} body{font-family:var(--font-body);background:var(--color-bg);color:var(--color-text);font-size:var(--text-base)}
    button,input,select,textarea{font:inherit;color:inherit} button{cursor:pointer;border:none;background:none} img,svg{max-width:100%;display:block}
    .shell{display:grid;grid-template-columns:var(--sidebar-w) 1fr;height:100dvh}.sidebar{background:var(--color-surface);border-right:1px solid var(--color-border);padding:var(--space-6);display:flex;flex-direction:column;gap:var(--space-6)}
    .brand{display:flex;gap:var(--space-3);align-items:center}.brand-icon{width:46px;height:46px;border-radius:14px;background:var(--color-primary);color:var(--color-text-inverse);display:grid;place-items:center}.brand h1{font-size:var(--text-lg)}.brand p{font-size:var(--text-xs);color:var(--color-text-muted)}
    .nav{display:grid;gap:var(--space-2)} .nav button,.footer-btn{padding:.92rem 1rem;border-radius:var(--radius-md);text-align:left;font-size:var(--text-sm);font-weight:700;color:var(--color-text-muted);transition:all var(--transition)} .nav button:hover,.nav button.active,.footer-btn:hover{background:var(--color-primary);color:var(--color-text-inverse);transform:translateY(-1px)}
    .sidebar-footer{margin-top:auto;display:grid;gap:var(--space-3);border-top:1px solid var(--color-divider);padding-top:var(--space-4)}
    .content{display:grid;grid-template-rows:auto 1fr;overflow:hidden}.topbar{display:flex;justify-content:space-between;align-items:center;gap:var(--space-4);padding:var(--space-5) var(--space-6);border-bottom:1px solid var(--color-border);background:rgba(255,255,255,.76);backdrop-filter:blur(12px)}
    [data-theme="dark"] .topbar{background:rgba(23,27,32,.72)}
    .heading h2{font-size:var(--text-xl)} .heading p{font-size:var(--text-sm);color:var(--color-text-muted);margin-top:4px}
    .toolbar{display:flex;gap:var(--space-3);align-items:center}
    .btn,.input,.select{min-height:44px;border-radius:var(--radius-md);border:1px solid var(--color-border);padding:.85rem 1rem;background:var(--color-surface)}
    .btn{font-size:var(--text-sm);font-weight:800;transition:all var(--transition)} .btn.primary{background:var(--color-primary);color:var(--color-text-inverse);border-color:var(--color-primary)} .btn:hover{transform:translateY(-1px);box-shadow:var(--shadow-sm)}
    .main{overflow:auto;padding:var(--space-6);display:grid;gap:var(--space-6)} .page{display:none;gap:var(--space-6)} .page.active{display:grid}
    .stats{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:var(--space-4)} .card{background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-lg);box-shadow:var(--shadow-sm)} .stat{padding:var(--space-5);display:grid;gap:var(--space-3)} .stat span{font-size:var(--text-xs);letter-spacing:.08em;text-transform:uppercase;color:var(--color-text-muted)} .stat strong{font-size:1.7rem;font-variant-numeric:tabular-nums}
    .badge{display:inline-flex;align-items:center;padding:.35rem .7rem;border-radius:var(--radius-full);font-size:var(--text-xs);font-weight:800}.success{background:var(--color-success-bg);color:var(--color-success)}.danger{background:var(--color-danger-bg);color:var(--color-danger)}.warning{background:var(--color-warning-bg);color:var(--color-warning)}.info{background:var(--color-info-bg);color:var(--color-info)}
    .grid-2{display:grid;grid-template-columns:1.15fr .85fr;gap:var(--space-4)} .panel-head{padding:var(--space-5);display:flex;justify-content:space-between;gap:var(--space-4);align-items:center;border-bottom:1px solid var(--color-divider)} .panel-head h3{font-size:var(--text-lg)} .panel-head p{font-size:var(--text-sm);color:var(--color-text-muted);margin-top:4px}
    .panel-body{padding:var(--space-4)} .list{display:grid;gap:var(--space-3)} .item{display:grid;grid-template-columns:1fr auto;gap:var(--space-4);padding:var(--space-4);border:1px solid var(--color-border);background:var(--color-surface-2);border-radius:var(--radius-md);transition:all var(--transition)} .item:hover{transform:translateY(-1px);box-shadow:var(--shadow-sm)}
    .meta{display:flex;flex-wrap:wrap;gap:var(--space-3);font-size:var(--text-xs);color:var(--color-text-muted);margin-top:6px}
    .form-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:var(--space-4)} .field{display:grid;gap:8px} .field label{font-size:var(--text-xs);letter-spacing:.08em;text-transform:uppercase;font-weight:800;color:var(--color-text-muted)} textarea.input{min-height:100px;resize:vertical}
    .table-wrap{overflow:auto} table{width:100%;border-collapse:collapse} th,td{text-align:left;padding:1rem;border-bottom:1px solid var(--color-divider);font-size:var(--text-sm)} th{font-size:var(--text-xs);text-transform:uppercase;letter-spacing:.08em;color:var(--color-text-muted)}
    .action-row{display:flex;flex-wrap:wrap;gap:var(--space-2)} .mini{padding:.65rem .85rem;border-radius:var(--radius-md);border:1px solid var(--color-border);background:var(--color-surface);font-size:var(--text-xs);font-weight:800} .mini.primary{background:var(--color-info);border-color:var(--color-info);color:#fff} .mini.delete{background:var(--color-danger);border-color:var(--color-danger);color:#fff}
    .critical{background:var(--color-danger-bg)!important} .warn{background:var(--color-warning-bg)!important}
    .auth,.loader,.modal{position:fixed;inset:0;display:grid;place-items:center;z-index:40;padding:var(--space-4)} .auth{background:linear-gradient(180deg,var(--color-bg),var(--color-surface-offset))} .auth-card,.modal-card{width:min(920px,100%);background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-xl);box-shadow:var(--shadow-md)} .auth-card{width:min(460px,100%);padding:var(--space-8);display:grid;gap:var(--space-5)} .hint{font-size:var(--text-sm);color:var(--color-text-muted)} .error{display:none;padding:.9rem 1rem;border-radius:var(--radius-md);background:var(--color-danger-bg);color:var(--color-danger);font-weight:700} .error.show{display:block}
    .loader{background:var(--color-bg);transition:opacity .4s ease, visibility .4s ease} .loader.hidden{opacity:0;visibility:hidden}.spinner{width:52px;height:52px;border:4px solid var(--color-primary-highlight);border-top-color:var(--color-primary);border-radius:50%;animation:spin .9s linear infinite}@keyframes spin{to{transform:rotate(360deg)}}
    .modal{display:none;background:rgba(8,10,12,.5)} .modal.open{display:grid} .modal-body{padding:var(--space-6);display:grid;gap:var(--space-4)} .kv{display:grid;grid-template-columns:180px 1fr;gap:var(--space-3);font-size:var(--text-sm)} .kv strong{color:var(--color-text-muted)}
    @media (max-width:1024px){.stats{grid-template-columns:repeat(2,minmax(0,1fr))}.grid-2{grid-template-columns:1fr}.shell{grid-template-columns:92px 1fr}.brand h1,.brand p,.nav span,.footer-btn span:last-child{display:none}.nav button,.footer-btn{text-align:center;padding:.9rem}.sidebar{padding:var(--space-5)}}
    @media (max-width:768px){html,body{overflow:auto}.shell{grid-template-columns:1fr;height:auto}.sidebar{display:none}.content{overflow:visible}.topbar{position:sticky;top:0;z-index:10;flex-wrap:wrap;padding:var(--space-4)}.main{padding:var(--space-4)}.stats,.form-grid{grid-template-columns:1fr}.item,.kv{grid-template-columns:1fr}}
    @media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}
  </style>
</head>
<body>
  <div class="loader" id="loader"><div style="display:grid;gap:1rem;place-items:center"><div class="spinner"></div><p class="hint">Carregando painel veterinário...</p></div></div>
  <section class="auth" id="auth">
    <form class="auth-card" id="loginForm">
      <div class="brand"><div class="brand-icon"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.1"><path d="M12 14c3.2 0 5-1.8 5-4.2S15.8 4 12 4 7 5.6 7 9.8 8.8 14 12 14Z"/><path d="M8 13 4 20"/><path d="M16 13l4 7"/><path d="M10 14l-1 6"/><path d="M14 14l1 6"/></svg></div><div><h2>Clínica Veterinária</h2><p>Acesso administrativo</p></div></div>
      <p class="hint">Login hardcoded para demonstração: admin / admin</p>
      <div class="error" id="loginError">Usuário ou senha inválidos.</div>
      <div class="field"><label for="username">Login</label><input class="input" id="username" value="admin" /></div>
      <div class="field"><label for="password">Senha</label><input class="input" id="password" type="password" value="admin" /></div>
      <button class="btn primary" type="submit">Entrar</button>
    </form>
  </section>

  <div class="shell" id="app" hidden>
    <aside class="sidebar">
      <div class="brand"><div class="brand-icon"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.1"><path d="M12 14c3.2 0 5-1.8 5-4.2S15.8 4 12 4 7 5.6 7 9.8 8.8 14 12 14Z"/><path d="M8 13 4 20"/><path d="M16 13l4 7"/><path d="M10 14l-1 6"/><path d="M14 14l1 6"/></svg></div><div><h1>VetCare</h1><p>Gestão clínica</p></div></div>
      <nav class="nav">
        <button class="active" data-page="dashboard"><span>Início</span></button>
        <button data-page="atendimentos"><span>Atendimentos</span></button>
        <button data-page="internacao"><span>Internação</span></button>
        <button data-page="especialistas"><span>Especialista externo</span></button>
        <button data-page="medicamentos"><span>Medicamentos</span></button>
        <button data-page="financeiro"><span>Financeiro</span></button>
      </nav>
      <div class="sidebar-footer">
        <button class="footer-btn" id="themeBtn"><span>Tema</span><span>Claro / Escuro</span></button>
        <button class="footer-btn" id="logoutBtn"><span>Sair</span><span>Encerrar sessão</span></button>
      </div>
    </aside>

    <section class="content">
      <header class="topbar">
        <div class="heading"><h2 id="pageTitle">Início</h2><p id="pageSubtitle">Visão geral dos atendimentos, internações, especialistas e vendas.</p></div>
        <div class="toolbar"><select class="select"><option>Hoje</option><option>Últimos 7 dias</option><option>Últimos 30 dias</option></select><button class="btn primary" id="quickAction">Novo atendimento</button></div>
      </header>
      <main class="main">
        <section class="page active" id="page-dashboard">
          <div class="stats" id="stats"></div>
          <div class="grid-2">
            <article class="card"><div class="panel-head"><div><h3>Atendimentos do dia</h3><p>Fila clínica e status atual</p></div></div><div class="panel-body"><div class="list" id="todayAppointments"></div></div></article>
            <article class="card"><div class="panel-head"><div><h3>Pacientes internados</h3><p>Monitoramento ativo</p></div></div><div class="panel-body"><div class="list" id="inpatientsOverview"></div></div></article>
          </div>
        </section>

        <section class="page" id="page-atendimentos">
          <div class="grid-2">
            <article class="card"><div class="panel-head"><div><h3>Novo atendimento</h3><p>Cadastre consulta, retorno ou emergência</p></div></div><div class="panel-body"><form id="appointmentForm" class="form-grid"><div class="field"><label>Nome do pet</label><input class="input" id="petName" required></div><div class="field"><label>Tutor</label><input class="input" id="ownerName" required></div><div class="field"><label>Tipo</label><select class="input" id="appointmentType"><option>Consulta</option><option>Retorno</option><option>Emergência</option></select></div><div class="field"><label>Status</label><select class="input" id="appointmentStatus"><option>Aguardando</option><option>Em atendimento</option><option>Finalizado</option></select></div><div class="field" style="grid-column:1/-1"><label>Observações</label><textarea class="input" id="appointmentNotes"></textarea></div><button class="btn primary" type="submit" style="grid-column:1/-1">Salvar atendimento</button></form></div></article>
            <article class="card"><div class="panel-head"><div><h3>Lista de atendimentos</h3><p>Controle operacional da clínica</p></div></div><div class="panel-body"><div class="list" id="appointmentsList"></div></div></article>
          </div>
        </section>

        <section class="page" id="page-internacao">
          <article class="card"><div class="panel-head"><div><h3>Internação</h3><p>Animais internados, responsável e evolução clínica</p></div></div><div class="panel-body"><div class="list" id="inpatientList"></div></div></article>
        </section>

        <section class="page" id="page-especialistas">
          <article class="card"><div class="panel-head"><div><h3>Especialistas externos</h3><p>Controle de encaminhamentos e visitas</p></div></div><div class="panel-body table-wrap"><table><thead><tr><th>Especialista</th><th>Área</th><th>Paciente</th><th>Data</th><th>Status</th></tr></thead><tbody id="specialistsTable"></tbody></table></div></article>
        </section>

        <section class="page" id="page-medicamentos">
          <article class="card"><div class="panel-head"><div><h3>Medicamentos e estoque</h3><p>Venda e controle de baixa de estoque</p></div></div><div class="panel-body"><div class="list" id="medicationsList"></div></div></article>
        </section>

        <section class="page" id="page-financeiro">
          <article class="card"><div class="panel-head"><div><h3>Financeiro</h3><p>Entradas por atendimento, especialistas e medicamentos</p></div></div><div class="panel-body table-wrap"><table><thead><tr><th>Data</th><th>Origem</th><th>Descrição</th><th>Categoria</th><th>Valor</th></tr></thead><tbody id="financeTable"></tbody></table></div></article>
        </section>
      </main>
    </section>
  </div>

  <div class="modal" id="modal"><div class="modal-card"><div class="panel-head"><div><h3>Detalhes completos</h3><p>Informações detalhadas do registro selecionado</p></div><button class="btn" id="closeModal">Fechar</button></div><div class="modal-body" id="modalBody"></div></div></div>

<script>
const AUTH={login:'admin',password:'admin'};
const state={theme:matchMedia('(prefers-color-scheme: dark)').matches?'dark':'light',db:null,page:'dashboard'};
const fmtMoney=v=>v.toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
const fmtDate=d=>new Date(d+'T12:00:00').toLocaleDateString('pt-BR');
const daysTo=d=>Math.ceil((new Date(d+'T12:00:00')-new Date())/86400000);
const titleMap={dashboard:['Início','Visão geral dos atendimentos, internações, especialistas e vendas.'],atendimentos:['Atendimentos','Controle de consultas, retornos e emergências.'],internacao:['Internação','Acompanhamento dos pacientes internados.'],especialistas:['Especialista externo','Encaminhamentos e visitas de apoio.'],medicamentos:['Medicamentos','Estoque, alertas e vendas.'],financeiro:['Financeiro','Lançamentos consolidados da clínica.']};
function setTheme(t){state.theme=t;document.documentElement.setAttribute('data-theme',t)}
async function loadDb(){const r=await fetch('./vet-db.json');state.db=await r.json();renderAll()}
function showLoader(ms=900){const el=document.getElementById('loader');el.classList.remove('hidden');setTimeout(()=>el.classList.add('hidden'),ms)}
function renderStats(){
  const stats=[
    ['Atendimentos hoje', state.db.appointments.length, 'info'],
    ['Internados', state.db.inpatients.filter(i=>i.status==='Internado').length, 'warning'],
    ['Especialistas agendados', state.db.specialists.filter(s=>s.status!=='Concluído').length, 'success'],
    ['Receita total', fmtMoney(state.db.finance.reduce((a,b)=>a+b.amount,0)), 'success']
  ];
  document.getElementById('stats').innerHTML=stats.map(s=>`<article class="card stat"><span>${s[0]}</span><strong>${s[1]}</strong><small class="badge ${s[2]}">${s[0]}</small></article>`).join('')
}
function renderTodayAppointments(){document.getElementById('todayAppointments').innerHTML=state.db.appointments.map(a=>`<button class="item" onclick="openRecord('appointment','${a.id}')"><div><strong>${a.pet}</strong><div class="meta"><span>${a.owner}</span><span>${a.type}</span><span>${a.status}</span></div></div><span class="badge ${a.status==='Finalizado'?'success':a.status==='Em atendimento'?'warning':'info'}">${a.time}</span></button>`).join('')}
function renderInpatientsOverview(){document.getElementById('inpatientsOverview').innerHTML=state.db.inpatients.map(p=>{const flag=daysTo(p.nextMedication)<0?'critical':daysTo(p.nextMedication)<=1?'warn':'';return `<button class="item ${flag}" onclick="openRecord('inpatient','${p.id}')"><div><strong>${p.pet}</strong><div class="meta"><span>Leito ${p.bed}</span><span>${p.vet}</span><span>${p.status}</span></div></div><span class="badge warning">${fmtDate(p.nextMedication)}</span></button>`}).join('')}
function renderAppointmentsList(){document.getElementById('appointmentsList').innerHTML=state.db.appointments.map(a=>`<div class="item"><div><strong>${a.pet}</strong><div class="meta"><span>Tutor: ${a.owner}</span><span>${a.type}</span><span>${a.status}</span></div></div><div class="action-row"><button class="mini primary" onclick="openRecord('appointment','${a.id}')">Detalhes</button><button class="mini delete" onclick="deleteAppointment('${a.id}')">Excluir</button></div></div>`).join('')}
function renderInpatients(){document.getElementById('inpatientList').innerHTML=state.db.inpatients.map(p=>{const critical=daysTo(p.nextMedication)<0;return `<div class="item ${critical?'critical':''}"><div><strong>${p.pet}</strong><div class="meta"><span>Tutor: ${p.owner}</span><span>Leito ${p.bed}</span><span>Médico: ${p.vet}</span><span>Próxima medicação: ${fmtDate(p.nextMedication)}</span></div></div><div class="action-row"><button class="mini primary" onclick="openRecord('inpatient','${p.id}')">Detalhes</button><button class="mini">Atualizar evolução</button></div></div>`}).join('')}
function renderSpecialists(){document.getElementById('specialistsTable').innerHTML=state.db.specialists.map(s=>`<tr onclick="openRecord('specialist','${s.id}')" style="cursor:pointer"><td>${s.name}</td><td>${s.area}</td><td>${s.pet}</td><td>${fmtDate(s.date)}</td><td><span class="badge ${s.status==='Concluído'?'success':'info'}">${s.status}</span></td></tr>`).join('')}
function renderMedications(){document.getElementById('medicationsList').innerHTML=state.db.medications.map(m=>{const cls=m.stock<=5?'critical':m.stock<=10?'warn':'';return `<div class="item ${cls}"><div><strong>${m.name}</strong><div class="meta"><span>Estoque: ${m.stock}</span><span>Validade: ${fmtDate(m.expiry)}</span><span>Preço: ${fmtMoney(m.price)}</span></div></div><div class="action-row"><button class="mini primary" onclick="openRecord('medication','${m.id}')">Detalhes</button><button class="mini">Registrar venda</button></div></div>`}).join('')}
function renderFinance(){document.getElementById('financeTable').innerHTML=state.db.finance.map(f=>`<tr onclick="openRecord('finance','${f.id}')" style="cursor:pointer"><td>${fmtDate(f.date)}</td><td>${f.origin}</td><td>${f.description}</td><td>${f.category}</td><td>${fmtMoney(f.amount)}</td></tr>`).join('')}
function renderAll(){renderStats();renderTodayAppointments();renderInpatientsOverview();renderAppointmentsList();renderInpatients();renderSpecialists();renderMedications();renderFinance()}
function switchPage(page){state.page=page;document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));document.querySelectorAll('.nav button').forEach(b=>b.classList.remove('active'));document.getElementById('page-'+page).classList.add('active');document.querySelector(`[data-page="${page}"]`).classList.add('active');document.getElementById('pageTitle').textContent=titleMap[page][0];document.getElementById('pageSubtitle').textContent=titleMap[page][1];showLoader(450)}
function openRecord(type,id){let item=null;if(type==='appointment') item=state.db.appointments.find(x=>x.id===id);if(type==='inpatient') item=state.db.inpatients.find(x=>x.id===id);if(type==='specialist') item=state.db.specialists.find(x=>x.id===id);if(type==='medication') item=state.db.medications.find(x=>x.id===id);if(type==='finance') item=state.db.finance.find(x=>x.id===id);if(!item) return;document.getElementById('modalBody').innerHTML=Object.entries(item).map(([k,v])=>`<div class='kv'><strong>${k}</strong><span>${typeof v==='number'&&k!=='stock'?fmtMoney(v):v}</span></div>`).join('');document.getElementById('modal').classList.add('open')}
function deleteAppointment(id){state.db.appointments=state.db.appointments.filter(a=>a.id!==id);renderStats();renderTodayAppointments();renderAppointmentsList()}

document.getElementById('loginForm').addEventListener('submit',async e=>{e.preventDefault();if(username.value.trim()===AUTH.login&&password.value.trim()===AUTH.password){document.getElementById('auth').style.display='none';document.getElementById('app').hidden=false;setTheme(state.theme);showLoader(1000);if(!state.db) await loadDb()}else{document.getElementById('loginError').classList.add('show')}})
document.querySelectorAll('.nav button').forEach(b=>b.addEventListener('click',()=>switchPage(b.dataset.page)))
document.getElementById('closeModal').addEventListener('click',()=>document.getElementById('modal').classList.remove('open'))
document.getElementById('modal').addEventListener('click',e=>{if(e.target.id==='modal') e.currentTarget.classList.remove('open')})
document.getElementById('themeBtn').addEventListener('click',()=>setTheme(state.theme=state.theme==='dark'?'light':'dark'))
document.getElementById('logoutBtn').addEventListener('click',()=>{document.getElementById('app').hidden=true;document.getElementById('auth').style.display='grid'})
document.getElementById('quickAction').addEventListener('click',()=>switchPage('atendimentos'))
document.getElementById('appointmentForm').addEventListener('submit',e=>{e.preventDefault();state.db.appointments.unshift({id:'app-'+crypto.randomUUID().slice(0,8),pet:petName.value,owner:ownerName.value,type:appointmentType.value,status:appointmentStatus.value,time:'Novo',notes:appointmentNotes.value});e.target.reset();renderStats();renderTodayAppointments();renderAppointmentsList();switchPage('atendimentos')})
window.openRecord=openRecord;window.deleteAppointment=deleteAppointment;setTheme(state.theme);showLoader(1200)
</script>
</body>
</html>
