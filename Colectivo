<html><head><base href="/" /><title>Sistema de Gestão Departamental</title><meta charset="utf-8" />
<style>
  body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
    background: #f5f5f5;
  }
  
  .department {
    display: none; /* Hide by default */
    background: white;
    padding: 20px;
    margin-bottom: 30px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    font-size: 14px; /* Base font size */
  }

  .department.active {
    display: block; /* Show when active */
  }

  @media screen and (max-width: 1400px) {
    .department {
      font-size: 12px;
    }
    
    table {
      font-size: 11px;
    }
  }

  @media screen and (max-width: 1200px) {
    .department {
      font-size: 11px;
    }
    
    table {
      font-size: 10px;
    }
  }

  table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
    display: block;
    overflow-x: auto;
    white-space: nowrap;
  }

  th, td {
    border: 1px solid #ddd;
    padding: 12px 8px;
    text-align: left;
  }

  th {
    position: sticky;
    top: 0;
    z-index: 1;
    background: #3498db;
    color: white;
  }

  tr:nth-child(even) {
    background: #f9f9f9;
  }

  .recommendations {
    background: #e8f4fc;
    padding: 15px;
    border-radius: 5px;
    margin-top: 20px;
  }

  .nav-tabs {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
    position: sticky;
    top: 0;
    background: #f5f5f5;
    padding: 10px 0;
    z-index: 100;
  }

  .nav-tab {
    padding: 10px 20px;
    background: #3498db;
    color: white;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
  }

  .nav-tab.active {
    background: #2980b9;
    font-weight: bold;
  }

  .nav-tab:hover {
    background: #2980b9;
  }

  .search-input {
    width: 100%;
    padding: 8px;
    margin: 10px 0;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-sizing: border-box;
  }

  @media screen and (max-width: 1200px) {
    th, td {
      padding: 8px 4px;
    }
  }

  .export-buttons {
    margin: 10px 0;
    display: flex;
    gap: 10px;
  }

  .export-btn {
    padding: 8px 15px;
    background: #2ecc71;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }

  .export-btn:hover {
    background: #27ae60;
  }

  /* Add to existing CSS */
  .editable {
    position: relative;
    cursor: pointer;
  }

  .editable:hover {
    background-color: #f0f0f0;
  }

  .editable:focus {
    outline: 2px solid #3498db;
    background-color: #fff;
  }

  input[type="date"] {
    padding: 5px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: inherit;
    font-size: inherit;
  }

  .date-cell {
    min-width: 120px; /* Ensure enough space for date picker */
  }

  .status-select {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: inherit;
    font-size: inherit;
    background-color: white;
  }

  .status-select:focus {
    outline: 2px solid #3498db;
  }

  .editable[contenteditable="true"] {
    background-color: #ffffff;
    cursor: text;
    min-width: 50px;
  }

  .editable[contenteditable="true"]:focus {
    outline: 2px solid #3498db;
    background-color: #f8f9fa;
  }

  .editable[contenteditable="true"]:hover {
    background-color: #f0f0f0;
  }

  #resumo-table td[contenteditable="true"] {
    text-align: right;
    padding-right: 10px;
  }

  .totals-row {
    font-weight: bold;
    background-color: #f0f0f0;
  }

  .totals-row .total-cell {
    text-align: right;
    padding-right: 10px;
  }
