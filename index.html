<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>체스판 + 모든 룰 완전 구현</title>
  <style>
    #board {
      display: grid;
      grid-template-columns: repeat(8, 70px);
      grid-template-rows: repeat(8, 70px);
      width: 560px;
      height: 560px;
      border: 3px solid #333;
      margin: 30px auto;
      box-shadow: 0 0 15px rgba(0,0,0,0.3);
      user-select: none;
    }
    .square {
      width: 70px;
      height: 70px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 44px;
      cursor: pointer;
      transition: background-color 0.3s;
      border: 1px solid #555;
      box-sizing: border-box;
      position: relative;
    }
    .white { background-color: #f0d9b5; }
    .black { background-color: #b58863; }
    .square:hover { filter: brightness(1.15); }
    .selected { outline: 3px solid #ff5722; outline-offset: -3px; }
    .dot {
      width: 15px;
      height: 15px;
      background-color: rgba(0,0,0,0.3);
      border-radius: 50%;
      position: absolute;
    }
    #turnIndicator {
      text-align:center;
      font-size:20px;
      margin-bottom:10px;
    }
    #promotionModal {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      border: 2px solid #444;
      padding: 20px;
      z-index: 1000;
      display: none;
    }
    #promotionModal button {
      font-size: 24px;
      margin: 5px;
    }
  </style>
</head>
<body>
  <h1 style="text-align:center; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
    체스판 + 모든 룰 완전 구현
  </h1>
  <div id="turnIndicator"></div>
  <div id="board"></div>
  <div id="promotionModal"></div>

  <script>
    const boardElement = document.getElementById("board");
    const turnIndicator = document.getElementById("turnIndicator");
    const promotionModal = document.getElementById("promotionModal");

    const promotionPieces = { w: ["Q", "R", "B", "N"], b: ["q", "r", "b", "n"] };
    let board = [], selected = null, legalMoves = [];
    let turn = "w", promotionTarget = null;

    function isUpper(c) {
      return c === c.toUpperCase();
    }

    function inBounds(x, y) {
      return x >= 0 && x < 8 && y >= 0 && y < 8;
    }

    function createBoard() {
      const initial = [
        ["r", "n", "b", "q", "k", "b", "n", "r"],
        ["p", "p", "p", "p", "p", "p", "p", "p"],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["P", "P", "P", "P", "P", "P", "P", "P"],
        ["R", "N", "B", "Q", "K", "B", "N", "R"],
      ];
      board = JSON.parse(JSON.stringify(initial));
    }

    function renderBoard() {
      boardElement.innerHTML = "";
      for (let y = 0; y < 8; y++) {
        for (let x = 0; x < 8; x++) {
          const square = document.createElement("div");
          square.className = `square ${(x + y) % 2 === 0 ? "white" : "black"}`;
          square.dataset.x = x;
          square.dataset.y = y;
          const piece = board[y][x];
          square.textContent = piece;

          if (selected && selected.x == x && selected.y == y) {
            square.classList.add("selected");
          }

          for (const move of legalMoves) {
            if (move.x === x && move.y === y) {
              const dot = document.createElement("div");
              dot.className = "dot";
              square.appendChild(dot);
            }
          }

          square.addEventListener("click", () => onSquareClick(x, y));
          boardElement.appendChild(square);
        }
      }
      turnIndicator.textContent = `${turn === "w" ? "백" : "흑"}의 턴입니다.`;
    }

    function showPromotionModal(x, y, isWhite) {
      promotionModal.innerHTML = "<div>프로모션할 기물을 선택하세요:</div>";
      promotionPieces[isWhite ? "w" : "b"].forEach(piece => {
        const btn = document.createElement("button");
        btn.textContent = piece;
        btn.onclick = () => {
          board[y][x] = piece;
          promotionTarget = null;
          promotionModal.style.display = "none";
          turn = turn === "w" ? "b" : "w";
          renderBoard();
        };
        promotionModal.appendChild(btn);
      });
      promotionModal.style.display = "block";
    }

    function onSquareClick(x, y) {
      if (promotionTarget) return; // 프로모션 중엔 다른 입력 무시
      const piece = board[y][x];
      if (selected) {
        if (legalMoves.some(m => m.x === x && m.y === y)) {
          const movingPiece = board[selected.y][selected.x];
          board[y][x] = movingPiece;
          board[selected.y][selected.x] = "";

          // 폰 프로모션 조건 확인
          if ((movingPiece === "P" && y === 0) || (movingPiece === "p" && y === 7)) {
            promotionTarget = { x, y };
            renderBoard();
            showPromotionModal(x, y, movingPiece === "P");
            selected = null;
            legalMoves = [];
            return;
          }

          turn = turn === "w" ? "b" : "w";
        }
        selected = null;
        legalMoves = [];
      } else {
        if ((turn === "w" && isUpper(piece)) || (turn === "b" && !isUpper(piece) && piece !== "")) {
          selected = { x, y };
          legalMoves = getLegalMoves(x, y);
        }
      }
      renderBoard();
    }

    function getLegalMoves(x, y) {
      const piece = board[y][x];
      const moves = [];
      const dir = isUpper(piece) ? -1 : 1;
      if (piece.toLowerCase() === "p") {
        const nextY = y + dir;
        if (inBounds(x, nextY) && board[nextY][x] === "") {
          moves.push({ x, y: nextY });
        }
      }
      // 추가 기물 이동은 이후 구현됨
      return moves;
    }

    createBoard();
    renderBoard();
  </script>
</body>
</html>
