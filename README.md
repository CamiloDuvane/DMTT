<html><head><base href="https://dmtt.gov.br/"><title>DMTT - Direção Municipal de Transportes e Trânsito</title><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
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
}

.nav-links a {
  color: white;
  text-decoration: none;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: var(--secondary);
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
</style>
</head>
<body>

<header class="header">
  <nav class="nav">
    <div class="nav-links">
      <a href="https://dmtt.gov.br/organograma">Organograma</a>
      <a href="https://dmtt.gov.br/receita">Receita</a>
      <a href="https://dmtt.gov.br/noticias">Notícias</a>
      <a href="https://dmtt.gov.br/sobre">Sobre</a>
      <a href="https://dmtt.gov.br/contato">Contato</a>
    </div>
    <div class="logo">
      <div class="logo-text">DMTT</div>
      <div class="logo-image">
        <img alt="Logo DMTT - Direção Municipal de Transportes e Trânsito" src="logo.png" width="60" height="60">
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
</script>

</body></html>
