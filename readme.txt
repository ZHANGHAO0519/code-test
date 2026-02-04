================================================================

1. Overview

This file describes a benchmark instance for an Aerial Emergency Rescue Routing Problem, involving a heterogeneous fleet of eVTOLs and helicopters. The data is structured for models that incorporate:

Multiple vehicle types with different speeds

Time deadlines

Customer nodes with time-sensitive (decaying) profits

Node priorities (by type)

Medical staff requirements

================================================================
VEHICLE(eVTOL)           VEHICLE(He)
SPEED    DEADLINE       SPEED    DEADLINE
  [v1]       [d]            [v2]       [d]


VEHICLE(eVTOL): Electric Vertical Take-Off and Landing aircraft.

VEHICLE(He): Helicopter.

SPEED: Cruising speed (km/h).

DEADLINE: Maximum allowed duration for a complete rescue mission (hours).

---

Node  Lon.             Lat.            PROFIT  k1   k2   S_T   TYPE  Medical_Demand
[...data rows...]

Node			Unique node identifier. Node 0 is the depot/warehouse.	Integer
Lon.				Longitude coordinate.	Decimal degrees (WGS-84)
Lat.				Latitude coordinate.	Decimal degrees (WGS-84)
PROFIT			Base profit for servicing this node.	Non-negative scalar
k1				Profit decay rate for Phase 1.	
k2				Profit decay rate for Phase 2.	
S_T				Service time required at the node.	Hours
TYPE			Node severity/priority type.	1 = Mildly affected site，2 = Severely affected site
Medical_Demand	Number of medical personnel units required.	Integer ≥ 0

================================================================
Example Data Row Interpretation：
Node: 1
Lon: 97.009147, Lat: 32.992911
PROFIT: 900
k1: 250, k2: 80
S_T: 0.1 h (6 minutes)
TYPE: 2 (Severely affected site)
Medical_Demand: 1