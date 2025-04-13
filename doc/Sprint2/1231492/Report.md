# Building 1 Network : 10.25.32.0 /23

## Equipmenent Table

| Hardware Deployment        | Packet Tracer   | Nomenclature |
|----------------------------|-----------------|--------------|
| Intermediate Cross-connect | Switch PT-Empty | B1_S0_IC     |
| Horizontal Cross-connect   | Switch PT-Empty | B1_S1_HC     |
| Horizontal Cross-connect   | Switch PT-Empty | B1_S3_HC     |
| Main Cross-connect         | Switch PT-Empty | B1_S2_MC     |
| Consolidation Point        | Switch PT-Empty | B1_S4_CP0    |
| Consolidation Point        | Switch PT-Empty | B1_S5_CP1    |
| Consolidation Point        | Switch PT-Empty | B1_S6_CP2    |
| Consolidation Point        | Switch PT-Empty | B1_S7_CP3    |
| Access Point               | Access Point PT | B1_AP        |
| Router                     | 2811            | B1_RT0       |
| ISP Router                 | 2811            | B1_ISP       |
| PC                         | PC_PT           | B1_PC0       |
| PC                         | PC_PT           | B1_PC1       |
| PC                         | PC_PT           | B1_PC2       |
| PC                         | PC_PT           | B1_PC3       |
| PC                         | PC_PT           | B1_PC4       |
| PC                         | PC_PT           | B1_PC5       |
| PC                         | PC_PT           | B1_PC6       |
| PC                         | PC_PT           | B1_PC7       |
| PC                         | PC_PT           | B1_PC8       |
| Laptop                     | Laptop_PT       | B1_LP0       |
| Laptop                     | Laptop_PT       | B1_LP1       |
| Server                     | Server_PT       | B1_SEV0      |
| Phone                      | 7960            | B1_PH0       |

___
## VLAN Details ##

| VLAN Name    | VLAN ID | Nodes | Mask | 
|:-------------|:-------:|:-----:|:-----|
| Ground Floor |   407   |  40   | 25   |
| Floor One    |   408   |  45   | 25   |
| Wireless     |   409   |  95   | 25   |
| DMZ          |   410   |  110  | 26   |
| VoIP         |   411   |  70   | 26   |




| ID  | Network prefix |     IPV4     |   First IP   |   Last IP    |  Broadcast   |
|:---:|:--------------:|:------------:|:------------:|:------------:|:------------:|
| 411 |      /25       |  10.25.32.0  |  10.25.32.1  | 10.25.32.126 | 10.25.32.127 |
| 410 |      /25       | 10.25.32.128 | 10.25.32.129 | 10.25.32.254 | 10.25.32.255 |
| 409 |      /25       |  10.25.33.0  |  10.25.33.1  | 10.25.33.126 | 10.25.33.127 |
| 408 |      /26       | 10.25.33.128 | 10.25.33.129 | 10.25.33.190 | 10.25.33.191 |
| 407 |      /26       | 10.25.33.192 | 10.25.33.193 | 10.25.33.254 | 10.25.33.255 |





___

## Detailed Explanation for the creation of Subnets:

**1 - The largest number of nodes:**  The first step is to identify the network that requires the largest number of hosts. As you can see in the table provided earlier our starting point will be the vlan number **410** with the name **DMZ (110 nodes).**

**2 - Selection of the appropriate subnet mask:** Once the network with the largest number of hosts is identified, the next step is to select a subnet mask that provides a sufficient number of IP addresses to accommodate all devices in that network segment while minimizing IP address waste. The logic is : The subnet mask is typically chosen to be close to, but greater than, the number of nodes required in each subnet. So for example, for VLAN number **410 ** the chosen mask was **/25** because it allows for network address size of 128.


**3 - Identification of available address ranges:** Once the subnet mask has been applied, it becomes possible to identify the available IP address ranges for assignment to devices in each subnet. This involves determining the first and last available IP addresses in each subnet, with one address reserved for the network address and another for the broadcast address.

- *Network Address:* This is the first address in the range and is used to identify the network itself. It is obtained by setting all host bits to zero within the subnet. For example, if the network address is 10.25.321.0, it signifies the beginning of the subnet.

- *Usable Addresses:* With a /25 subnet mask, there are 7 bits available for host addresses (32 - 25 = 7). This provides a total of 2^7 - 2 = 126 usable addresses for hosts. The subtraction of 2 is because the first and last addresses in the range are reserved for the network address and the broadcast address, respectively.

- *First Usable Address:* This is the second address in the range, after the network address, and is typically assigned to the first host device. In this case, it would be 10.25.321.1.

- *Last Usable Address:* This is the second-to-last address in the range and is typically assigned to the last host device. In this case, it would be 10.25.321.126.

- *Broadcast Address:* This is the last address in the range and is used to send data to all hosts within the subnet. It is obtained by setting all host bits to one within the subnet. In this case, it would be 10.25.321.127.

**4 - The process is repeated for all networks in descending order of nodes obtaining something like this table:**  

| VLAN ID |      SubNet      |  
|:-------:|:----------------:|
|   411   | 10.25.321.1/25   | 
|   410   | 10.25.321.129/25 | 
|   409   |  10.25.322.1/25  | 
|   408   | 10.25.322.129/26 | 
|   407   | 10.25.322.193/26 | 
___