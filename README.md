# virus.intercept
HACKED
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>System Alert - Virus Detected</title>
  <style>
    body {
      background-color: #000;
      color: red;
      font-family: monospace;
      text-align: center;
      margin: 0;
      padding: 0;
    }

    h1 {
      font-size: 3em;
      margin-top: 2em;
    }

    #scan-log {
      margin-top: 2em;
      font-size: 1.2em;
      color: lime;
    }

    #countdown {
      font-size: 2em;
      color: yellow;
      margin-top: 30px;
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0, 0, 0, 0.95);
      z-index: 9999;
    }
  </style>
</head>
<body>
  <div class="overlay" id="overlay">
    <h1>⚠️ WARNING: Virus Detected ⚠️</h1>
    <div id="scan-log">Initializing virus scan...</div>
    <div id="countdown"></div>
    <audio id="alertSound" autoplay loop>
      <source src="https://www.soundjay.com/button/beep-07.wav" type="audio/wav">
    </audio>
  </div>

  <script>
    const messages = [
      "Scanning system files...",
      "Trojan.Win32.Agent found in C:/Windows/System32",
      "Malware injecting into memory...",
      "System integrity compromised.",
      "Encrypting user data...",
      "Deleting boot files...",
      "Sending logs to attacker server...",
      "VIRUS STATUS: ACTIVE"
    ];

    const scanLog = document.getElementById("scan-log");
    const countdown = document.getElementById("countdown");

    let index = 0;
    let countdownValue = 30;

    // Loop through fake messages
    function runFakeScan() {
      if (index < messages.length) {
        scanLog.innerText = messages[index];
        index++;
        setTimeout(runFakeScan, 1500);
      } else {
        startCountdown();
        alert("Your system has been infected.\nDo NOT turn off your computer.\nContact support immediately.");
      }
    }

    // Countdown function
    function startCountdown() {
      countdown.innerText = `System destruction in: ${countdownValue}s`;
      if (countdownValue > 0) {
        countdownValue--;
        setTimeout(startCountdown, 1000);
      } else {
        document.body.innerHTML = `<h1 style="color:red;">💀 SYSTEM FAILURE 💀</h1><p style="color:white;">All data has been lost. Just kidding 😄</p>`;
        stopAlertSound();
      }
    }

    // Play alert sound
    function stopAlertSound() {
      const sound = document.getElementById("alertSound");
      sound.pause();
      sound.currentTime = 0;
    }

    // Start everything
    window.onload = () => {
      runFakeScan();
    };
  </script>
</body>
</html>