</style>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf-autotable/3.5.31/jspdf.plugin.autotable.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/docx/7.8.2/docx.min.js"></script>
</head>
<body>
  <h1>Sistema de Gestão Departamental</h1>
  
  <div class="nav-tabs">
    <a href="#vereador" class="nav-tab">Vereador</a>
    <a href="#dmtt" class="nav-tab">Directos</a>
    <a href="#darhf" class="nav-tab">DARHF</a>
    <a href="#dl" class="nav-tab">DL</a>
    <a href="#dot" class="nav-tab">DOT</a>
    <a href="#dtp" class="nav-tab">DTP</a>
    <a href="#secretaria" class="nav-tab">Secretaria</a>
    <a href="#resumo" class="nav-tab">Resumo</a>
  </div>

  <div id="vereador" class="department active">
    <h2>Vereador</h2>
    <input type="text" class="search-input" placeholder="Pesquisar recomendações..." onkeyup="searchTable(this, 'vereador-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('vereador-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('vereador-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('vereador-table')">Exportar Word</button>
    </div>
    <div class="recommendations">
      <h3>Recomendações</h3>
      <table id="vereador-table">
        <tr>
          <th>Departamentos</th>
          <th>Recomendação</th>
          <th>Prazo</th>
          <th>Ponto de Situação</th>
        </tr>
        <tr>
          <td rowspan="3">Secretaria</td>
          <td class="editable" contenteditable="true">Implementar novo sistema de gestão</td>
          <td class="editable date-cell" contenteditable="true">15/12/2023</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em análise" selected>Em análise</option>
              <option value="Pendente">Pendente</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">Desenvolver plano de formação</td> 
          <td class="editable date-cell" contenteditable="true">20/01/2024</td>
          <td class="editable">
            <select class="status-select">
              <option value="Pendente" selected>Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">Atualizar procedimentos internos</td>
          <td class="editable date-cell" contenteditable="true">10/11/2023</td>
          <td class="editable">
            <select class="status-select">
              <option value="Concluído" selected>Concluído</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
            </select>
          </td>
        </tr>
        <tr>
          <td rowspan="3">DOT</td>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Pendente" selected>Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em análise" selected>Em análise</option>
              <option value="Pendente">Pendente</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Concluído" selected>Concluído</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
            </select>
          </td>
        </tr>
        <tr>
          <td rowspan="3">DL</td>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Concluído" selected>Concluído</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em análise" selected>Em análise</option>
              <option value="Pendente">Pendente</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Pendente" selected>Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td rowspan="3">DARHF</td>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em progresso" selected>Em progresso</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Concluído" selected>Concluído</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Pendente" selected>Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td rowspan="3">DTP</td>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em análise" selected>Em análise</option>
              <option value="Pendente">Pendente</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Em progresso" selected>Em progresso</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em andamento">Em andamento</option>
              <option value="Concluído">Concluído</option>
            </select>
          </td>
        </tr>
        <tr>
          <td class="editable" contenteditable="true">...</td>
          <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
          <td class="editable">
            <select class="status-select">
              <option value="Concluído" selected>Concluído</option>
              <option value="Pendente">Pendente</option>
              <option value="Em análise">Em análise</option>
              <option value="Em progresso">Em progresso</option>
              <option value="Em andamento">Em andamento</option>
            </select>
          </td>
        </tr>
      </table>
    </div>
  </div>

  <div id="dmtt" class="department">
    <h2>Directos</h2>
    <input type="text" class="search-input" placeholder="Pesquisar actividades..." onkeyup="searchTable(this, 'dmtt-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('dmtt-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('dmtt-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('dmtt-table')">Exportar Word</button>
    </div>
    <table id="dmtt-table">
      <tr>
        <th>Actividades</th>
        <th>Descrição</th>
        <th>Orientação</th>
        <th>Ponto de Situação</th>
        <th>Prazo</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Fiscalização de Transportes</td>
        <td class="editable" contenteditable="true">Inspeção regular dos veículos públicos</td>
        <td class="editable" contenteditable="true">Seguir protocolo padrão</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">30/12/2023</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Manutenção de Sinais</td>
        <td class="editable" contenteditable="true">Reparo e substituição de sinalizações</td>
        <td class="editable" contenteditable="true">Priorizar áreas críticas</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">15/01/2024</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 3</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 4</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 5</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 6</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
    </table>
  </div>

  <div id="darhf" class="department">
    <h2>DARHF</h2>
    <input type="text" class="search-input" placeholder="Pesquisar actividades..." onkeyup="searchTable(this, 'darhf-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('darhf-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('darhf-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('darhf-table')">Exportar Word</button>
    </div>
    <table id="darhf-table">
      <tr>
        <th>Actividades</th>
        <th>Descrição</th>
        <th>Orientação</th>
        <th>Ponto de Situação</th>
        <th>Prazo</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Fiscalização de Transportes</td>
        <td class="editable" contenteditable="true">Inspeção regular dos veículos públicos</td>
        <td class="editable" contenteditable="true">Seguir protocolo padrão</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">30/12/2023</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Manutenção de Sinais</td>
        <td class="editable" contenteditable="true">Reparo e substituição de sinalizações</td>
        <td class="editable" contenteditable="true">Priorizar áreas críticas</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">15/01/2024</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 3</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 4</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 5</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 6</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
    </table>
  </div>

  <div id="dl" class="department">
    <h2>DL (Departamento de Licenciamento)</h2>
    <input type="text" class="search-input" placeholder="Pesquisar licenças..." onkeyup="searchTable(this, 'dl-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('dl-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('dl-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('dl-table')">Exportar Word</button>
    </div>
    <table id="dl-table">
      <tr>
        <th>Nº Ord</th>
        <th>Nome da Empresa/Proprietário</th>
        <th>Distrito</th>
        <th>Endereço</th>
        <th>Matrícula</th>
        <th>Marca da Viatura</th>
        <th>Lotação</th>
        <th>Nº da Licença</th>
        <th>Data de Emissão</th>
        <th>Data de Validade</th>
        <th>Situação da Licença</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">1</td>
        <td class="editable" contenteditable="true">Transportes Rápidos, Lda</td>
        <td class="editable" contenteditable="true">Urbano</td>
        <td class="editable" contenteditable="true">Av. Principal, 123</td>
        <td class="editable" contenteditable="true">ABC-123</td>
        <td class="editable" contenteditable="true">Toyota Hiace</td>
        <td class="editable" contenteditable="true">15</td>
        <td class="editable" contenteditable="true">L2023-001</td>
        <td class="editable date-cell" contenteditable="true">01/01/2023</td>
        <td class="editable date-cell" contenteditable="true">31/12/2023</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">2</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">3</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">4</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">5</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">6</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Activa" selected>Activa</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
      </tr>
    </table>
  </div>

  <div id="dot" class="department">
    <h2>DOT (Departamento de Operações e Transportes)</h2>
    <input type="text" class="search-input" placeholder="Pesquisar actividades..." onkeyup="searchTable(this, 'dot-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('dot-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('dot-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('dot-table')">Exportar Word</button>
    </div>
    <table id="dot-table">
      <tr>
        <th>Actividades</th>
        <th>Descrição</th>
        <th>Orientação</th>
        <th>Ponto de Situação</th>
        <th>Prazo</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Fiscalização de Transportes</td>
        <td class="editable" contenteditable="true">Inspeção regular dos veículos públicos</td>
        <td class="editable" contenteditable="true">Seguir protocolo padrão</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">30/12/2023</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Manutenção de Sinais</td>
        <td class="editable" contenteditable="true">Reparo e substituição de sinalizações</td>
        <td class="editable" contenteditable="true">Priorizar áreas críticas</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">15/01/2024</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 3</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 4</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 5</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 6</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
    </table>
  </div>

  <div id="dtp" class="department">
    <h2>DTP (Departamento de Transportes Públicos)</h2>
    <input type="text" class="search-input" placeholder="Pesquisar actividades..." onkeyup="searchTable(this, 'dtp-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('dtp-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('dtp-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('dtp-table')">Exportar Word</button>
    </div>
    <table id="dtp-table">
      <tr>
        <th>Actividades</th>
        <th>Descrição</th>
        <th>Orientação</th>
        <th>Ponto de Situação</th>
        <th>Prazo</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Fiscalização de Transportes</td>
        <td class="editable" contenteditable="true">Inspeção regular dos veículos públicos</td>
        <td class="editable" contenteditable="true">Seguir protocolo padrão</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">30/12/2023</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Manutenção de Sinais</td>
        <td class="editable" contenteditable="true">Reparo e substituição de sinalizações</td>
        <td class="editable" contenteditable="true">Priorizar áreas críticas</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">15/01/2024</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 3</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 4</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 5</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Actividade 6</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable">
          <select class="status-select">
            <option value="Em andamento" selected>Em andamento</option>
            <option value="Pendente">Pendente</option>
            <option value="Em análise">Em análise</option>
            <option value="Em progresso">Em progresso</option>
            <option value="Concluído">Concluído</option>
          </select>
        </td>
        <td class="editable date-cell" contenteditable="true">DD/MM/YYYY</td>
      </tr>
    </table>
  </div>

  <div id="secretaria" class="department">
    <h2>Secretaria</h2>
    <input type="text" class="search-input" placeholder="Pesquisar informações..." onkeyup="searchTable(this, 'secretaria-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('secretaria-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('secretaria-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('secretaria-table')">Exportar Word</button>
    </div>
    <table id="secretaria-table">
      <tr>
        <th>Informação</th>
        <th>Detalhe</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Horário de Funcionamento</td>
        <td class="editable" contenteditable="true">8:00 - 15:30</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Serviços</td>
        <td class="editable" contenteditable="true">Atendimento ao público, Protocolo</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Responsável</td>
        <td class="editable" contenteditable="true">Maria Silva</td>
      </tr>
    </table>
  </div>

  <div id="resumo" class="department">
    <h2>Resumo</h2>
    <input type="text" class="search-input" placeholder="Pesquisar resumo..." onkeyup="searchTable(this, 'resumo-table')">
    <div class="export-buttons">
      <button class="export-btn" onclick="exportToPDF('resumo-table')">Exportar PDF</button>
      <button class="export-btn" onclick="exportToExcel('resumo-table')">Exportar Excel</button>
      <button class="export-btn" onclick="exportToWord('resumo-table')">Exportar Word</button>
    </div>
    <table id="resumo-table">
      <tr>
        <th>Tipo de Licença</th>
        <th>Actividade</th>
        <th>Inicio</th>
        <th>Renovação</th>
        <th>Substituição de via</th>
        <th>Acréscimo de via</th>
        <th>Mudança de Rota</th>
        <th>Transferência de Proprietário</th>
        <th>2ª via</th>
        <th>Total Q.</th>
        <th>Valores</th>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Licença de Camiões</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Semi Colectivo</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Colectivo</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable date-cell" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
        <td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Taxi</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Taxi de Aplicativo</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Taxi de mercadoria</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Moto Taxi</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Escolar</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Transportes Fúnebres</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Transportes de Passageiros</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Licença de Ciclomotores</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Livrete de Ciclomotores</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr>
        <td class="editable" contenteditable="true">Oficinas</td>
        <td class="editable" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable date-cell" contenteditable="true">...</td><td class="editable" contenteditable="true">...</td>
      </tr>
      <tr class="totals-row">
        <td class="editable" contenteditable="true"><strong>TOTAL</strong></td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
        <td class="total-cell">0</td>
      </tr>
    </table>
  </div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Hide all departments initially except first one
    const departments = document.querySelectorAll('.department');
    departments.forEach((dept, index) => {
        if (index === 0) {
            dept.classList.add('active');
        }
    });

    // Add click handlers to nav tabs
    document.querySelectorAll('.nav-tab').forEach(tab => {
        tab.addEventListener('click', function(e) {
            e.preventDefault();
            
            // Hide all departments
            departments.forEach(dept => {
                dept.classList.remove('active');
            });
            
            // Show clicked department
            const targetId = this.getAttribute('href').substring(1);
            document.getElementById(targetId).classList.add('active');
            
            // Update active tab styling
            document.querySelectorAll('.nav-tab').forEach(t => {
                t.classList.remove('active');
            });
            this.classList.add('active');
        });
    });
    makeTableEditable('vereador-table');
    makeTableEditable('dmtt-table');
    makeTableEditable('darhf-table');
    makeTableEditable('dl-table');
    makeTableEditable('dot-table');
    makeTableEditable('dtp-table');
    makeTableEditable('secretaria-table');
    makeTableEditable('resumo-table');
    calculateRowTotals(); // Initialize totals
});

