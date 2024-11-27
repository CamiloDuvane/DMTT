<html><head><base href="https://camiloduvane.github.io/DMTT/"><title>DMTT - Direção Municipal de Transportes e Trânsito</title><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<style>
:root {
  --primary: #4CAF50;  /* Change from #1a4b8c to a green color */
  --secondary: #e63946;
  --light: #f1faee;
  --dark: #2e7d32;     /* Change from #1d3557 to darker green */
  --gray: #81c784;     /* Change from #457b9d to lighter green */
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
}

body {
  background: var(--light);
  color: var(--dark);
  line-height: 1.6;
}

.header {
  background: var(--primary);
  color: white;
  padding: 1rem;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.nav {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
}

.logo-image {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  overflow: hidden;
  background: #fff;
}

.logo-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.nav-links {
  display: flex;
  gap: 2rem;
  position: relative;
}

.nav-links a {
  color: white;
  text-decoration: none;
  transition: color 0.3s;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: var(--primary);
  min-width: 200px; /* Increased width for code */
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  border-radius: 4px;
  top: 100%;
  right: 0;
}

.dropdown-content a {
  color: white;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  white-space: pre-wrap; /* Allow code to wrap */
  font-family: 'Courier New', monospace; /* Better font for code */
}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown-content a:hover {
  background-color: #81c784;  /* Use new gray (light green) color */
}

.hero {
  background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('banner.jpg');
  background-size: cover;
  background-position: center;
  height: 60vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-align: center;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.quick-links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  padding: 4rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.quick-link-card {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  transition: transform 0.3s;
}

.quick-link-card:hover {
  transform: translateY(-5px);
}

.news-section {
  background: var(--primary);
  color: white;
  padding: 4rem 2rem;
}

.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.news-card {
  background: white;
  color: var(--dark);
  padding: 1.5rem;
  border-radius: 8px;
}

.footer {
  background: var(--dark);
  color: white;
  padding: 2rem;
  text-align: center;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1rem;
}

.social-links a {
  color: white;
  text-decoration: none;
}

@media (max-width: 768px) {
  .nav {
    flex-direction: column;
    gap: 1rem;
  }
  
  .nav-links {
    flex-direction: column;
    align-items: center;
  }
  
  .hero h1 {
    font-size: 2rem;
  }
}

/* Add new styles for employee section */
.employee-section {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: var(--light);
  z-index: 1000;
  padding: 2rem;
  overflow-y: auto;
}

.employee-section.active {
  display: block;
}

.back-button {
  position: fixed;
  top: 1rem;
  left: 1rem;
  padding: 0.5rem 1rem;
  background: #1a4b8c;  /* Change from var(--primary) to blue */
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  z-index: 1001;
}

.back-button:hover {
  background: #143d73;  /* Darker blue for hover */
}

.filters {
  display: flex;
  gap: 1rem;
  margin: 2rem auto;
  max-width: 1200px;
  padding: 0 1rem;
}

.filters input,
.filters select {
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

.filters input {
  flex: 2; /* Changed from flex: 1 to give more space to the name filter */
  min-width: 300px; /* Add minimum width */
  padding: 0.75rem; /* Slightly increase padding */
  font-size: 1.1rem; /* Slightly larger font size */
}

.filters select {
  flex: 1;
  min-width: 200px;
}

.employee-count {
  max-width: 1200px;
  margin: 1rem auto;
  padding: 0 1rem;
  font-weight: bold;
  color: #000000;  /* Changed from var(--primary) to black */
  font-size: 1.1em;
}

.employee-list {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.employee-item {
  background: white;
  margin-bottom: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.employee-header {
  padding: 1rem;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.employee-header:hover {
  background: #f5f5f5;
}

.employee-details {
  display: none;
  padding: 1rem;
  border-top: 1px solid #eee;
}

.employee-details.active {
  display: block;
}

.employee-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 3rem auto;
}

.employee-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  display: grid;
  grid-template-columns: 100px 1fr;
  gap: 1.5rem;
}

.employee-card img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
}

.employee-info {
  display: grid;
  gap: 0.5rem;
}

.employee-info h3 {
  margin-bottom: 0.5rem;
  color: #000000;  /* Changed from var(--primary) to black */
}

.info-row {
  display: grid;
  grid-template-columns: 120px 1fr;
  gap: 1rem;
  font-size: 0.9rem;
  border-bottom: 1px solid #eee;
  padding: 0.5rem 0;
}

.info-label {
  font-weight: bold;
  color: var(--gray);
}

.status-active {
  color: #000000;  /* Changed from #2ecc71 to black */
  font-weight: bold;
}

/* Add to existing CSS */
.org-section {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  z-index: 1000;
  padding: 2rem;
  overflow-y: auto;
}

.org-section.active {
  display: block;
}

.org-chart {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px; /* Reduce vertical gap between levels */
  padding: 60px 20px 30px 20px; /* Reduce top/bottom padding */
  max-width: 1400px;
  margin: 0 auto;
}

.level {
  display: flex;
  flex-wrap: wrap;
  gap: 15px; /* Reduce horizontal gap between boxes */
  justify-content: center;
  padding: 0 20px;
}

.level::after {
  content: '';
  position: absolute;
  bottom: -15px; /* Reduce vertical connector height */
  left: 50%;
  transform: translateX(-50%);
  width: 2px;
  height: 15px;
  background: rgba(0,0,0,0.1);
}

.level:last-child::after {
  display: none;
}

.box {
  background: white;
  border-radius: 20px;
  padding: 15px; /* Reduce padding */
  width: 180px; /* Make boxes slightly smaller */
  text-align: center;
  box-shadow: 0 15px 30px rgba(0,0,0,0.1);
  transition: all 0.3s ease;
  border: 1px solid rgba(0,0,0,0.05);
}

.box:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.15);
}

.avatar {
  width: 80px; /* Make avatars smaller */
  height: 80px;
  border-radius: 50%;
  margin: 0 auto 10px;
  overflow: hidden;
  border: 4px solid #4CAF50;  /* Change border color to match new primary */
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.name {
  font-size: 1.1em; /* Slightly smaller font */
  font-weight: 600;
  color: #2c3e50;
  margin-bottom: 5px;
}

.position {
  font-size: 0.9em; /* Slightly smaller font */
  color: #000000;  /* Changed from #4CAF50 to black */
  font-weight: 500;
  margin-bottom: 8px;
}

.contact-info {
  font-size: 0.9em;
  color: #666;
  padding-top: 10px;
  border-top: 1px solid #eee;
  margin-top: 10px;
  line-height: 1.6;
}

/* Add styles for services section */
.servicos-section {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: var(--light);
  z-index: 1000;
  padding: 2rem;
  overflow-y: auto;
}

.servicos-section.active {
  display: block;
}

.servicos-container {
  max-width: 1200px;
  margin: 2rem auto;
  padding: 0 1rem;
}

.servicos-container h2 {
  text-align: center;
  color: #000000;  /* Changed from var(--primary) to black */
  margin-bottom: 2rem;
  font-size: 2rem;
}

.servicos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.servico-card {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  transition: transform 0.3s;
}

.servico-card:hover {
  transform: translateY(-5px);
}

.servico-card h3 {
  color: #000000;  /* Changed from var(--primary) to black */
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.servico-card ul {
  list-style: none;
  padding: 0;
}

.servico-card ul li {
  padding: 0.5rem 0;
  border-bottom: 1px solid #eee;
}

.servico-card ul li:last-child {
  border-bottom: none;
}

/* Updated legislacao styles */
.legislacao-container h2 {
  text-align: center;
  color: #000000;  /* Changed from var(--primary) to black */
  margin-bottom: 2rem;
}

.legislacao-container .documento-lista a {
  color: #000000;  /* Changed from var(--primary) to black */
}

/* Update A6 preview styles */
.a6-preview, .license-back {
    background: white;
    margin: 20px auto;
    padding: 10mm;
    position: relative;
    width: 105mm;  /* Standard A6 width */
    height: 148mm; /* Standard A6 height */
    font-size: 10px;
    box-sizing: border-box;
    border: 2px solid darkgreen;
    outline: 2px solid #ffd700;
    outline-offset: 2px;
    box-shadow: 0 0 0 6px darkred;
    display: flex;
    flex-direction: column;
}

/* Update print styles */
@media print {
    body * {
        visibility: hidden;
    }
    
    .a6-preview, .license-back {
        visibility: visible;
        position: absolute;
        left: 1.5mm;
        top: 1.5mm;
        width: 93mm;  /* A6 width minus margins */
        height: 136mm; /* A6 height minus margins */
        margin: 0;
        padding: 10mm;
        border: 2px solid darkgreen !important;
        outline: 2px solid #ffd700 !important;
        outline-offset: 2px !important;
        box-shadow: 0 0 0 6px darkred !important;
        -webkit-print-color-adjust: exact;
        print-color-adjust: exact;
    }

    .license-back {
        position: absolute;
        top: 280mm; /* Position the back side on next page */
        page-break-before: always;
    }
}

/* Optimize content spacing */
.license-header {
    margin-bottom: 5px;
}

.municipality-info {
    margin-bottom: 5px;
}

.license-details {
    flex-grow: 1;
    font-size: 10px;
    line-height: 1.3;
}

.license-details p {
    margin: 3px 0;
}

.signature-section {
    margin-top: auto;
    margin-bottom: 10px;
}

/* Adjust signature elements */
.signature-section p {
    margin: 2px 0;
    font-size: 10px;
}

/* Add this to existing CSS */
.license-form {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  padding: 25px;
}

.license-form h2 {
  grid-column: 1 / -1;
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid #3498db;
  color: #2c3e50;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 8px;
  color: #34495e;
  font-size: 14px;
}

input, select {
  height: 40px;
  width: 100%;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 8px 12px;
  font-size: 14px;
  transition: border-color 0.3s ease;
}

select:focus, input:focus {
  outline: none;
  border-color: #3498db;
  box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
}

.preview {
  margin-top: 20px;
  padding: 20px;
  border: 1px dashed #ddd;
}

/* Update print styles */
@media print {
    body * {
        visibility: hidden;
    }
    
    .a6-preview, .license-back {
        visibility: visible;
        position: absolute;
        left: 1.5mm;
        top: 1.5mm;
        width: 93mm;  /* A6 width minus margins */
        height: 136mm; /* A6 height minus margins */
        margin: 0;
        padding: 10mm;
        border: 2px solid darkgreen !important;
        outline: 2px solid #ffd700 !important;
        outline-offset: 2px !important;
        box-shadow: 0 0 0 6px darkred !important;
        -webkit-print-color-adjust: exact;
        print-color-adjust: exact;
    }

    .license-back {
        position: absolute;
        top: 280mm; /* Change from 140mm to 280mm to move to third page */
        page-break-before: always;
    }
}

/* Add additional license styling */
.license-header {
    text-align: center;
    margin-bottom: 5px;
    position: relative;
    z-index: 1;
}

.logo-placeholder {
    width: 50px;
    height: 50px;
    margin: 0 auto 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.municipality-info {
    text-align: center;
    margin-bottom: 5px;
    padding: 3px;
    border-radius: 4px;
}

.municipality-info h3 {
    margin: 2px 0;
    font-size: 16px;
    color: #000;
    text-align: center;
    font-weight: bold;
}

.municipality-info h4 {
    margin: 2px 0;
    font-size: 14px;
    color: #000;
    text-align: center;
    font-weight: bold;
}

.municipality-info h5 {
    margin: 2px 0;
    font-size: 12px;
    color: #000;
    text-align: center;
    font-weight: bold;
}

.license-number {
    color: #ff0000;
    text-decoration: underline;
    font-weight: bold;
    margin: 10px 0;
    font-size: 14px;
    text-transform: uppercase;
    text-align: center;
}

.license-details {
    text-align: left;
    margin: 5px 0;
    background: transparent;
    padding: 5px;
    border-radius: 4px;
    flex-grow: 1;
    position: relative;
    z-index: 1;
}

.license-details p {
    margin: 3px 0;
    padding: 2px 0;
}

.license-details strong {
    color: #444;
    min-width: 80px;
    display: inline-block;
}

.watermark {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(3);
    opacity: 0.1;
    z-index: 0;
    pointer-events: none;
}

#qrcode {
    position: absolute;
    bottom: 20px;
    right: 20px;
    z-index: 1;
}

.license-type-back {
    text-align: center;
    margin-top: 20px;
    font-size: 12px;
    font-weight: bold;
}

/* Add these styles for the signature section */
.signature-section {
    text-align: center;
    padding: 5px;
    margin-top: auto;
    margin-bottom: 10px;
    position: relative;
    z-index: 1;
}

.signature-section p {
    margin: 2px 0;
    font-weight: bold;
    font-size: 10px;
}

.signature-line {
    width: 150px;
    height: 1px;
    background: #000;
    margin: 10px auto;
}

/* Add styles for selected vias display */
.selected-vias button:hover {
    background: #ff0000 !important;
    transform: scale(1.05);
}

.selected-vias li {
    transition: all 0.3s ease;
    background: white;
    padding: 5px;
    border-radius: 4px;
    margin-bottom: 5px !important;
}

.selected-vias li:hover {
    background: rgba(0,0,0,0.05);
}
</style>
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
</head>
<body>

<header class="header">
  <nav class="nav">
    <div class="nav-links">
      <a href="https://camiloduvane.github.io/Orgranograma/">Organograma</a>
      <a href="https://camiloduvane.github.io/Receitas/">Receita</a>
      <a href="https://camiloduvane.github.io/Funcionarios/">Funcionarios</a>
      <a href="https://camiloduvane.github.io/Colectivo/">Colectivo</a>
      <a href="https://dmtt.gov.br/contato">Contato</a>
      <div class="dropdown">
        <a href="javascript:void(0)" style="cursor: pointer;">Mais</a>
        <div class="dropdown-content">
          <a href="https://dmtt.gov.br/servicos">Serviços</a>
          <a href="https://dmtt.gov.br/projetos">Projetos</a>
          <a href="https://dmtt.gov.br/documentos">Documentos</a>
          <a href="https://dmtt.gov.br/legislacao">Legislação</a>
          <a href="https://dmtt.gov.br/sistema" style="border-top: 1px solid rgba(255,255,255,0.1);">
            Sistema
          </a>
        </div>
      </div>
    </div>
    <div class="logo">
      <div class="logo-text">DMTT</div>
      <div class="logo-image">
        <img alt="Logo DMTT - Direção Municipal de Transportes e Trânsito" src="DMTT.bmp" width="60" height="60">
      </div>
    </div>
  </nav>
</header>

<section class="hero">
  <div>
    <h1>Direção Municipal de Transportes e Trânsito</h1>
    <p>Trabalhando por uma mobilidade mais segura e eficiente</p>
  </div>
</section>

<section class="quick-links">
  <div class="quick-link-card">
    <h3>Licenciamento</h3>
    <p>Realize o licenciamento do seu veículo de forma rápida e segura.</p>
    <a href="https://dmtt.gov.br/licenciamento">Saiba mais →</a>
  </div>
  
  <div class="quick-link-card">
    <h3>Multas</h3>
    <p>Consulte e pague suas multas de trânsito.</p>
    <a href="https://dmtt.gov.br/multas">Consultar →</a>
  </div>
  
  <div class="quick-link-card">
    <h3>Educação no Trânsito</h3>
    <p>Conheça nossas campanhas educativas.</p>
    <a href="https://dmtt.gov.br/educacao">Ver campanhas →</a>
  </div>
</section>

<section class="news-section">
  <div class="news-grid">
    <div class="news-card">
      <h3>Novos semáforos inteligentes</h3>
      <p>DMTT inicia o estudo de instalação de semáforos com tecnologia adaptativa...</p>
      <small>06/12/2024</small>
    </div>
    
    <div class="news-card">
      <h3>Maputo Pedalando</h3>
      <p>Ações de conscientização marcam o início do Maputo Pedalando...</p>
      <small>16/11/2024</small>
    </div>
    
    <div class="news-card">
      <h3>Alteração de itinerário</h3>
      <p>Novas rotas de transportes Semi-Colectivo entram em vigor a partir do próximo mês...</p>
      <small>06/12/2024</small>
    </div>
  </div>
</section>

<div id="employeeSection" class="employee-section">
  <button class="back-button" onclick="hideEmployees()">← Voltar</button>
  
  <div class="filters">
    <input type="text" id="nameFilter" placeholder="Filtrar por nome...">
    <select id="departmentFilter">
      <option value="">Todos os Departamentos</option>
      <option value="Vereação">Vereação</option>
      <option value="Direcção">Direcção</option>
      <option value="Departamento de Administração e Recursos Humanos">DARHF</option>
      <option value="Departamento de Licenciamento">DL</option>
      <option value="Departamento de Operações e Trânsito">DOT</option>
      <option value="Departamento de Transportes Público">DTP</option>
      <option value="Secretaria">Secretaria</option>
      <option value="BRT">BRT</option>
    </select>
    <select id="statusFilter">
      <option value="">Todos os Status</option>
      <option value="Ativo">Ativo</option>
      <option value="Inativo">Inativo</option>
      <option value="Ferias">De Férias</option>
    </select>
  </div>

  <div class="employee-count">
    Total de Funcionários: <span id="employeeCount">0</span>
  </div>

  <div class="employee-list">
    <!-- Employee items will be generated by JavaScript -->
  </div>
</div>

<div id="orgSection" class="org-section">
  <button class="back-button" onclick="hideOrg()">← Voltar</button>
  
  <div class="org-chart">
    <!-- Vereador Level -->
    <div class="level">
      <div class="box">
        <div class="avatar">
          <img src="vereador.jpg" alt="Vereador">
        </div>
        <div class="name">Fernando Uache</div>
        <div class="position">Vereador</div>
        <div class="contact-info" style="display: none;">
          <p>Email: vereador@example.com</p>
          <p>Telefone: (+258) 1234-5678</p>
        </div>
      </div>
    </div>
    <!-- Director Level -->
    <div class="level">
      <div class="box">
        <div class="avatar">
          <img src="diretor1.jpg" alt="Diretor 1">
        </div>
        <div class="name">Nelson Gustavo Massango</div>
        <div class="position">Diretor Municipal de Transportes e Trânsito</div>
        <div class="contact-info" style="display: none;">
          <p>Email: diretor1@example.com</p>
          <p>Telefone: (+258) 2345-6789</p>
        </div>
      </div>
      <div class="box">
        <div class="avatar">
          <img src="diretor2.jpg" alt="Diretor 2">
        </div>
        <div class="name">Por Nomear</div>
        <div class="position">Diretor Adjunto</div>
        <div class="contact-info" style="display: none;">
          <p>Email: diretor2@example.com</p>
          <p>Telefone: (+258) 3456-7890</p>
        </div>
      </div>
    </div>
    <!-- Department Level -->
    <div class="level">
      <div class="box">
        <div class="avatar">
          <img src="departamento1.jpg" alt="Departamento 1">
        </div>
        <div class="name">Carlos Vilanculos</div>
        <div class="position">Departamento de Administração de Recursos Humanos e Finanças</div>
        <div class="contact-info" style="display: none;">
          <p>Email: dep.transito@example.com</p>
          <p>Telefone: (11) 4567-8901</p>
        </div>
      </div>
      <div class="box">
        <div class="avatar">
          <img src="departamento2.jpg" alt="Departamento 2">
        </div>
        <div class="name">Amilton Tembe</div>
        <div class="position">Departamento de Licenciamento</div>
        <div class="contact-info" style="display: none;">
          <p>Email: dep.projetos@example.com</p>
          <p>Telefone: (11) 5678-9012</p>
        </div>
      </div>
      <div class="box">
        <div class="avatar">
          <img src="departamento3.jpg" alt="Departamento 3">
        </div>
        <div class="name">Vasco Nhaquila</div>
        <div class="position">Departamento de Transportes Públicos</div>
        <div class="contact-info" style="display: none;">
          <p>Email: dep.operacoes@example.com</p>
          <p>Telefone: (11) 6789-0123</p>
        </div>
      </div>
      <div class="box">
        <div class="avatar">
          <img src="departamento4.jpg" alt="Departamento 4">
        </div>
        <div class="name">Baltazar Hilario</div>
        <div class="position">Departamento de Operações e Trânsito</div>
        <div class="contact-info" style="display: none;">
          <p>Email: dep.fiscalizacao@example.com</p>
          <p>Telefone: (11) 7890-1234</p>
        </div>
      </div>
      <div class="box">
        <div class="avatar">
          <img src="departamento5.jpg" alt="Departamento 5">
        </div>
        <div class="name">José Chiau</div>
        <div class="position">Secretária Geral</div>
        <div class="contact-info" style="display: none;">
          <p>Email: dep.admin@example.com</p>
          <p>Telefone: (11) 8901-2345</p>
        </div>
      </div>
    </div>
  </div>
</div>

<div id="servicosSection" class="servicos-section">
  <button class="back-button" onclick="hideServicos()">← Voltar</button>
  
  <div class="servicos-container">
    <h2>Nossos Serviços</h2>
    
    <div class="servicos-grid">
      <div class="servico-card">
        <h3>Licenciamento de Veículos</h3>
        <ul>
          <li>Primeira matrícula</li>
          <li>Renovação de licença</li>
          <li>Transferência de propriedade</li>
          <li>Alteração de características</li>
          <li>Segunda via de documentos</li>
        </ul>
      </div>

      <div class="servico-card">
        <h3>Transportes Públicos</h3>
        <ul>
          <li>Licenciamento de operadores</li>
          <li>Autorização de rotas</li>
          <li>Vistoria de veículos</li>
          <li>Gestão de terminais</li>
          <li>Fiscalização de serviços</li>
        </ul>
      </div>

      <div class="servico-card">
        <h3>Gestão de Trânsito</h3>
        <ul>
          <li>Sinalização viária</li>
          <li>Fiscalização de trânsito</li>
          <li>Educação no trânsito</li>
          <li>Estudos de tráfego</li>
          <li>Gestão semafórica</li>
        </ul>
      </div>

      <div class="servico-card">
        <h3>Atendimento ao Público</h3>
        <ul>
          <li>Reclamações</li>
          <li>Sugestões</li>
          <li>Consulta de processos</li>
          <li>Informações gerais</li>
          <li>Agendamento de serviços</li>
        </ul>
      </div>
    </div>
  </div>
</div>

<footer class="footer">
  <p>© 2024 Direção Municipal de Transportes e Trânsito - Todos os direitos reservados</p>
  <div class="social-links">
    <a href="https://facebook.com/dmtt">Facebook</a>
    <a href="https://instagram.com/dmtt">Instagram</a>
    <a href="https://twitter.com/dmtt">Twitter</a>
  </div>
</footer>

<script>
// User roles and credentials system
const users = [
  {
    username: 'CWD',
    password: '1234',
    role: 'Administrador',
    name: 'Camilo Duvane'
  },
  // Gestores
  {
    username: 'GST1',
    password: '5678',
    role: 'Gestor',
    name: 'Carlos Vilanculos'
  },
  {
    username: 'GST2', 
    password: '9012',
    role: 'Gestor',
    name: 'Amilton Tembe'
  },
  // Supervisores
  {
    username: 'SPV1',
    password: '3456',
    role: 'Supervisor',
    name: 'Vasco Nhaquila'
  },
  {
    username: 'SPV2',
    password: '7890',
    role: 'Supervisor',
    name: 'Baltazar Hilario'
  },
  // Técnicos
  {
    username: 'TEC1',
    password: '2345',
    role: 'Técnico',
    name: 'Jose Chiau'
  },
  {
    username: 'TEC2',
    password: '6789',
    role: 'Técnico',
    name: 'Leonilde Chitofo'
  }
];

// Function to update form fields based on license type
function updateFormFields() {
    const licenseType = document.getElementById('licenseType').value;
    const capacityGroup = document.querySelector('label[for="capacity"]').parentElement;
    const routeGroup = document.querySelector('label[for="route"]').parentElement;
    const viaGroup = document.querySelector('label[for="via"]').parentElement;
    const grossWeightGroup = document.getElementById('grossWeightGroup');
    
    const isTaxiType = ['taxi', 'taxiMercadoria', 'taxiApp', 'motoTaxi'].includes(licenseType);
    const isRouteType = ['semicolectivo', 'passageiros'].includes(licenseType);
    
    if (licenseType === 'camiao') {
        capacityGroup.style.display = 'none';
        routeGroup.style.display = 'none';
        viaGroup.style.display = 'block';
        grossWeightGroup.style.display = 'block';
        viaGroup.querySelector('label').textContent = 'Vias Autorizadas:';
        document.getElementById('via').multiple = true;
    } else if (isTaxiType) {
        capacityGroup.style.display = 'block';
        routeGroup.style.display = 'none';
        viaGroup.style.display = 'none';
        grossWeightGroup.style.display = 'none';
        document.querySelector('label[for="capacity"]').textContent = 'Praça:';
        updateTaxiStands();
    } else {
        capacityGroup.style.display = 'block';
        routeGroup.style.display = isRouteType ? 'block' : 'none';
        viaGroup.style.display = isRouteType ? 'block' : 'none';
        grossWeightGroup.style.display = 'none';
        document.querySelector('label[for="capacity"]').textContent = 'Lotação:';
        resetCapacityOptions();
    }
}

// Function to show login form
function showSistemaLogin() {
  const content = `
    <div class="sistema-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
      display: flex;
      justify-content: center;
      align-items: center;
    ">
      <button class="back-button" onclick="hideSistemaLogin()">← Voltar</button>
      
      <div class="login-card" style="
        background: white;
        padding: 2rem;
        border-radius: 8px;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        width: 100%;
        max-width: 400px;
      ">
        <h2 style="text-align: center; margin-bottom: 2rem; color: #000000;">Acesso ao Sistema</h2>
        
        <form id="loginForm" style="display: grid; gap: 1rem;">
          <div style="display: grid; gap: 0.5rem;">
            <label for="username" style="font-weight: bold;">Usuário:</label>
            <input type="text" id="username" name="username" required style="
              padding: 0.5rem;
              border: 1px solid #ddd;
              border-radius: 4px;
              font-size: 1rem;
            ">
          </div>
          
          <div style="display: grid; gap: 0.5rem;">
            <label for="password" style="font-weight: bold;">Senha:</label>
            <input type="password" id="password" name="password" required style="
              padding: 0.5rem;
              border: 1px solid #ddd;
              border-radius: 4px;
              font-size: 1rem;
            ">
          </div>
          
          <button type="submit" style="
            background: #1a4b8c;
            color: white;
            padding: 0.75rem;
            border: none;
            border-radius: 4px;
            font-size: 1rem;
            cursor: pointer;
            margin-top: 1rem;
          ">Entrar</button>
          
          <div id="loginMessage" style="
            color: red;
            text-align: center;
            margin-top: 1rem;
            display: none;
          "></div>
          
          <a href="#" style="
            text-align: center;
            color: #1a4b8c;
            text-decoration: none;
            font-size: 0.9rem;
            margin-top: 0.5rem;
          ">Esqueceu a senha?</a>
        </form>
      </div>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
  document.body.style.overflow = 'hidden';
  
  // Updated login handler with role-based access
  document.getElementById('loginForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    
    const user = users.find(u => u.username === username && u.password === password);
    
    if (user) {
      // Store user info in session
      sessionStorage.setItem('currentUser', JSON.stringify({
        username: user.username,
        role: user.role,
        name: user.name
      }));
      
      // Instead of redirecting to different URLs, show the licensing system
      hideSistemaLogin();
      showLicensingSystem();
    } else {
      // Show error message
      const msgElement = document.getElementById('loginMessage');
      msgElement.textContent = 'Usuário ou senha inválidos. Por favor tente novamente.';
      msgElement.style.display = 'block';
    }
  });
}

// Function to hide login form
function hideSistemaLogin() {
  const section = document.querySelector('.sistema-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

function showLicensingSystem() {
  const content = `<div class="licensing-section" style="
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1000;
    overflow-y: auto;
    background: var(--light);
    padding: 2rem;
  ">
    <button class="back-button" onclick="hideLicensingSystem()">← Voltar</button>
    
    <div class="container">
      <h1>Sistema de Licenciamento</h1>
      <div class="license-form">
        <h2>Nova Licença</h2>
        
        <div class="form-group">
          <label for="licenseType">Tipo de Licença:</label>
          <select id="licenseType" onchange="updateFormFields()">
            <option value="camiao">Licença de Camião</option>
            <option value="semicolectivo">Semi-Colectivo</option>
            <option value="taxi">Táxi</option>
            <option value="taxiApp">Táxi de Aplicativo</option>
            <option value="taxiMercadoria">Táxi de Mercadoria</option>
            <option value="motoTaxi">Moto-Táxi</option>
            <option value="escolar">Escolar</option>
            <option value="funebre">Transporte Fúnebre</option>
            <option value="passageiros">Transporte de Passageiros</option>
            <option value="ciclomotores">Licença de Ciclomotores</option>
            <option value="livreteCiclomotores">Livrete de Ciclomotores</option>
            <option value="oficinas">Oficinas</option>
          </select>
        </div>
        
        <div class="form-group" id="grossWeightGroup">
          <label for="grossWeight">Peso Bruto:</label>
          <input type="text" id="grossWeight" placeholder="Em toneladas">
        </div>
        
        <div class="form-group">
          <label for="licenseNumber">Número da Licença:</label>
          <input type="text" id="licenseNumber" readonly>
        </div>
        
        <div class="form-group">
          <label for="ownerName">Nome do Proprietário/Empresa:</label>
          <input type="text" id="ownerName">
        </div>
        
        <div class="form-group">
          <label for="address">Endereço:</label>
          <input type="text" id="address">
        </div>
        
        <div class="form-group">
          <label for="plate">Matrícula:</label>
          <input type="text" id="plate">
        </div>
        
        <div class="form-group">
          <label for="brand">Marca:</label>
          <input type="text" id="brand">
        </div>

        <div class="form-group">
          <label for="route">Rota:</label>
          <select id="route">
            <option value="">Selecione a rota</option>
            <option value="baixa_zimpecto">Baixa-Zimpecto</option>
            <option value="baixa_combatentes">Baixa P.Combatentes</option>
            <option value="baixa_laulane">Baixa-Laulane</option>
            <option value="ba_voador_malhazine">BA.voador-Malhazine</option>
          </select>
        </div>

        <div class="form-group">
          <label for="via">Via:</label>
          <select id="via" multiple>
            <option value="julius_nyerere">Av. Julius Nyerere</option>
            <option value="vladimir_lenine">Av. Vladimir Lenine</option>
            <option value="eduardo_mondlane">Av. Eduardo Mondlane</option>
            <option value="mao_tse_tung">Av. Mao Tse Tung</option>
            <option value="guerra_popular">Av. Guerra Popular</option>
            <option value="karl_marx">Av. Karl Marx</option>
            <option value="acordo_lusaka">Av. Acordo de Lusaka</option>
            <option value="fplm">Av. FPLM</option>
            <option value="angola">Av. Angola</option>
            <option value="zimbabwe">Av. Zimbabwe</option>
          </select>
        </div>

        <div class="form-group">
          <label for="duration">Duração:</label>
          <select id="duration">
            <option value="1">1 Mês</option>
            <option value="2">2 Meses</option>
            <option value="3">3 Meses</option>
            <option value="4">4 Meses</option>
            <option value="5">5 Meses</option>
            <option value="6">6 Meses</option>
            <option value="7">7 Meses</option>
            <option value="8">8 Meses</option>
            <option value="9">9 Meses</option>
            <option value="10">10 Meses</option>
            <option value="11">11 Meses</option>
            <option value="12">12 Meses</option>
          </select>
        </div>

        <div class="form-group">
          <label for="schedule">Horário:</label>
          <select id="schedule">
            <option value="24">24 Horas</option>
          </select>
        </div>

        <div class="form-group">
          <label for="paymentType">Forma de Depósito:</label>
          <select id="paymentType">
            <option value="numerario">Numerário</option>
            <option value="deposito">Depósito</option>
            <option value="transferencia">Transferência</option>
          </select>
        </div>
        
        <div class="form-group">
          <label for="bank">Banco:</label>
          <select id="bank" onchange="updateAccounts()">
            <option value="">Selecione o banco</option>
            <option value="BIM">BIM</option>
            <option value="BCI">BCI</option>
            <option value="Standard">Standard Bank</option>
            <option value="Absa">Absa</option>
          </select>
        </div>
        
        <div class="form-group">
          <label for="account">Conta:</label>
          <select id="account">
            <option value="">Selecione primeiro o banco</option>
          </select>
        </div>
        
        <div class="form-group">
          <label for="amount">Valor:</label>
          <input type="text" id="amount">
        </div>
        
        <div class="form-group">
          <label for="reference">Referência:</label>
          <input type="text" id="reference">
        </div>
        
        <div class="form-group">
          <label for="contact">Contacto:</label>
          <input type="text" id="contact" placeholder="(+258) " maxlength="16">
        </div>
        
        <div class="form-group">
          <label for="nuit">NUIT:</label>
          <input type="text" id="nuit" minlength="9" maxlength="12">
        </div>
        <div class="form-group">
          <button onclick="generateLicense()" style="
              background: #3498db;
              color: white;
              border: none;
              padding: 12px 24px;
              font-size: 14px;
              font-weight: 500;
              border-radius: 4px;
              cursor: pointer;
              transition: all 0.3s ease;
          ">Gerar Licença</button>
        </div>
      </div>
      
      <div class="preview">
        <h3>Pré-visualização</h3>
        <div id="licensePreview"></div>
      </div>
    </div>
  </div>`;

  document.body.insertAdjacentHTML('beforeend', content);
  document.body.style.overflow = 'hidden';
}

function hideLicensingSystem() {
  const section = document.querySelector('.licensing-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

// Helper functions for the licensing system
function validateNUIT(input) {
  let nuit = input.replace(/\D/g, '');
  if (nuit.length > 12) {
    nuit = nuit.slice(0, 12);
  }
  return nuit;
}

function generateLicenseNumber() {
  const licenseType = document.getElementById('licenseType').value;
  const year = new Date().getFullYear();
  let count = parseInt(localStorage.getItem('licenseCount') || 0) + 1;
  localStorage.setItem('licenseCount', count);
  const paddedCount = count.toString().padStart(3, '0');
  const letterMap = {
    'camiao': 'LC',
    'semicolectivo': 'SC',
    'taxi': 'T',
    'taxiApp': 'TA',
    'taxiMercadoria': 'TM',
    'motoTaxi': 'MT',
    'escolar': 'E',
    'funebre': 'F',
    'passageiros': 'P',
    'ciclomotores': 'C',
    'livreteCiclomotores': 'L',
    'oficinas': 'O'
  };
  return `${paddedCount}/${year}/${letterMap[licenseType]}`;
}

function generateLicense() {
    const nuit = document.getElementById('nuit').value;
    
    if (nuit.length < 9 || nuit.length > 12) {
        alert('O NUIT deve ter entre 9 e 12 dígitos.');
        return;
    }

    if (!confirm('Tem certeza que deseja gerar a licença? Por favor, verifique se todos os dados estão corretos.\n\nAdvertência: Após gerar a licença, os dados serão registrados no sistema.')) {
        return;
    }

    // Generate license number first
    document.getElementById('licenseNumber').value = generateLicenseNumber();

    // Get all form values
    const licenseType = document.getElementById('licenseType').value;
    const licenseNumber = document.getElementById('licenseNumber').value;
    const ownerName = document.getElementById('ownerName').value;
    const address = document.getElementById('address').value;
    const plate = document.getElementById('plate').value;
    const brand = document.getElementById('brand').value;
    const grossWeight = document.getElementById('grossWeight').value;
    const duration = document.getElementById('duration').value;
    const schedule = document.getElementById('schedule').value;
    const route = document.getElementById('route').value;
    const selectedVias = Array.from(document.getElementById('via').selectedOptions)
        .map(option => option.text)
        .join(' - ');

    const preview = document.getElementById('licensePreview');
    
    const licenseDetailsHtml = `
        <p><strong>Nome:</strong> ${ownerName}</p>
        <p><strong>Endereço:</strong> ${address}</p>
        <p><strong>Matrícula:</strong> ${plate}</p>
        <p><strong>Marca:</strong> ${brand}</p>
        ${licenseType === 'camiao' ? `
            <p><strong>Peso Bruto:</strong> ${grossWeight} toneladas</p>
        ` : `
            ${route ? `<p><strong>Rota:</strong> ${route}</p>` : ''}
            ${selectedVias ? `<p><strong>Vias:</strong> ${selectedVias}</p>` : ''}
        `}
        <p><strong>Duração:</strong> ${duration} ${duration === '1' ? 'Mês' : 'Meses'}</p>
        <p><strong>Horário:</strong> ${schedule}</p>
        <p><strong>Data de Emissão:</strong> ${new Date().toLocaleDateString()}</p>
        <p><strong>Validade:</strong> ${new Date(new Date().setMonth(new Date().getMonth() + parseInt(duration))).toLocaleDateString()}</p>
    `;

    const licenseBackHtml = (() => {
        if (licenseType === 'camiao') {
            return `
                <div class="license-back">
                    <div class="watermark"><img src="logo.png" alt="Logotipo do Município" width="15" height="15"></div>
                    <div class="license-type-back">
                        <h3>Licença de Camião</h3>
                        <div class="authorized-routes">
                            <h4>Vias Autorizadas:</h4>
                            <p style="margin: 10px 0; line-height: 1.4;">${selectedVias}</p>
                        </div>
                    </div>
                    <div style="position: absolute; bottom: 40px; left: 10px; right: 120px; text-align: justify; font-size: 8px; font-weight: bold; padding: 5px;">
                        A licença é intransferível e será considerada válida apenas quando apresentada em conjunto com o livrete oficial correspondente ao veículo ao qual está vinculada, garantindo a conformidade com as normas vigentes e evitando qualquer uso indevido.
                    </div>
                    <div id="qrcode"></div>
                </div>
            `;
        } else {
            return `
                <div class="license-back">
                    <div class="watermark"><img src="logo.png" alt="Logotipo do Município" width="15" height="15"></div>
                    <div class="license-type-back">
                        <h3>Licença de Transporte</h3>
                    </div>
                    <div style="position: absolute; bottom: 40px; left: 10px; right: 120px; text-align: justify; font-size: 8px; font-weight: bold; padding: 5px;">
                        A licença é intransferível e será considerada válida apenas quando apresentada em conjunto com o livrete oficial correspondente ao veículo ao qual está vinculada, garantindo a conformidade com as normas vigentes e evitando qualquer uso indevido.
                    </div>
                    <div id="qrcode"></div>
                </div>
            `;
        }
    })();

    const licenseTemplate = `
        <div class="a6-preview">
            <div class="watermark"><img src="logo.png" alt="Logotipo do Município" width="15" height="15"></div>
            <div class="license-header">
                <div class="logo-placeholder"><img src="logo.png" alt="Logotipo do Município" width="50" height="50"></div>
                <div class="municipality-info">
                    <h3>MUNICÍPIO DE MAPUTO</h3>
                    <h4>CONSELHO MUNICIPAL</h4>
                    <h5>PELOURO DE MOBILIDADE, TRANSPORTES E TRÂNSITO</h5>
                </div>
                <div class="license-number">${licenseType} Nº ${licenseNumber}</div>
            </div>
            <div class="license-details">
                ${licenseDetailsHtml}
            </div>
            <div class="signature-section">
                <p>Data: ${new Date().toLocaleDateString()}</p>
                <div class="signature-line"></div>
                <p>O Responsável</p>
            </div>
        </div>
        ${licenseBackHtml}
        <div style="text-align: center; margin-top: 20px;">
            <button onclick="printLicense()" style="
                background: #3498db;
                color: white;
                border: none;
                padding: 12px 24px;
                font-size: 14px;
                font-weight: 500;
                border-radius: 4px;
                cursor: pointer;
                transition: all 0.3s ease;
            ">Imprimir Licença</button>
        </div>`;

    preview.innerHTML = licenseTemplate;
    
    // Generate QR code
    const qrcodeDiv = document.getElementById("qrcode");
    qrcodeDiv.innerHTML = '';
    
    new QRCode(qrcodeDiv, {
        text: `License: ${licenseNumber}\nOwner: ${ownerName}\nType: ${licenseType}`,
        width: 100,
        height: 100
    });
}

// Update print function
function printLicense() {
    window.print();
}

// Adiciona comportamento de scroll suave aos links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    const href = this.getAttribute('href');
    if (href === '#') return;
    
    e.preventDefault();
    const target = document.querySelector(href);
    if (target) {
      target.scrollIntoView({
        behavior: 'smooth'
      });
    }
  });
});

// Adiciona classe active ao link atual na navegação
const currentLocation = location.href;
const menuItems = document.querySelectorAll('.nav-links a');
menuItems.forEach(link => {
  if(link.href === currentLocation) {
    link.classList.add('active');
  }
});

// Function to show employee section
function showEmployees() {
  document.getElementById('employeeSection').classList.add('active');
  document.body.style.overflow = 'hidden';
}

// Function to hide employee section
function hideEmployees() {
  document.getElementById('employeeSection').classList.remove('active');
  document.body.style.overflow = 'auto';
}

// Update the Funcionarios link to trigger the employee section
document.querySelector('a[href="https://camiloduvane.github.io/Funcionarios/"]').addEventListener('click', function(e) {
  e.preventDefault();
  showEmployees();
});

// Function to show org section
function showOrg() {
  document.getElementById('orgSection').classList.add('active');
  document.body.style.overflow = 'hidden';
}

// Function to hide org section
function hideOrg() {
  document.getElementById('orgSection').classList.remove('active');
  document.body.style.overflow = 'auto';
}

// Add click handler for organogram link
document.querySelector('a[href="https://camiloduvane.github.io/Orgranograma/"]').addEventListener('click', function(e) {
  e.preventDefault();
  showOrg();
});

// Function to show services section
function showServicos() {
  document.getElementById('servicosSection').classList.add('active');
  document.body.style.overflow = 'hidden';
}

// Function to hide services section
function hideServicos() {
  document.getElementById('servicosSection').classList.remove('active');
  document.body.style.overflow = 'auto';
}

// Add this event listener to show services section
document.querySelector('.dropdown-content a[href="https://dmtt.gov.br/servicos"]').addEventListener('click', function(e) {
  e.preventDefault();
  showServicos();
});

// Add the showDetails function from original code
function showDetails(element) {
  const contactInfo = element.querySelector('.contact-info');
  contactInfo.style.display = contactInfo.style.display === 'block' ? 'none' : 'block';
}

// Add this to your existing JavaScript
const employees = [
  {
    id: 1,
    name: 'Fernando Uache',
    photo: 'fernandouache.jpg',
    position: 'Vereador',
    category: 'Técnico Superior N1',
    education: '...Por preencher...',
    location: 'Pacio',
    department: 'Vereação',
    status: 'Ativo'
  },
  {
    id: 2,
    name: 'Nelson Gustavo Massango',
    photo: 'nelsongustavomassango.jpg',
    position: 'Director',
    category: 'Técnico Suprior N1',
    education: 'Estatística',
    location: 'Direcção',
    department: 'Direcção',
    status: 'Ativo'
  },
  {
    id: 3,
    name: 'Carlos Vilanculos',
    photo: 'camiloduvane.jpg',
    position: 'Chefe de Departamento',
    category: 'Técnico Profissional',
    education: 'Contabilidade e Finanças',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 4,
    name: 'Amilton Tembe',
    photo: 'camiloduvane.jpg',
    position: 'Chefe de Departamento',
    category: 'Ensino Geral',
    education: '12° Classe',
    location: 'DL',
    department: 'Departamento de Licenciamento',
    status: 'Ativo'
  },
{
    id: 5,
    name: 'Vasco Nhaquila',
    photo: 'camiloduvane.jpg',
    position: 'Chefe de Departamento',
    category: 'Técnico Supervisor N1',
    education: 'Administração Pública',
    location: 'DTP',
    department: 'Departamento de Transportes Público',
    status: 'Ativo'
  },
{
    id: 6,
    name: 'Baltazar Hilário Nhacumbe',
    photo: 'camiloduvane.jpg',
    position: 'Chefe de Departamento',
    category: 'Técnico Profissional',
    education: 'Eletricidade',
    location: 'DOT',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  },
{
    id: 7,
    name: 'Safo Charles Mahumana',
    photo: 'camiloduvane.jpg',
    position: 'Chefe de Recepção',
    category: 'Técnico Supervisor N1',
    education: 'Gestão e Políticas Públicas',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 8,
    name: 'José Chiau',
    photo: 'camiloduvane.jpg',
    position: 'Chefe da Secretaria',
    category: 'Técnico Supervisor N1',
    education: 'Administração Pública',
    location: 'Secretaria',
    department: 'Secretaria',
    status: 'Ativo'
  },
  {
    id: 9,
    name: 'Ana Paula Francisco Muchanga',
    photo: 'camiloduvane.jpg',
    position: 'Secretaria Executiva',
    category: 'Técnica Profissional',
    education: 'Contabilidade e Gestão',
    location: 'Pacio',
    department: 'Vereação',
    status: 'Ativo'
  },
  {
    id: 10,
    name: 'Silvia Laurinda Tembe Machié',
    photo: 'camiloduvane.jpg',
    position: 'Secretaria Executiva',
    category: 'Técnica Profissional',
    education: 'Administração Pública',
    location: 'Secretaria',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 11,
    name: 'Camilo Wiliamo Duvane',
    photo: 'camiloduvane.jpg',
    position: 'Técnico',
    category: 'Técnico Supervisor N1',
    education: 'Contabilidade e Auditoria',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 12,
    name: 'Loide Atalia da Sílvia Massangaie Castelo David',
    photo: 'camiloduvane.jpg',
    position: 'Directora Adjunta',
    category: 'Técnica Supervisor N1',
    education: 'Engenharia Civil',
    location: 'Direcção',
    department: 'Direcção',
    status: 'Inativo'
  },

{
    id: 13,
    name: 'Obadias José Djedje',
    photo: 'camiloduvane.jpg',
    position: 'Coordenador',
    category: 'Técnico Supervisor N1',
    education: 'Engenheiro de Transportes',
    location: 'BRT',
    department: 'BRT',
    status: 'Inativo'
  },
{
    id: 14,
    name: 'Pedro Luís Jamal',
    photo: 'camiloduvane.jpg',
    position: 'Técnico',
    category: 'Supervisor N1',
    education: 'Engenheiro Civil',
    location: 'BRT',
    department: 'BRT',
    status: 'Ativo'
  },
{
    id: 15,
    name: 'Sara Ernesto Macaringue',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Supervisor N1',
    education: 'Engenheira Civil',
    location: 'BRT',
    department: 'BRT',
    status: 'Ativo'
  },
{
    id: 16,
    name: 'Leonilde da Victoria José Chitofo',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Técnica Supervisor N1',
    education: 'Contabilidade e Auditoria',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
{
    id: 17,
    name: 'Felicidade Francisco Macamo',
    photo: 'camiloduvane.jpg',
    position: 'Chefe da Secretaria',
    category: 'Técnica Supervisor N1',
    education: 'Contabilidade e Auditoria',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
{
    id: 18,
    name: 'Egimenia Julião Churane',
    photo: 'camiloduvane.jpg',
    position: 'Técnica Superior N1',
    category: 'Técnica Supervisor N1',
    education: 'Gestão e Políticas Públicas',
    location: 'DARHF', 
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Inativo'
  },
{
    id: 19,
    name: 'Henriqueta Muchanga Buque',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Técnica Profissional',
    education: 'Contabilidade e Gestão',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 20,
    name: 'Mateus Eduardo Mahotas',
    photo: 'camiloduvane.jpg',
    position: 'Auxiliar',
    category: 'Assistente Técnico',
    education: '10° Classe',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 21,
    name: 'Omar Momad Omar',
    photo: 'camiloduvane.jpg',
    position: 'Auxiliar',
    category: 'Auxiliar',
    education: '7° Classe',
    location: 'DARHF',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 22,
    name: 'Gilda Francisco Zimba',
    photo: 'camiloduvane.jpg',
    position: 'Fiscal',
    category: 'Técnica Supervisores N1',
    education: 'Gestão de Recursos Humanos',
    location: 'Fiscalização',
    department: 'Departamento de Operação e Trânsito',
    status: 'Ativo'
  },
  {
    id: 23,
    name: 'Amélia Salmina Francisco Nubo',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Técnica Superior N1',
    education: 'Gestão de Recursos Humanos',
    location: 'Secretária',
    department: 'Departamento de Administração e Recursos Humanos',
    status: 'Ativo'
  },
  {
    id: 24,
    name: 'Helena Da Clara Tito',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Técnica Superior N1',
    education: 'Arquitetura',
    location: 'DOT',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }, 
  {
    id: 25,
    name: 'Adérito Quefasse Canhavato',
    photo: 'camiloduvane.jpg',
    position: 'Técnico',
    category: 'Técnico',
    education: '12° Classe',
    location: 'Secretaria',
    department: 'Secretaria',
    status: 'Ativo'
  }, 
  {
    id: 26,
    name: 'José Joaquim Madlante',
    photo: 'camiloduvane.jpg',
    position: 'Técnico',
    category: 'Técnica Superior N1',
    education: 'Engenheiro',
    location: 'DOT',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }, 
  {
    id: 27,
    name: 'Catarina Armando Chicuava',
    photo: 'camiloduvane.jpg',
    position: 'Técnica',
    category: 'Técnica Superior N1',
    education: 'Economia',
    location: 'DOT',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }, 
  {
      id: 28,
    name: 'Ivete Salvador Muxanga',
    photo: 'camiloduvane.jpg',
    position: 'Fiscal',
    category: 'Técnica Superior N1',
    education: 'Gestão de Recursos Humanos',
    location: 'Fiscalização',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }, 
  {
    id: 29,
    name: 'Hernane Alfredo Cumbana',
    photo: 'camiloduvane.jpg',
    position: 'Fiscal',
    category: 'Técnico Profissional',
    education: 'Gestão de Transportes',
    location: 'Fiscalização',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }, 
  {
     id: 30,
    name: 'Aníbal António Nhacuongo',
    photo: 'camiloduvane.jpg',
    position: 'Auxiliar',
    category: 'Assistente Técnico',
    education: '10° Classe',
    location: 'DOT',
    department: 'Departamento de Operações e Trânsito',
    status: 'Ativo'
  }
];

function renderEmployees(filteredEmployees = employees) {
  const employeeList = document.querySelector('.employee-list');
  // Update employee count
  document.getElementById('employeeCount').textContent = filteredEmployees.length;
  
  employeeList.innerHTML = filteredEmployees.map(emp => `
    <div class="employee-item">
      <div class="employee-header" onclick="toggleDetails(${emp.id})">
        <span>${emp.name}</span>
        <span>${emp.department}</span>
      </div>
      <div class="employee-details" id="details-${emp.id}">
        <div class="employee-card">
          <img alt="Foto do funcionário ${emp.name}" src="${emp.photo}" width="100" height="100">
          <div class="employee-info">
            <h3>${emp.name}</h3>
            <div class="info-row">
              <span class="info-label">Cargo de Chefia:</span>
              <span>${emp.position}</span>
            </div>
            <div class="info-row">
              <span class="info-label">Categoria:</span>
              <span>${emp.category}</span>
            </div>
            <div class="info-row">
              <span class="info-label">Formação:</span>
              <span>${emp.education}</span>
            </div>
            <div class="info-row">
              <span class="info-label">Locação:</span>
              <span>${emp.location}</span>
            </div>
            <div class="info-row">
              <span class="info-label">Departamento:</span>
              <span>${emp.department}</span>
            </div>
            <div class="info-row">
              <span class="info-label">Status:</span>
              <span class="status-active">${emp.status}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  `).join('');
}

function toggleDetails(id) {
  const details = document.getElementById(`details-${id}`);
  details.classList.toggle('active');
}

function filterEmployees() {
  const nameFilter = document.getElementById('nameFilter').value.toLowerCase();
  const departmentFilter = document.getElementById('departmentFilter').value;
  const statusFilter = document.getElementById('statusFilter').value;

  const filtered = employees.filter(emp => {
    const matchName = emp.name.toLowerCase().includes(nameFilter);
    const matchDepartment = !departmentFilter || emp.department === departmentFilter;
    const matchStatus = !statusFilter || emp.status === statusFilter;
    return matchName && matchDepartment && matchStatus;
  });

  renderEmployees(filtered);
}

// Add event listeners for filters
document.getElementById('nameFilter').addEventListener('input', filterEmployees);
document.getElementById('departmentFilter').addEventListener('change', filterEmployees);
document.getElementById('statusFilter').addEventListener('change', filterEmployees);

// Initial render
renderEmployees();

// New functions for Receita, Projetos, Documentos, Colectivo, and Contato
function showReceita() {
  const content = `
    <div class="receita-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
    ">
      <button class="back-button" onclick="hideReceita()">← Voltar</button>
      
      <div class="date-filter" style="margin: 2rem 0; text-align: center;">
        <input type="date" id="startDate">
        <input type="date" id="endDate">
        <select id="weekFilter">
          <option>Semana 1</option>
          <option>Semana 2</option>
          <option>Semana 3</option>
          <option>Semana 4</option>
        </select>
      </div>

      <table style="width: 90%; max-width: 1200px; margin: 2rem auto; border-collapse: collapse; background: white;">
        <thead>
          <tr style="background: var(--primary); color: white;">
            <th style="padding: 1rem;">Tipo de Licença</th>
            <th>Quantidade de Entrada</th>
            <th>Quantidade de Saída</th>
            <th>Valor Total (MT)</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">Licença de Transporte Público</td>
            <td style="text-align: center;">200</td>
            <td style="text-align: center;">150</td>
            <td style="text-align: right;">75,000.00</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">Licença de Táxi</td>
            <td style="text-align: center;">100</td>
            <td style="text-align: center;">80</td>
            <td style="text-align: right;">40,000.00</td>
          </tr>
          <tr style="background: #f5f5f5; font-weight: bold;">
            <td style="padding: 1rem; border: 1px solid #ddd;">TOTAL</td>
            <td style="text-align: center;">300</td>
            <td style="text-align: center;">230</td>
            <td style="text-align: right;">115,000.00</td>
          </tr>
        </tbody>
      </table>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideReceita() {
  const section = document.querySelector('.receita-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

function showProjetos() {
  const content = `
    <div class="projetos-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
    ">
      <button class="back-button" onclick="hideProjetos()">← Voltar</button>
      
      <div class="projetos-grid" style="max-width: 1200px; margin: 2rem auto; display: grid; gap: 2rem; padding: 2rem;">
        <div class="projeto-card" style="background: white; padding: 2rem; border-radius: 8px;">
          <h3>Projeto BRT</h3>
          <p>Sistema de transporte rápido por ônibus para Maputo.</p>
          <div class="documento-lista">
            <a href="docs/brt-plano.pdf" target="_blank" style="display: block; margin: 1rem 0;">
              📄 Plano Diretor BRT (PDF)
            </a>
            <a href="docs/brt-estudos.pdf" target="_blank" style="display: block; margin: 1rem 0;">
              📄 Estudos de Viabilidade (PDF)
            </a>
          </div>
        </div>
      </div>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideProjetos() {
  const section = document.querySelector('.projetos-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

function showDocumentos() {
  const content = `
    <div class="documentos-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
    ">
      <button class="back-button" onclick="hideDocumentos()">← Voltar</button>
      
      <div class="documentos-grid" style="max-width: 1200px; margin: 2rem auto; display: grid; gap: 2rem; padding: 2rem;">
        <div class="documento-card" style="background: white; padding: 2rem; border-radius: 8px;">
          <h3>Formulários</h3>
          <div class="documento-lista">
            <a href="docs/form1.pdf" target="_blank">📄 Formulário de Licença (PDF)</a>
            <a href="docs/form1.docx" target="_blank">📝 Formulário de Licença (Word)</a>
            <a href="docs/planilha.xlsx" target="_blank">📊 Planilha de Controle (Excel)</a>
          </div>
        </div>
      </div>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideDocumentos() {
  const section = document.querySelector('.documentos-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

function showColectivo() {
  const content = `
    <div class="colectivo-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
    ">
      <button class="back-button" onclick="hideColectivo()">← Voltar</button>
      
      <table style="width: 90%; max-width: 1200px; margin: 2rem auto; border-collapse: collapse; background: white;">
        <thead>
          <tr style="background: var(--primary); color: white;">
            <th style="padding: 1rem;">N° Ordem</th>
            <th>Responsável</th>
            <th>Atividade</th>
            <th>Descrição</th>
            <th>Prazo</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">001</td>
            <td>Carlos Silva</td>
            <td>Manutenção de Rotas</td>
            <td>Revisão das rotas existentes</td>
            <td>30/06/2024</td>
            <td style="color: green;">Em Andamento</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">002</td>
            <td>Ana Santos</td>
            <td>Fiscalização</td>
            <td>Inspeção de terminais</td>
            <td>15/07/2024</td>
            <td style="color: orange;">Pendente</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">003</td>
            <td>Pedro Costa</td>
            <td>Manutenção</td>
            <td>Reparação de semáforos</td>
            <td>20/07/2024</td>
            <td style="color: green;">Em Andamento</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">004</td>
            <td>Maria Luisa</td>
            <td>Documentação</td>
            <td>Atualização de registros</td>
            <td>25/07/2024</td>
            <td style="color: red;">Atrasado</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">005</td>
            <td>João Paulo</td>
            <td>Treinamento</td>
            <td>Capacitação de fiscais</td>
            <td>01/08/2024</td>
            <td style="color: green;">Em Andamento</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">006</td>
            <td>Sofia Lima</td>
            <td>Planejamento</td>
            <td>Definição de novas rotas</td>
            <td>10/08/2024</td>
            <td style="color: orange;">Pendente</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">007</td>
            <td>Lucas Mendes</td>
            <td>Manutenção</td>
            <td>Pintura de faixas</td>
            <td>15/08/2024</td>
            <td style="color: green;">Em Andamento</td>
          </tr>
          <tr>
            <td style="padding: 1rem; border: 1px solid #ddd;">008</td>
            <td>Clara Oliveira</td>
            <td>Fiscalização</td>
            <td>Vistoria de veículos</td>
            <td>20/08/2024</td>
            <td style="color: orange;">Pendente</td>
          </tr>
        </tbody>
      </table>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideColectivo() {
  const section = document.querySelector('.colectivo-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

function showContato() {
  const content = `
    <div class="contato-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
    ">
      <button class="back-button" onclick="hideContato()">← Voltar</button>
      
      <div class="contato-card" style="max-width: 800px; margin: 2rem auto; background: white; padding: 2rem; border-radius: 8px;">
        <h2>DMTT - Direção Municipal de Transportes e Trânsito</h2>
        
        <div class="contato-info" style="margin-top: 2rem;">
          <h3>Linha de Atendimento</h3>
          <p>📞 +258 21 XXX XXX</p>
          
          <h3>Reclamações</h3>
          <p>📱 +258 84 XXX XXXX</p>
          <p>📧 reclamacoes@dmtt.gov.mz</p>
          
          <h3>Email Geral</h3>
          <p>📧 info@dmtt.gov.mz</p>
          
          <h3>Site</h3>
          <p>🌐 www.dmtt.gov.mz</p>
          
          <h3>Redes Sociais</h3>
          <div class="social-links" style="display: flex; gap: 1rem;">
            <a href="https://facebook.com/dmtt" style="text-decoration: none; color: #4267B2;">
              <span style="font-size: 1.2rem;">📱</span> Facebook
            </a>
            <a href="https://wa.me/258XXXXXXXX" style="text-decoration: none; color: #25D366;">
              <span style="font-size: 1.2rem;">💬</span> WhatsApp
            </a>
          </div>
        </div>
      </div>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideContato() {
  const section = document.querySelector('.contato-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

// Add common styles for back button
const backButtonStyles = `
.back-button {
  position: fixed;
  top: 1rem;
  left: 1rem;
  padding: 0.5rem 1rem;
  background: #1a4b8c;  /* Change from var(--primary) to blue */
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  z-index: 1001;
}

.back-button:hover {
  background: #143d73;  /* Darker blue for hover */
}
`;

// Add the styles to the document
if (!document.querySelector('#backButtonStyles')) {
  const styleElement = document.createElement('style');
  styleElement.id = 'backButtonStyles';
  styleElement.textContent = backButtonStyles;
  document.head.appendChild(styleElement);
}

// Add event listeners to the navigation links
document.querySelector('a[href="https://camiloduvane.github.io/Receitas/"]').addEventListener('click', function(e) {
  e.preventDefault();
  showReceita();
});

document.querySelector('a[href="https://dmtt.gov.br/projetos"]').addEventListener('click', function(e) {
  e.preventDefault();
  showProjetos();
});

document.querySelector('a[href="https://dmtt.gov.br/documentos"]').addEventListener('click', function(e) {
  e.preventDefault();
  showDocumentos();
});

document.querySelector('a[href="https://camiloduvane.github.io/Colectivo/"]').addEventListener('click', function(e) {
  e.preventDefault();
  showColectivo();
});

document.querySelector('a[href="https://dmtt.gov.br/contato"]').addEventListener('click', function(e) {
  e.preventDefault();
  showContato();
});

// Add new functions to handle the Legislação section
function showLegislacao() {
  const content = `
    <div class="legislacao-section" style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1000;
      overflow-y: auto;
      background: var(--light);
      padding: 2rem;
    ">
      <button class="back-button" onclick="hideLegislacao()">← Voltar</button>
      
      <div class="legislacao-container" style="max-width: 1200px; margin: 2rem auto;">
        <h2 style="text-align: center; color: #000000; margin-bottom: 2rem;">Legislação</h2>
        
        <div class="legislacao-grid" style="display: grid; gap: 2rem;">
          <div class="legislacao-card" style="background: white; padding: 2rem; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
            <h3>Leis de Trânsito</h3>
            <div class="documento-lista" style="display: grid; gap: 1rem; margin-top: 1rem;">
              <a href="docs/lei-transito.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Lei de Base do Trânsito
              </a>
              <a href="docs/regulamento-transito.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Regulamento do Código de Trânsito
              </a>
            </div>
          </div>
          
          <div class="legislacao-card" style="background: white; padding: 2rem; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
            <h3>Decretos</h3>
            <div class="documento-lista" style="display: grid; gap: 1rem; margin-top: 1rem;">
              <a href="docs/decreto1.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Decreto 1/2023 - Regulamentação de Transportes
              </a>
              <a href="docs/decreto2.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Decreto 2/2023 - Normas de Sinalização
              </a>
            </div>
          </div>
          
          <div class="legislacao-card" style="background: white; padding: 2rem; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
            <h3>Portarias</h3>
            <div class="documento-lista" style="display: grid; gap: 1rem; margin-top: 1rem;">
              <a href="docs/portaria1.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Portaria 1/2023 - Regulamentação de Licenças
              </a>
              <a href="docs/portaria2.pdf" target="_blank" style="display: flex; align-items: center; text-decoration: none; color: #000000;">
                <span style="margin-right: 0.5rem;">📄</span>
                Portaria 2/2023 - Normas de Fiscalização
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  `;
  
  document.body.insertAdjacentHTML('beforeend', content);
}

function hideLegislacao() {
  const section = document.querySelector('.legislacao-section');
  if (section) {
    section.remove();
  }
  document.body.style.overflow = 'auto';
}

// Add event listener for legislacao link
document.querySelector('a[href="https://dmtt.gov.br/legislacao"]').addEventListener('click', function(e) {
  e.preventDefault();
  showLegislacao();
});

// Update the Sistema link event listener
document.querySelector('a[href="https://dmtt.gov.br/sistema"]').addEventListener('click', function(e) {
  e.preventDefault();
  showSistemaLogin();
});

// Update the updateAccounts function
function updateAccounts() {
    const bankAccounts = {
        'BIM': ['123456789', '987654321'],
        'BCI': ['456789123', '321654987'],
        'Standard': ['789123456', '654987321'],
        'Absa': ['147258369', '963852741']
    };
    
    const bank = document.getElementById('bank').value;
    const accountSelect = document.getElementById('account');
    accountSelect.innerHTML = '<option value="">Selecione a conta</option>';
    
    if (bank && bankAccounts[bank]) {
        bankAccounts[bank].forEach(account => {
            const option = document.createElement('option');
            option.value = account;
            option.textContent = account;
            accountSelect.appendChild(option);
        });
    }
}
</script>
</body></html>
