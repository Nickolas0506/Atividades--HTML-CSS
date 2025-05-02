<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Xadrez com Torres Refinadas nos Cantos</title>
  <style>
    body {
      margin: 0;
      background-color: #111;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: 'Segoe UI Symbol', 'Noto Sans Symbols', 'Arial Unicode MS', sans-serif;
    }

    .wrapper {
      position: relative;
      width: calc(60px * 8 + 8px); /* largura tabuleiro + borda */
      height: calc(60px * 8 + 8px);
    }

    .chessboard {
      display: grid;
      grid-template-columns: repeat(8, 60px);
      grid-template-rows: repeat(8, 60px);
      border: 4px solid #000;
      box-shadow: 0 0 15px #007BFF;
      position: relative;
      z-index: 1; /* Tabuleiro no topo */
    }

    .square {
      width: 60px;
      height: 60px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 42px;
    }

    .blue {
      background-color: #007BFF;
    }

    .black {
      background-color: #000;
    }

    .white-piece {
      color: #ffffff;
    }

    .black-piece {
      color: #dddddd;
    }

    /* Estilo refinado para as torres */
    .corner-tower {
      position: absolute;
      width: 50px;
      height: 50px;
      background: linear-gradient(135deg, #333, #555);
      border: 3px solid #222;
      border-radius: 5px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 28px;
      color: #fff;
      box-shadow: 0 0 15px rgba(0, 123, 255, 0.7);
      z-index: 0; /* Coloca as torres atrás do tabuleiro */
      transform: rotate(45deg);
    }

    /* Posições das torres nos cantos */
    .top-left     { top: -25px; left: -25px; }
    .top-right    { top: -25px; right: -25px; }
    .bottom-left  { bottom: -25px; left: -25px; }
    .bottom-right { bottom: -25px; right: -25px; }

    /* Efeito de borda iluminada */
    .corner-tower:before {
      content: '';
      position: absolute;
      top: -5px;
      left: -5px;
      right: -5px;
      bottom: -5px;
      border: 2px solid #007BFF;
      border-radius: 8px;
      opacity: 0.6;
      box-shadow: 0 0 10px 3px #007BFF;
    }

  </style>
</head>
<body>
  <div class="wrapper">
    <!-- Torres refinadas nos cantos -->
    <div class="corner-tower top-left">🗼</div>
    <div class="corner-tower top-right">🗼</div>
    <div class="corner-tower bottom-left">🗼</div>
    <div class="corner-tower bottom-right">🗼</div>

    <!-- Tabuleiro -->
    <div class="chessboard" id="board"></div>
  </div>

  <script>
    const pieces = {
      wK: '♔', wQ: '♕', wR: '♖', wB: '♗', wN: '♘', wP: '♙',
      bK: '♚', bQ: '♛', bR: '♜', bB: '♝', bN: '♞', bP: '♟'
    };

    const layout = [
      ['bR','bN','bB','bQ','bK','bB','bN','bR'],
      ['bP','bP','bP','bP','bP','bP','bP','bP'],
      ['','','','','','','',''],
      ['','','','','','','',''],
      ['','','','','','','',''],
      ['','','','','','','',''],
      ['wP','wP','wP','wP','wP','wP','wP','wP'],
      ['wR','wN','wB','wQ','wK','wB','wN','wR']
    ];

    const board = document.getElementById('board');

    for (let row = 0; row < 8; row++) {
      for (let col = 0; col < 8; col++) {
        const square = document.createElement('div');
        square.classList.add('square');
        square.classList.add((row + col) % 2 === 0 ? 'blue' : 'black');

        const piece = layout[row][col];
        if (piece) {
          square.textContent = pieces[piece];
          square.classList.add(piece[0] === 'w' ? 'white-piece' : 'black-piece');
        }

        board.appendChild(square);
      }
    }
  </script>
</body>
</html>
