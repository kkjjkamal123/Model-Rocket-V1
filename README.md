<!-- HEADER BANNER -->
<div align="center">

```
 ██████╗      ██████╗ █████╗ ███╗   ██╗██████╗ ██╗   ██╗
 ██╔══██╗    ██╔════╝██╔══██╗████╗  ██║██╔══██╗╚██╗ ██╔╝
 ██████╔╝    ██║     ███████║██╔██╗ ██║██║  ██║ ╚████╔╝
 ██╔══██╗    ██║     ██╔══██║██║╚██╗██║██║  ██║  ╚██╔╝
 ██║  ██║    ╚██████╗██║  ██║██║ ╚████║██████╔╝   ██║
 ╚═╝  ╚═╝     ╚═════╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═════╝    ╚═╝
```

### **Model-V1 · R-Candy Sugar Propellant Rocketry Project**
*From a blank bench to a flying rocket — built from scratch, simulated, and documented.*

---

![Status](https://img.shields.io/badge/Status-Active%20Build-brightgreen?style=for-the-badge&logo=rocket)
![Motor Class](https://img.shields.io/badge/Motor%20Class-B%20%E2%86%92%20F-orange?style=for-the-badge)
![Propellant](https://img.shields.io/badge/Propellant-KNSB%2065%3A35-blue?style=for-the-badge)
![Apogee Target](https://img.shields.io/badge/Target%20Apogee-200--300%20m-red?style=for-the-badge)
![OpenRocket](https://img.shields.io/badge/Simulation-OpenRocket-9cf?style=for-the-badge)

</div>

---

## 🚀 What Is This?

This repository is a complete, first-principles model rocketry project built on **R-Candy (KNSB sugar propellant)** — designed, simulated, and documented by an engineering student. The primary goal is a clean, stable flight to **200–300 m apogee** using a custom-cast B-class motor — a realistic, achievable target for a first build.

The project covers everything: the physics and chemistry behind the propellant, CAD and 3D-print files for every structural component, OpenRocket `.ork` simulation files with custom `.eng` motor curves, step-by-step build procedures, and full safety documentation.

This is not a kit. Every dimension, every fin, every gram of propellant is understood and intentional.

---

## 📐 Project Structure

```
Model-Rocket-V1/
│
├── 📁 ork/
│   ├── RCandy_250m.ork          ← OpenRocket design file (target: ~250 m)
│   └── RCandy_B4_RC-B4.eng     ← Custom KNSB motor thrust curve (B class, 4 g)
│
├── 📁 stl/                      ← 3D-print files (PLA, PETG — airframe only)
│   ├── nose_cone.stl
│   ├── fin_x1_print3.stl        ← Print ×3 (one per fin)
│   ├── fin_alignment_jig.stl    ← Assembly tool — print & discard
│   └── launch_lug.stl
│
├── 📁 step/                     ← Editable CAD (SolidWorks / Fusion / FreeCAD)
│   ├── nose_cone.step
│   ├── fin.step
│   ├── fin_alignment_jig.step
│   └── launch_lug.step
│
├── BUILD_GUIDE.md               ← Full step-by-step build procedure
├── SESSION_REPORT.md            ← Engineering session log & decisions
└── README.md                    ← You are here
```

---

## ✈️ Design Specifications — RCandy-250

| Parameter | Value |
|---|---|
| **Target apogee** | 200–300 m (sim: ~250 m) |
| **Airframe diameter** | 18 mm |
| **Total length** | ~28 cm |
| **Nose cone** | Ogive, 70 mm, PLA |
| **Body tube** | 210 mm, phenolic/cardboard |
| **Fins** | 3× trapezoidal, 2.0 mm birch ply, airfoil section |
| **Fin span** | 30 mm · root 45 mm · tip 20 mm · sweep 25 mm |
| **Motor class** | B — KNSB 65:35, **4 g propellant** |
| **Total impulse** | ~5.1 N·s |
| **Burn time** | ~0.53 s |
| **Max velocity** | ~145 m/s (M0.42) |
| **Recovery** | Streamer 5×70 cm, Kevlar anchor |
| **Stability** | ≥1.5 cal (Barrowman) — verify in OpenRocket |

> **Motor note:** The `.eng` file (`RC-B4`) encodes a KNSB thrust curve scaled to produce ~250 m on this exact airframe. Re-simulate after any weight change.

---

## 🧪 Propellant — KNSB 65:35

The fuel is **KNSB: potassium nitrate + sorbitol** at a 65:35 mass ratio. This is the standard beginner sugar propellant — safer than KNSU (sucrose) because sorbitol melts at a lower temperature (~110 °C vs 150 °C+), giving a wider, more forgiving casting window.

| Compound | Role | Mass (4 g grain) |
|---|---|---|
| Potassium nitrate KNO₃ | Oxidiser | **2.6 g** |
| Sorbitol C₆H₁₄O₆ | Fuel / binder | **1.4 g** |

**Delivered specific impulse:** ~130 s · **Burn character:** progressive, low slag

### ⚗️ Casting Summary

1. Grind KNO₃ alone to fine powder (no fuel present, no flame)
2. Melt sorbitol in a dedicated metal pan, off open flame, thermometer ≤120 °C
3. Remove from heat — stir in KNO₃ until a uniform smooth paste forms
4. If mix smokes or darkens → flood with water and discard immediately
5. Cast around the 8 mm coring rod, tap out bubbles, cure fully, inspect for cracks

> Full casting procedure with safety protocols is in `BUILD_GUIDE.md`.

---

## 🖨️ 3D Printing — What to Print

All STL files are validated watertight. Motor casing, nozzle, and bulkhead must **never** be printed — use machined graphite/aluminium for those.

| File | Qty | Material | Infill | Notes |
|---|---|---|---|---|
| `nose_cone.stl` | 1 | PLA or PETG | 15–20% | 3 perimeters, 0.2 mm layer |
| `fin_x1_print3.stl` | 3 | PETG or carbon PETG | 30–40% | Print each fin flat for grain alignment |
| `fin_alignment_jig.stl` | 1 | PLA | 10% | Assembly aid — discard after glue sets |
| `launch_lug.stl` | 1 | PETG | 25% | Drill to match your rail rod diameter |

**Orientation:** print fins flat on the bed (skin parallel to fin surface). Sand the mating surfaces to 120 grit before epoxying.

> ⚠ Never print nozzle, motor casing, retaining bulkhead, or any part that contacts combustion gases.

---

## 🔭 Simulation — OpenRocket

All simulation is done in **OpenRocket** (free, open-source). The `.ork` file contains the full Barrowman aerodynamic model, all component masses, and the configured motor.

### Setup in 3 steps

```
1. File → Preferences → User-defined thrust curves → Add file
   → select RCandy_B4_RC-B4.eng → OK → Restart OpenRocket

2. File → Open → RCandy_250m.ork

3. Simulate → Run simulation
   Check: Stability ≥ 1.5 cal  |  Rail-exit velocity ≥ 15 m/s
```

### Flight profile (simulated, ISA atmosphere, 2 m/s wind)

| Phase | Time | Altitude |
|---|---|---|
| Ignition & rail-exit | 0 s | 0 m |
| Motor burnout | ~0.5 s | ~18 m |
| Coast to apogee | ~3.5 s | **~250 m** |
| Streamer deploy | ~3.5 s | 250 m |
| Ground recovery | ~65 s | 0 m |

> **Always re-simulate after the rocket is fully built and weighed.** An extra 5 g shifts the apogee by tens of metres.

---

## 🔧 Build Overview

Full procedure is in `BUILD_GUIDE.md`. The sequence at a glance:

```
[1] Gather materials & verify all masses
[2] Cut & finish body tube (210 mm)
[3] Print and sand nose cone + fins
[4] Mark fin lines on tube (use tube_wrap template)
[5] Epoxy fins using alignment jig — 120° spacing
[6] Apply 3 mm fillet radius at fin roots
[7] Glue motor mount, add positive retention
[8] Anchor Kevlar shock cord → attach streamer
[9] Prime, paint, and polish airframe
[10] Simulate in OpenRocket (must: ≥1.5 cal, ≥15 m/s rail-exit)
[11] Cast KNSB grain (with mentor, off open flame, ≤120 °C)
[12] Assemble motor — graphite nozzle, forward bulkhead, delay
[13] Range: 1 m rail, e-match, all personnel ≥30 m behind cover
[14] Fire — log actual vs predicted apogee
```

---

## ⚠️ Safety — Non-Negotiable

Sugar motors are **live ordnance**. These rules are not suggestions.

- Never work alone — an **experienced mentor must be present** at every stage
- Legal authorisation for your site and motor class is mandatory before any live work
- Eye protection at all times during casting, assembly, and flight
- Cast off open flame — never exceed 120 °C, never rush the cool-down
- Electric ignition only — **≥30 m behind a solid barrier**, continuity check before arming
- Never 3D-print combustion-path parts (nozzle, casing, bulkhead) — PLA/PETG will fail catastrophically
- Discard any batch that smokes, darkens, or shows uneven mixing — do not fly a suspect grain
- Store finished motors in a cool, dry location — separated from igniters until range day

---

## 📦 Five-Model Progression (Full Pack)

This repository focuses on the **200–300 m target (RCandy-250)**. The full five-model progression from the design session is documented below for reference — build in order, do not skip ahead.

| # | Model | Level | Dia | Fuel | Impulse | Apogee | Recovery |
|---|---|---|---|---|---|---|---|
| **→ 0** | **RCandy-250** | **Beginner ★ Start here** | **18 mm** | **4 g KNSB** | **B (5.1 N·s)** | **~250 m** | **Streamer** |
| 1 | Skylark-S | Beginner | 18 mm | 6 g | C (7.6 N·s) | ~548 m | Streamer |
| 2 | Cadet-24 | Beginner–Int | 29 mm | 15 g | D (19.1 N·s) | ~502 m | 30 cm chute |
| 3 | MaxAlt-24 | Intermediate | 24 mm | 30 g | E (38.2 N·s) | ~1129 m | Streamer+chute |
| 4 | Altair-29 | Int–Adv | 29 mm | 40 g | F (51.0 N·s) | ~964 m | 45 cm chute |
| 5 | Apex-29 | Advanced | 29 mm | 55 g | F (70.1 N·s) | ~1238 m | Dual-deploy |

> Files for the full five-model pack (Skylark → Apex) are referenced in `SESSION_REPORT.md`.

---

## 🔬 Key Engineering Concepts

<details>
<summary><strong>Why KNSB instead of KNSU?</strong></summary>

KNSU uses sucrose as the fuel, which melts at ~150 °C — a hot, narrow window that punishes inattention with scorching or partial decomposition. KNSB uses sorbitol (~110 °C melt), which is far more forgiving on a first cast. Both deliver similar specific impulse (~130 s). For a first build, KNSB is the correct choice.

</details>

<details>
<summary><strong>Why 65:35 KNO₃:fuel ratio?</strong></summary>

65:35 sits near the stoichiometric balance that maximises delivered Isp in castable sugar propellants. Moving toward more oxidiser increases burn temperature and rate, eventually becoming uncontrollable. Moving toward more fuel creates a lazy, low-performance burn with excess carbon residue. 65:35 is the proven, community-validated sweet spot.

</details>

<details>
<summary><strong>What is stability calibres?</strong></summary>

Stability = (CG − CP) / diameter, where CG is the centre of gravity and CP is the centre of pressure. A value ≥ 1.5 cal means the rocket is 1.5 body-diameters nose-heavy — enough aerodynamic restoring force to keep it flying straight. Below ~1.0 cal the rocket is prone to weathercocking or going ballistic. OpenRocket computes this automatically; always verify before flight.

</details>

<details>
<summary><strong>Why can't I just print the nozzle?</strong></summary>

At ignition, the nozzle throat sees combustion gases at ~1600–1800 °C and chamber pressures of 3–10 MPa. PLA softens at 60 °C and PETG at ~85 °C — both fail instantly. Nozzles must be machined from graphite (preferred), mild steel, or similar refractory materials. This is not a workaround — it is a structural requirement.

</details>

---

## 🛠️ Tools & Software Used

| Category | Tool |
|---|---|
| Flight simulation | OpenRocket (free) |
| CAD / solid modelling | SolidWorks · FreeCAD · STEP-compatible |
| Slicer | Bambu Studio · Cura · PrusaSlicer |
| Propellant design | Manual 1-DOF + thrust curve scaling |
| Documentation | Markdown · LaTeX-ready |

---

## 📋 Bill of Materials (RCandy-250)

| Item | Source / Spec | Est. Cost |
|---|---|---|
| Body tube, 18 mm ID phenolic/cardboard | Craft store / hardware | ₹40–80 |
| Birch plywood, 2.0 mm × 150×150 mm | Hobby / art supply | ₹60–100 |
| PLA filament (nose cone) | 3D print service / own printer | ₹20–40 |
| Epoxy — 30-min structural | Araldite Standard or equiv | ₹80–150 |
| Potassium nitrate (KNO₃) | Agricultural supplier / photo grade | ₹50–100 |
| Sorbitol | Pharmacy / chemical supplier | ₹30–60 |
| Kevlar shock cord, 3 mm, 40 cm | Kite shop / online | ₹30 |
| Mylar/plastic streamer, 5×70 cm | Stationery / party shop | ₹10–20 |
| Electric igniter (e-match) | Pyro supplier | ₹30–80 |
| Graphite nozzle, 4 mm throat, 18 mm OD | Machine shop or import | ₹200–600 |
| **Total estimate** | | **₹550–1230** |

> Costs are approximate Indian market estimates. Nozzle is the single most significant variable — plan accordingly.

---

## 📄 Repository Files Quick-Reference

| File | Purpose |
|---|---|
| `RCandy_250m.ork` | OpenRocket design — load this to simulate |
| `RCandy_B4_RC-B4.eng` | Motor thrust curve — add to OpenRocket first |
| `stl/nose_cone.stl` | 3D-print (PLA) — 1 piece |
| `stl/fin_x1_print3.stl` | 3D-print (PETG) — print 3× |
| `stl/fin_alignment_jig.stl` | Print 1×, discard after use |
| `stl/launch_lug.stl` | Print 1× (PETG) |
| `step/*.step` | Editable CAD for all parts |
| `BUILD_GUIDE.md` | Full step-by-step construction + safety |
| `SESSION_REPORT.md` | Design decisions, physics rationale, session log |

---

## 📡 Disclaimer

This is an educational engineering project. Sugar motors are live ordnance. Nothing in this repository replaces hands-on guidance from a qualified rocketry mentor, compliance with local laws, and proper range safety protocols. Build, cast, and fly responsibly.

---

<div align="center">

*Built from scratch. Simulated. Documented. Ready to fly.*

`v1.0 · 2026-06-16 · Model-Rocket-V1`

</div>
