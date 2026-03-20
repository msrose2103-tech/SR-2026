
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Secret Birthday Access</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Poppins", sans-serif;
      background: linear-gradient(135deg, #ffebee, #fff3e0, #f3e5f5);
    }

    .card {
      background: rgba(255,255,255,0.9);
      padding: 30px 35px;
      border-radius: 20px;
      box-shadow: 0 15px 40px rgba(0,0,0,0.2);
      max-width: 350px;
      width: 90%;
      text-align: center;
    }

    h1 {
      margin-top: 0;
      font-size: 1.6rem;
    }

    .input-group {
      margin: 20px 0;
      text-align: left;
    }

    label {
      display: block;
      margin-bottom: 6px;
      font-size: 0.9rem;
    }

    input[type="password"] {
      width: 100%;
      padding: 10px 12px;
      border-radius: 10px;
      border: 1px solid #ccc;
      font-size: 1rem;
    }

    button {
      margin-top: 10px;
      width: 100%;
      padding: 10px 0;
      border: none;
      border-radius: 999px;
      background: linear-gradient(135deg, #ff8a80, #ffb74d);
      color: #fff;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(255,138,128,0.6);
    }

    button:hover {
      filter: brightness(1.05);
    }

    .error {
      margin-top: 10px;
      color: #d32f2f;
      font-size: 0.85rem;
      min-height: 1.2em;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Enter Secret Password 🔐</h1>
    <p style="font-size:0.9rem;opacity:0.8;">
      Only Roshini can open the surprise letter!
    </p>

    <form onsubmit="return checkPassword(event)">
      <div class="input-group">
        <label for="password">Password</label>
        <input id="password" type="password" autocomplete="off" required>
      </div>
      <button type="submit">Unlock Birthday Surprise 🎁</button>
      <div class="error" id="errorMsg"></div>
    </form>
  </div>
  <script>
    // change this to any password you want
    const CORRECT_PASSWORD = "Warrior Princess";

    function checkPassword(e) {
      e.preventDefault(); // stop normal form submit

      const input = document.getElementById("password");
      const errorMsg = document.getElementById("errorMsg");

      if (input.value === CORRECT_PASSWORD) {
        errorMsg.textContent = "";
        // redirect to your countdown envelope page
        window.location.href = "Birthday.html"; // <- change if your file name is different
      } else {
        errorMsg.textContent = "Wrong password. Try again 💔";
        input.value = "";
        input.focus();
      }
      return false;
    }
  </script>
</body>
</html>
