# aos_proj
This repo contains files of Distributed File system project.

There are few files:
1. Master Server
2. Chunk servers
3. meta-data.json
4. Client1
5. client2

First the Master server is started using cmd :  python3 master_server.py

Then chunk servers are started using cmd : python3 chunk_server1.py ... (same way server 2 and server 3)

Then client is connected to master server (client1.py)

The master server will store all the information of client ip, port in the meta data on the master server.

out of the chunk servers, one chunk server will be the primary server.

The information about the primary server is returned to client and the client is connected to that primary server.

Then the client can request for the file operations.

The file is granted to client for a time out of 120 seconds on lease.

During this 120 seconds other clients will receive a message that the file is not available! you are in the queue for the same file.

In case the primary server fails, new server is assigned as primary by the master server.

This project is implemented in python using TCP/IP socket programming.
