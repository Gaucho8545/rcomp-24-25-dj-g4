RCOMP 2024-2025 Project - Sprint 2 planning
===========================================
### Sprint master: 1231492 ###


| Task ID | Task description                                                                                                                                                                                       | Task's assignee |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
| 2.1    | Development of a layer two and layer three Packet Tracer simulation for building 1, encompassing the campus backbone. Integration of every member’s Packet Tracer simulation into a single simulation. | 1231492         |
| 2.2    | Development of a layer two and layer three Packet Tracer simulation for building 2, encompassing the campus backbone.                                                                                  | (Num de quem faz o B2)        |
| 2.3    | Development of a layer two and layer three Packet Tracer simulation for building 3, encompassing the campus backbone.                                                                                  | (Num de quem faz o B3)         |


# 2. Technical decisions and coordination
In this section, all technical decisions taken in the planning meeting should be mentioned. 		
Most importantly, all technical decisions impacting on the subtasks implementation must be settled on this meeting and specified here.

## Packet Tracer Version
We used the 8.2.2.0400 version

## Device Naming
The naming of the devices has the following pattern: the names always start with "B" and the number of the building,
followed by "_". a short for the type of device (ex: LP for laptop), and the number of the count of the type of the device used within the building, starting from 0.
For switches, there is also a specification for the type of switch it is (ex: CP for consolidation point), and in case it´s the horizontal-cross-connect, it also has the floor in which he is on in the name.



## VLAN's Database
| VLAN ID | VLAN Name | VLAN Description                                                 |
|---------|-----------|------------------------------------------------------------------|
| 406     | Backbone  | Backbone's VLAN                                                  |
| 407     | Ground-1  | Management Building 1- Floor 0                                   |
| 408     | Floor-1   | Management Building 1- Floor 1                                   |
| 409     | Wi-fi-1   | Management Building 1- Wifi Network                              |
| 410     | DMZ-1     | Management Building 1- serves, administration workstations, etc  |
| 411     | VoIP-1    | Management Building 1- IP-phones                                 |
| 412     | Ground-2  | Management Building 2 - Floor 0                                  |
| 413     | Floor-2   | Management Building 2 - Floor 1                                  |
| 414     | Wi-fi-2   | Management Building 2 - Wifi Network                             |
| 415     | DMZ-2     | Management Building 2 - serves, administration workstations, etc |
| 416     | VoIP-2    | Management Building 2 - IP-phones                                |
| 417     | Floor-3   | Management Building 3 - Floor 1                                  |
| 418     | Wi-fi-3   | Management Building 3 - Wifi Network                             |
| 419     | VoIP-3    | Management Building 3 - IP-phones                                |
| 420     | DMZ-3     | Management Building 3 - serves, administration workstations, etc |
| 421     | Ground-3  | Management Building 3 - Floor 0                                  |


## VTP domain
The VTP domain name we decided to adopt was "r2425djg4"

## IPV4 Addresses

### Global network: 10.25.32.0 /20
### Networks:
- Backbone  : 10.25.32.0 /24
- Building 1: 10.25.33.0 /23
- Building 2: 10.25.323.0 /22
- Building 3: 10.25.36.0 /22


### Backbone 
|   VLAN   | VLAN ID | Nodes | Mask | 
|:--------:|:-------:|:-----:|:----:|
| Backbone |   406   |  220  |  24  |  

### Building 1 
| VLAN    | VLAN ID | Nodes | Mask | 
|:-------------|:-------:|:-----:|:-----|
| Ground Floor |   407   |  40   | 26   |
| Floor One    |   408   |  45   | 26   |
| Wi-fi        |   409   |  95   | 25   |
| DMZ          |   410   |  110  | 25   |
| VoIP         |   411   |  70   | 25   |

### Building 2 
| VLAN    | VLAN ID | Nodes | Mask | 
|:-------------|:-------:|:-----:|:-----|
| Ground Floor |   412   |  100  | 25   |
| Floor One    |   413   |  110  | 25   |
| Wireless     |   414   |  200  | 24   |
| DMZ          |   415   |  60   | 26   |
| VoIP         |   416   |  120  | 25   |

### Building 3 
| VLAN         | VLAN ID | Nodes | Mask | 
|:-------------|:-------:|:-----:|:-----|
| Floor One    |   417   |  135  | 24   |
| Wi-Fi        |   418   |  220  | 24   |
| VoIP         |   419   |  170  | 24   |
| DMZ          |   420   |  50   | 26   |
| Ground Floor |   421   |  115  | 25   |







### Backbone 
| ID  | Network prefix |     IPV4     |   First IP    |    Last IP    |   Broadcast   |
|:---:|:--------------:|:------------:|:-------------:|:-------------:|:-------------:|
| 341 |      /24       |  10.25.32.0  | 10.25.32.1    | 10.25.32.254 | 10.25.32.255 |


