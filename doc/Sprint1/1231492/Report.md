# Structured Cabling Deployment Plan Building 1


## Building 1
This building hold the data centre and also houses the main cross-connect for the structured cabling system.
Its horizontal dimensions are approximately 20 × 20 meters, with two floors.


### Floor 0 (Ground Floor)


#### Special Considerations/Constraints


* Has an underfloor cable raceway connected to the external technical ditch.


* *No network outlets are required in neither of the common areas.


* In the remaining spaces, the standard number of network outlets per area ratio is to be enforced.


* Contains 6 rooms, (1.0.1, 1.0.2, 1.0.3, 1.0.4, 1.0.5, 1.0.6, 1.0.7)

---

#### Room's Measurements


#### Room's Area
|Room Nº | Width(m) | Length(m) | Area(m^2) |
|-------:|:--------:|:---------:|:---------:|
| 1.0.1  |   3.04   |    4.82   |   14.65   |
| 1.0.2  |   3.04   |    4.82   |   14.65   |
| 1.0.3  |   3.04   |    4.82   |   14.65   |
| 1.0.4  |   3.21   |    4.82   |   15.47   |
| 1.0.5  |   5.14   |    6.96   |   35.77   |
| 1.0.6  |   5.8    |    7.2    |   22.05   |
| 1.0.7  |   5.14   |    6.96   |   35.77   |


---

### Network Outlets Number

###### The number of outputs is obtained using the next scheme:

| Area (m^2)  | Number of outputs |
|------------:|:-----------------:|
| 0 to 10     |        2          |
| 10 to 20    |        4          |
| 20 to 30    |        6          |
| 30 to 40    |        8          |




|Room Nº || Nº of Outlets |
|-------:|:--------------:|
| 1.0.1  |       4        |
| 1.0.2  |       4        |
| 1.0.3  |       4        |
| 1.0.4  |       4        |
| 1.0.5  |       8        |
| 1.0.6  |       6        |
| 1.0.7  |       8        |



### Cabling Structure and Component Identification


#### Hardware Inventories

| Outlets | CAT7 Cables | Monomodo 10 Cables | Access Point | Telecommunications Enclosure |
|:-------:|:-----------:|:------------------:|:------------:|:----------------------------:|
|   38    |    93.9m    |        7m          |      1       |              3               |

---

### Justification/Comments

The cables that will be connected to the outlets come from the horizontal cross-connect placed in the room 1.0.5 For this reason.
To connect the HC, a cable from the Intermediate Cross-Connect comes from the above floor where the IC is placed. So, in this floor, 5.5 meters of fibre cable is used (HC in placed 1 meter from the ground) (3 meters for HC to 1Floor and mor 2.5m to the roof).
However, to make the IC and MC active, they also need to be connected. The cable which make this possible, comes from outside the building, enters the room and goes to the floor 1 through the ceiling passageway, meaning 4 meters.

As there is underfloor raceways (which is used everywhere), the cables need to get out of the HC and get there.
So, first step is to send cables to the nearest floor passageways and then add the height of the HC, which is 1 meter (every cable length will contain this "extra").

Also, every network outlet is placed 1 meter from the ground, so that amount will also be taken in account in every outlet.

When calculating the length of cable required for the cabling system in a building, I followed a comprehensive approach that accounted for the specific routing of the cable.
To calculate the length of cable needed, I first determined the approximate distance to get to every floor passageway.
Then, I calculated the relative distance to the outlets, meaning the distance between the passageway to the outlet, in each room.
By combining these distances, I was able to determine the total length of cable required for the entire system.


#### Acess Point

To provide wireless LAN coverage (Wi-Fi), access points must be installed.
Each can provide wireless coverage within 25 meters radius, so to ensure that the entire floor is completely covered, access point outlets were placed near the middle but a little further north of the building and further to the right.

---

<br>

### Cable Measurements
#### Room 1.0.1 1.0.2 1.0.3
|       | Cable Lenght (meters) |
|------:|:---------------------:|
 Total |      29.73            |




#### Room 1.0.4
|        | Cable Length (meters) |
|-------:|:---------------------:|
|  Total |         9.91          |

<br>

#### Room 1.0.5 1.0.7
| Room   | Cable Length (meters) | Height (meters) |
|:------:|:---------------------:|:---------------:|
| 1.0.5  |          23.18        |       4.0       |
| 1.0.7  |          18.58        |       ----      |
| Total  |          41.76        |       4.0       |

<br>

#### Room 1.0.6
|        | Cable Length (meters) |
|:------:|:---------------------:|
| Total  |         19.50         |

<br>


### Total Length of Cable

| CAT7 cable | Monomodo 10 cable |
|:----------:|:-----------------:|
|    93.9    |         7         |

<br>


### Floor 1

---
#### Special Considerations/Constraints


* Rooms 1.1.3 will store the main cross-connect for the structured cabling system.


* There is a removable dropped ceiling, placed 2.5 meters from the ground, covering the entire floor, perfect toinstall cable raceways.


