# Description of Building 2

- **Floors:**
    - Floor 0: 11 rooms, WC, stairs and corridors, equipped with an underfloor cable raceway and connected to the external technical ditch.
    - Floor 1: 15 rooms, WC, staris and corridors, with a removable dropped ceiling, providing an ideal empty space for cable raceways.

# Measurements and Specifications

## Floor 0 Room Specifications

| Room Number | Width (m) | Length (m) | Area (m²) | Number of Outlets    |
|-------------|-----------|------------|-----------|----------------------|
| 2.0.1       | 3.33      | 8.35       | 27.81     | 6                    |
| 2.0.2       | 3.33      | 8.35       | 27.81     | 6                    |
| 2.0.3       | 3.33      | 5.82       | 19.38     | 4                    |
| 2.0.4       | 3.33      | 5.82       | 19.38     | 4                    |
| 2.0.5       | 4.99      | 10.87      | 54.24     | 12                   |
| 2.0.6       | 8.55      | 11.02      | 94.22     | 5 (Special Use Room) |
| 2.0.7       | 8.55      | 11.02      | 94.22     | 5 (Special Use Room) |
| 2.0.8       | 3.32      | 8.52       | 28.29     | 6                    |
| 2.0.9       | 3.32      | 8.52       | 28.29     | 6                    |
| 2.0.10      | 3.32      | 4.68       | 15.54     | 4                    |
| 2.0.11      | 3.32      | 3.57       | 11.85     | 0 (Storage Room)     |

*Note: It is required that there is 2 outlets per 10$m^2$*

*Exceptions:*
- Rooms 2.0.6 and 2.0.7 have a special use and the only network outlets required are along the underfloor
  cable raceway, five outlets in each room.
- Room 2.0.11 is a storage area and may be used to house a cross-connect, no network outlets are required
  there, and the same applies to the restrooms, the entrance hall, and other common areas.


## Floor 1 Measurements

## Floor 1 Room Specifications

| Room Number | Width (m) | Length (m) | Area (m²) | Number of Outlets |
|-------------|-----------|------------|-----------|-------------------|
| 2.1.1       | 3.86      | 6.94       | 26.79     | 6                 |
| 2.1.2       | 3.86      | 6.94       | 26.79     | 6                 |
| 2.1.3       | 3.86      | 6.94       | 26.79     | 6                 |
| 2.1.4       | 3.86      | 6.94       | 26.79     | 6                 |
| 2.1.5       | 3.86      | 6.94       | 26.79     | 6                 |
| 2.1.6       | 2.49      | 6.91       | 32.54     | 8                 |
| 2.1.7       | 4.45      | 6.91       | 32.54     | 8                 |
| 2.1.8       | 4.45      | 6.91       | 32.54     | 8                 |
| 2.1.9       | 4.45      | 6.91       | 32.54     | 8                 |
| 2.1.10      | 4.39      | 6.91       | 32.54     | 8                 |
| 2.1.11      | 4.13      | 6.91       | 29.92     | 6                 |
| 2.1.12      | 1.67      | 6.91       | 12.19     | 0                 |
| 2.1.13      | 2.52      | 6.88       | 32.54     | 8                 |
| 2.1.14      | 4.39      | 6.88       | 32.54     | 8                 |
| 2.1.15      | 6.67      | 6.88       | 32.54     | 8                 |


*Note: It is required that there is 2 outlets per 10$m^2$*

*Exceptions:*
- Room 2.1.12 is a storage area and may be used to house a cross-connect, no network
  outlets are required there, and the same goes for restrooms, halls, and corridors.


# Deployment Systems Design

## Floor 0 Cabling

<img src="Floor 0.png" alt="Cabling" width="500">

Figure 1 - Floor 0 Cabling Deployment


### Consolidation Points

- The Consolidation Point in 2.0.7 covers rooms 2.0.7 and 2.0.6.
- The Consolidation Point in 2.0.5 covers rooms 2.0.5 and 2.0.4.
- The Consolidation Point in 2.0.3 covers rooms 2.0.3, 2.0.2 and 2.0.1.


### Cabling System

- The cables used inside the floor are, as recommended, copper cables CAT7, with only a Monomode 10 cable being used to connect to the Horizontal Cross-Connect.
- Cables within rooms are inside the walls.
- 2.0.11 stores both an Intermediate Cross-Connect (IC) and a Horizontal Cross-Connect (HC).
- The HC connects directly to all the nearby outlets in rooms 2.0.10, 2.0.9 and 2.0.8 and to the Consolidation Points in 2.0.7, 2.0.5 and 2.0.3.

### Access Points

- The access point is placed in the center of the floor, providing total coverage for all rooms.

## Floor 1 Cabling

<img src="Floor 1.png" alt="Cabling" width="500">

Figure 2 - Floor 1 Cabling Deployment

### Consolidation Points

- The Consolidation Point in 2.1.9 is covering rooms 2.1.9, 2.1.8, 2.1.7 and 2.1.6.
- The Consolidation Point in 2.1.3 covers rooms 2.1.1, 2.1.2, 2.1.3, 2.1.4 and 2.1.5.
- The Consolidation Point in 2.1.14 covers rooms 2.1.13, 2.1.14 and 2.1.15.
- Cables from the HC are connected through the roof to the rooms 2.1.15 and 2.1.5, where they are passed to the wall and connected to the Consolidation Points.


### Cabling System

- The cables used inside the floor are, as recommended, copper cables CAT7.
- Cables within rooms navigate through the walls, except to the rooms 2.1.15 and 2.1.5, where they pass through the ceiling and then along the walls.
- 2.1.12 stores the Horizontal Cross-Connect (HC).

### Access Points

- The access point is placed in the center of the floor, providing total coverage for all rooms.

# Hardware Inventory

## **Floor 0**

| Item                            | Units used |
|:--------------------------------|:----------:|
| Outlets                         |     58     |
| Cables                          |     17     |
| Monomode 10                     |     1      |
| Access Points                   |     1      |
| IC (Intermediate Cross-Connect) |     1      |
| HC (Horizontal Cross-Connect)   |     1      |
| Consolidation Points            |     3      |


## **Floor 1**

| Item                          | Units used |
|:------------------------------|:----------:|
| Outlets                       |     96     |
| CAT7 Cables                   |     29     |
| Monomode 10                   |     0      |
| Access Points                 |     1      |
| HC (Horizontal Cross-Connect) |     1      |