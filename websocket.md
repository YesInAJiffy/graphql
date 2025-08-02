
**WebSockets** are a communication protocol that provides **full-duplex**, **persistent** connections between a client (like a browser) and a server. Unlike HTTP, which is request-response based, WebSockets allow both sides to send and receive data **independently and continuously** over the same connection.

---

### 🔄 How WebSockets Work

1. **Handshake**:  
   The client initiates a WebSocket connection using an HTTP request with special headers (`Upgrade: websocket`).  
   The server responds with `101 Switching Protocols`, confirming the upgrade.

2. **Persistent Connection**:  
   Once established, the connection stays open, allowing real-time data exchange without repeated HTTP requests.

3. **Bidirectional Communication**:  
   Both client and server can send messages at any time — ideal for chat apps, live dashboards, games, etc.

---

### 🧠 Key Features

| Feature              | Description |
|----------------------|-------------|
| **Full-duplex**      | Both client and server can send/receive simultaneously. |
| **Low latency**      | No need to re-establish connections for each message. |
| **Efficient**        | Less overhead than HTTP polling or long-polling. |
| **Real-time**        | Perfect for live updates, notifications, and streaming. |

---

### 📦 Use Cases

- **Chat applications**
- **Live sports scores**
- **Stock market tickers**
- **Multiplayer games**
- **Collaborative tools (e.g., Google Docs)**



## Install dependencies
#### Install Node
https://nodejs.org/en/download
#### Install websocket package
npm install ws

## Client Side Code
``` Javascript
const WebSocket = require('ws');
const readline = require('readline');

// Connect to the WebSocket server
const socket = new WebSocket('ws://localhost:8080');

// Create a readline interface for user input
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});
let userName = '';

// Listen for messages from the server
socket.on('message', (message) => {
  console.log(`Message from server: ${message}`);
});

// Handle connection open
socket.on('open', () => {
  console.log('Connected to server');
  console.log('Please enter user name:')

  

  // Prompt user for input and send messages to the server
  rl.on('line', (input) => {
    if(!userName){
      console.log(`Welcome ${input}! You can start chatting now.`);
      userName = input;
      console.log('Type your message and press Enter to send:');
    }
    input = `${userName}: ${input}`;
    socket.send(input);
  });
});

// Handle connection closure
socket.on('close', () => {
  console.log('Disconnected from server');
  rl.close();
});

```
## Client Side Code - Running from Browser
``` Javascript
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = () => {
  console.log('✅ Connected to local server');
  socket.send('Hello from browser!');
};

socket.onmessage = event => {
  console.log('📨 Server says:', event.data);
};

socket.onclose = () => {
  console.log('❌ Disconnected');
};

socket.onerror = error => {
  console.error('⚠️ Error:', error);
};
```

## Server Side Code
``` JavaScript
const WebSocket = require('ws');

// Create a WebSocket server
const server = new WebSocket.Server({ port: 8080 });

server.on('connection', (socket) => {
  console.log('Client connected');

  // Listen for messages from the client
  socket.on('message', (message) => {
    console.log(`Received: ${message}`);
    // Echo the message back to the client
    socket.send(`Received ${message}`);
  });

  // Handle client disconnection
  socket.on('close', () => {
    console.log('Client disconnected');
  });
});

console.log('WebSocket server is running on ws://localhost:8080');

```
