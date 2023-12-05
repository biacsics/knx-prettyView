# knx-prettyView
Docker Compose file for the easy to use KNX pretty view visualization.

## how to use it
To run the **KNX Pretty View** you need three containers.
* [biacsics/**knx-pretty-view-server**](https://hub.docker.com/r/biacsics/knx-pretty-view-server) *(The backend and communication to the **KNX-bus**)*
* [biacsics/**knx-pretty-view-app**](https://hub.docker.com/r/biacsics/knx-pretty-view-app) *(The web frontend)*
* mariadb *(The database to hold configuration and historical **KNX-bus data** )*
 
## KNX Pretty View server
The server is a node backend. It was developed in typescript with express and socket.io.
It consists of the following modules:
* KNX-Server *(The KNX-module for the KNX-communication. Read and write access to the **KNX-Bus**)*
* DataPointManager *(Manage the data points and write them into the database. tracked values)*
* DataManager *(Gets the data from the KNX module and saves the data for charts into the database)*
* REST & Socket Provider *(Communication endpoint for the web frontend)*
* 
![The backend topology](https://i.ibb.co/0ZjVGJ0/KNX-pretty-view-server-topology.png)

## KNX Pretty View web frontend
The web frontend is developed with Angular.
### Example view:
![KNX-Pretty-View example view](https://i.ibb.co/vZ9NfMZ/KNX-Visu-1.jpg)

### Example view in edit mode:
![KNX-Pretty-View example view in edit mode](https://i.ibb.co/w6CMG9D/KNX-Visu-2.jpg)



