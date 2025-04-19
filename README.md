<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Envelope do Amor</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      background-color: #ffeef0; /* Cor de fundo */
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      font-family: 'Segoe UI', sans-serif;
    }

    .container {
      position: relative;
      width: 250px; /* Tamanho menor para o envelope */
      height: 230px; /* Ajuste de altura para o envelope */
      cursor: pointer;
      perspective: 1000px;
      z-index: 2;
    }

    .envelope {
      width: 100%;
      height: 100%;
      position: relative;
      background: #ff6b81; /* Envelope rosa */
      border-radius: 10px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.2);
      overflow: hidden;
      z-index: 1;
    }

    .flap {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #ff7f94; /* Parte superior do envelope */
      clip-path: polygon(0 0, 50% 50%, 100% 0);
      transform-origin: top;
      transition: transform 0.6s ease;
      z-index: 3;
    }

    .carta {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      width: 85%; /* Tamanho ajustado para a carta */
      height: auto;
      max-height: 550px; /* Ajuste da altura máxima para a carta */
      background: white;
      border-radius: 10px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.15);
      padding: 20px;
      text-align: center;
      font-size: 16px;
      color: #e63946;
      opacity: 0;
      line-height: 1.6;
      transition: all 0.6s ease;
      z-index: 2;
    }

    .container.aberto .flap {
      transform: rotateX(180deg);
    }

    .container.aberto .carta {
      transform: translate(-50%, -50%) scale(1);
      opacity: 1;
    }

    @media (max-width: 500px) {
      .container {
        width: 75vw; /* Ajuste da largura do envelope em dispositivos móveis */
        height: 70vw;
      }

      .carta {
        width: 90vw;
        height: auto;
        font-size: 5vw;
        padding: 5vw;
      }
    }
  </style>
</head>
<body>

  <!-- Envelope -->
  <div class="container" onclick="abrirEnvelope()">
    <div class="envelope">
      <div class="flap"></div>
    </div>
    <div class="carta">
      Como as flores desabrocham no campo, assim o meu coração floresce ao pensar em você. <br><br>
      Que o amor e a beleza que Deus criou ao nosso redor se reflitam na nossa amizade, e que Ele sempre nos abençoe com alegria e renovação. <br><br>
      'As flores apareceram na terra, o tempo de cantar chegou' (Cânticos 2:12). <br><br>
      E como diz em Eclesiastes 4:9: 'Melhor é serem dois do que um, porque têm melhor paga do seu trabalho'. <br><br>
      Que possamos sempre caminhar juntos, apoiando-nos mutuamente em todos os momentos.
    </div>
  </div>

  <!-- JS -->
  <script>
    function abrirEnvelope() {
      document.querySelector('.container').classList.toggle('aberto');
    }
  </script>

</body>
</html>
