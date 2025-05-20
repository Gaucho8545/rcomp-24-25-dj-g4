# Building 2 Network : 10.25.34.0 /22

## Equipmenent Table

| Hardware Deployment        | Packet Tracer  | Nomenclature |
|----------------------------|----------------|--------------|
| Intermediate Cross-connect | Switch-PT      | B2_S0_IC     |
| Horizontal Cross-connect   | Switch-PT      | B2_S1_HC     |
| Consolidation Point        | 8960-24TT      | B2_S2_CP0    |
| Consolidation Point        | 8960-24TT      | B2_S3_CP1    |
| Consolidation Point        | 8960-24TT      | B2_S4_CP2    |
| Horizontal Cross-connect   | Switch-PT      | B2_S5_HC     |
| Consolidation Point        | 8960-24TT      | B2_S6_CP3    |
| Consolidation Point        | 8960-24TT      | B2_S7_CP4    |
| Consolidation Point        | 8960-24TT      | B2_S8_CP5    |
| Access Point               | AccessPoint-PT | B2_AP0       |
| Access Point               | AccessPoint-PT | B2_AP1       |
| Router                     | 2811           | B2_RT0       |
| PC                         | PC_PT          | B2_PC0       |
| PC                         | PC_PT          | B2_PC1       |
| PC                         | PC_PT          | B2_PC2       |
| PC                         | PC_PT          | B2_PC3       |
| PC                         | PC_PT          | B2_PC4       |
| PC                         | PC_PT          | B2_PC5       |
| PC                         | PC_PT          | B2_PC8       |
| PC                         | PC_PT          | B2_PC9       |
| PC                         | PC_PT          | B2_PC10      |
| PC                         | PC_PT          | B2_PC11      |
| PC                         | PC_PT          | B2_PC12      |
| PC                         | PC_PT          | B2_PC13      |
| Laptop                     | Laptop_PT      | B2_LP0       |
| Laptop                     | Laptop_PT      | B2_LP1       |
| Server                     | Server_PT      | B2_SEV0      |
| Phone                      | 7960           | B2_PH0       |

___
## VLAN Details ##

| VLAN Name    | VLAN ID | Nodes | Mask | 
|:-------------|:-------:|:-----:|:-----|
| Floor One    |   412   |  110  | 25   |
| WiFi         |   413   |  200  | 24   |
| VoIP         |   414   |  120  | 25   |
| DMZ          |   415   |  60   | 26   |
| Ground Floor |   416   |  100  | 25   |




| ID  | Network Prefix |     IPV4     |   First IP   |   Last IP    |  Broadcast   |
|:---:|:--------------:|:------------:|:------------:|:------------:|:------------:|
| 412 |      /25       |  10.25.34.0  |  10.25.34.1  | 10.25.34.126 | 10.25.34.127 |
| 413 |      /24       | 10.25.34.128 | 10.25.34.129 | 10.25.35.126 | 10.25.35.127 |
| 414 |      /25       | 10.25.35.128 | 10.25.35.129 | 10.25.35.254 | 10.25.35.255 |
| 415 |      /26       |  10.25.36.0  |  10.25.36.1  | 10.25.36.62  | 10.25.36.63  |
| 416 |      /25       |  10.25.35.0  |  10.25.35.1  | 10.25.35.126 | 10.25.35.127 |




___

## Detailed Explanation for the creation of Subnets:

**1 - The largest number of nodes:** The first step is to identify the network that requires the largest number of hosts. As you can see in the table provided earlier, our starting point will be the VLAN number **413** with the name **WiFi (200 nodes).**

**2 - Selection of the appropriate subnet mask:** Once the network with the largest number of hosts is identified, the next step is to select a subnet mask that provides a sufficient number of IP addresses to accommodate all devices in that network segment while minimizing IP address waste. The logic is: The subnet mask is typically chosen to be close to, but greater than, the number of nodes required in each subnet. So, for example, for VLAN number **413** the chosen mask was **/24** because it allows for a network address size of 256 addresses.

**3 - Identification of available address ranges:** Once the subnet mask has been applied, it becomes possible to identify the available IP address ranges for assignment to devices in each subnet. This involves determining the first and last available IP addresses in each subnet, with one address reserved for the network address and another for the broadcast address.

- *Network Address:* This is the first address in the range and is used to identify the network itself. It is obtained by setting all host bits to zero within the subnet. For example, if the network address is **10.25.34.0**, it signifies the beginning of the subnet.

- *Usable Addresses:* With a **/25** subnet mask, there are 7 bits available for host addresses (32 - 25 = 7). This provides a total of **2^7 - 2 = 126** usable addresses for hosts. The subtraction of 2 is because the first and last addresses in the range are reserved for the network address and the broadcast address, respectively. For a **/24** mask, there are 8 bits for hosts, providing **2^8 - 2 = 254 usable addresses.**

- *First Usable Address:* This is the second address in the range, after the network address, and is typically assigned to the first host device. For example, for **VLAN 412 (Floor One)**, this would be **10.25.34.1**.

- *Last Usable Address:* This is the second-to-last address in the range and is typically assigned to the last host device. For example, for **VLAN 412 (Floor One)**, this would be **10.25.34.126**.

- *Broadcast Address:* This is the last address in the range and is used to send data to all hosts within the subnet. It is obtained by setting all host bits to one within the subnet. For example, for **VLAN 412 (Floor One)**, this would be **10.25.34.127**.

**4 - The process is repeated for all networks in descending order of nodes obtaining something like this table:**

| VLAN ID |     SubNet      |  
|:-------:|:---------------:|
|   412   |  10.25.34.0/25  | 
|   413   | 10.25.34.128/24 | 
|   414   | 10.25.35.128/25 | 
|   415   |  10.25.36.0/26  | 
|   416   |  10.25.35.1/25  | 
___