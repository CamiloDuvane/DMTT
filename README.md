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
  min-width: 200px;
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
  white-space: pre-wrap;
  font-family: 'Courier New', monospace;
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

.search-container {
  margin: 20px;
  display: flex;
  gap: 10px;
  justify-content: center;
}

.search-container input,
.search-container select {
  padding: 8px;
  border: 1px solid var(--gray);
  border-radius: 4px;
  font-size: 14px;
}

#employeeTable {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
  background: white;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
}

#employeeTable th,
#employeeTable td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

#employeeTable th {
  background-color: var(--primary);
  color: white;
  font-weight: bold;
}

.employee-photo {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.status-activo {
  color: #28a745;
  background: #d4edda;
  padding: 4px 8px;
  border-radius: 4px;
}

.status-inativo {
  color: #dc3545;
  background: #f8d7da;
  padding: 4px 8px;
  border-radius: 4px;
}

.status-deferias {
  color: #ffc107;
  background: #fff3cd;
  padding: 4px 8px;
  border-radius: 4px;
}

.status-destacado {
  color: #17a2b8;
  background: #d1ecf1;
  padding: 4px 8px;
  border-radius: 4px;
}

.employee-section {
  display: none;
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
</style>
</head>
<body>

<header class="header">
  <nav class="nav">
    <div class="nav-links">
      <a href="https://camiloduvane.github.io/Orgranograma/">Organograma</a>
      <a href="https://camiloduvane.github.io/Receitas/">Receita</a>
      <a href="#" id="funcionariosLink">Funcionarios</a>
      <a href="https://camiloduvane.github.io/Relatorio/">Relatório</a>
      <a href="https://dmtt.gov.br/contato">Contato</a>
      <div class="dropdown">
        <a href="#" style="cursor: pointer;">Mais</a>
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
      <p>DMTT inicia instalação de semáforos com tecnologia adaptativa...</p>
      <small>10/01/2024</small>
    </div>
    
    <div class="news-card">
      <h3>Campanha Maio Amarelo</h3>
      <p>Ações de conscientização marcam o início do Maio Amarelo...</p>
      <small>05/01/2024</small>
    </div>
    
    <div class="news-card">
      <h3>Alteração de itinerário</h3>
      <p>Novas rotas de ônibus entram em vigor a partir do próximo mês...</p>
      <small>03/01/2024</small>
    </div>
  </div>
</section>

<div id="employeeSection" class="employee-section">
  <div class="search-container">
    <input type="text" id="nameSearch" placeholder="Pesquisar por nome...">
    <select id="departmentSearch">
        <option value="">Todos os Departamentos</option>
        <option value="VMTT">VMTT</option>
        <option value="DMTT">DMTT</option>
        <option value="DARHF">DARHF</option>
        <option value="DOT">DOT</option>
        <option value="DTP">DTP</option>
        <option value="Fiscalização">Fiscalização</option>
        <option value="Licenciamento">Licenciamento</option>
        <option value="Secretaria">Secretaria</option>
        <option value="BRT">BRT</option>
    </select>
    <select id="statusSearch">
        <option value="">Todos os Status</option>
        <option value="Activo">Activo</option>
        <option value="Inativo">Inativo</option>
        <option value="De Férias">De Férias</option>
        <option value="Destacado">Destacado</option>
    </select>
  </div>

  <table id="employeeTable">
    <thead>
        <tr>
            <th>N/o</th>
            <th>Foto</th>
            <th>Nome</th>
            <th>Cargo de Chefia</th>
            <th>Categoria</th>
            <th>Formação</th>
            <th>Locação</th>
            <th>Departamento</th>
            <th>Status</th>
        </tr>
    </thead>
    <tbody id="employeeTableBody">
    </tbody>
  </table>
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
    e.preventDefault();
    document.querySelector(this.getAttribute('href')).scrollIntoView({
      behavior: 'smooth'
    });
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

// Employee data array
let employees = [
    { id: 1, name: 'João Silva', role: 'Diretor', category: 'Executive', education: 'Mestrado', location: 'Escritório Central', department: 'DMTT', status: 'Activo', photo: '#007bff' },
    { id: 2, name: 'Maria Souza', role: 'Gerente de Trânsito', category: 'Management', education: 'Graduação', location: 'Escritório Central', department: 'VMTT', status: 'Activo', photo: '#28a745' },
    { id: 3, name: 'Carlos Mendes', role: 'Analista', category: 'Staff', education: 'Técnico', location: 'Setor de Licenciamento', department: 'Licenciamento', status: 'Inativo', photo: '#dc3545' },
    { id: 4, name: 'Ana Costa', role: 'Coordenador', category: 'Management', education: 'Graduação', location: 'Fiscalização', department: 'Fiscalização', status: 'De Férias', photo: '#ffc107' },
    { id: 5, name: 'Lucas Pereira', role: 'Assistente', category: 'Staff', education: 'Pós-graduação', location: 'Setor de Educação', department: 'Educação', status: 'Destacado', photo: '#17a2b8' }
];

function renderEmployees() {
    const tbody = document.getElementById('employeeTableBody');
    tbody.innerHTML = '';
    
    employees.forEach(emp => {
        const row = document.createElement('tr');
        const statusClass = `status-${emp.status?.toLowerCase().replace(' ', '') || 'activo'}`;
        row.innerHTML = `
            <td>${emp.id}</td>
            <td><svg class="employee-photo" viewBox="0 0 50 50">
                <circle cx="25" cy="25" r="20" fill="${emp.photo}"/>
            </svg></td>
            <td>${emp.name}</td>
            <td>${emp.role || '-'}</td>
            <td>${emp.category || '-'}</td>
            <td>${emp.education || '-'}</td>
            <td>${emp.location || '-'}</td>
            <td>${emp.department || '-'}</td>
            <td><span class="${statusClass}">${emp.status || 'Activo'}</span></td>
        `;
        tbody.appendChild(row);
    });
}

function filterTable() {
    const nameSearch = document.getElementById('nameSearch').value.toLowerCase();
    const departmentSearch = document.getElementById('departmentSearch').value;
    const statusSearch = document.getElementById('statusSearch').value;
    
    const filteredEmployees = employees.filter(emp => {
        const nameMatch = emp.name.toLowerCase().includes(nameSearch);
        const departmentMatch = !departmentSearch || emp.department === departmentSearch;
        const statusMatch = !statusSearch || emp.status === statusSearch;
        return nameMatch && departmentMatch && statusMatch;
    });
    
    const tbody = document.getElementById('employeeTableBody');
    tbody.innerHTML = '';
    
    filteredEmployees.forEach(emp => {
        const row = document.createElement('tr');
        const statusClass = `status-${emp.status?.toLowerCase().replace(' ', '') || 'activo'}`;
        row.innerHTML = `
            <td>${emp.id}</td>
            <td><svg class="employee-photo" viewBox="0 0 50 50">
                <circle cx="25" cy="25" r="20" fill="${emp.photo}"/>
            </svg></td>
            <td>${emp.name}</td>
            <td>${emp.role || '-'}</td>
            <td>${emp.category || '-'}</td>
            <td>${emp.education || '-'}</td>
            <td>${emp.location || '-'}</td>
            <td>${emp.department || '-'}</td>
            <td><span class="${statusClass}">${emp.status || 'Activo'}</span></td>
        `;
        tbody.appendChild(row);
    });
}

document.getElementById('nameSearch').addEventListener('input', filterTable);
document.getElementById('departmentSearch').addEventListener('change', filterTable);
document.getElementById('statusSearch').addEventListener('change', filterTable);

// Initial render
renderEmployees();

// Modify the funcionariosLink event listener
document.getElementById('funcionariosLink').addEventListener('click', function(e) {
  e.preventDefault();
  const employeeSection = document.getElementById('employeeSection');
  
  // Toggle visibility
  if (employeeSection.style.display === 'block') {
    employeeSection.style.display = 'none';
  } else {
    employeeSection.style.display = 'block';
    // Scroll to employee section
    employeeSection.scrollIntoView({ behavior: 'smooth' });
  }
});
</script>

</body></html>