function searchTable(input, tableId) {
  const filter = input.value.toLowerCase();
  const table = document.getElementById(tableId);
  const rows = table.getElementsByTagName('tr');

  for (let i = 1; i < rows.length; i++) { // Start from 1 to skip header
    const cells = rows[i].getElementsByTagName('td');
    let found = false;
    
    for (let j = 0; j < cells.length; j++) {
      const cell = cells[j];
      if (cell) {
        const text = cell.textContent || cell.innerText;
        if (text.toLowerCase().indexOf(filter) > -1) {
          found = true;
          break;
        }
      }
    }
    
    rows[i].style.display = found ? '' : 'none';
  }
}

function makeTableEditable(tableId) {
  const table = document.getElementById(tableId);
  const cells = table.getElementsByTagName('td');
  
  for(let cell of cells) {
    // If it's a numeric cell in the resumo table (Actividade through 2ª via columns)
    if(tableId === 'resumo-table' && 
       (cell.cellIndex >= 1 && cell.cellIndex <= 8 || cell.cellIndex === 10)) { // Added cell.cellIndex === 10 for Valores column
      cell.setAttribute('contenteditable', 'true');
      cell.classList.add('editable');
      
      // Add input validation for numbers
      cell.addEventListener('input', function() {
        let value = this.textContent.replace(/[^0-9]/g, '');
        this.textContent = value;
      });
      
      cell.addEventListener('blur', calculateRowTotals);
    } else if(cell.classList.contains('status-select-cell')) {
      // Handle status select cells
    } else if(cell.classList.contains('date-cell')) {
      // Handle date cells  
    } else {
      // Regular editable cells
      cell.setAttribute('contenteditable', 'true');
      cell.classList.add('editable');
    }
  }
}

