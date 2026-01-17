<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>EmadForShare  - File & Chat</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: #fff;
    }
    header {
      padding: 15px;
      text-align: center;
      background: rgba(0,0,0,0.3);
      font-size: 22px;
      font-weight: bold;
    }
    .container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      padding: 20px;
    }
    .card {
      background: rgba(255,255,255,0.1);
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
    }
    h2 {
      margin-top: 0;
      text-align: center;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border-radius: 8px;
      border: none;
      outline: none;
      font-size: 14px;
    }
    button {
      background: #00c6ff;
      color: #000;
      font-weight: bold;
      cursor: pointer;
    }
    button:hover {
      background: #00a2d4;
    }
    .chat-box {
      height: 250px;
      overflow-y: auto;
      background: rgba(0,0,0,0.3);
      padding: 10px;
      border-radius: 8px;
      margin-top: 10px;
    }
    .message {
      margin-bottom: 8px;
      padding: 6px 8px;
      background: rgba(255,255,255,0.15);
      border-radius: 6px;
      font-size: 13px;
    }
    footer {
      text-align: center;
      padding: 10px;
      font-size: 12px;
      opacity: 0.8;
    }
    @media(max-width: 768px) {
      .container {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <header>
    EmadForShare  – File Sharing & Live Chat
  </header>

  <div class="container">
    <!-- File Sharing -->
    <div class="card">
      <h2>📁 File Sharing</h2>
      <input type="file" id="fileInput" />
      <button onclick="uploadFile()">Upload File</button>
      <p id="fileStatus"></p>
      <p><small>(Here you can share your files and text secuerly so you can remember it)</small></p>
    </div>

    <!-- Chat -->
    <div class="card">
      <h2>💬 Live Text Chat</h2>
      <input type="text" id="username" placeholder="Your name" />
      <div class="chat-box" id="chatBox"></div>
      <input type="text" id="message" placeholder="Type a message..." />
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <footer>
    Made for Project Purpose | AirForShare Style Website
  </footer>

  <script>
    // -------- FILE UPLOAD (DEMO) --------
    function uploadFile() {
      const file = document.getElementById('fileInput').files[0];
      const status = document.getElementById('fileStatus');

      if (!file) {
        status.innerText = 'Please select a file first.';
        return;
      }

      status.innerText = `File \"${file.name}\" ready to share (backend required).`;
    }

    // -------- CHAT (LOCAL DEMO) --------
    const chatBox = document.getElementById('chatBox');

    function sendMessage() {
      const user = document.getElementById('username').value || 'Guest';
      const msg = document.getElementById('message').value;

      if (msg.trim() === '') return;

      const div = document.createElement('div');
      div.className = 'message';
      div.innerText = user + ': ' + msg;
      chatBox.appendChild(div);
      chatBox.scrollTop = chatBox.scrollHeight;

      document.getElementById('message').value = '';
    }
  </script>
</body>
</html>