### Building 1 
| ID  | Network prefix |        IPV4        |   First IP   |   Last IP    |  Broadcast   |
|:---:|:--------------:|:------------------:|:------------:|:------------:|:------------:|
| ISP |      /30       |  	87.5.128.46 | 	87.5.128.45  |  87.5.128.46  |  87.5.128.47  |
| 411 |      /25       |     10.25.32.0     |  10.25.32.1  | 10.25.32.126 | 10.25.32.127 |
| 410 |      /25       |    10.25.32.128    | 10.25.32.129 | 10.25.32.254 | 10.25.32.255 |
| 409 |      /25       |     10.25.33.0     |  10.25.33.1  | 10.25.33.126 | 10.25.33.127 |
| 408 |      /26       |    10.25.33.128    | 10.25.33.129 | 10.25.33.190 | 10.25.33.191 |
| 407 |      /26       |    10.25.33.192    | 10.25.33.193 | 10.25.33.254 | 10.25.33.255 |


### Building 2 (Alterar)
| ID  | Network prefix |     IPV4      |   First IP    |    Last IP    |   Broadcast   |
|:---:|:--------------:|:-------------:|:-------------:|:-------------:|:-------------:|
| 347 |      /25       |  172.21.26.0  |  172.21.26.1  | 172.21.26.126 | 172.21.26.127 |
| 348 |      /25       |  172.21.25.0  |  172.21.25.1  | 172.21.25.126 | 172.21.25.127 |
| 349 |      /24       |  172.21.24.0  |  172.21.24.1  | 172.21.24.254 | 172.21.24.255 |
| 350 |      /26       | 172.21.26.128 | 172.21.26.129 | 172.21.26.190 | 172.21.26.191 |
| 351 |      /25       | 172.21.25.128 | 172.21.25.129 | 172.21.25.254 | 172.21.25.255 |

### Building 3 (Alterar)
| ID  | Network prefix |     IPV4      |   First IP    |    Last IP    |   Broadcast   |
|:---:|:--------------:|:-------------:|:-------------:|:-------------:|:-------------:|
| 353 |      /24       |  172.21.20.0  |  172.21.20.1  | 172.21.20.254 | 172.21.20.255 |
| 354 |      /24       |  172.21.21.0  |  172.21.21.1  | 172.21.21.254 | 172.21.21.255 |
| 352 |      /24       |  172.21.22.0  |  172.21.22.1  | 172.21.22.254 | 172.21.28.255 |
| 356 |      /25       |  172.21.23.0  |  172.21.23.1  | 172.21.23.126 | 172.21.23.127 |
| 355 |      /26       | 172.21.23.128 | 172.21.23.129 | 172.21.23.190 | 172.21.23.191 |




### Every member of the team should deliver a packet tracer simulation of their buidling.

### 1231492

| Task ID | Task description                                                                  |
|---------|-----------------------------------------------------------------------------------|
| 2.1.1   | Place devices - PCs, Laptops, Servers, IP Phones, Switches, Routers, Access Point |
| 2.1.2   | Give name to all devices using the name convention                                |
| 2.1.3   | Configure the VTP domain on the main switch                                       |
| 2.1.4   | Add all VLANs to the main switch                                                  |
| 2.1.5   | Make all the connections between devices                                          |
| 2.1.6   | Change ports to trunk mode                                                        |
| 2.1.7   | Change the mode of all the others swtiches to client                              |
| 2.1.8   | Attribute the corresponding VLANs                                                 |
| 2.1.9   | Configure IPs on PCs and Laptops                                                  |
| 2.1.10  | Create subInterfaces on the IC_Router                                             |
| 2.1.11  | Add the MC_Router                                                                 |
| 2.1.12  | Add every possibility on the static table on the MC_Router                        |
| 2.1.13  | Add Modern, PT Cloud and ISP Router                                               |
| 2.1.14  | Make the simulation for the backbone                                              |
| 2.1.15  | Document and justify the entire process                                           |


###   (Num de quem faz o B2)   (Alterar)

| Task ID | Task description                                                                  |
|---------|-----------------------------------------------------------------------------------|
| 2.2.1   | Place devices - PCs, Laptops, Servers, IP Phones, Switches, Routers, Access Point |
| 2.2.2   | Give name to all devices using the name convention                                |
| 2.2.3   | Configure the VTP domain on the main switch                                       |
| 2.2.4   | Add all VLANs to the main switch                                                  |
| 2.2.5   | Make all the connections between devices                                          |
| 2.2.6   | Change ports to trunk mode                                                        |
| 2.2.7   | Change the mode of all the others switches to client                              |
| 2.2.8   | Attribute the corresponding VLANs                                                 |
| 2.2.9   | Configure IPs on PCs and Laptops                                                  |
| 2.2.10  | Create subInterfaces on the IC_Router                                             |
| 2.2.11  | Document and justify the entire process                                           |


###  (Num de quem faz o B3) (Alterar)

| Task ID | Task description                                                                  |
|---------|-----------------------------------------------------------------------------------|
| 2.3.1   | Place devices - PCs, Laptops, Servers, IP Phones, Switches, Routers, Access Point |
| 2.3.2   | Give name to all devices using the name convention                                |
| 2.3.3   | Configure the VTP domain on the main switch                                       |
| 2.3.4   | Add all VLANs to the main switch                                                  |
| 2.3.5   | Make all the connections between devices                                          |
| 2.3.6   | Change ports to trunk mode                                                        |
| 2.3.7   | Change the mode of all the others switches to client                              |
| 2.3.8   | Attribute the corresponding VLANs                                                 |
| 2.3.9   | Configure IPs on PCs and Laptops                                                  |
| 2.3.10  | Create subInterfaces on the IC_Router                                             |
| 2.3.11  | Document and justify the entire process                                           |




