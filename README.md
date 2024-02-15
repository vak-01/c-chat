### Welcome to ENet UDP networking library client-server project!

This project consists of two main components: the client and the server, implemented in C language using the ENet library. Below you'll find a detailed overview of both components, including technical details and usage instructions.

### Server

The server component (`server.c`) initializes an ENet host to handle incoming connections from clients. Here are some important details about the server:

- **Address Configuration**: The server binds to any available IP address (`ENET_HOST_ANY`) and listens on port `7777`.
  
- **Maximum Clients**: It supports up to `32` concurrent clients (`MAX_CLIENTS`).

- **Event Handling**: The server waits for events such as connection, data receive, and disconnection. Upon receiving events, it processes them accordingly.

- **Connection Handling**: When a client connects, the server logs the client's address and stores relevant information about the client.

- **Data Reception**: Upon receiving data from a client, the server logs the packet details and cleans up the packet.

- **Disconnection Handling**: The server handles client disconnections gracefully, logging the event and resetting the client's information.

### Client

The client component (`client.c`) establishes a connection to the server and communicates with it. Here are some key points about the client:

- **Initialization**: The client initializes the ENet library and creates a host for communication.

- **Connection**: It connects to the server at `127.0.0.1:7777`, allocating two channels for communication.

- **Connection Status**: The client waits for up to `5` seconds to establish a connection with the server.

- **Data Reception**: It waits for events, including receiving data from the server.

- **Disconnection**: The client initiates disconnection after receiving data, allowing `3` seconds for the disconnection to succeed.

- **Graceful Disconnection**: If disconnection succeeds, it logs the event; otherwise, it resets the connection.


### Additional Notes

- Ensure that you have the ENet library installed or linked properly while compiling.
