<!DOCTYPE html>
<html>
<head>
  <style>
    table {
      border-collapse: collapse;
      margin: 0 auto;
    }
    td {
      border: 1px solid #000;
      width: 50px;
      height: 50px;
      text-align: center;
      font-size: 24px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <table id="bingo-card"></table>

  <script>
    const cardSize = 5;
    const maxNumber = 75;
    const bingoCard = document.getElementById('bingo-card');
    const cells = [];

    // カードのセルを生成して表示
    for (let row = 0; row < cardSize; row++) {
      const rowElement = document.createElement('tr');
      bingoCard.appendChild(rowElement);
      for (let col = 0; col < cardSize; col++) {
        const cellValue = getRandomUniqueNumber();
        const cell = document.createElement('td');
        cell.textContent = cellValue;
        cells.push(cellValue);
        rowElement.appendChild(cell);
        cell.addEventListener('click', () => toggleCell(cell));
      }
    }

    // セルのクリック時の処理
    function toggleCell(cell) {
      cell.classList.toggle('selected');
      checkBingo();
    }

    // ビンゴが達成されたかどうかを確認
    function checkBingo() {
      // この部分にビンゴの判定ロジックを追加できます
      // セルがビンゴになった場合、セルの背景色などを変更できます
    }

    // 一意のランダムな数値を生成
    function getRandomUniqueNumber() {
      while (true) {
        const randomNumber = Math.floor(Math.random() * maxNumber) + 1;
        if (cells.indexOf(randomNumber) === -1) {
          return randomNumber;
        }
      }
    }
  </script>
</body>
</html>
