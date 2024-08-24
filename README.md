# Networking-InterChat-Project

## Overview

The Networking Chat Application is a basic implementation of a client-server chat system using sockets and multithreading in C. This application demonstrates fundamental concepts in network programming, including client-server communication, handling multiple clients, and message routing.

### Server

The server program (server.c) serves as the central hub for communication between clients. It listens for incoming client connections on a specified port and manages these connections concurrently. Key responsibilities of the server include:

- *Listening for Connections*: The server waits for incoming connection requests from clients.
- *Accepting Connections*: Once a connection request is received, the server accepts it and creates a new thread to handle communication with the connected client.
- *Routing Messages*: The server facilitates message passing between clients by receiving messages from one client and forwarding them to the intended recipient.
- *Client Management*: The server maintains a list of connected clients and their corresponding socket descriptors. It can provide a list of all connected clients when requested.

### Client

The client program (client.c) represents the end-user interface for interacting with the chat application. Each client can connect to the server, send commands, and receive messages. Key features of the client include:

- *Connecting to the Server*: The client establishes a connection to the server using a specified IP address and port.
- *Sending Commands*: The client can send various commands to the server. Supported commands include:
  - *LIST*: Requests a list of all connected clients along with their socket IDs.
  - *SEND*: Sends a message to a specific client. The user is prompted to enter the recipient's client index and the message content.
- *Receiving Messages*: The client continuously listens for incoming messages from the server and displays them in real-time.

### Use Cases

This chat application can be used as a learning tool to understand the basics of network communication and concurrent programming. It can also serve as a foundation for more complex chat applications with additional features such as private messaging, group chats, and persistent user authentication.

### Design Considerations

- *Multithreading*: The server uses multithreading to handle multiple client connections simultaneously, ensuring that the server remains responsive.
- *Synchronization*: Proper synchronization is implemented using mutexes to manage access to shared resources, such as the list of connected clients.
- *Error Handling*: Basic error handling is included to manage common issues such as connection failures and invalid commands.

By exploring this project, you will gain practical experience with socket programming, thread management, and network communication principles.



### How to Compile 
gcc -o server server.c -lpthread
gcc -o client client.c -lpthread

./server
./client


### Example : 
Server started listening on port 8080...
Client 1 connected.
Client 2 connected.

Enter command: LIST
Received: Client 1 is at socket 3.
Client 2 is at socket 4.

Enter command: SEND
Enter client index to send message to: 2
Enter message: Hello, Client 2!
