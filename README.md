# Client-Server_Communication_Setup-App
# Project: Client-Server Chat Application Simulation 
This project aims to test all the concepts learned so far regarding mutual exclusion and locking via practical implementation. The task is to simulate a chat application using a client-server communication setup without the use of sockets, but with multi-threading.

## `1. Implementation`

The client-server communication allows multiple clients to communicate with each other by sending a message destined for another client via a central server. The server knows all the clients in the network. Each client communication will be handled by two threads, a reader and a writer.

- **Reader**: Checks for any new message on the server for the client and logs the message in the client's chat.
- **Writer**: Sends new messages, destined for a specific client, to the server and logs the message in the client's chat.

At least four client objects will be created and initialized with at least ten random messages to send to a randomly selected client.

The server will be represented by a data structure holding messages for clients. Each thread has a fixed location on the server where it receives new messages. The server does not keep chat history; a new message for a specific client overrides the old one.

## `2. Mutual Exclusion`

Mutual exclusion will be enforced at the following key points:

- **Client Chat**: The reader and writer shall log messages using mutual exclusion.
- **Server**: Mutual exclusion shall be enforced to manage writers writing to the same client.