function calculateRowTotals() {
  const resumoTable = document.getElementById('resumo-table');
  const rows = resumoTable.getElementsByTagName('tr');
  const columnTotals = new Array(11).fill(0); // Array to store column totals
  
  // Start from 1 to skip header row, end before last row (totals row)
  for (let i = 1; i < rows.length - 1; i++) {
    const cells = rows[i].getElementsByTagName('td');
    let rowTotal = 0;
    
    // Sum cells from index 1 to 8 (Actividade through 2ª via)
    for (let j = 1; j <= 8; j++) {
      const value = parseInt(cells[j].textContent) || 0;
      rowTotal += value;
      columnTotals[j] += value; // Add to column total
    }
    
    // Set the total in the Total Q. column (index 9)
    if(cells[9]) {
      cells[9].textContent = rowTotal;
      columnTotals[9] += rowTotal;
    }

    // Add the Valores column to totals
    if(cells[10]) {
      const valoresValue = parseInt(cells[10].textContent.replace(/[^0-9]/g, '')) || 0;
      columnTotals[10] += valoresValue;
    }
  }
  
  // Update totals row
  const totalsRow = rows[rows.length - 1].getElementsByTagName('td');
  for(let i = 1; i <= 10; i++) {
    if(i === 10) {
      totalsRow[i].textContent = columnTotals[i].toLocaleString() + ' MZN';
    } else {
      totalsRow[i].textContent = columnTotals[i];
    }
  }
}

