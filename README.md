<!DOCTYPE html> 
 <html lang="pt-BR">  
<head>  
  <meta charset="UTF-8">    <!-- Responsividade -->  <meta name="viewport"  
content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

  <!-- PWA -->    <meta name="theme-color" content="#e63946">  
  <meta name="apple-mobile-web-app-capable" content="yes">  
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">    <title>Treino Luiz Lopes</title>  
  <style>  
:root {  
  --primary: #e63946;  
  --dark: #1d3557;  
}  body {
font-family: sans-serif;
margin: 0;
background: #f4f4f4;
padding-bottom: 20px;
}

header {
background: var(--primary);
color: white;
padding: 15px;
text-align: center;
font-weight: bold;
position: sticky;
top: 0;
z-index: 10;
}

nav {
display: flex;
overflow-x: auto;
background: white;
border-bottom: 1px solid #ddd;
position: sticky;
top: 46px;
z-index: 9;
}

nav button {
padding: 10px 15px;
border: none;
background: none;
white-space: nowrap;
font-weight: bold;
color: #666;
}

nav button.active {
color: var(--primary);
border-bottom: 3px solid var(--primary);
}

main section { display: none; }
main section.active { display: block; }

.card {
background: white;
margin: 10px;
padding: 15px;
border-radius: 8px;
box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

label {
display: flex;
align-items: center;
gap: 10px;
margin: 10px 0;
font-size: 14px;
}

input[type="checkbox"] {
width: 18px;
height: 18px;
accent-color: var(--primary);
}

/* 🔥 BARRAS MAIS RÁPIDAS */
.progress {
background: #eee;
height: 8px;
border-radius: 4px;
overflow: hidden;
margin-top: 10px;
}

.progress span {
display: block;
height: 100%;
background: var(--primary);
width: 0%;
transition: width 0.15s linear; /* MAIS RÁPIDO */
}

textarea {
width: 100%;
height: 60px;
margin-bottom: 10px;
border: 1px solid #ccc;
border-radius: 4px;
padding: 5px;
}

button {
background: var(--primary);
color: white;
border: none;
padding: 10px;
border-radius: 4px;
width: 100%;
font-weight: bold;
cursor: pointer;
}
</style>

  <!-- Manifest -->    <link rel="manifest" href="manifest.json">  
</head>  <body>  <header>8 SEMANAS LUIZ LOPES</header>  <nav id="mainNav">  
  <button class="active" onclick="showTab('dash', this)">DASH</button>  
  <button onclick="showTab('Sem1', this)">Sem 1</button>  
  <button onclick="showTab('Sem2', this)">Sem 2</button>  
  <button onclick="showTab('Sem3', this)">Sem 3</button>  
  <button onclick="showTab('Sem4', this)">Sem 4</button>  
  <button onclick="showTab('Sem5', this)">Sem 5</button>  
  <button onclick="showTab('Sem6', this)">Sem 6</button>  
  <button onclick="showTab('Sem7', this)">Sem 7</button>  
  <button onclick="showTab('Sem8', this)">Sem 8</button>  
  <button onclick="showTab('cardio', this)">Cardio</button>  
  <button onclick="showTab('dieta', this)">Dieta</button>  
</nav>  <main>  <section id="dash" class="active">  
  <div class="card">  
    <h2>Status Geral</h2>  
    <p>Peso Atual: <input type="number" id="peso" step="0.1"> kg</p>  
    <p>Semana: <input type="number" id="semana" min="1" max="8"></p>  
    <p>Fase: <strong id="fase"></strong></p>  
  </div>    <div class="card">  
    <h2>Progresso Geral</h2>  
    <div class="progress">  
      <span id="progressGeral"></span>  
    </div>  
    <p id="percentGeral">0%</p>  
  </div>  
</section>  <!-- SEMANAS -->  <section id="Sem1"><div class="card"><h2>Semana 1</h2><div class="progress"><span id="progSem1"></span></div><p id="txtSem1">0%</p></div></section>  
<section id="Sem2"><div class="card"><h2>Semana 2</h2><div class="progress"><span id="progSem2"></span></div><p id="txtSem2">0%</p></div></section>  
<section id="Sem3"><div class="card"><h2>Semana 3</h2><div class="progress"><span id="progSem3"></span></div><p id="txtSem3">0%</p></div></section>  
<section id="Sem4"><div class="card"><h2>Semana 4</h2><div class="progress"><span id="progSem4"></span></div><p id="txtSem4">0%</p></div></section>  
<section id="Sem5"><div class="card"><h2>Semana 5</h2><div class="progress"><span id="progSem5"></span></div><p id="txtSem5">0%</p></div></section>  
<section id="Sem6"><div class="card"><h2>Semana 6</h2><div class="progress"><span id="progSem6"></span></div><p id="txtSem6">0%</p></div></section>  
<section id="Sem7"><div class="card"><h2>Semana 7</h2><div class="progress"><span id="progSem7"></span></div><p id="txtSem7">0%</p></div></section>  
<section id="Sem8"><div class="card"><h2>Semana 8</h2><div class="progress"><span id="progSem8"></span></div><p id="txtSem8">0%</p></div></section>  <section id="cardio">  
  <div class="card">  
    <h2>Cardio</h2>  
    <label><input type="checkbox"> Caminhada</label>  
    <label><input type="checkbox"> Corrida</label>  
    <label><input type="checkbox"> Escada</label>  
  </div>  
</section>  <section id="dieta">  
  <div class="card">  
    <h2>Dieta</h2>  
    <textarea placeholder="Café..."></textarea>  
    <textarea placeholder="Almoço..."></textarea>  
    <textarea placeholder="Jantar..."></textarea>  
    <button>Salvar Dieta</button>  
  </div>  
</section>  </main>  <!-- JS -->  <script src="js/app.js"></script>  <!-- Service Worker -->  <script>  
if ('serviceWorker' in navigator) {  
  navigator.serviceWorker.register('sw.js');  
}  
</script>  </body>  
</html>  
