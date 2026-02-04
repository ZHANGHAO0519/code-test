# eVTOL-Based Post-Disaster Emergency Medical Transport with Time-Dependent Rewards  
## real-world Instance Data Description

---

## 1. Overview

This file describes a benchmark instance for an **eVTOL-Based Post-Disaster Emergency Medical Transport with Time-Dependent Rewards**, involving a heterogeneous fleet of **eVTOLs** and **helicopters**. The data is structured for models that incorporate:

- Multiple vehicle types with different speeds  
- Time deadlines  
- Customer nodes with time-sensitive (decaying) profits  
- Node priorities (by type)  
- Medical staff requirements  

---

## 2. Vehicle Information

| VEHICLE (eVTOL) |        | VEHICLE (He) |        |
|------------------|--------|---------------|--------|
| SPEED            | DEADLINE | SPEED         | DEADLINE |
| `[v1]`           | `[d]`    | `[v2]`        | `[d]`    |

### Definitions

- **VEHICLE (eVTOL)**: Electric Vertical Take-Off and Landing aircraft.  
- **VEHICLE (He)**: Helicopter.  
- **SPEED**: Cruising speed (km/h).  
- **DEADLINE**: Maximum allowed duration for a complete response mission (hours).  

---

## 3. Node Data Format

Each row in the node data file follows the format:


### Field Definitions

| Field | Description | Type / Unit |
|-------|-------------|-------------|
| Node | Unique node identifier. Node 0 is the hospital. | Integer |
| Lon | Longitude coordinate. | Decimal degrees (WGS-84) |
| Lat | Latitude coordinate. | Decimal degrees (WGS-84) |
| PROFIT | Base profit for servicing this node. | Non-negative scalar |
| k1 | Profit decay rate for Phase 1. | Non-negative scalar |
| k2 | Profit decay rate for Phase 2. | Non-negative scalar |
| S_T | Service time required at the node. | Hours |
| TYPE | Node severity/priority type. | 1 = Mildly affected site; 2 = Severely affected site |
| Medical_Demand | Number of medical personnel units required. | Integer ≥ 0 |

---

## 4. Example Data Row Interpretation

**Example Node:**

- **Node**: 1  
- **Lon**: 97.009147  
- **Lat**: 32.992911  
- **PROFIT**: 900  
- **k1**: 250  
- **k2**: 80  
- **S_T**: 0.1 h (6 minutes)  
- **TYPE**: 2 (Severely affected site)  
- **Medical_Demand**: 1  
- 

