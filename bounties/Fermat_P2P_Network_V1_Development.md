# Fermat P2P Network V1 Development Bounty

### Introduction
The main objective of this bounty is to create a decentralized P2P network between the Fermat Nodes. In this first approach we'll create the first version of a Network Node and the first version of the Client Node. The current implementation called Cloud Client and Cloud Server are going to be used as a reference to extract whatever is useful, and that technology is going to still be supported as an alternative communication method.

The Network Node will have all the features needed for the interaction with its peers.

### Glossary

* Fermat Network: Fermat peer-to-peer network.
* Network Node: Fermat Network decentralized server.
* Network Client: Fermat Network decentralized Client.
* Seed Server: Fermat First Network Node. It's the first reference for all the new nodes. There could be more than one seed server. The seed server's IP address and port are known by clients while compiling.
* Network Relationships:
  * Node-Node
  * Client-Node
  * Client-Client
* Network Node Catalog: Distributed catalog of nodes. It is used for the discovering and searching of Nodes. It will be managed by Nodes.
* Node Profile: Profile of each node, it'll contain the necessary information to communicate with it: IP, port, name, etc.
* Actor Catalog: Distributed catalog of Actors. Is used for the discovering and searching of  Actors. It will be managed by Nodes.
* Network Node Channel: Communication Channel between Nodes.
* Network Client Channel: Communication Channel between Node and Client & Vice-versa.
* Network Call Channel: Communication Channel between Client and Client.

### Scope
The **"Fermat Network"** will be the *"peer-to-peer"* network used by the Fermat system, and it'll be made up of two types of components, the nodes called **"Network Nodes"** and the clients caled **"Network Clients"** which interact with each other, these interactions could be **"Node to Node"**, **"Node to Client"** and **"Client to Client"**. 

The **"Network Nodes"** will be the components responsible to maintain the intercommunication between the *"peer-to-peer"* network, these will act as decentralized servers that provide specialized services to each of the clients as well as other nodes, it also has the responsibility of presenting and making each of these clients known on the network.

One of the main problems with *"peer to peer"* networks is the discovery of the nodes available on the network, for this a nodes distributed catalog will be implemented **"Network Node Catalog"** whose objective is to maintain the relationship and existence of each of the nodes available that make up the network, the basic information of each of the nodes will be stored, known as **"NodeProfile"**, that will have data such as: IP, ports, name, location etc.  The nodes will have the exclusive responsibility of managing and maintaining this catalog. **"Network Node"**, these will have the responsibility of filling, sharing and keeping this catalog updated.

an implementation of an actors catalog will also be featured **"Actor Catalog"** that will be used for searching and finding of each one of them on the "peer-to-peer" network, just like in the case of the **"Network Node Catalog"**  the nodes will have the exclusive responsibility of managing and maintaining this catalog **"Network Node"**.

It has been determined that every **"Network Node"** will be made up of two main communication channels known as **"Network Node Channel"** y **"Network Client Channel"**, each one specialized on the exchange of data between the components of the network depending of its type; meaning, they will have an exclusive communication channel in order to send information from  **"Network Node"** to **"Network Node"** , and another channel used to send information from **"Network Clients"** to **"Network Node"** and vice versa.

The client **"Network Client"** will run in each of the devices that will serve as clients of the peer-to-peer network, they are responsible of providing an interface or API of communication to the other components of the system such as **"Network Services"** and **"Actors"**. 

The clients will count on two exclusive communication channels called **"Network Client Channel"** and **"Network Call Channel"**, the first one used for the interaction with network nodes, and another one used to send data and information between network clients.


We have identified the following use cases and methods for each of these channels, that will be exposed as services for each of them:

### Fermat Network Nodes:
#### Network Node Channel:

1. AddNodeToCatalog   (NodeProfile)
2. UpdateNodeInCatalog   (NodeProfile)
3. GetCatalog    (Records, Offset)
4. GetCatalogTxs  (Records, Timestamp)
5. ReceiveNodeCatalogTransactions (NodeCatalogTxs)
6. ReceiveActorCatalogTransactions (ActorCatalogTxs)
#### Network Client Channel:

