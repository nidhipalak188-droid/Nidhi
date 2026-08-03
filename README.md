<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My AI Assistant</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: Arial, sans-serif; }
    body { background-color: #121212; color: #fff; display: flex; flex-direction: column; height: 100vh; }
    header { padding: 15px; background: #1e1e1e; text-align: center; font-size: 1.2rem; font-weight: bold; border-bottom: 1px solid #333; }
    #chat-box { flex: 1; padding: 15px; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; }
    .message { max-width: 80%; padding: 12px 16px; border-radius: 12px; font-size: 0.95rem; line-height: 1.4; }
    .user { background-color: #007bff; align-self: flex-end; }
    .ai { background-color: #2a2a2a; align-self: flex-start; }
    #input-container { padding: 12px; background: #1e1e1e; display: flex; gap: 8px; border-top: 1px solid #333; }
    input { flex: 1; padding: 12px; border-radius: 8px; border: 1px solid #444; background: #2a2a2a; color: white; outline: none; }
    button { padding: 12px 18px; border-radius: 8px; border: none; background-color: #007bff; color: white; font-weight: bold; cursor: pointer; }
    button:hover { background-color: #0056b3; }
  </style>
</head>
<body>

  <header>🤖 My Personal AI Assistant</header>

  <div id="chat-box">
    <div class="message ai">Hello! I am your AI assistant. How can I help you today?</div>
  </div>

  <div id="input-container">
    <input type="text" id="user-input" placeholder="Type your message here..." />
    <button onclick="sendMessage()">Send</button>
  </div>

  <script>
    function sendMessage() {
      const inputField = document.getElementById('user-input');
      const chatBox = document.getElementById('chat-box');
      const messageText = inputField.value.trim();

      if (messageText === '') return;

      // Add User Message
      const userMessage = document.createElement('div');
      userMessage.className = 'message user';
      userMessage.textContent = messageText;
      chatBox.appendChild(userMessage);

      inputField.value = '';
      chatBox.scrollTop = chatBox.scrollHeight;

      // Simulated AI response (Replace with real API logic if desired)
      setTimeout(() => {
        const aiMessage = document.createElement('div');
        aiMessage.className = 'message ai';
        aiMessage.textContent = "I received your message: '" + messageText + "'. I am ready to help!";
        chatBox.appendChild(aiMessage);
        chatBox.scrollTop = chatBox.scrollHeight;
      }, 600);
    }
  </script>

</body>
</html>

