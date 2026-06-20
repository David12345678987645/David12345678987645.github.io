<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Solicitud de Habeas Corpus</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,500;0,600;0,700;1,500&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #f4f1e8;
    --surface: #ffffff;
    --ink: #1c2333;
    --navy: #142440;
    --navy-deep: #0c1830;
    --rule: #d9d2bd;
    --rule-soft: #e8e3d3;
    --brick: #963a2a;
    --brick-soft: #f1ddd5;
    --green: #1f6d4a;
    --green-dark: #154f37;
    --green-soft: #e3efe8;
    --muted: #6b6657;
  }

  *{ box-sizing: border-box; }

  body{
    margin:0;
    background: var(--bg);
    background-image:
      repeating-linear-gradient(0deg, rgba(0,0,0,0.015) 0px, rgba(0,0,0,0.015) 1px, transparent 1px, transparent 3px);
    color: var(--ink);
    font-family: 'Inter', system-ui, sans-serif;
    line-height: 1.5;
    -webkit-font-smoothing: antialiased;
  }

  .wrap{
    max-width: 720px;
    margin: 0 auto;
    padding: 0 20px 64px;
  }

  /* Letterhead */
  .letterhead{
    background: var(--navy);
    background-image: linear-gradient(160deg, var(--navy) 0%, var(--navy-deep) 100%);
    color: #f4f1e8;
    margin: 0 -20px 0;
    padding: 36px 20px 44px;
    position: relative;
    overflow: hidden;
  }
  .letterhead::after{
    content:"";
    position:absolute;
    left:0; right:0; bottom:0;
    height: 6px;
    background: repeating-linear-gradient(90deg, #b8924a 0 14px, #a07f3f 14px 16px);
    opacity:.7;
  }
  .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: .14em;
    text-transform: uppercase;
    color: #c9b98a;
    margin: 0 0 10px;
  }
  h1{
    font-family:'Lora', serif;
    font-weight: 600;
    font-size: clamp(28px, 5vw, 38px);
    margin: 0 0 12px;
    letter-spacing: -0.01em;
  }
  .lede{
    max-width: 56ch;
    color: #d8d4c4;
    font-size: 15px;
    margin: 0;
  }
  .stamp{
    position: absolute;
    top: 28px;
    right: 24px;
    border: 2px solid #c0594a;
    color: #e2897c;
    font-family:'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: .12em;
    padding: 6px 10px;
    transform: rotate(6deg);
    border-radius: 3px;
    opacity: .85;
  }

  /* Card */
  .card{
    background: var(--surface);
    margin-top: -22px;
    border-radius: 4px;
    box-shadow: 0 18px 40px -22px rgba(12,24,48,0.35);
    border: 1px solid var(--rule-soft);
    position: relative;
  }

  form{ padding: 8px 28px 28px; }

  section.block{
    padding: 26px 0;
    border-bottom: 1px solid var(--rule-soft);
  }
  section.block:last-of-type{ border-bottom: none; }

  .block-head{
    display:flex;
    align-items:baseline;
    gap: 10px;
    margin-bottom: 18px;
  }
  .block-num{
    font-family:'Lora', serif;
    font-style: italic;
    font-weight: 600;
    font-size: 14px;
    color: var(--brick);
  }
  .block-title{
    font-family:'Lora', serif;
    font-weight: 600;
    font-size: 17px;
    color: var(--navy);
    margin: 0;
  }

  .field{
    margin-bottom: 16px;
  }
  .field:last-child{ margin-bottom: 0; }

  label{
    display:block;
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
    margin-bottom: 6px;
  }
  label .req{ color: var(--brick); margin-left: 2px; }
  label .opt{
    font-weight: 400;
    color: var(--muted);
    font-size: 12px;
  }
  .hint{
    font-size: 12px;
    color: var(--muted);
    margin: 4px 0 0;
  }

  input[type=text], input[type=tel], input[type=datetime-local], select, textarea{
    width: 100%;
    font-family: 'Inter', sans-serif;
    font-size: 14.5px;
    color: var(--ink);
    background: #fcfbf8;
    border: 1px solid #cbc4ac;
    border-radius: 3px;
    padding: 10px 12px;
    transition: border-color .15s, box-shadow .15s;
  }
  textarea{ resize: vertical; min-height: 76px; }

  input:focus, select:focus, textarea:focus{
    outline: none;
    border-color: var(--navy);
    box-shadow: 0 0 0 3px rgba(20,36,64,0.12);
  }

  .grid-2{
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  @media (max-width: 540px){
    .grid-2{ grid-template-columns: 1fr; }
    .letterhead{ padding-top: 30px; }
    .stamp{ position: static; display:inline-block; margin-top: 14px; transform: rotate(-2deg); }
  }

  fieldset{
    border: none;
    margin: 0;
    padding: 0;
  }
  .check-row{
    display:flex;
    gap: 10px;
    align-items:flex-start;
    padding: 8px 0;
    border-bottom: 1px dashed var(--rule-soft);
  }
  .check-row:last-of-type{ border-bottom: none; }
  .check-row input[type=checkbox]{
    margin-top: 3px;
    width: 16px; height: 16px;
    accent-color: var(--navy);
    flex-shrink: 0;
  }
  .check-row label{
    margin: 0;
    font-weight: 400;
    font-size: 14px;
    color: var(--ink);
  }

  /* Submit */
  .submit-bar{
    padding: 22px 28px 30px;
    background: var(--green-soft);
    border-top: 1px solid var(--rule-soft);
    border-radius: 0 0 4px 4px;
  }
  .submit-bar p{
    margin: 0 0 14px;
    font-size: 12.5px;
    color: #2f4a3c;
  }
  button#sendBtn{
    width: 100%;
    background: var(--green);
    color: #fff;
    border: none;
    border-radius: 3px;
    padding: 15px 20px;
    font-family: 'Inter', sans-serif;
    font-weight: 700;
    font-size: 15.5px;
    letter-spacing: .01em;
    cursor: pointer;
    display:flex;
    align-items:center;
    justify-content:center;
    gap: 10px;
    transition: background .15s, transform .1s;
  }
  button#sendBtn:hover{ background: var(--green-dark); }
  button#sendBtn:active{ transform: translateY(1px); }
  button#sendBtn:disabled{
    background: #8aa698;
    cursor: not-allowed;
  }

  .spinner{
    width: 15px; height: 15px;
    border: 2px solid rgba(255,255,255,.4);
    border-top-color: #fff;
    border-radius: 50%;
    animation: spin .7s linear infinite;
    display:none;
  }
  button#sendBtn.loading .spinner{ display:inline-block; }
  @keyframes spin{ to{ transform: rotate(360deg); } }

  .status{
    margin-top: 14px;
    padding: 12px 14px;
    border-radius: 3px;
    font-size: 13.5px;
    display:none;
  }
  .status.show{ display:block; }
  .status.ok{ background:#dcefe2; color:#155c37; border:1px solid #aed8bb; }
  .status.err{ background:var(--brick-soft); color:#7a2e20; border:1px solid #e2b6a8; }

  footer{
    text-align:center;
    padding: 22px 10px 0;
    font-size: 12px;
    color: var(--muted);
  }
  footer a{ color: var(--navy); }
</style>
</head>
<body>
<div class="wrap">

  <header class="letterhead">
    <p class="eyebrow">Petición constitucional · Recurso de urgencia</p>
    <h1>Solicitud de Habeas Corpus</h1>
    <p class="lede">Completa los datos para preparar y enviar la solicitud. Toda la información se transmite directamente al canal de seguimiento del equipo de respuesta.</p>
    <span class="stamp">Urgente</span>
  </header>

  <div class="card">
    <form id="habeasForm" novalidate>

      <section class="block">
        <div class="block-head">
          <span class="block-num">I.</span>
          <h2 class="block-title">Datos de la persona detenida</h2>
        </div>

        <div class="field">
          <label for="detNombre">Nombre completo del detenido<span class="req">*</span></label>
          <input type="text" id="detNombre" required>
        </div>

        <div class="grid-2">
          <div class="field">
            <label for="detDoc">Documento de identidad<span class="opt">(opcional)</span></label>
            <input type="text" id="detDoc">
          </div>
          <div class="field">
            <label for="fechaDet">Fecha y hora de la detención<span class="req">*</span></label>
            <input type="datetime-local" id="fechaDet" required>
          </div>
        </div>
      </section>

      <section class="block">
        <div class="block-head">
          <span class="block-num">II.</span>
          <h2 class="block-title">Datos de la detención</h2>
        </div>

        <div class="field">
          <label for="lugarDet">Lugar donde ocurrió la detención<span class="req">*</span></label>
          <input type="text" id="lugarDet" placeholder="Dirección, ciudad, punto de referencia" required>
        </div>

        <div class="field">
          <label for="lugarActual">Lugar actual donde se encuentra el detenido<span class="opt">(si se conoce)</span></label>
          <input type="text" id="lugarActual" placeholder="Comisaría, cuartel, centro de detención...">
        </div>

        <div class="grid-2">
          <div class="field">
            <label for="institucion">Institución o cuerpo de seguridad</label>
            <select id="institucion">
              <option value="">— Selecciona —</option>
              <option>Policía Nacional</option>
              <option>Policía Local</option>
              <option>Guardia Civil</option>
              <option>Fuerzas Armadas</option>
              <option>Otra</option>
            </select>
          </div>
          <div class="field">
            <label for="placaAgente">Nombre y/o placa del agente<span class="opt">(opcional)</span></label>
            <input type="text" id="placaAgente" placeholder="Ej. Agente 4471">
          </div>
        </div>

        <div class="field">
          <label for="motivoOficial">Motivo de la detención informado por la autoridad<span class="opt">(opcional)</span></label>
          <textarea id="motivoOficial" placeholder="Lo que la autoridad indicó al momento de la detención"></textarea>
        </div>
      </section>

      <section class="block">
        <div class="block-head">
          <span class="block-num">III.</span>
          <h2 class="block-title">Motivo de la solicitud</h2>
        </div>

        <fieldset>
          <div class="check-row">
            <input type="checkbox" id="m1" value="Detención sin orden judicial">
            <label for="m1">Detención sin orden judicial</label>
          </div>
          <div class="check-row">
            <input type="checkbox" id="m2" value="No fue presentado ante un juez dentro del plazo legal">
            <label for="m2">No fue presentado ante un juez dentro del plazo legal</label>
          </div>
          <div class="check-row">
            <input type="checkbox" id="m3" value="Incomunicación / no se permite contacto con familiares o abogado">
            <label for="m3">Incomunicación / no se permite contacto con familiares o abogado</label>
          </div>
          <div class="check-row">
            <input type="checkbox" id="m4" value="Indicios de malos tratos o posible tortura">
            <label for="m4">Indicios de malos tratos o posible tortura</label>
          </div>
          <div class="check-row">
            <input type="checkbox" id="m5" value="Otras">
            <label for="m5">Otras</label>
          </div>
        </fieldset>

        <div class="field" style="margin-top:14px;">
          <label for="motivoDetalle">Explica con más detalle el motivo de la solicitud<span class="req">*</span></label>
          <textarea id="motivoDetalle" placeholder="Describe lo ocurrido con el mayor detalle posible: hechos, hora, testigos, condiciones..." required></textarea>
        </div>
      </section>

      <section class="block">
        <div class="block-head">
          <span class="block-num">IV.</span>
          <h2 class="block-title">Datos de quien solicita</h2>
        </div>

        <div class="grid-2">
          <div class="field">
            <label for="solNombre">Nombre completo<span class="req">*</span></label>
            <input type="text" id="solNombre" required>
          </div>
        </div>

        <div class="field">
          <label for="solTelefono">Teléfono de contacto<span class="req">*</span></label>
          <input type="tel" id="solTelefono" placeholder="+34 600 000 000" required>
        </div>

        <div class="field">
          <label for="infoAdicional">Información adicional o testigos<span class="opt">(opcional)</span></label>
          <textarea id="infoAdicional" placeholder="Nombres de testigos, datos de contacto, cualquier otro dato relevante"></textarea>
        </div>
      </section>

      <div class="submit-bar">
        <p>Al enviar, los datos de este formulario se transmiten de forma inmediata al equipo de seguimiento. Revisa la información antes de continuar.</p>
        <button type="submit" id="sendBtn">
          <span class="spinner"></span>
          <span class="btn-text">Enviar solicitud</span>
        </button>
        <div class="status" id="status"></div>
      </div>
    </form>
  </div>

  <footer>
    Esta herramienta no sustituye la asesoría de un abogado.<br>
    Para asistencia legal inmediata, contacta a un profesional o a la defensoría pública de tu zona.
  </footer>
</div>

<script>
  // ───────────────────────────────────────────────────────────
  // CONFIGURACIÓN: pega aquí la URL de tu webhook de Discord.
  // Server Settings → Integrations → Webhooks → New Webhook → Copy URL
  // ───────────────────────────────────────────────────────────
  const DISCORD_WEBHOOK_URL = "https://discord.com/api/webhooks/1517856410317095054/nDK6pmCV4Cw59J13VtpmPd6lGXWm_4Tmcu4x5hLoVEJEByI73NrBWquXb0_fCvBf9PDl";

  const form = document.getElementById('habeasForm');
  const btn = document.getElementById('sendBtn');
  const btnText = btn.querySelector('.btn-text');
  const statusBox = document.getElementById('status');

  function showStatus(kind, msg){
    statusBox.className = 'status show ' + kind;
    statusBox.textContent = msg;
  }

  function val(id){
    return document.getElementById(id).value.trim();
  }

  function truncate(str, max){
    if (!str) return '— No indicado —';
    return str.length > max ? str.slice(0, max - 1) + '…' : str;
  }

  function fmtFecha(raw){
    if (!raw) return '— No indicada —';
    const d = new Date(raw);
    if (isNaN(d)) return raw;
    return d.toLocaleString('es-ES', { dateStyle: 'long', timeStyle: 'short' });
  }

  form.addEventListener('submit', async (e) => {
    e.preventDefault();

    if (DISCORD_WEBHOOK_URL.includes('PEGA_AQUI')) {
      showStatus('err', 'Falta configurar la URL del webhook de Discord en el código antes de usar este formulario.');
      return;
    }

    const required = ['detNombre','fechaDet','lugarDet','motivoDetalle','solNombre','solTelefono'];
    let missing = false;
    required.forEach(id => {
      const el = document.getElementById(id);
      if (!el.value.trim()) {
        el.style.borderColor = '#963a2a';
        missing = true;
      } else {
        el.style.borderColor = '';
      }
    });
    if (missing) {
      showStatus('err', 'Completa los campos obligatorios marcados con *.');
      return;
    }

    const motivos = ['m1','m2','m3','m4','m5']
      .filter(id => document.getElementById(id).checked)
      .map(id => document.getElementById(id).value);

    const payload = {
      content: '📋 **Nueva solicitud de Habeas Corpus <@&1490738175998431425>**',
      embeds: [
        {
          title: 'Solicitud de Habeas Corpus',
          color: 2071626, // verde
          timestamp: new Date().toISOString(),
          fields: [
            { name: '👤 Detenido — nombre completo', value: truncate(val('detNombre'), 1024) },
            { name: '🪪 Documento de identidad', value: truncate(val('detDoc'), 1024), inline: true },
            { name: '🕒 Fecha y hora de la detención', value: truncate(fmtFecha(val('fechaDet')), 1024), inline: true },
            { name: '📍 Lugar de la detención', value: truncate(val('lugarDet'), 1024) },
            { name: '🏢 Lugar actual de reclusión', value: truncate(val('lugarActual'), 1024) },
            { name: '🚓 Institución', value: truncate(val('institucion'), 1024), inline: true },
            { name: '🔢 Agente / placa', value: truncate(val('placaAgente'), 1024), inline: true },
            { name: '📝 Motivo informado por la autoridad', value: truncate(val('motivoOficial'), 1024) },
            { name: '⚖️ Motivos marcados de la solicitud', value: motivos.length ? truncate(motivos.join('\n• '), 1024) : '— Ninguno marcado —' },
            { name: '🗒️ Detalle del motivo', value: truncate(val('motivoDetalle'), 1024) },
            { name: '🙋 Solicitante', value: truncate(val('solNombre'), 1024), inline: true },
            { name: '🔗 Relación con el detenido', value: truncate(val('solRelacion'), 1024), inline: true },
            { name: '📞 Teléfono de contacto', value: truncate(val('solTelefono'), 1024) },
            { name: 'ℹ️ Información adicional / testigos', value: truncate(val('infoAdicional'), 1024) }
          ]
        }
      ]
    };

    btn.disabled = true;
    btn.classList.add('loading');
    btnText.textContent = 'Enviando…';
    statusBox.className = 'status';

    try {
      const res = await fetch(DISCORD_WEBHOOK_URL, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(payload)
      });

      if (res.ok || res.status === 204) {
        showStatus('ok', 'Solicitud enviada correctamente. El equipo de seguimiento ha sido notificado.');
        form.reset();
      } else {
        showStatus('err', 'No se pudo enviar la solicitud (código ' + res.status + '). Inténtalo de nuevo.');
      }
    } catch (err) {
      showStatus('err', 'Error de conexión al enviar la solicitud. Verifica tu internet e inténtalo de nuevo.');
    } finally {
      btn.disabled = false;
      btn.classList.remove('loading');
      btnText.textContent = 'Enviar solicitud';
    }
  });
</script>
</body>
</html>
