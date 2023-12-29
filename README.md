# knx-prettyView
Docker Compose file for the easy to use KNX pretty view visualization.

[!NOTE]
!! In development


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

![The backend topology](https://i.ibb.co/0ZjVGJ0/KNX-pretty-view-server-topology.png)

## KNX Pretty View app
The web frontend is developed with the [angular.io](https://angular.io/) framework.

At the time it provides the following section:

* **Playground** *(The playground is for the visualisation. You can have multiple playground at the same time)*
* **Datapoint Manager** *(Automatically retrieves recognized data points from the backend and show them in a list view)*
* **Datapoint Trend** *(Display historical data in a multi-axis line chart)*
* **Studio** **Section: SVG-Editor**(without demo data), **Template studio**(inactive), **image studio**(for background images)
* **User Management** *(**Profile**(current user), **User List**)*

### Quick Overview
![KNX-Pretty-View example view in edit mode](https://i.ibb.co/vPyFtwY/KNX-Visu.jpg)

## First start
Download the **docker-compose.yml** and save in into a directory.
Run the command in the same foulder where the **docker-compose.yml** file is stored: 
**docker compose up** 

If all three containers running you can access the **KNX Pretty View** over the url:localhost and port:4000 [http://localhost:4000](http://localhost:4000)
> **Username**: administrator **Password**: passwort

If you run the **KNX Pretty View** the first time, the **docker-compose.yml** provides two volumes.
* **KNX-PrettyView-DB** *(The database volume for backups. Direct access to the database files)*
* **KNX-PrettyView-Server** *(The server volume for the environment file and certification files)*

Later more ... :-)


## old german videos from 2021
[First look and feel **KNX Pretty View**](https://www.youtube.com/watch?v=EQ3pKWaOTY0&list=PLkmww0sGtMHCGLVOXR2k6Qp7p6WZXpO32)


## Update V0.0.4
* Value tendency support for the label value (now you can display a tendency for value change with and without difference value)
 ![KNX-Pretty-View tendency](https://i.ibb.co/9T2nNX4/KNx-View-tendency.jpg)