* No network outlets are required in neither of the common areas and in the room 1.1.3.


* In the remaining spaces, the standard number of network outlets per area ratio is to be enforced.


* Contains 5 rooms (1.1.1, 1.1.2, 1.1.3, 1.1.4, 1.1.5)


#### Room's Measurements

#### Room's Area

| Room Nº | Width(m)  |  Length(m) | Area(m2) |
|--------:|:---------:|:----------:|:--------:|
|   1.1.1 |   3.48    |    6.96    |   24.22  |
|   1.1.2 |   3.48    |    6.96    |   24.22  |
|   1.1.3 |   11.43   |    6.96    |   79.55  |
|   1.1.4 |   5.14    |    4.29    |   22.02  |
|   1.1.5 |   5.14    |    6.96    |   35.77  |


---

### Network Outlets Number

###### The number of outputs is obtained using the next scheme:

| Area (m^2)  | Number of outputs |
|------------:|:-----------------:|
| 0 to 10     |        2          |
| 10 to 20    |        4          |
| 20 to 30    |        6          |
| 30 to 40    |        8          |




|Room Nº || Nº of Outlets |
|-------:|:--------------:|
| 1.1.1  |       6        |
| 1.1.2  |       6        |
| 1.1.3  |      ----      |
| 1.1.4  |       6        |
| 1.1.5  |       8        |




#### Hardware Inventories

| Outlets | CAT7 Cables | Monomodo 10 Cables | Access Point | Telecommunications Enclosure |
|:-------:|:-----------:|:------------------:|:------------:|:----------------------------:|
|   26    |   67.88m    |         2.5m       |      1       |              6               |

---

### Justification/Commments

Every cable also comes from the [HC]. However, this floor has a peculiar feature. It houses the Main Cross-Connect, an the Intermediate Cross-Connect.
So, a fibre cable (monomode 10) will come from the floor bellow, to connect to the [MC]. The cable travels through the ceiling passageway to be connected to the MC so, 2.5 meters.

From here, the MC, will be connected to the [IC]. The IC will then send cable, again, to the floor below and to the HC on the current floor.
From here, we can start connecting cable to outlets and [CPs].

As this floor has a removable dropped ceiling, the cables raceways are installed on the ceiling.
This dropped ceiling has a height of 2.5 meters, so, in order to make the cable arrive to the outlet, is has to go down.
Like previously said, the outlets are being placed 1 meter from the ground, so the cable has to go down 1.5 meters.
On the below tables, this is taken into account on the Height and Descent column.
This can also be seen in the cabling system plan image above, represented by the *yellow arrow*.

However, the cable does not go down on every outlet.
On some situations, as it can be seen in the image, the cable goes down on an outlet and then reach all the nearby ones.

Everything starts from the room 1.1.3, so is from there that we will start the calculations.

Finally, each Patch Panel has to be stored inside a Telecommunication Enclosure.
A bigger [TL] will be used to store the MC, IC and HC placed inside Room 1.1.3.


#### Access Point

To provide wireless LAN coverage (Wi-Fi), access points must be installed.
Each can provide wireless coverage within 25 meters radius, so to ensure that the entire floor is completely covered, access point outlets were placed near the middle but a little further north of the building and further to the right.

---

<br>

#### Cable Measurements

##### Cable on the ceiling plus the descent

|        | Cable Lenght (meters) | Height and Descent (meters) |
|  Total |         31.04         |            11.5             |

##### Cable on the wall

### Room 1.1.1 1.1.2

|        | Cable Lenght (meters) |
|  Total |         6.21          |

### Room 1.1.4

|        | Cable Lenght (meters) |
|  Total |          9.89         |

### Room 1.1.5

|        | Cable Lenght (meters) |
|  Total |         11.74         |

### Total Length of Cable

| CAT7 cable | Monomodo 10 cable |
|-----------:|:-----------------:|
|   67.88    |        2.5        |

---

## Backbone

As this Building houses the Main Cross-Connect, it has the responsibility to provide for the other buildings.
Cables will leave the building, through an underground passageway, travel through a Technical Ditch and get inside each building to be connected to an Intermediate Cross-Connect.

So, like previously said, this building provides network connection to all the other buildings in the campus by a single cable, for each building.
So it would be tragic if that cable broke up.
For this reason we will be using, two cables.


### Backbone Cable Measurements

|             Path | Cable Length (meters) |
|-----------------:|:---------------------:|
| 1-->2 (shortest) |         75.5          |
|  1-->2 (longest) |         531.68        |
|  1-->3(shortest) |         280.33        |
|   1-->3(longest) |         325.01        |
|  1-->4(shortest) |         228.34        |
|   1-->4(longest) |         378.34        |
|            Total | 1819.2 + 40 = 1859.2  |


<br>



## Total Inventory



| Outlets | CAT7 Cables | Monomode 10 Cables | Access Point | Telecommunications Enclosure |
|:-------:|:-----------:|:------------------:|:------------:|:----------------------------:|
|   64    |    161.78m  |        1868.7m     |      2       |              6               |