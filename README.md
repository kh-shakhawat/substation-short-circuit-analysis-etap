# Substation Short Circuit & Load Flow Analysis using ETAP

**Course Project — Power System Analysis (7th Semester)**
B.Sc. in Electrical and Electronic Engineering

## 📌 Overview

This project presents a short circuit and load flow analysis of a sample power distribution substation, modeled and simulated in **ETAP (Electrical Transient Analyzer Program)**. The study evaluates fault current behavior, voltage drops, and loading levels across the network to assess system reliability and protection requirements.

## ⚡ System Description

The modeled network consists of:

- **Utility Source (U1 Equivalent):** 1991.858 MVAsc short circuit capacity
- **T_sub Bus:** 230 kV
- **Power Transformer (T2):** 156.25 MVA, steps down 230 kV → 13.8 kV
- **Cable1:** Interconnecting cable (36-1/C 750) from transformer LV side to substation bus
- **Sub Station Bus:** 13.8 kV
- **Two Distribution Feeders:**
  - Feeder 1 – Load 1: 40 MVA
  - Feeder 1 – Load 2: 40 MVA

![Single Line Diagram](images/power_flow_analysis.png)

## 🎯 Objectives

- Model a realistic substation single-line diagram (SLD) in ETAP
- Perform **three-phase short circuit analysis** at the 230 kV and 13.8 kV buses
- Perform **load flow analysis** to determine bus loading (%), voltage drop, and current distribution
- Analyze the **AC and DC components of fault current**, including decay behavior over time
- Evaluate results for protection device (breaker/relay) rating and coordination purposes

## 🛠️ Methodology

1. Built the single-line diagram in ETAP with source, transformer, cable, bus, and load elements
2. Assigned equipment ratings (MVA, kV, impedance) based on standard substation parameters
3. Ran the **Short Circuit Study** module to obtain:
   - Total fault current
   - AC component of fault current (rms)
   - DC component of fault current
   - Top envelope of fault current
   - Percent DC component
4. Ran the **Load Flow Study** to obtain bus loading percentages and voltage drops
5. Exported and analyzed plots using ETAP Plot Manager

## 📊 Results

### Load Flow — Bus Loading
| Bus | Loading (%) |
|---|---|
| T_sub (230 kV) | 100% |
| T1 LS (13.8 kV) | 95.8% |
| Sub Station Bus (13.8 kV) | 95.74% |

![Load Flow Results](images/power_system_analysis_.png)

### Short Circuit — Fault Current Summary
- **Total Fault Current:** Oscillating waveform, peak ≈ 18 kA (initial)
- **AC Component (rms):** Decays from ≈ 6.35 kA to ≈ 6.1 kA over 0.1 sec
- **Top Envelope of Fault Current:** Decays from 18 kA to ≈ 9.2 kA
- **DC Component:** Decays from ≈ 10 kA toward near-zero over the fault duration
- **Fault current at T_sub bus:** 5.866 kA (steady-state)

![Fault Current Plots](images/Screenshot_2026-08-14_112804.png)

### Voltage Drop
- HS side (T1 HS): 0.009 kV Vd,ln
- LS side (T1 LS): 0.005 kV Vd,ln
- Line loading at T_sub: 132.8%

## 📁 Repository Structure

```
├── README.md
├── images/
│   ├── power_flow_analysis.png
│   ├── power_system_analysis_.png
│   ├── Screenshot_2026-08-14_112204.png
│   ├── Screenshot_2026-08-14_112445.png
│   ├── Screenshot_2026-08-14_112631.png
│   └── Screenshot_2026-08-14_112804.png
└── report/ (optional: full ETAP report / .sip file)
```

## 🧰 Tools Used

- **ETAP 19.0.1** (Power System Modeling & Simulation)
  - Short Circuit Analysis Module
  - Load Flow Analysis Module
  - Plot Manager

## 📖 Conclusion

The simulation confirms that the substation's fault current levels and bus loading percentages remain within acceptable limits under the studied fault condition. The AC and DC fault current decay curves provide essential input for selecting appropriately rated circuit breakers and designing protection coordination schemes for the 230 kV and 13.8 kV sides of the system.

## 👤 Author

**Kh. Shakhawat Hossen Soikot**
B.Sc. in Electrical and Electronic Engineering
7th Semester — Power System Analysis Course Project

---
*This project was completed as part of academic coursework and is shared for educational and portfolio purposes.*
