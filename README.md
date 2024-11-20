<html><head><base href="https://camiloduvane.github.io/DMTT/"><title>DMTT - Direção Municipal de Transportes e Trânsito</title><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<style>
:root {
  --primary: #1a4b8c;
  --secondary: #e63946;
  --light: #f1faee;
  --dark: #1d3557;
  --gray: #457b9d;
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
  background-color: var(--gray);
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
  background: var(--primary);
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  z-index: 1001;
}

.back-button:hover {
  background: var(--dark);
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
  flex: 1;
}

.employee-count {
  max-width: 1200px;
  margin: 1rem auto;
  padding: 0 1rem;
  font-weight: bold;
  color: var(--primary);
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
  color: var(--primary);
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
  color: #2ecc71;
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
  border: 4px solid #4CAF50;
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
  color: #4CAF50;
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
</style>
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
          <a href="https://dmtt.gov.br/codigo" style="border-top: 1px solid rgba(255,255,255,0.1);">
            Código de Trânsito
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
      <p>Novas rotas de transportes Semi-Colectivo  entram em vigor a partir do próximo mês...</p>
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
      <option value="BRT">BRT</option>option>
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

<footer class="footer">
  <p>© 2024 Direção Municipal de Transportes e Trânsito - Todos os direitos reservados</p>
  <div class="social-links">
    <a href="https://facebook.com/dmtt">Facebook</a>
    <a href="https://instagram.com/dmtt">Instagram</a>
    <a href="https://twitter.com/dmtt">Twitter</a>
  </div>
</footer>

<script>
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
</script>

</body></html>
