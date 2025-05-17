<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Clínica Francielly Rodrigues - Sistema de Gestão</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #0b1a33;
      --primary-light: #143059;
      --secondary: #4a6fa5;
      --success: #28a745;
      --danger: #dc3545;
      --warning: #ffc107;
      --info: #17a2b8;
      --light: #f8f9fa;
      --dark: #343a40;
      --gray: #6c757d;
      --white: #ffffff;
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f5f7fa;
      color: #333;
      line-height: 1.6;
    }
    
    header {
      background: var(--primary);
      color: var(--white);
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    }
    
    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    
    .logo i {
      font-size: 1.8rem;
      color: var(--secondary);
    }
    
    nav {
      background: var(--white);
      padding: 0.8rem;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
      position: sticky;
      top: 0;
      z-index: 100;
    }
    
    nav ul {
      display: flex;
      justify-content: center;
      list-style: none;
      gap: 1rem;
    }
    
    nav button {
      padding: 0.6rem 1.2rem;
      border: none;
      border-radius: 5px;
      background: var(--primary);
      color: var(--white);
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: 500;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    nav button:hover {
      background: var(--primary-light);
      transform: translateY(-2px);
    }
    
    nav button i {
      font-size: 0.9rem;
    }
    
    .container {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 1rem;
    }
    
    .section {
      background: var(--white);
      border-radius: 8px;
      box-shadow: 0 2px 15px rgba(0, 0, 0, 0.05);
      padding: 1.5rem;
      margin-bottom: 2rem;
      animation: fadeIn 0.5s ease;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .hidden {
      display: none;
    }
    
    h2 {
      color: var(--primary);
      margin-bottom: 1.5rem;
      padding-bottom: 0.5rem;
      border-bottom: 2px solid var(--primary-light);
      display: flex;
      align-items: center;
      gap: 10px;
    }
    
    h2 i {
      color: var(--secondary);
    }
    
    .card {
      background: var(--white);
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
      padding: 1rem;
      margin-bottom: 1rem;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      border-left: 4px solid var(--primary);
    }
    
    .card:hover {
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    }
    
    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
    }
    
    .card-title {
      font-size: 1.1rem;
      font-weight: 600;
      color: var(--primary);
    }
    
    .card-body {
      margin-bottom: 0.5rem;
    }
    
    .card-footer {
      display: flex;
      gap: 0.5rem;
      margin-top: 0.8rem;
    }
    
    button {
      padding: 0.5rem 1rem;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 5px;
    }
    
    .btn-primary {
      background: var(--primary);
      color: var(--white);
    }
    
    .btn-primary:hover {
      background: var(--primary-light);
    }
    
    .btn-success {
      background: var(--success);
      color: var(--white);
    }
    
    .btn-success:hover {
      background: #218838;
    }
    
    .btn-danger {
      background: var(--danger);
      color: var(--white);
    }
    
    .btn-danger:hover {
      background: #c82333;
    }
    
    .btn-warning {
      background: var(--warning);
      color: var(--dark);
    }
    
    .btn-warning:hover {
      background: #e0a800;
    }
    
    .btn-info {
      background: var(--info);
      color: var(--white);
    }
    
    .btn-info:hover {
      background: #138496;
    }
    
    .btn-sm {
      padding: 0.3rem 0.6rem;
      font-size: 0.85rem;
    }
    
    input, select, textarea {
      width: 100%;
      padding: 0.7rem;
      border: 1px solid #ddd;
      border-radius: 5px;
      margin-bottom: 1rem;
      font-family: inherit;
      transition: border 0.3s ease;
    }
    
    input:focus, select:focus, textarea:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(11, 26, 51, 0.1);
    }
    
    .form-group {
      margin-bottom: 1rem;
    }
    
    .form-label {
      display: block;
      margin-bottom: 0.5rem;
      font-weight: 500;
      color: var(--primary);
    }
    
    .form-row {
      display: flex;
      gap: 1rem;
    }
    
    .form-row .form-group {
      flex: 1;
    }
    
    .status-indicator {
      display: inline-block;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      margin-right: 5px;
    }
    
    .status-scheduled {
      background: var(--info);
    }
    
    .status-completed {
      background: var(--success);
    }
    
    .status-canceled {
      background: var(--danger);
    }
    
    .badge {
      display: inline-block;
      padding: 0.25rem 0.5rem;
      border-radius: 50px;
      font-size: 0.75rem;
      font-weight: 600;
    }
    
    .badge-primary {
      background: var(--primary-light);
      color: var(--white);
    }
    
    .badge-success {
      background: var(--success);
      color: var(--white);
    }
    
    .badge-danger {
      background: var(--danger);
      color: var(--white);
    }
    
    .badge-warning {
      background: var(--warning);
      color: var(--dark);
    }
    
    .search-box {
      position: relative;
      margin-bottom: 1.5rem;
    }
    
    .search-box input {
      padding-left: 2.5rem;
    }
    
    .search-box i {
      position: absolute;
      left: 1rem;
      top: 50%;
      transform: translateY(-50%);
      color: var(--gray);
    }
    
    .actions-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 1.5rem;
    }
    
    .calendar-view {
      display: flex;
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
    }
    
    .time-column {
      flex: 0 0 80px;
      background: #f8f9fa;
    }
    
    .time-slot {
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-bottom: 1px solid #eee;
      font-size: 0.9rem;
      color: var(--gray);
    }
    
    .schedule-column {
      flex: 1;
      background: var(--white);
    }
    
    .schedule-slot {
      height: 60px;
      border-bottom: 1px solid #eee;
      position: relative;
      overflow: hidden;
    }
    
    .appointment {
      position: absolute;
      left: 0;
      right: 0;
      padding: 0.5rem;
      margin: 0.2rem;
      border-radius: 5px;
      font-size: 0.85rem;
      overflow: hidden;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .appointment:hover {
      transform: scale(1.02);
      box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
    }
    
    .appointment-primary {
      background: #e0f0ff;
      border-left: 3px solid var(--primary);
    }
    
    .appointment-success {
      background: #e6ffed;
      border-left: 3px solid var(--success);
    }
    
    .appointment-danger {
      background: #ffecec;
      border-left: 3px solid var(--danger);
    }
    
    .appointment-warning {
      background: #fff8e1;
      border-left: 3px solid var(--warning);
    }
    
    .appointment-title {
      font-weight: 600;
      margin-bottom: 0.2rem;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
    
    .appointment-time {
      font-size: 0.75rem;
      color: var(--gray);
    }
    
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s ease;
    }
    
    .modal.active {
      opacity: 1;
      visibility: visible;
    }
    
    .modal-content {
      background: var(--white);
      border-radius: 8px;
      width: 90%;
      max-width: 600px;
      max-height: 90vh;
      overflow-y: auto;
      box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
      transform: translateY(-20px);
      transition: all 0.3s ease;
    }
    
    .modal.active .modal-content {
      transform: translateY(0);
    }
    
    .modal-header {
      padding: 1rem;
      border-bottom: 1px solid #eee;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .modal-title {
      font-size: 1.25rem;
      font-weight: 600;
      color: var(--primary);
    }
    
    .modal-close {
      background: none;
      border: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--gray);
    }
    
    .modal-body {
      padding: 1rem;
    }
    
    .modal-footer {
      padding: 1rem;
      border-top: 1px solid #eee;
      display: flex;
      justify-content: flex-end;
      gap: 0.5rem;
    }
    
    .tabs {
      display: flex;
      border-bottom: 1px solid #ddd;
      margin-bottom: 1.5rem;
    }
    
    .tab {
      padding: 0.8rem 1.5rem;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      font-weight: 500;
      color: var(--gray);
      transition: all 0.3s ease;
    }
    
    .tab.active {
      color: var(--primary);
      border-bottom-color: var(--primary);
    }
    
    .tab:hover:not(.active) {
      color: var(--primary-light);
    }
    
    .tab-content {
      display: none;
    }
    
    .tab-content.active {
      display: block;
    }
    
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1rem;
      margin-bottom: 2rem;
    }
    
    .stat-card {
      background: var(--white);
      border-radius: 8px;
      padding: 1.5rem;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
      text-align: center;
    }
    
    .stat-value {
      font-size: 2rem;
      font-weight: 700;
      color: var(--primary);
      margin-bottom: 0.5rem;
    }
    
    .stat-label {
      color: var(--gray);
      font-size: 0.9rem;
    }
    
    .alert {
      padding: 1rem;
      border-radius: 5px;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    
    .alert-success {
      background: #e6ffed;
      color: #28a745;
      border-left: 4px solid #28a745;
    }
    
    .alert-danger {
      background: #ffecec;
      color: #dc3545;
      border-left: 4px solid #dc3545;
    }
    
    .alert-warning {
      background: #fff8e1;
      color: #ffc107;
      border-left: 4px solid #ffc107;
    }
    
    .alert-info {
      background: #e0f7ff;
      color: #17a2b8;
      border-left: 4px solid #17a2b8;
    }
    
    @media (max-width: 768px) {
      nav ul {
        flex-wrap: wrap;
      }
      
      .form-row {
        flex-direction: column;
        gap: 0;
      }
      
      .stats-grid {
        grid-template-columns: 1fr;
      }
      
      .calendar-view {
        flex-direction: column;
      }
      
      .time-column {
        display: flex;
        flex: 1;
        overflow-x: auto;
      }
      
      .time-slot {
        width: 80px;
        flex-shrink: 0;
        height: 40px;
      }
      
      .schedule-column {
        overflow-x: auto;
      }
      
      .schedule-slot {
        height: 40px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">
      <i class="fas fa-clinic-medical"></i>
      <h1>Clínica Francielly Rodrigues</h1>
    </div>
    <div class="user-info">
      <span id="current-date"></span>
    </div>
  </header>

  <nav>
    <ul>
      <li>
        <button onclick="mostrar('dashboard')">
          <i class="fas fa-tachometer-alt"></i> Dashboard
        </button>
      </li>
      <li>
        <button onclick="mostrar('clientes')">
          <i class="fas fa-users"></i> Clientes
        </button>
      </li>
      <li>
        <button onclick="mostrar('agendamentos')">
          <i class="fas fa-calendar-alt"></i> Agendamentos
        </button>
      </li>
      <li>
        <button onclick="mostrar('procedimentos')">
          <i class="fas fa-procedures"></i> Procedimentos
        </button>
      </li>
      <li>
        <button onclick="mostrar('relatorios')">
          <i class="fas fa-chart-bar"></i> Relatórios
        </button>
      </li>
    </ul>
  </nav>

  <div class="container">
    <!-- Dashboard -->
    <section id="dashboard" class="section">
      <h2><i class="fas fa-tachometer-alt"></i> Dashboard</h2>
      
      <div class="stats-grid">
        <div class="stat-card">
          <div class="stat-value" id="total-clientes">0</div>
          <div class="stat-label">Clientes Cadastrados</div>
        </div>
        <div class="stat-card">
          <div class="stat-value" id="total-agendamentos">0</div>
          <div class="stat-label">Agendamentos Hoje</div>
        </div>
        <div class="stat-card">
          <div class="stat-value" id="total-procedimentos">0</div>
          <div class="stat-label">Procedimentos</div>
        </div>
        <div class="stat-card">
          <div class="stat-value" id="faturamento-mes">R$ 0</div>
          <div class="stat-label">Faturamento Mensal</div>
        </div>
      </div>
      
      <div class="actions-bar">
        <h3><i class="fas fa-calendar-day"></i> Agenda do Dia</h3>
        <button class="btn-primary" onclick="mostrar('agendamentos')">
          <i class="fas fa-calendar-plus"></i> Novo Agendamento
        </button>
      </div>
      
      <div id="agenda-hoje"></div>
    </section>

    <!-- Clientes -->
    <section id="clientes" class="section hidden">
      <h2><i class="fas fa-users"></i> Gestão de Clientes</h2>
      
      <div class="actions-bar">
        <div class="search-box">
          <i class="fas fa-search"></i>
          <input type="text" id="buscaCliente" placeholder="Buscar cliente por nome, WhatsApp..." oninput="filtrarClientes()">
        </div>
        <button class="btn-primary" onclick="abrirModalCliente()">
          <i class="fas fa-plus"></i> Novo Cliente
        </button>
      </div>
      
      <div class="status-legend">
        <span><i class="fas fa-circle status-scheduled"></i> Agendado</span>
        <span><i class="fas fa-circle status-completed" style="margin-left:15px;"></i> Atendido</span>
        <span><i class="fas fa-circle status-canceled" style="margin-left:15px;"></i> Cancelado</span>
      </div>
      
      <div id="listaClientes"></div>
    </section>

    <!-- Agendamentos -->
    <section id="agendamentos" class="section hidden">
      <h2><i class="fas fa-calendar-alt"></i> Agendamentos</h2>
      
      <div class="tabs">
        <div class="tab active" onclick="mudarAbaAgendamento('diario')">Visão Diária</div>
        <div class="tab" onclick="mudarAbaAgendamento('semanal')">Visão Semanal</div>
        <div class="tab" onclick="mudarAbaAgendamento('mensal')">Visão Mensal</div>
      </div>
      
      <div class="tab-content active" id="diario">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Data</label>
            <input type="date" id="dataAgendamento" onchange="carregarAgendamentosDiarios()">
          </div>
          <div class="form-group">
            <label class="form-label">Procedimento</label>
            <select id="filtroProcedimento" onchange="carregarAgendamentosDiarios()">
              <option value="">Todos os procedimentos</option>
            </select>
          </div>
        </div>
        
        <div class="calendar-view">
          <div class="time-column" id="colunaHoras"></div>
          <div class="schedule-column" id="listaAgendamentos"></div>
        </div>
      </div>
      
      <div class="tab-content" id="semanal">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Semana de</label>
            <input type="date" id="dataSemana" onchange="carregarAgendamentosSemanais()">
          </div>
        </div>
        <div id="agenda-semanal"></div>
      </div>
      
      <div class="tab-content" id="mensal">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Mês</label>
            <input type="month" id="dataMes" onchange="carregarAgendamentosMensais()">
          </div>
        </div>
        <div id="agenda-mensal"></div>
      </div>
    </section>

    <!-- Procedimentos -->
    <section id="procedimentos" class="section hidden">
      <h2><i class="fas fa-procedures"></i> Procedimentos</h2>
      
      <div class="actions-bar">
        <div class="search-box">
          <i class="fas fa-search"></i>
          <input type="text" id="buscaProcedimento" placeholder="Buscar procedimento..." oninput="filtrarProcedimentos()">
        </div>
        <button class="btn-primary" onclick="abrirModalProcedimento()">
          <i class="fas fa-plus"></i> Novo Procedimento
        </button>
      </div>
      
      <div id="listaProcedimentos"></div>
    </section>

    <!-- Relatórios -->
    <section id="relatorios" class="section hidden">
      <h2><i class="fas fa-chart-bar"></i> Relatórios</h2>
      
      <div class="tabs">
        <div class="tab active" onclick="mudarAbaRelatorio('faturamento')">Faturamento</div>
        <div class="tab" onclick="mudarAbaRelatorio('procedimentos')">Procedimentos</div>
        <div class="tab" onclick="mudarAbaRelatorio('clientes')">Clientes</div>
      </div>
      
      <div class="tab-content active" id="faturamento">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">De</label>
            <input type="date" id="dataInicioRelatorio">
          </div>
          <div class="form-group">
            <label class="form-label">Até</label>
            <input type="date" id="dataFimRelatorio">
          </div>
          <div class="form-group">
            <button class="btn-primary" onclick="gerarRelatorioFaturamento()">
              <i class="fas fa-chart-line"></i> Gerar Relatório
            </button>
          </div>
        </div>
        
        <div id="grafico-faturamento"></div>
        <div id="tabela-faturamento"></div>
      </div>
      
      <div class="tab-content" id="procedimentos">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Período</label>
            <select id="periodoProcedimentos">
              <option value="7">Últimos 7 dias</option>
              <option value="30" selected>Últimos 30 dias</option>
              <option value="90">Últimos 3 meses</option>
              <option value="180">Últimos 6 meses</option>
              <option value="365">Último ano</option>
              <option value="custom">Personalizado</option>
            </select>
          </div>
          <div class="form-group" id="customProcedimentos" style="display:none;">
            <label class="form-label">Data Personalizada</label>
            <input type="date" id="dataCustomProcedimentos">
          </div>
          <div class="form-group">
            <button class="btn-primary" onclick="gerarRelatorioProcedimentos()">
              <i class="fas fa-chart-pie"></i> Gerar Relatório
            </button>
          </div>
        </div>
        
        <div id="grafico-procedimentos"></div>
        <div id="tabela-procedimentos"></div>
      </div>
      
      <div class="tab-content" id="clientes">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Ordenar por</label>
            <select id="ordenacaoClientes">
              <option value="frequencia">Frequência</option>
              <option value="valor">Valor Gasto</option>
              <option value="recencia">Recência</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">Limite</label>
            <select id="limiteClientes">
              <option value="10">Top 10</option>
              <option value="20">Top 20</option>
              <option value="50">Top 50</option>
              <option value="100">Top 100</option>
              <option value="0">Todos</option>
            </select>
          </div>
          <div class="form-group">
            <button class="btn-primary" onclick="gerarRelatorioClientes()">
              <i class="fas fa-chart-bar"></i> Gerar Relatório
            </button>
          </div>
        </div>
        
        <div id="grafico-clientes"></div>
        <div id="tabela-clientes"></div>
      </div>
    </section>
  </div>

  <!-- Modal Cliente -->
  <div class="modal" id="modalCliente">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title" id="modalClienteTitulo">Novo Cliente</h3>
        <button class="modal-close" onclick="fecharModal('modalCliente')">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label class="form-label">Nome Completo</label>
          <input type="text" id="nomeCliente" placeholder="Digite o nome completo">
        </div>
        <div class="form-group">
          <label class="form-label">WhatsApp</label>
          <input type="tel" id="whatsCliente" placeholder="Digite o número com DDD">
        </div>
        <div class="form-group">
          <label class="form-label">E-mail</label>
          <input type="email" id="emailCliente" placeholder="Digite o e-mail (opcional)">
        </div>
        <div class="form-group">
          <label class="form-label">Observações</label>
          <textarea id="obsCliente" rows="3" placeholder="Alergias, preferências, etc."></textarea>
        </div>
        
        <h4>Procedimentos</h4>
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Procedimento</label>
            <select id="procedimentoSelect">
              <option value="">Selecione um procedimento</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">Data</label>
            <input type="date" id="dataProcedimento">
          </div>
          <div class="form-group">
            <label class="form-label">Hora</label>
            <input type="time" id="horaProcedimento">
          </div>
        </div>
        <button class="btn-primary btn-sm" onclick="adicionarProcedimentoCliente()">
          <i class="fas fa-plus"></i> Adicionar Procedimento
        </button>
        
        <div id="listaProcedimentosCliente" style="margin-top:1rem;"></div>
      </div>
      <div class="modal-footer">
        <button class="btn-danger" onclick="fecharModal('modalCliente')">Cancelar</button>
        <button class="btn-success" onclick="salvarCliente()">Salvar Cliente</button>
      </div>
    </div>
  </div>

  <!-- Modal Procedimento -->
  <div class="modal" id="modalProcedimento">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title" id="modalProcedimentoTitulo">Novo Procedimento</h3>
        <button class="modal-close" onclick="fecharModal('modalProcedimento')">&times;</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label class="form-label">Nome do Procedimento</label>
          <input type="text" id="nomeProcedimento" placeholder="Digite o nome do procedimento">
        </div>
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Preço (R$)</label>
            <input type="number" id="precoProcedimento" step="0.01" placeholder="0,00">
          </div>
          <div class="form-group">
            <label class="form-label">Duração (minutos)</label>
            <input type="number" id="duracaoProcedimento" placeholder="Tempo estimado">
          </div>
        </div>
        <div class="form-group">
          <label class="form-label">Descrição</label>
          <textarea id="descricaoProcedimento" rows="3" placeholder="Detalhes do procedimento"></textarea>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn-danger" onclick="fecharModal('modalProcedimento')">Cancelar</button>
        <button class="btn-success" onclick="salvarProcedimento()">Salvar Procedimento</button>
      </div>
    </div>
  </div>

  <!-- Modal Agendamento -->
  <div class="modal" id="modalAgendamento">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">Detalhes do Agendamento</h3>
        <button class="modal-close" onclick="fecharModal('modalAgendamento')">&times;</button>
      </div>
      <div class="modal-body" id="detalhesAgendamento">
        <!-- Preenchido dinamicamente -->
      </div>
      <div class="modal-footer">
        <button class="btn-info" id="btnWhatsApp">
          <i class="fab fa-whatsapp"></i> Enviar Mensagem
        </button>
        <button class="btn-warning" id="btnEditarAgendamento">
          <i class="fas fa-edit"></i> Editar
        </button>
        <button class="btn-danger" id="btnCancelarAgendamento">
          <i class="fas fa-times"></i> Cancelar
        </button>
      </div>
    </div>
  </div>

  <script>
   // Variáveis globais
    let clientes = JSON.parse(localStorage.getItem("clientes")) || [];
    let procedimentos = JSON.parse(localStorage.getItem("procedimentos")) || [];
    let clienteEditandoIndex = null;
    let procedimentosTemp = [];
    let agendamentoEditando = null;


    // Inicialização
        document.addEventListener('DOMContentLoaded', function() {
      atualizarDataAtual();
      carregarProcedimentosDropdown();
      carregarDashboard();
      carregarAgendamentosDiarios();
      
      
      // Configurar data padrão para hoje
      const hoje = new Date();
      const hojeStr = hoje.toISOString().split('T')[0];
      document.getElementById('dataAgendamento').value = hojeStr;
      document.getElementById('dataSemana').value = hojeStr;
      
      const mesAtual = hoje.toISOString().slice(0, 7);
      document.getElementById('dataMes').value = mesAtual;
      
      // Mostrar dashboard por padrão
      mostrar('dashboard');
    });

    // Funções utilitárias - CORRIGIDAS
    function formatarData(dataStr) {
      if (!dataStr) return '';
      const [y, m, d] = dataStr.split('-');
      return `${d}/${m}/${y}`;
    }

    function formatarMoeda(valor) {
      return new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(valor || 0);
    }

    function atualizarDataAtual() {
      const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
      const hoje = new Date().toLocaleDateString('pt-BR', options);
      document.getElementById('current-date').textContent = hoje;
    }

    function salvarLocal() {
      localStorage.setItem("clientes", JSON.stringify(clientes));
      localStorage.setItem("procedimentos", JSON.stringify(procedimentos));
    }
    
    // Funções de navegação
    function mostrar(secao) {
      document.querySelectorAll(".section").forEach(s => s.classList.add("hidden"));
      document.getElementById(secao).classList.remove("hidden");
      
    // Atualizar dados específicos da seção quando aberta
      if (secao === 'clientes') {
        listarClientes();
      } else if (secao === 'dashboard') {
        carregarDashboard();
      } else if (secao === 'procedimentos') {
        listarProcedimentos();
      } else if (secao === 'agendamentos') {
        carregarAgendamentosDiarios();
      }
    }


    function mudarAbaAgendamento(aba) {
      document.querySelectorAll('#agendamentos .tab').forEach(tab => tab.classList.remove('active'));
      document.querySelectorAll('#agendamentos .tab-content').forEach(content => content.classList.remove('active'));
      
      document.querySelector(`#agendamentos .tab[onclick="mudarAbaAgendamento('${aba}')"]`).classList.add('active');
      document.getElementById(aba).classList.add('active');
      
      // Carregar dados da aba selecionada
      if (aba === 'diario') {
        carregarAgendamentosDiarios();
      } else if (aba === 'semanal') {
        carregarAgendamentosSemanais();
      } else if (aba === 'mensal') {
        carregarAgendamentosMensais();
      }
    }

    function mudarAbaRelatorio(aba) {
      document.querySelectorAll('#relatorios .tab').forEach(tab => tab.classList.remove('active'));
      document.querySelectorAll('#relatorios .tab-content').forEach(content => content.classList.remove('active'));
      
      document.querySelector(`#relatorios .tab[onclick="mudarAbaRelatorio('${aba}')"]`).classList.add('active');
      document.getElementById(aba).classList.add('active');
    }

    // Funções de modal
    function abrirModal(modalId, titulo = '') {
      if (titulo) {
        document.getElementById(`${modalId}Titulo`).textContent = titulo;
      }
      document.getElementById(modalId).classList.add('active');
    }

    function fecharModal(modalId) {
      document.getElementById(modalId).classList.remove('active');
    }

    function abrirModalCliente(index = null) {
      clienteEditandoIndex = index;
      const modal = document.getElementById('modalCliente');
      
      if (index !== null) {
        // Modo edição
        document.getElementById('modalClienteTitulo').textContent = 'Editar Cliente';
        const cliente = clientes[index];
        
        document.getElementById('nomeCliente').value = cliente.nome || '';
        document.getElementById('whatsCliente').value = cliente.whatsapp || '';
        document.getElementById('emailCliente').value = cliente.email || '';
        document.getElementById('obsCliente').value = cliente.observacoes || '';
        
        procedimentosTemp = [...(cliente.procedimentos || [])];
      } else {
        // Modo novo cliente
        document.getElementById('modalClienteTitulo').textContent = 'Novo Cliente';
        document.getElementById('nomeCliente').value = '';
        document.getElementById('whatsCliente').value = '';
        document.getElementById('emailCliente').value = '';
        document.getElementById('obsCliente').value = '';
        
        procedimentosTemp = [];
      }
      
      atualizarListaProcedimentosModal();
      abrirModal('modalCliente');
    }

    function abrirModalProcedimento(index = null) {
      const modal = document.getElementById('modalProcedimento');
      
      if (index !== null) {
        // Modo edição
        document.getElementById('modalProcedimentoTitulo').textContent = 'Editar Procedimento';
        const procedimento = procedimentos[index];
        
        document.getElementById('nomeProcedimento').value = procedimento.nome || '';
        document.getElementById('precoProcedimento').value = procedimento.preco || '';
        document.getElementById('duracaoProcedimento').value = procedimento.duracao || '';
        document.getElementById('descricaoProcedimento').value = procedimento.descricao || '';
      } else {
        // Modo novo procedimento
        document.getElementById('modalProcedimentoTitulo').textContent = 'Novo Procedimento';
        document.getElementById('nomeProcedimento').value = '';
        document.getElementById('precoProcedimento').value = '';
        document.getElementById('duracaoProcedimento').value = '';
        document.getElementById('descricaoProcedimento').value = '';
      }
      
      abrirModal('modalProcedimento');
    }

    function abrirModalAgendamento(clienteIndex, procedimentoIndex) {
      const cliente = clientes[clienteIndex];
      const procedimento = cliente.procedimentos[procedimentoIndex];
      agendamentoEditando = { clienteIndex, procedimentoIndex };
      
      const modalBody = document.getElementById('detalhesAgendamento');
      modalBody.innerHTML = `
        <div class="card">
          <div class="card-header">
            <h3>${cliente.nome}</h3>
            <span class="badge ${procedimento.cancelado ? 'badge-danger' : new Date(procedimento.data + 'T' + procedimento.hora) < new Date() ? 'badge-success' : 'badge-primary'}">
              ${procedimento.cancelado ? 'Cancelado' : (new Date(procedimento.data + 'T' + procedimento.hora) < new Date() ? 'Concluído' : 'Agendado')}
            </span>
          </div>
          <div class="card-body">
            <p><strong>Procedimento:</strong> ${procedimento.procedimento}</p>
            <p><strong>Data:</strong> ${formatarData(procedimento.data)}</p>
            <p><strong>Hora:</strong> ${procedimento.hora}</p>
            <p><strong>WhatsApp:</strong> ${cliente.whatsapp}</p>
            ${cliente.email ? `<p><strong>E-mail:</strong> ${cliente.email}</p>` : ''}
            ${cliente.observacoes ? `<p><strong>Observações:</strong> ${cliente.observacoes}</p>` : ''}
          </div>
        </div>
      `;
      
      // Configurar botão do WhatsApp
      document.getElementById('btnWhatsApp').onclick = () => {
        const msg = encodeURIComponent(`Olá ${cliente.nome}, tudo bem? Aqui é da Clínica Francielly Rodrigues, estamos entrando em contato sobre seu agendamento para ${procedimento.procedimento} no dia ${formatarData(procedimento.data)} às ${procedimento.hora}.`);
        window.open(`https://wa.me/${cliente.whatsapp}?text=${msg}`, '_blank');
      };
      
      // Configurar botão de edição
      document.getElementById('btnEditarAgendamento').onclick = () => {
        editarAgendamento(clienteIndex, procedimentoIndex);
        fecharModal('modalAgendamento');
      };
      
      // Configurar botão de cancelamento
      document.getElementById('btnCancelarAgendamento').onclick = () => {
        if (confirm('Deseja realmente cancelar este agendamento?')) {
          cancelarAgendamento(clienteIndex, procedimentoIndex);
          fecharModal('modalAgendamento');
        }
      };
      
      // Esconder botão de cancelamento se já estiver cancelado
      if (procedimento.cancelado) {
        document.getElementById('btnCancelarAgendamento').style.display = 'none';
      }
      
      abrirModal('modalAgendamento');
    }

    // Funções de clientes
    function listarClientes() {
      const lista = document.getElementById('listaClientes');
      lista.innerHTML = '';
      
      if (clientes.length === 0) {
        lista.innerHTML = '<div class="alert alert-info"><i class="fas fa-info-circle"></i> Nenhum cliente cadastrado ainda.</div>';
        return;
      }
      
      // Ordenar clientes pelo último procedimento agendado
      const clientesOrdenados = [...clientes].sort((a, b) => {
        const ultimoA = a.procedimentos && a.procedimentos.length > 0 ? 
          new Date(a.procedimentos[a.procedimentos.length - 1].data + 'T' + a.procedimentos[a.procedimentos.length - 1].hora) : new Date(0);
        const ultimoB = b.procedimentos && b.procedimentos.length > 0 ? 
          new Date(b.procedimentos[b.procedimentos.length - 1].data + 'T' + b.procedimentos[b.procedimentos.length - 1].hora) : new Date(0);
        return ultimoB - ultimoA;
      });
      
      clientesOrdenados.forEach((cliente, index) => {
        const card = document.createElement('div');
        card.className = 'card';
        
        let procedimentosHtml = '<ul style="margin-top:10px;">';
        (cliente.procedimentos || []).forEach((p, pIndex) => {
          const dt = new Date(p.data + 'T' + p.hora);
          let statusClass = 'status-scheduled';
          let statusIcon = '<i class="far fa-clock"></i>';
          
          if (p.cancelado) {
            statusClass = 'status-canceled';
            statusIcon = '<i class="fas fa-ban"></i>';
          } else if (dt < new Date()) {
            statusClass = 'status-completed';
            statusIcon = '<i class="fas fa-check"></i>';
          }
          
          procedimentosHtml += `
            <li style="margin-bottom:5px; display:flex; align-items:center;">
              <span class="${statusClass}" style="margin-right:5px;">${statusIcon}</span>
              <span>${p.procedimento} - ${formatarData(p.data)} às ${p.hora}</span>
            </li>
          `;
        });
        procedimentosHtml += '</ul>';
        
        card.innerHTML = `
          <div class="card-header">
            <div class="card-title">${cliente.nome}</div>
            <div>
              <span class="badge badge-primary">${cliente.procedimentos ? cliente.procedimentos.length : 0} procedimentos</span>
            </div>
          </div>
          <div class="card-body">
            <p><i class="fas fa-phone-alt"></i> ${cliente.whatsapp}</p>
            ${cliente.email ? `<p><i class="fas fa-envelope"></i> ${cliente.email}</p>` : ''}
            ${procedimentosHtml}
          </div>
          <div class="card-footer">
            <button class="btn-info btn-sm" onclick="contatarCliente('${cliente.whatsapp}')">
              <i class="fab fa-whatsapp"></i> WhatsApp
            </button>
            <button class="btn-primary btn-sm" onclick="abrirModalCliente(${index})">
              <i class="fas fa-edit"></i> Editar
            </button>
            <button class="btn-danger btn-sm" onclick="excluirCliente(${index})">
              <i class="fas fa-trash"></i> Excluir
            </button>
          </div>
        `;
        
        lista.appendChild(card);
      });
    }

    function filtrarClientes() {
      const termo = document.getElementById('buscaCliente').value.toLowerCase().trim();
      const cards = document.querySelectorAll('#listaClientes .card');
      
      cards.forEach(card => {
        const texto = card.textContent.toLowerCase();
        card.style.display = texto.includes(termo) ? 'block' : 'none';
      });
    }

    function salvarCliente() {
      const nome = document.getElementById('nomeCliente').value.trim();
      const whatsapp = document.getElementById('whatsCliente').value.trim();
      const email = document.getElementById('emailCliente').value.trim();
      const observacoes = document.getElementById('obsCliente').value.trim();
      
      // Validações básicas
      if (!nome) {
        alert('Por favor, informe o nome do cliente.');
        return;
      }
      
      if (!whatsapp) {
        alert('Por favor, informe o número do WhatsApp.');
        return;
      }
      
      if (procedimentosTemp.length === 0) {
        alert('Por favor, adicione pelo menos um procedimento para o cliente.');
        return;
      }
      
      const cliente = {
        nome,
        whatsapp,
        email,
        observacoes,
        procedimentos: [...procedimentosTemp]
      };
      
      if (clienteEditandoIndex !== null) {
        // Edição de cliente existente
        clientes[clienteEditandoIndex] = cliente;
      } else {
        // Novo cliente
        clientes.push(cliente);
      }
      
      salvarLocal();
      fecharModal('modalCliente');
      listarClientes();
      carregarDashboard();
    }

    function excluirCliente(index) {
      if (confirm('Tem certeza que deseja excluir este cliente e todos os seus agendamentos?')) {
        clientes.splice(index, 1);
        salvarLocal();
        listarClientes();
        carregarDashboard();
      }
    }

    function contatarCliente(whatsapp) {
      window.open(`https://wa.me/${whatsapp}`, '_blank');
    }

    // Funções de procedimentos do cliente
    function carregarProcedimentosDropdown() {
      const select = document.getElementById('procedimentoSelect');
      const selectFiltro = document.getElementById('filtroProcedimento');
      
      // Limpar selects
      select.innerHTML = '<option value="">Selecione um procedimento</option>';
      selectFiltro.innerHTML = '<option value="">Todos os procedimentos</option>';
      
      // Adicionar procedimentos
      procedimentos.forEach(p => {
        const option = document.createElement('option');
        option.value = p.nome;
        option.textContent = `${p.nome} - ${formatarMoeda(p.preco)}`;
        select.appendChild(option.cloneNode(true));
        
        // Para o select de filtro também
        selectFiltro.appendChild(option);
      });
    }

    function adicionarProcedimentoCliente() {
      const procedimentoNome = document.getElementById('procedimentoSelect').value;
      const data = document.getElementById('dataProcedimento').value;
      const hora = document.getElementById('horaProcedimento').value;
      
      if (!procedimentoNome || !data || !hora) {
        alert('Por favor, preencha todos os campos do procedimento.');
        return;
      }
      
      // Verificar conflito de horário
      if (verificarConflitoAgendamento(data, hora)) {
        alert('Já existe um agendamento para este horário. Por favor, escolha outro horário.');
        return;
      }
      
      // Encontrar o procedimento completo para pegar o preço e duração
      const procedimentoCompleto = procedimentos.find(p => p.nome === procedimentoNome);
      
      procedimentosTemp.push({
        procedimento: procedimentoNome,
        data,
        hora,
        preco: procedimentoCompleto ? procedimentoCompleto.preco : 0,
        duracao: procedimentoCompleto ? procedimentoCompleto.duracao : 30,
        cancelado: false
      });
      
      // Limpar campos
      document.getElementById('dataProcedimento').value = '';
      document.getElementById('horaProcedimento').value = '';
      
      atualizarListaProcedimentosModal();
    }

    function verificarConflitoAgendamento(data, hora) {
      // Verificar se já existe agendamento para este horário
      for (const cliente of clientes) {
        for (const proc of cliente.procedimentos || []) {
          if (proc.data === data && proc.hora === hora && !proc.cancelado) {
            return true;
          }
        }
      }
      
      // Verificar também os procedimentos temporários que estão sendo adicionados
      for (const proc of procedimentosTemp) {
        if (proc.data === data && proc.hora === hora && !proc.cancelado) {
          return true;
        }
      }
      
      return false;
    }

    function atualizarListaProcedimentosModal() {
      const lista = document.getElementById('listaProcedimentosCliente');
      lista.innerHTML = '';
      
      if (procedimentosTemp.length === 0) {
        lista.innerHTML = '<p style="color:#666; font-style:italic;">Nenhum procedimento adicionado.</p>';
        return;
      }
      
      procedimentosTemp.forEach((proc, index) => {
        const div = document.createElement('div');
        div.className = 'card';
        div.style.marginBottom = '10px';
        div.style.padding = '10px';
        
        const dt = new Date(proc.data + 'T' + proc.hora);
        let statusClass = 'status-scheduled';
        let statusText = 'Agendado';
        
        if (proc.cancelado) {
          statusClass = 'status-canceled';
          statusText = 'Cancelado';
        } else if (dt < new Date()) {
          statusClass = 'status-completed';
          statusText = 'Concluído';
        }
        
        div.innerHTML = `
          <div style="display:flex; justify-content:space-between; align-items:center;">
            <div>
              <span class="${statusClass}"></span>
              <strong>${proc.procedimento}</strong>
              <span style="margin-left:10px;">${formatarData(proc.data)} às ${proc.hora}</span>
            </div>
            <div>
              <button class="btn-danger btn-sm" onclick="removerProcedimentoTemp(${index})">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div style="margin-top:5px;">
            <small>Preço: ${formatarMoeda(proc.preco)} | Duração: ${proc.duracao} min</small>
          </div>
        `;
        
        lista.appendChild(div);
      });
    }

    function removerProcedimentoTemp(index) {
      procedimentosTemp.splice(index, 1);
      atualizarListaProcedimentosModal();
    }

    // Funções de procedimentos (serviços)
    function listarProcedimentos() {
      const lista = document.getElementById('listaProcedimentos');
      lista.innerHTML = '';
      
      if (procedimentos.length === 0) {
        lista.innerHTML = '<div class="alert alert-info"><i class="fas fa-info-circle"></i> Nenhum procedimento cadastrado ainda.</div>';
        return;
      }
      
      procedimentos.forEach((proc, index) => {
        const card = document.createElement('div');
        card.className = 'card';
        
        card.innerHTML = `
          <div class="card-header">
            <div class="card-title">${proc.nome}</div>
            <div>
              <span class="badge badge-primary">${formatarMoeda(proc.preco)}</span>
            </div>
          </div>
          <div class="card-body">
            <p><strong>Duração:</strong> ${proc.duracao || '--'} minutos</p>
            ${proc.descricao ? `<p><strong>Descrição:</strong> ${proc.descricao}</p>` : ''}
          </div>
          <div class="card-footer">
            <button class="btn-primary btn-sm" onclick="abrirModalProcedimento(${index})">
              <i class="fas fa-edit"></i> Editar
            </button>
            <button class="btn-danger btn-sm" onclick="excluirProcedimento(${index})">
              <i class="fas fa-trash"></i> Excluir
            </button>
          </div>
        `;
        
        lista.appendChild(card);
      });
    }

    function filtrarProcedimentos() {
      const termo = document.getElementById('buscaProcedimento').value.toLowerCase().trim();
      const cards = document.querySelectorAll('#listaProcedimentos .card');
      
      cards.forEach(card => {
        const texto = card.textContent.toLowerCase();
        card.style.display = texto.includes(termo) ? 'block' : 'none';
      });
    }

    function salvarProcedimento() {
      const nome = document.getElementById('nomeProcedimento').value.trim();
      const preco = parseFloat(document.getElementById('precoProcedimento').value);
      const duracao = parseInt(document.getElementById('duracaoProcedimento').value) || 30;
      const descricao = document.getElementById('descricaoProcedimento').value.trim();
      
      if (!nome || isNaN(preco)) {
        alert('Por favor, informe pelo menos o nome e o preço do procedimento.');
        return;
      }
      
      const procedimento = {
        nome,
        preco,
        duracao,
        descricao
      };
      
      // Se estiver editando, encontrar o índice
      const tituloModal = document.getElementById('modalProcedimentoTitulo').textContent;
      if (tituloModal.startsWith('Editar')) {
        // Encontrar o índice do procedimento que está sendo editado
        const nomeOriginal = tituloModal.replace('Editar Procedimento - ', '').trim();
        const index = procedimentos.findIndex(p => p.nome === nomeOriginal);
        
        if (index !== -1) {
          procedimentos[index] = procedimento;
        }
      } else {
        // Novo procedimento
        procedimentos.push(procedimento);
      }
      
      salvarLocal();
      fecharModal('modalProcedimento');
      listarProcedimentos();
      carregarProcedimentosDropdown();
      carregarDashboard();
    }

    function excluirProcedimento(index) {
      if (confirm('Tem certeza que deseja excluir este procedimento? Isso não afetará os agendamentos já existentes.')) {
        procedimentos.splice(index, 1);
        salvarLocal();
        listarProcedimentos();
        carregarProcedimentosDropdown();
        carregarDashboard();
      }
    }

    // Funções de agendamentos
    function carregarAgendamentosDiarios() {
      const dataSelecionada = document.getElementById('dataAgendamento').value;
      const procedimentoFiltro = document.getElementById('filtroProcedimento').value;
      
      if (!dataSelecionada) return;
      
      const horasColuna = document.getElementById('colunaHoras');
      const agendamentosColuna = document.getElementById('listaAgendamentos');
      
      horasColuna.innerHTML = '';
      agendamentosColuna.innerHTML = '';
      
      // Criar coluna de horas (7h às 21h)
      for (let h = 7; h <= 21; h++) {
        const hora = h.toString().padStart(2, '0') + ':00';
        
        // Coluna de horas
        const horaDiv = document.createElement('div');
        horaDiv.className = 'time-slot';
        horaDiv.textContent = hora;
        horasColuna.appendChild(horaDiv);
        
        // Coluna de agendamentos
        const slotDiv = document.createElement('div');
        slotDiv.className = 'schedule-slot';
        agendamentosColuna.appendChild(slotDiv);
      }
      
      // Preencher agendamentos
      clientes.forEach((cliente, clienteIndex) => {
        cliente.procedimentos.forEach((proc, procIndex) => {
          if (proc.data === dataSelecionada && 
              (!procedimentoFiltro || proc.procedimento === procedimentoFiltro)) {
            
            const hora = proc.hora;
            const horaNum = parseInt(hora.split(':')[0]);
            
            if (horaNum >= 7 && horaNum <= 21) {
              const slotIndex = horaNum - 7;
              const slotDiv = agendamentosColuna.children[slotIndex];
              
              let appointmentClass = 'appointment-primary';
              if (proc.cancelado) {
                appointmentClass = 'appointment-danger';
              } else if (new Date(proc.data + 'T' + proc.hora) < new Date()) {
                appointmentClass = 'appointment-success';
              }
              
              const appointmentDiv = document.createElement('div');
              appointmentDiv.className = `appointment ${appointmentClass}`;
              appointmentDiv.innerHTML = `
                <div class="appointment-title">${cliente.nome}</div>
                <div class="appointment-time">${proc.procedimento} - ${proc.hora}</div>
              `;
              appointmentDiv.onclick = () => abrirModalAgendamento(clienteIndex, procIndex);
              
              slotDiv.appendChild(appointmentDiv);
            }
          }
        });
      });
    }

    function carregarAgendamentosSemanais() {
      const dataInicio = new Date(document.getElementById('dataSemana').value);
      if (isNaN(dataInicio.getTime())) return;
      
      // Ajustar para começar na segunda-feira
      const diaSemana = dataInicio.getDay();
      const diff = dataInicio.getDate() - diaSemana + (diaSemana === 0 ? -6 : 1); // Ajuste para segunda-feira
      dataInicio.setDate(diff);
      
      const agendaSemanal = document.getElementById('agenda-semanal');
      agendaSemanal.innerHTML = '';
      
      // Criar cabeçalho com os dias da semana
      const diasSemana = ['Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sábado', 'Domingo'];
      const cabecalho = document.createElement('div');
      cabecalho.style.display = 'grid';
      cabecalho.style.gridTemplateColumns = 'repeat(7, 1fr)';
      cabecalho.style.marginBottom = '10px';
      cabecalho.style.fontWeight = 'bold';
      cabecalho.style.textAlign = 'center';
      
      diasSemana.forEach((dia, i) => {
        const dataDia = new Date(dataInicio);
        dataDia.setDate(dataInicio.getDate() + i);
        
        const diaDiv = document.createElement('div');
        diaDiv.textContent = `${dia} (${dataDia.getDate()}/${dataDia.getMonth() + 1})`;
        cabecalho.appendChild(diaDiv);
      });
      
      agendaSemanal.appendChild(cabecalho);
      
      // Criar linhas com agendamentos
      const linhasDiv = document.createElement('div');
      linhasDiv.style.display = 'grid';
      linhasDiv.style.gridTemplateColumns = 'repeat(7, 1fr)';
      linhasDiv.style.gap = '10px';
      
      diasSemana.forEach((_, i) => {
        const dataDia = new Date(dataInicio);
        dataDia.setDate(dataInicio.getDate() + i);
        const dataStr = dataDia.toISOString().split('T')[0];
        
        const diaDiv = document.createElement('div');
        diaDiv.style.minHeight = '200px';
        diaDiv.style.border = '1px solid #eee';
        diaDiv.style.padding = '10px';
        diaDiv.style.borderRadius = '5px';
        
        const agendamentosDia = [];
        
        clientes.forEach(cliente => {
          cliente.procedimentos.forEach(proc => {
            if (proc.data === dataStr) {
              agendamentosDia.push({
                cliente,
                proc,
                hora: proc.hora
              });
            }
          });
        });
        
        // Ordenar por horário
        agendamentosDia.sort((a, b) => a.hora.localeCompare(b.hora));
        
        if (agendamentosDia.length === 0) {
          diaDiv.innerHTML = '<p style="color:#999; font-style:italic;">Nenhum agendamento</p>';
        } else {
          agendamentosDia.forEach(ag => {
            const agDiv = document.createElement('div');
            agDiv.className = 'card';
            agDiv.style.marginBottom = '5px';
            agDiv.style.padding = '5px';
            agDiv.style.fontSize = '0.9rem';
            
            let statusClass = 'status-scheduled';
            if (ag.proc.cancelado) {
              statusClass = 'status-canceled';
            } else if (new Date(ag.proc.data + 'T' + ag.proc.hora) < new Date()) {
              statusClass = 'status-completed';
            }
            
            agDiv.innerHTML = `
              <div style="display:flex; justify-content:space-between;">
                <span><span class="${statusClass}"></span> <strong>${ag.proc.hora}</strong></span>
                <span>${ag.proc.procedimento}</span>
              </div>
              <div>${ag.cliente.nome}</div>
            `;
            
            diaDiv.appendChild(agDiv);
          });
        }
        
        linhasDiv.appendChild(diaDiv);
      });
      
      agendaSemanal.appendChild(linhasDiv);
    }

    function carregarAgendamentosMensais() {
      const mesAno = document.getElementById('dataMes').value;
      if (!mesAno) return;
      
      const [ano, mes] = mesAno.split('-');
      const primeiroDia = new Date(ano, mes - 1, 1);
      const ultimoDia = new Date(ano, mes, 0);
      
      const agendaMensal = document.getElementById('agenda-mensal');
      agendaMensal.innerHTML = '<p style="color:#666;">Carregando agendamentos do mês...</p>';
      
      // Simular carregamento assíncrono
      setTimeout(() => {
        agendaMensal.innerHTML = '';
        
        // Agrupar agendamentos por dia
        const agendamentosPorDia = {};
        
        clientes.forEach(cliente => {
          cliente.procedimentos.forEach(proc => {
            const [procAno, procMes, procDia] = proc.data.split('-');
            if (procAno === ano && procMes === mes) {
              if (!agendamentosPorDia[procDia]) {
                agendamentosPorDia[procDia] = [];
              }
              
              agendamentosPorDia[procDia].push({
                cliente,
                proc
              });
            }
          });
        });
        
        // Criar calendário
        const calendarioDiv = document.createElement('div');
        calendarioDiv.style.display = 'grid';
        calendarioDiv.style.gridTemplateColumns = 'repeat(7, 1fr)';
        calendarioDiv.style.gap = '5px';
        calendarioDiv.style.marginTop = '10px';
        
        // Cabeçalho com dias da semana
        const diasSemana = ['Dom', 'Seg', 'Ter', 'Qua', 'Qui', 'Sex', 'Sáb'];
        diasSemana.forEach(dia => {
          const diaDiv = document.createElement('div');
          diaDiv.style.textAlign = 'center';
          diaDiv.style.fontWeight = 'bold';
          diaDiv.style.padding = '5px';
          diaDiv.style.background = '#f0f0f0';
          diaDiv.textContent = dia;
          calendarioDiv.appendChild(diaDiv);
        });
        
        // Dias vazios no início (se o mês não começar na segunda)
        const primeiroDiaSemana = primeiroDia.getDay();
        for (let i = 0; i < primeiroDiaSemana; i++) {
          const vazioDiv = document.createElement('div');
          vazioDiv.style.minHeight = '80px';
          vazioDiv.style.background = '#f9f9f9';
          calendarioDiv.appendChild(vazioDiv);
        }
        
        // Dias do mês
        for (let dia = 1; dia <= ultimoDia.getDate(); dia++) {
          const diaDiv = document.createElement('div');
          diaDiv.style.minHeight = '80px';
          diaDiv.style.padding = '5px';
          diaDiv.style.border = '1px solid #eee';
          diaDiv.style.position = 'relative';
          
          const diaNumDiv = document.createElement('div');
          diaNumDiv.textContent = dia;
          diaNumDiv.style.fontWeight = 'bold';
          diaNumDiv.style.marginBottom = '5px';
          diaDiv.appendChild(diaNumDiv);
          
          const diaStr = dia.toString().padStart(2, '0');
          if (agendamentosPorDia[diaStr]) {
            const countDiv = document.createElement('div');
            countDiv.textContent = `${agendamentosPorDia[diaStr].length} agendamento(s)`;
            countDiv.style.fontSize = '0.8rem';
            countDiv.style.color = '#666';
            diaDiv.appendChild(countDiv);
            
            // Adicionar tooltip com detalhes
            diaDiv.title = agendamentosPorDia[diaStr]
              .map(ag => `${ag.proc.hora} - ${ag.cliente.nome}: ${ag.proc.procedimento}`)
              .join('\n');
            
            // Destaque se houver agendamentos
            diaDiv.style.background = '#f0f8ff';
            diaDiv.style.cursor = 'pointer';
            diaDiv.onclick = () => {
              document.getElementById('dataAgendamento').value = `${ano}-${mes}-${diaStr}`;
              mostrar('agendamentos');
              mudarAbaAgendamento('diario');
            };
          }
          
          calendarioDiv.appendChild(diaDiv);
        }
        
        agendaMensal.appendChild(calendarioDiv);
      }, 500);
    }

    function editarAgendamento(clienteIndex, procedimentoIndex) {
      const cliente = clientes[clienteIndex];
      const procedimento = cliente.procedimentos[procedimentoIndex];
      
      // Preencher formulário de cliente com os dados existentes
      clienteEditandoIndex = clienteIndex;
      document.getElementById('modalClienteTitulo').textContent = `Editar Agendamento - ${cliente.nome}`;
      
      document.getElementById('nomeCliente').value = cliente.nome || '';
      document.getElementById('whatsCliente').value = cliente.whatsapp || '';
      document.getElementById('emailCliente').value = cliente.email || '';
      document.getElementById('obsCliente').value = cliente.observacoes || '';
      
      // Criar lista de procedimentos com apenas o procedimento sendo editado
      procedimentosTemp = [{
        ...procedimento,
        editando: true,
        originalIndex: procedimentoIndex
      }];
      
      atualizarListaProcedimentosModal();
      abrirModal('modalCliente');
    }

    function cancelarAgendamento(clienteIndex, procedimentoIndex) {
      clientes[clienteIndex].procedimentos[procedimentoIndex].cancelado = true;
      salvarLocal();
      
      // Atualizar visualização
      const abaAtiva = document.querySelector('#agendamentos .tab.active').getAttribute('onclick');
      if (abaAtiva.includes('diario')) {
        carregarAgendamentosDiarios();
      } else if (abaAtiva.includes('semanal')) {
        carregarAgendamentosSemanais();
      }
      
      carregarDashboard();
    }

    // Funções do dashboard
    function carregarDashboard() {
      // Total de clientes
      document.getElementById('total-clientes').textContent = clientes.length;
      
      // Total de agendamentos hoje
      const hoje = new Date().toISOString().split('T')[0];
      const agendamentosHoje = clientes.reduce((total, cliente) => {
        return total + (cliente.procedimentos || []).filter(p => p.data === hoje && !p.cancelado).length;
      }, 0);
      document.getElementById('total-agendamentos').textContent = agendamentosHoje;
      
      // Total de procedimentos
      document.getElementById('total-procedimentos').textContent = procedimentos.length;
      
      // Faturamento mensal
      const mesAtual = new Date().toISOString().slice(0, 7);
      const faturamento = clientes.reduce((total, cliente) => {
        (cliente.procedimentos || []).forEach(p => {
          if (p.data.startsWith(mesAtual) && !p.cancelado) {
            total += p.preco || 0;
          }
        });
        return total;
      }, 0);
      document.getElementById('faturamento-mes').textContent = formatarMoeda(faturamento);
      
      // Carregar agenda do dia
      carregarAgendaHoje();
    }

    function carregarAgendaHoje() {
      const hoje = new Date().toISOString().split('T')[0];
      const agendaHoje = document.getElementById('agenda-hoje');
      agendaHoje.innerHTML = '';
      
      const agendamentos = [];
      
      clientes.forEach(cliente => {
        (cliente.procedimentos || []).forEach(proc => {
          if (proc.data === hoje && !proc.cancelado) {
            agendamentos.push({
              cliente,
              proc
            });
          }
        });
      });
      
      if (agendamentos.length === 0) {
        agendaHoje.innerHTML = '<div class="alert alert-info"><i class="fas fa-info-circle"></i> Nenhum agendamento para hoje.</div>';
        return;
      }
      
      // Ordenar por horário
      agendamentos.sort((a, b) => a.proc.hora.localeCompare(b.proc.hora));
      
      agendamentos.forEach(ag => {
        const card = document.createElement('div');
        card.className = 'card';
        card.style.marginBottom = '10px';
        
        const horaAtual = new Date().getHours() + ':' + new Date().getMinutes().toString().padStart(2, '0');
        let statusClass = 'status-scheduled';
        let statusText = 'Agendado';
        
        if (ag.proc.hora < horaAtual) {
          statusClass = 'status-completed';
          statusText = 'Concluído';
        }
        
        card.innerHTML = `
          <div class="card-header">
            <div class="card-title">${ag.proc.hora} - ${ag.cliente.nome}</div>
            <span class="badge ${statusClass === 'status-scheduled' ? 'badge-primary' : 'badge-success'}">${statusText}</span>
          </div>
          <div class="card-body">
            <p><strong>Procedimento:</strong> ${ag.proc.procedimento}</p>
            <p><strong>WhatsApp:</strong> ${ag.cliente.whatsapp}</p>
          </div>
          <div class="card-footer">
            <button class="btn-info btn-sm" onclick="contatarCliente('${ag.cliente.whatsapp}')">
              <i class="fab fa-whatsapp"></i> Contatar
            </button>
            <button class="btn-primary btn-sm" onclick="document.getElementById('dataAgendamento').value='${hoje}'; mostrar('agendamentos');">
              <i class="fas fa-calendar-day"></i> Ver Dia
            </button>
          </div>
        `;
        
        agendaHoje.appendChild(card);
      });
    }

    // Funções de relatórios (simuladas)
    function gerarRelatorioFaturamento() {
      const inicio = document.getElementById('dataInicioRelatorio').value;
      const fim = document.getElementById('dataFimRelatorio').value;
      
      if (!inicio || !fim) {
        alert('Por favor, selecione o período para o relatório.');
        return;
      }
      
      // Simular geração de relatório
      document.getElementById('grafico-faturamento').innerHTML = `
        <div class="alert alert-info">
          <i class="fas fa-chart-line"></i> Relatório de faturamento de ${formatarData(inicio)} a ${formatarData(fim)} (simulado)
        </div>
      `;
      
      document.getElementById('tabela-faturamento').innerHTML = `
        <table style="width:100%; border-collapse:collapse; margin-top:1rem;">
          <thead>
            <tr style="background:#f0f0f0;">
              <th style="padding:10px; text-align:left;">Data</th>
              <th style="padding:10px; text-align:right;">Atendimentos</th>
              <th style="padding:10px; text-align:right;">Faturamento</th>
            </tr>
          </thead>
          <tbody>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">${formatarData(inicio)}</td>
              <td style="padding:10px; text-align:right;">5</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(750)}</td>
            </tr>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">${formatarData(fim)}</td>
              <td style="padding:10px; text-align:right;">8</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(1200)}</td>
            </tr>
            <tr style="font-weight:bold; background:#f9f9f9;">
              <td style="padding:10px;">Total</td>
              <td style="padding:10px; text-align:right;">13</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(1950)}</td>
            </tr>
          </tbody>
        </table>
      `;
    }

    function gerarRelatorioProcedimentos() {
      document.getElementById('grafico-procedimentos').innerHTML = `
        <div class="alert alert-info">
          <i class="fas fa-chart-pie"></i> Relatório de procedimentos mais realizados (simulado)
        </div>
      `;
      
      document.getElementById('tabela-procedimentos').innerHTML = `
        <table style="width:100%; border-collapse:collapse; margin-top:1rem;">
          <thead>
            <tr style="background:#f0f0f0;">
              <th style="padding:10px; text-align:left;">Procedimento</th>
              <th style="padding:10px; text-align:right;">Quantidade</th>
              <th style="padding:10px; text-align:right;">Faturamento</th>
            </tr>
          </thead>
          <tbody>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Limpeza de Pele</td>
              <td style="padding:10px; text-align:right;">25</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(3750)}</td>
            </tr>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Botox</td>
              <td style="padding:10px; text-align:right;">18</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(5400)}</td>
            </tr>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Preenchimento</td>
              <td style="padding:10px; text-align:right;">12</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(4800)}</td>
            </tr>
          </tbody>
        </table>
      `;
    }

    function gerarRelatorioClientes() {
      document.getElementById('grafico-clientes').innerHTML = `
        <div class="alert alert-info">
          <i class="fas fa-chart-bar"></i> Relatório de clientes mais frequentes (simulado)
        </div>
      `;
      
      document.getElementById('tabela-clientes').innerHTML = `
        <table style="width:100%; border-collapse:collapse; margin-top:1rem;">
          <thead>
            <tr style="background:#f0f0f0;">
              <th style="padding:10px; text-align:left;">Cliente</th>
              <th style="padding:10px; text-align:right;">Atendimentos</th>
              <th style="padding:10px; text-align:right;">Valor Gasto</th>
            </tr>
          </thead>
          <tbody>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Ana Silva</td>
              <td style="padding:10px; text-align:right;">8</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(2400)}</td>
            </tr>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Carlos Oliveira</td>
              <td style="padding:10px; text-align:right;">6</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(1800)}</td>
            </tr>
            <tr style="border-bottom:1px solid #eee;">
              <td style="padding:10px;">Mariana Santos</td>
              <td style="padding:10px; text-align:right;">5</td>
              <td style="padding:10px; text-align:right;">${formatarMoeda(1500)}</td>
            </tr>
          </tbody>
        </table>
      `;
    }
  </script>
</body>
</html>