function getCurrentUser() {
  // In a real app this would get the logged in user
  return "Usuário do Sistema";
}

function exportToPDF(tableId) {
  const { jsPDF } = window.jspdf;
  const doc = new jsPDF();
  
  doc.autoTable({
    html: '#' + tableId,
    theme: 'grid',
    headStyles: { fillColor: [52, 152, 219] },
    didDrawPage: function(data) {
      // Add footer
      const pageHeight = doc.internal.pageSize.height;
      doc.setFontSize(8);
      doc.text('Elaborado por computador', 20, pageHeight - 10);
      doc.text('Impresso por: ' + getCurrentUser(), 20, pageHeight - 15);
    }
  });
  
  doc.save(tableId + '.pdf');
}

function exportToExcel(tableId) {
  const table = document.getElementById(tableId);
  const wb = XLSX.utils.table_to_book(table, {sheet: "Sheet1"});

  // Add footer sheet
  const ws = wb.Sheets["Sheet1"];
  const range = XLSX.utils.decode_range(ws['!ref']);
  const footerRow = range.e.r + 2;

  ws[XLSX.utils.encode_cell({r: footerRow, c: 0})] = {t: 's', v: 'Elaborado por computador'};
  ws[XLSX.utils.encode_cell({r: footerRow + 1, c: 0})] = {t: 's', v: 'Impresso por: ' + getCurrentUser()};

  XLSX.writeFile(wb, tableId + '.xlsx');
}

function exportToWord(tableId) {
  const table = document.getElementById(tableId);
  const doc = new docx.Document({
    sections: [{
      properties: {},
      children: [
        new docx.Table({
          rows: Array.from(table.rows).map(row => {
            return new docx.TableRow({
              children: Array.from(row.cells).map(cell => {
                return new docx.TableCell({
                  children: [new docx.Paragraph({text: cell.innerText})],
                });
              }),
            });
          }),
        }),
        new docx.Paragraph({text: ""}),
        new docx.Paragraph({text: "Elaborado por computador"}),
        new docx.Paragraph({text: "Impresso por: " + getCurrentUser()}),
      ],
    }],
  });

  docx.Packer.toBlob(doc).then(blob => {
    const url = window.URL.createObjectURL(blob);
    const a = document.createElement("a");
    document.body.appendChild(a);
    a.href = url;
    a.download = tableId + '.docx';
    a.click();
    window.URL.revokeObjectURL(url);
  });
}
</script>

</body></html>
