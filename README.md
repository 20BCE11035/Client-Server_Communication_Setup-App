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

## `3. Output`

The following output will be produced:

- When a thread attempts to send a message: `(SEND) [Thread-Name]: { sender:[client-name] , recipient:[client-name]}`.
- When a thread successfully sends a message: `(SEND) [Thread-Name]: SUCCESSFUL`.
- When a thread reads a new message: `(RECEIVE) [Thread-Name]: { recipient:[client-name], sender:[client-name] }`.

## `4. Notes`

You will have to get creative with handling threads, queues, and locks. Each queue should have their own lock when accessed. Any locks used in the program will be written from scratch, i.e., no using Java's pre-built locks. Some of Java's pre-built data structures might be used. Any locks used will be fair.

## `5. Concepts`

The following concepts will be tested in this project:

- Consensus
- Semaphores
- TASLock
- TTASLock
- Exponential Backoff
- ALock
- CLH Lock
- Composite Lock
- Fine grain synchronisation
- OptimisticList synchronisation
