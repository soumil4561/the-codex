using RPC, MOM, etc.
### Layered Protocols
A protocol is a set of rules and conventions that describe how information is to be exchanged between two entities.
- A layered protocol architecture provides a conceptual framework for dividing the complex task of exchanging information between remote hosts into simpler tasks.
- Each protocol layer has a narrowly defined responsibility.
- A protocol layer provides a standard interface to the next higher protocol layer.

#### Connection vs Connectionless
With connection-oriented protocols, before exchanging data the sender and receiver first explicitly establish a connection, and possibly negotiate the protocol they will use. When they are done, they must release (terminate) the connection. The telephone is a connection-oriented communication system. With connectionless protocols, no setup in advance is needed. The sender just transmits the first message when it is ready. Dropping a letter in a mailbox is an example of connectionless communication. With computers, both connection-oriented and connectionless communication are common.

![[Pasted image 20241008194730.png]]

### Socket Programming
A socket is a type of medium that provides a connection between two devices. With the help of a socket, different applications are attached to the local network with different ports. 
Socket Programming is a method to connect two nodes over a network to establish a means of communication between those two nodes. A node represents a computer or a physical device with an internet connection.
![[Pasted image 20241008195112.png]]

![[Pasted image 20241008195126.png]]

### Berkley Socket
Abstraction through which application may send or receive data
Provides access to Interprocess Communication services

Identified by: IP Address, type, port

Two types:
![[Pasted image 20241008195334.png]]

There are some procedures that we have to follow to establish client-server communication. These are as follows. 
1. Socket: With the help of a socket, we can create a new communication. 
2. Bind: With the help of this we can attach the local address with the socket. 
3. Listen: With this help; we can accept the connection. 
4. Accept: With this help; we can block the incoming connection until the request arrives. 
5. Connect: With this help; we can attempt to establish the connection. 
6. Send: With the help of this; we can send the data over the network. 
7. Receive: With this help; we can receive the data over the network. 
8. Close: With the help of this, we can release the connection from the network.

### RPC (remote procedure calls)
Remote Procedure Call (RPC) is a communication technology that is used by one program to make a request to another program for utilizing its service on a network without even knowing the  network’s details. A function call or a subroutine call are other terms for a procedure call.

Based on client server concept

An RPC, like a local procedure call, is based on the synchronous operation that requires the requesting application to be stopped until the remote process returns its results.

#### Working
1. **Argument Passing**: The client places the procedure's arguments in a specific location.
2. **Control Transfer**: The control is passed to the remote procedure (callee), where the execution environment is set up with copies of the arguments.
3. **Execution**: The server executes the procedure in its own environment.
4. **Result Return**: Once the procedure completes, the result is sent back to the client, restoring control to it.
5. **Communication**: Client and server communicate using a message-passing mechanism.
6. **Server Handling**: The server extracts parameters, executes the procedure, and sends the response.
7. **Asynchronous Option**: The client may continue working while waiting for the server's response.
8. **Threading**: Servers can create threads to handle multiple incoming requests.

#### Types of RPC


#### Adv and Disadv




Next on the list: [[Parallel Computing]]