## Purpose
The purpose of this project is to implement a **Remote Procedure Call (RPC) protocol**, a communication protocol widely used to enable a program to request a service from a program located on another computer in a network. RPC is a key technique in distributed systems and networked applications, as it allows processes to communicate and execute functions as if they were running locally, making networked applications more seamless and efficient.

This project aims to:
- **Demonstrate basic RPC functionality** by establishing a client-server model where the client can call procedures (functions) on the server remotely, with the necessary arguments and data being transmitted across a network.
- **Implement core networking components** like sockets and data serialization, which are essential for sending complex data structures and requests over a network reliably.
- **Handle common RPC use cases** by developing a robust protocol that includes error handling, function mapping, and response processing, enabling functions to be dynamically located and executed on the server.
- **Introduce students to distributed computing concepts** by allowing them to create, test, and debug applications that work across a network, a foundational skill in network programming and systems design.

This project is an essential exercise in network programming, socket management, and distributed systems, allowing students to understand the fundamentals of remote communications in a controlled environment.


## File Description
| File    | Description |
| -------- | ------- |
| rpc.c rpc.h | main rpc logic    |
| send_recv_rpc_data.c send_recv_rpc_data.h| send/receive rpc_data (refer to rpc.h) structure through the socket     |
| dataStructure.c dataStructure.h   | data structure helpers    |
| protocol.txt| protocol description|
|client.c|a very simple rpc test client|
|server.c |a very simple rpc test server|
|server.a client.a | advanced testing framework artifacts, the name "server/client" clashed with server.c, client.c, but they are not relevant with each other

## Complie
(Notice: some complied artifacts in Makefile are for marking purpose)
### Main Artifacts
    make

### Very Simple Test client/server
    make
    make cs

### Advanced marking frameworks
    make
    make ci

### clean main
    make clean

### clean advanced marking frameworks executable
    make clean-ci
    
## Run Very Simple test client/server after compiling
Server Terminal Window

    ./server

Client Terminal Window

    ./client

server terminal window

    add2: arguments 127 and 127
    multi2: arguments 0 and 100
    multi2: arguments 1 and 100

client terminal window

    ERROR: Function add3 does not exist
    successfully found multi2 on server
    successfully found add2 on server
    Result of adding 127 and 127: 254
    Result of multipling 0 and 100: 0
    Result of multipling 1 and 100: 100

## Run advanced marking framework
`input: *.in`  
`sample output: *.out`

server terminal window

    ./ci-server < cases/1+1/server.in

client terminal window

    ./ci-client < cases/1+1/client.in

or check diff simultaneously

    ./ci-client < cases/1+1/client.in | diff - cases/1+1/client.out
