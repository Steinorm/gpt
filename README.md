<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ChatGPT Style Chatbot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }

    .chat-container {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      max-width: 600px;
      margin: auto;
      background: white;
      border: 1px solid #ccc;
      border-radius: 8px;
      overflow: hidden;
    }

    .chat-box {
      flex: 1;
      padding: 16px;
      overflow-y: auto;
    }

    .message {
      margin: 10px 0;
      padding: 10px;
      border-radius: 6px;
      max-width: 80%;
    }

    .user {
      background-color: #d1e7dd;
      align-self: flex-end;
    }

    .bot {
      background-color: #f8d7da;
      align-self: flex-start;
    }

    .input-box {
      display: flex;
      border-top: 1px solid #ccc;
    }

    .input-box input {
      flex: 1;
      padding: 12px;
      border: none;
      font-size: 16px;
    }

    .input-box button {
      padding: 12px;
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
    }

    .input-box button:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>
  <div class="chat-container">
    <div class="chat-box" id="chatBox">
      <!-- Messages will appear here -->
    </div>
    <div class="input-box">
      <input type="text" id="userInput" placeholder="Type your message..." />
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <script>
    function sendMessage() {
      const input = document.getElementById('userInput');
      const chatBox = document.getElementById('chatBox');
      const message = input.value.trim();

      if (message === '') return;

      // Add user message
      const userMsg = document.createElement('div');
      userMsg.className = 'message user';
      userMsg.textContent = message;
      chatBox.appendChild(userMsg);

      // Dummy bot response
      const botMsg = document.createElement('div');
      botMsg.className = 'message bot';
      botMsg.textContent = "Bot: " + message;
      chatBox.appendChild(botMsg);

      // Clear input and scroll down
      input.value = '';
      chatBox.scrollTop = chatBox.scrollHeight;
    }
  </script>
</body>
</html>

