
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
