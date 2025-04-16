# Convertisseur
Pour convertir l'euro le fcfa rt le dollard
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Convertisseur FCFA</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #2b2b2b, #1c1c1c);
      color: #f0f0f0;
      text-align: center;
      padding: 40px;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
    }

    input, select, button {
      padding: 12px;
      margin: 12px;
      border-radius: 8px;
      border: 2px solid #333;
      font-size: 16px;
      width: 200px;
    }

    button {
      background-color: #ff5733;
      color: white;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    button:hover {
      background-color: #e04e2a;
      transform: scale(1.05);
    }

    input:focus, select:focus {
      border-color: #ff5733;
      outline: none;
    }

    .result {
      margin-top: 20px;
      font-size: 24px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <div>
    <h1>Convertisseur FCFA ⇄ Euro / USD</h1>
    <input type="number" id="amount" placeholder="Montant">
    <select id="currency">
      <option value="fcfa-eur">FCFA → EUR</option>
      <option value="eur-fcfa">EUR → FCFA</option>
      <option value="fcfa-usd">FCFA → USD</option>
      <option value="usd-fcfa">USD → FCFA</option>
    </select>
    <br>
    <button onclick="convert()">Convertir</button>

    <div class="result" id="result"></div>
  </div>

  <script>
    function convert() {
      const amount = parseFloat(document.getElementById("amount").value);
      const type = document.getElementById("currency").value;
      let result = 0;

      const rates = {
        "fcfa-eur": amount / 655.957,
        "eur-fcfa": amount * 655.957,
        "fcfa-usd": amount / 610,
        "usd-fcfa": amount * 610
      };

      result = rates[type];
      document.getElementById("result").textContent = "Résultat : " + result.toFixed(2);
    }
  </script>

</body>
</html>
