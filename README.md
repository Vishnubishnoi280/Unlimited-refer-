# Unlimited-refer-
Unlimited refer 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Referral Web App</title>
  <style>
    body { font-family: sans-serif; text-align: center; margin-top: 50px; }
    input, button { padding: 10px; margin: 10px; }
    #refLink { font-weight: bold; color: green; }
  </style>
</head>
<body>
  <h1>Unlimited Referral System</h1>
  <p>Enter your name to generate your referral link:</p>
  <input type="text" id="username" placeholder="Your name">
  <button onclick="generateReferral()">Generate Link</button>
  <p id="output"></p>

  <script>
    function generateReferral() {
      const username = document.getElementById('username').value.trim();
      if (username) {
        const link = `${window.location.origin}${window.location.pathname}?ref=${encodeURIComponent(username)}`;
        document.getElementById('output').innerHTML = `Your referral link: <br><span id="refLink">${link}</span>`;
      } else {
        alert("Please enter a name.");
      }
    }

    // Show who referred you if any
    const urlParams = new URLSearchParams(window.location.search);
    const ref = urlParams.get('ref');
    if (ref) {
      document.body.insertAdjacentHTML("beforeend", `<p>You were referred by: <b>${ref}</b></p>`);
    }
  </script>
</body>
</html>
