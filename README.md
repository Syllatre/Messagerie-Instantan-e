# Chat Application with WebSocket and Spring Boot

This repository contains a simple chat application that uses WebSocket for real-time communication between clients and the server. The backend is built with Spring Boot, and the frontend uses SockJS and STOMP over WebSocket for message passing.

## Features

- Real-time bi-directional communication between server and clients using WebSocket.
- Simple chat functionalities to join/leave chat and send/receive messages.
- Colorful avatars for users.

## Backend

The backend is a Spring Boot application that configures a WebSocket endpoint and sets up a message broker for handling messages.

### Key Components

- `WebSocketConfig`: Configures WebSocket message broker endpoints and prefixes.
- `WebSocketEventListener`: Listens to WebSocket disconnect events and broadcasts leave messages.
- `ChatController`: Handles incoming WebSocket messages for adding users and sending chat messages.
- `ChatMessage`: Data model for the chat message containing content, sender, and message type.

### Message Types

- `CHAT`: A standard chat message.
- `JOIN`: A message indicating a user has joined the chat.
- `LEAVE`: A message indicating a user has left the chat.

## Frontend

The frontend is a simple HTML/CSS/JavaScript application that establishes a WebSocket connection and handles incoming and outgoing messages.

### Key Functions

- `connect`: Establishes the WebSocket connection and subscribes to the chat topic.
- `onConnected`: Sends a message to the server to add a new user.
- `onError`: Handles errors in establishing a WebSocket connection.
- `sendMessage`: Sends a new chat message to the server.
- `onMessageReceived`: Handles incoming messages and updates the chat UI.
- `getAvatarColor`: Assigns a color to the user's avatar based on their username.

## Getting Started

### Prerequisites

- JDK 1.8 or later
- Maven 3.2+

### Running the Application

1. Clone the repository:
2.  Navigate to the project directory:
3. Build the project with Maven:
4. Run the application:
5. 5. Open your browser and go to `http://localhost:8080`.

### Interacting with the Chat

1. Enter your username to join the chat.
2. Send a message to the public chatroom.
3. Your message should now be visible to all users connected to the chat.