1. GetNearbyNodes (Location)
2. CheckIn(ClientProfile), 
3. CeckIn(NetworkServiceProfile) 
4. CheckIn(ActorProfile)
5. CheckOut(ClientProfile), 
6. CeckOut(NetworkServiceProfile) 
7. CheckOut(ActorProfile)
8. CheckedInProfileDiscoveryQuery  (DiscoveryQueryParams)
9. ActorProfileTraceDiscoveryQuery  (DiscoveryQueryParams)     
10. ChangeClientProfileHome (Profile, HomeNodeProfile)
11. NetworkServiceCall (FromNetworkService, ToNetworkService)   
12. ActorCall (FromActor, ToActor, FromNetworkService)

### Fermat Network Clients:
#### Network Client Channel:

1. GetNearbyNodes (Location)
2. RegisterProfile (Profile, ParentProfile)  
3. UnRegisterProfile (Profile)
4. RegisteredProfileDiscoveryQuery  (DiscoveryQueryParams)
5. ActorTraceDiscoveryQuery  (DiscoveryQueryParams)     
6. ChangeProfileHome (Profile, HomeNodeProfile)
7. NetworkServiceCall (FromNetworkService, ToNetworkService)   
8. ActorCall (FromActor, ToActor, FromNetworkService)
#### Network Call Channel:

1. ConnetToVpnChannel()
2. SendMessage()

### Tasks

Taking into account the responsibility that must be achieved by the **"Network Nodes"** for distributing and maintaining the actor and node catalogs we established a series of tasks, to be done by agent components:

1. Spread Node Catalog Tasks
2. Spread Actor Catalog Tasks

### Network Node Features

#### Task: Spread Node Catalog 
This is an agent that runs every 1 minute in the Network Node. When you start the agent the Network Node verifies in the "NODES_CATALOG_TRANSACTIONS_PENDING_FOR_PROPAGATION" table if new records exist, in case records do exist the Network Node searches in the Network Nodes catalog for 10 Network Nodes that have fewer late record notifications then it gets a Network Node from the list and tries to connect with the Network Node, if the connection is successful a block of transactions is sent, it receives a response from the other Network Node it verifies it if is a "late information notification" it then increases the value of the field "LATE_NOTIFICATION_COUNTER" for that Network Node it then updates the base record in the data base and closes the connection with that Network Node, the accountant of successful spreads increases, in case it wasn't able to connect it gets a Network Node again from the list and it tries to connect with it to send it the block of transactions; after going over the 10 Network Nodes that have fewer late record notifications the Network Nodes catalog validates if the accountant of  successful spreading is equal to 10 it then clears the transactions sent to the other Network Nodes in the "NODE_CATALOG_TRANSACTIONS_PENDING_FOR_PROPAGATION" table and the agent is put to sleep during the time configured, in case the accountant of successful spreads is different to 10 it then searches in the Network Nodes catalog for 10 that have fewer late record notifications and it repeats the whole transaction once more.

#### Task: Spread Actor Catalog 
This scheduled task is in charge of making the spread task between the nodos, the information stored in the actors catalog, begins verifying in the  "ACTOR_CATALOG_TRANSACTIONS_PENDING_FOR_PROPAGATION" table if records exist, when it finds such records the agent then connects with other "Network Nodes" and it will pass on the set of transactions in one block. Every time it passes on the block successfully to other "Network Nodes" the accountant will begin to deduct "successful spreads", once it confirms the accountant has reached the number zero (0) it will to proceed to clear all the records found stored in the "ACTOR_CATALOG_TRANSACTIONS_PENDING_FOR_PROPAGATION" table.

#### Database:

