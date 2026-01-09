<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Painel Telesr</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #1e1e2f;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  #painel {
    background-color: #2b2b3c;
    padding: 20px;
    border-radius: 10px;
    width: 300px;
    box-shadow: 0 0 15px rgba(0,0,0,0.5);
  }

  h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #00ffff;
  }

  .button {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: 0.2s;
  }

  .button:hover {
    opacity: 0.8;
  }

  .botao-slide {
    background-color: #444466;
    color: #fff;
  }

  .botao-injetar {
    background-color: #00bfff;
    color: #fff;
  }

  .status {
    margin-top: 10px;
    text-align: center;
    font-weight: bold;
    color: #00ff00;
  }

  .hidden {
    display: none;
  }
</style>
</head>
<body>

<div id="painel">
  <h2>telesr</h2>

  <button class="button botao-slide" data-slide="cabeca">Cabeça</button>
  <button class="button botao-slide" data-slide="pescoco">Pescoço</button>
  <button class="button botao-slide" data-slide="peito">Peito</button>
  <button class="button botao-slide" id="esconder-todos">Esconder Todos</button>
  
  <button class="button botao-injetar" id="injetar">Injetar</button>
  
  <div class="status" id="status"></div>
</div>

<script>
  const botaoInjetar = document.getElementById('injetar');
  const status = document.getElementById('status');
  const botoesSlide = document.querySelectorAll('.botao-slide');

  let injetando = false;

  // Função do botão injetar
  botaoInjetar.addEventListener('click', () => {
    if (injetando) return;
    injetando = true;
    status.textContent = "Injetando auxílio...";
    setTimeout(() => {
      status.textContent = "Auxílio injetado com sucesso!";
      injetando = false;
    }, 3000);
  });

  // Resetar botão injetar quando qualquer outro botão é clicado
  botoesSlide.forEach(botao => {
    botao.addEventListener('click', () => {
      if (botao.id === 'esconder-todos') {
        // Esconder todos os slides
        alert("Todos os slides foram escondidos!");
      }
      status.textContent = "";
    });
  });
</script>

</body>
</html>