![network node data base](https://cloud.githubusercontent.com/assets/12099493/11034740/0d57f5ea-86c0-11e5-9bcb-b47911df4e26.png)

### Network Node Channel Features

#### Process: Receive Actor Catalog Transactions

This process begins when the Network Node receives a new block of transactions from another Network Node, it then deducts one from the pending spread accountant, it obtains a transaction from the block and it verifies if a record exists in the "ACTOR_CATALOG" table, if it is so, it then takes another transaction from the block and repeats the transaction, in case the record does not exist in the  "ACTOR_CATALOG" table it then applies the transaction in the "ACTOR_CATALOG" table, saves the transaction in the "ACTORS_CATALOG_TRANSACTIONS" table and verifies if the spread has reached the maximum number of nodes if the pending spread accountant is different to 0 it then saves the transactions in the "PENDING_CATALOG_TRANSACTIONS_FOR_PROPAGATION" table.

#### Process: Get Catalog
This process begins when the "Network Node" receives a new catalog request of "Network Node", it then searches and filters through the number of requested records in the "NODES_CATALOG" table and lastly it returns the catalog to the other requesting "Network Node".

#### Process: Get Catalog Transactions
This process begins when the "Network Node" receives a new catalog request of "Network Node" transactions, it then searches and filters through the number of requested records in the "CATALOG_TRANSACTIONS" table and lastly it returns the catalog to the other requesting "Network Node".

#### Process: Receive Node Catalog Transactions
In this process a "Network Node" receives a new block of transactions, it then takes a transaction from the block to process, for each received transaction it verifies if it exists in the "NODE_CATALOG" table, if a record exists then it increases the late notification accountant in case the record does not exist it then applies the transaction in the "NODE_CATALOG" table, then saves the transaction in the "CATALOG_TRANSACTIONS" table and lastly saves the transactions in the "NODES_CATALOG_TRANSACTIONS_PENDING_FOR_PROPAGATION" table and responds to the "Network Node" that sent the block, the number of reords already known.

#### Process: Client To Node Connection
This process begins when the "Network Node" receives a new connection request from a "Network Client" if the connection is successful it then adds to the "CLIENT_CONNECTION_HISTORY" data base a new record with the "Network Node" profile with a status of "SUCCESS" and then an exchange of public passwords is made, if the connection is not successful it then adds to the "CLIENT_CONNECTION_HISTORY" data base a new record with the Network Node profile with a status of "FAIL" and it sends a notification of failed connection.

#### Process: Get Nearby Nodes
This process begins when the "Network Node" receives a new list request of nearby "Network Nodes", it then estimates the distance of the Network Nodes recorded in the "NODE_CATALOG" table in relation to the geolocation of the Network Client it then organizes the estimated results from low to high, then it pulls out the closest first 50 nodes and lastly it returns the list to the Network Client.

### Network Client Features

#### Database: 
![client node data base](https://cloud.githubusercontent.com/assets/12099493/11034748/1972311a-86c0-11e5-9e4a-b698b36a0c5a.png)

## Other resources:

### Workflows:

https://prezi.com/ae3v-gqmxeuy/fermat-network/

### Live Meetings recorded:

https://plus.google.com/events/cm854k049ils0im37bunqf6j6pk
https://plus.google.com/events/ce2ot7dru6k4nn7grqnmt05ke4s
https://plus.google.com/events/caacvbclj1l3jkutpv4rqcc6mgk
https://plus.google.com/events/cqi7tt576hmg2clindlduqhjfjc
https://plus.google.com/events/cdmbbvvvah3gf6vqveaf67g8hs0

## Timeline

Based on current workload and available resources, the delivery date for this bounty will be **April 2016**.

## Evaluation

In order to be considered successful this bounty must pass the following tests:

* Management and distribution of Node Catalog:
  * Successful registration of Multiple Network Nodes to the Seed Server.
  * Proper updating of the Nodes Catalog when done.
  * Right spread of the Nodes Catalog (7).
* Successful registration of Actors.
* Successful registration of Network Clients.
* Successful registration of Network Services.
* Management and distribution of Actors Catalog:
  * Successful registration of Multiple Actors to the Seed Server. LUIS:  ???? que seria esto ???
  * Proper updating of the Actors Catalog when done.
  * Right spread of the Actors Catalog (7).
* Geolocation search (get nearby nodes).
* Network Calls between clients.
* Actor Calls between clients.
* Test migration of one network service to the new scheme (selected: ccp-actor-network-service-intra-actor).
  
*[Evaluation results to be completed after evaluation]*

## Limitations
* Call analysis not completed.
* Database and File System add-ons linux version creation in progress.
* Location Add-on linux version not created.
* 


LUIS: No veo el tema del HOME Node de los clientes, desde su eleccion, su aceptacion por parte de un nodo, la mudanza de un home node a otro, etc. Fijense si ademas de eso no le falta mas nada a este doc.

