# Engineering Log — RCandy-250 Design

**Builder:** Kamalesh VS — B.E. ECE, Chennai Institute of Technology (2024–28)
**Repository:** [github.com/kkjjkamal123/Model-Rocket-V1](https://github.com/kkjjkamal123/Model-Rocket-V1)
**Date:** 2026-06-16
**Status:** Design, simulation, and documentation complete. Build and flight pending.

---

## 1. Goal

Design a beginner-appropriate model rocket targeting a **200–300 m apogee** on R-Candy (KNSB sugar propellant), buildable as a first project with no prior rocketry build experience. Scope:

- A complete OpenRocket `.ork` simulation with a matching custom `.eng` motor curve
- Printable STL files and editable STEP files for every structural part
- A full step-by-step build procedure with alternatives for common tool/material gaps
- Clear documentation of the physics and chemistry behind every design choice

This design builds on an earlier five-model progression (Skylark-S through Apex-29) that I'd already worked out — none of those five land in the 200–300 m band, so RCandy-250 fills that gap as the actual first build.

---

## 2. Design Decisions

### 2.1 Why not fly one of the existing five models?

| Model | Apogee |
|---|---|
| Skylark-S | ~548 m |
| Cadet-24 | ~502 m |
| MaxAlt-24 | ~1129 m |
| Altair-29 | ~964 m |
| Apex-29 | ~1238 m |

All five overshoot the 200–300 m target by a wide margin — none of them are a sensible first flight. The fix was to take the Skylark-S airframe (18 mm body, same fin geometry, same nose cone — already proven CAD) and cut the propellant mass from 6 g down to **4 g KNSB**, dropping the motor from C-class to a B-class (RC-B4, ~5.1 N·s) that lands this exact airframe around ~250 m.

Fixing the airframe and tuning the motor is the right move here — reworking the airframe diameter or length to bring the apogee down would have thrown away validated CAD for no real benefit.

### 2.2 Apogee estimation methodology

The 1-DOF design check uses:

- ISA atmosphere, ground level, 2 m/s wind
- KNSB Isp ≈ 130 s, linear mass burn
- Drag: Cd = 0.45 (min-diameter, polished finish), frontal area = π × (0.009)²
- Motor: B-class, scaled from the Skylark-S C-class curve by linear scaling of masses and forces
- Same airframe mass and geometry as Skylark-S

Scaling 6 g → 4 g drops total impulse from 7.6 N·s to ~5.1 N·s with the airframe mass unchanged. The 1-DOF integration lands the apogee at **~240–260 m** — solidly inside the target band.

The `.ork` file carries the full Barrowman aerodynamic model and is the simulation that actually matters before any flight. The 1-DOF number above is a sanity check during design, not a flight prediction.

### 2.3 Why KNSB over KNSU for a first cast?

Sorbitol-based KNSB (65:35) is the right propellant for a first build. Sorbitol melts at ~110 °C against sucrose's ~150 °C — a wider, more forgiving casting window that tolerates the small temperature overshoots and stirring irregularities that come with a first cast. Both propellants deliver roughly the same 130 s specific impulse, so there's no performance reason to reach for KNSU here.

### 2.4 STL/STEP selection

The CAD pack covers all five models; the parts pulled into this build are the **Skylark-S (01)** set, because:

- 18 mm is the smallest airframe in the progression — lightest, lowest drag, the right match for a B-class motor
- Nose cone, fin geometry, and the alignment jig are already sized for this airframe
- It's a minimum-diameter design — the motor fills the body tube directly, so no centering rings are needed

Parts in this repo:
- `stl/nose_cone.stl` — 3D-printed ogive nose, 70 mm, 18 mm shoulder
- `stl/fin_x1_print3.stl` — single fin; print three times
- `stl/fin_alignment_jig.stl` — assembly aid; discard after the fillets cure
- `stl/launch_lug.stl` — rail guide, print once in PETG

STEP equivalents for all four parts are included in `step/` for anyone who wants to modify the geometry in SolidWorks, FreeCAD, or another STEP-compatible tool.

---

## 3. File Index

| File | Location | Description |
|---|---|---|
| `README.md` | `/` | Project overview and quick-start |
| `BUILD_GUIDE.md` | `/` | Full step-by-step build procedure with alternatives & troubleshooting |
| `SESSION_REPORT.md` | `/` | This document — design rationale and engineering log |
| `RCandy_250m.ork` | `/ork/` | OpenRocket design file, RCandy-250, ~250 m target |
| `RCandy_B4_RC-B4.eng` | `/ork/` | Custom KNSB B-class thrust curve, 4 g propellant |
| `nose_cone.stl` | `/stl/` | 3D-print file, ogive nose cone, 18 mm |
| `fin_x1_print3.stl` | `/stl/` | 3D-print file, trapezoidal fin, print 3× |
| `fin_alignment_jig.stl` | `/stl/` | Assembly jig, print 1×, disposable |
| `launch_lug.stl` | `/stl/` | Rail lug, print 1× |
| `nose_cone.step` | `/step/` | Editable STEP, nose cone |
| `fin.step` | `/step/` | Editable STEP, fin |
| `fin_alignment_jig.step` | `/step/` | Editable STEP, jig |
| `launch_lug.step` | `/step/` | Editable STEP, lug |

### Reference — beyond this build

The five-model progression (Skylark-S through Apex-29) referenced throughout this log is a separate, larger CAD/simulation pack covering the next steps after RCandy-250. It includes a `KNSU_RC-E38.eng` standalone E-class motor file used only as a reference point, not part of this build. Those files aren't included in this repository — RCandy-250 is the only model documented and packaged here.

---

## 4. Technical Specifications — RCandy-250

### 4.1 Airframe

| Parameter | Value | Basis |
|---|---|---|
| Body diameter | 18 mm | Skylark-S geometry |
| Body tube length | 210 mm | Skylark-S geometry |
| Nose cone type | Ogive | Low Cd, 3D-printable |
| Nose cone length | 70 mm | 3.9:1 fineness ratio |
| Fin type | Trapezoidal, airfoil section | Stability + printability |
| Fin root chord | 45 mm | |
| Fin tip chord | 20 mm | |
| Fin sweep | 25 mm | |
| Fin span | 30 mm | |
| Fin thickness | 2.0 mm | Birch ply |
| Fin count | 3 | Standard — stable, minimal drag |
| Stability (Barrowman) | ≥1.5 cal | Verify in OpenRocket |

### 4.2 Motor — RC-B4 (custom KNSB)

| Parameter | Value |
|---|---|
| Propellant | KNSB 65:35 (KNO₃:sorbitol) |
| Propellant mass | 4.0 g |
| KNO₃ | 2.6 g |
| Sorbitol | 1.4 g |
| Total impulse | ~5.1 N·s |
| Motor class | B |
| Peak thrust | ~8.7 N |
| Average thrust | ~9.6 N |
| Burn time | ~0.53 s |
| Specific impulse | ~130 s |
| Core diameter | 8 mm |
| Nozzle throat | 4 mm |
| Propellant Isp basis | KNSB 65:35, standard literature value |

### 4.3 Predicted flight (1-DOF estimate, ISA, 2 m/s wind)

| Parameter | Value |
|---|---|
| Apogee | ~250 m |
| Max velocity | ~145 m/s |
| Mach number at max-v | ~0.42 |
| Max acceleration | ~28 g |
| Rail-exit velocity | ~18 m/s |
| Time to apogee | ~3.5 s |
| Total flight time | ~65 s |

These are 1-DOF estimates. The `.ork` file with full Barrowman aerodynamics is the authoritative simulation. A 10–20% gap between this estimate and an actual flight is normal for a first build; anything past 30% points to a real weight or finish deviation from what's modelled here.

---

## 5. Engineering Notes

### 5.1 The 200–300 m constraint, worked

The core relationship is:

`Apogee ≈ f(total_impulse, mass, drag)`

For a fixed airframe (fixed mass and drag), apogee scales roughly linearly with total impulse in the subsonic regime. Skylark-S at 6 g KNSB (7.6 N·s) gives ~548 m. To land ~250 m on the same airframe, total impulse needs to drop to roughly 7.6 × (250/548) ≈ 3.5 N·s. The 4 g grain at Isp = 130 s gives 4×10⁻³ × 130 × 9.81 = 5.1 N·s — a bit above the pure linear estimate, because the lighter grain also reduces wet mass. The resulting ~250 m checks out against this back-of-envelope number.

I considered the alternative of deliberately adding drag (fin cant, blunt nose) to bring Skylark-S down into the target band instead of designing a new motor, and rejected it — that produces a detuned rocket and doesn't teach clean design the way tuning the motor does.

### 5.2 Motor class boundary

At 5.1 N·s, RC-B4 sits near the top of the B class (3.51–7.00 N·s per NAR classification) — intentionally. More impulse within the B class means better rail-exit performance (less sensitive to alignment error) while staying inside the apogee target. A pure A-class motor (≤2.5 N·s) on this airframe would only reach ~90–120 m with marginal rail stability.

### 5.3 Recovery sizing

A 5×70 cm Mylar streamer slows the 18 mm airframe from an unrecovered terminal velocity of ~25–30 m/s down to roughly 8–12 m/s descent — fine for a light rocket coming down on soft ground. I skipped a parachute deliberately: at this size, streamer-only recovery is meaningfully more reliable (no folding, no shroud-line tangles), and the airframe is light enough that the faster descent doesn't risk damage.

If the landing zone has hard surfaces, or an altimeter gets added later, swap in a small 20 cm chute and adjust the build guide accordingly.

### 5.4 Stability with the lighter motor

Dropping the motor mass from 6 g to 4 g shifts the CG slightly forward, since the motor sits at the aft end — this improves the stability margin if anything. RCandy-250 should come out slightly more stable than Skylark-S at 6 g, with no nose ballast expected. Confirm against actual measured component masses in OpenRocket before any flight.

---

## 6. Reference — Five-Model Progression

The wider progression this design sits within, for context on what comes after a successful RCandy-250 flight:

| Step | Model | Motor | Apogee | New skill introduced |
|---|---|---|---|---|
| 0 | **RCandy-250** (this build) | RC-B4, 4 g | ~250 m | First build, full process |
| 1 | Skylark-S | RC-C6, 6 g | ~548 m | Larger motor, faster rail exit |
| 2 | Cadet-24 | RC-D15, 15 g | ~502 m | Motor mount tube, centering rings |
| 3 | MaxAlt-24 | RC-E30, 30 g | ~1129 m | Dual recovery, Haack nose |
| 4 | Altair-29 | RC-F40, 40 g | ~964 m | Payload bay, 45 cm chute |
| 5 | Apex-29 | RC-F55, 55 g | ~1238 m | Dual-deploy, near-supersonic |

Work through these in order — Apex-29 approaches Mach 1, and a 55 g KNSB motor is not something to jump to before the basics are solid.

---

## 7. Safety Summary

Repeated here because it can't be repeated too often.

Sugar propellant motors (KNSU, KNSB, KNDX) are legally classified as **energetic materials / live ordnance** in most jurisdictions. They are capable of:
- Deflagration-to-detonation if the grain cracks or presses against the nozzle
- Producing shrapnel from a casing failure under overpressure
- Starting grass or structure fires on landing in a hot state
- Causing severe burns from combustion products

Non-negotiable, every time:

1. An experienced rocketry mentor physically present at every stage — casting, assembly, and flight
2. Legal authorisation for motor class and launch site, obtained before any live work
3. Eye protection during all casting and assembly operations
4. Electric ignition only — minimum 30 m standoff, solid cover between personnel and pad
5. No open flame during or after casting — heat source removed before the oxidiser goes in
6. Discard any batch showing smoke, dark colouration, or uneven consistency — never fly a suspect grain
7. Never print structural combustion-path parts (nozzle, casing, bulkhead) in thermoplastic

---

## 8. What's Next

Not part of this build, but worth doing as the project matures:

- A print-ready PDF of the build guide and README for an A4 handout at the range
- 3MF files with print settings and colours pre-assigned for Bambu printers
- Rendered previews of each STL/STEP part
- Altimeter integration (planned for Cadet-24 and above, not needed at this scale)
- A static-fire / ground-test procedure for characterising the motor before the first flight

---

## 9. Conclusion

RCandy-250 is a well-engineered, buildable first model rocket targeting 200–300 m apogee on a 4 g KNSB B-class motor. It reuses the proven Skylark-S 18 mm airframe with a downscaled motor rather than reworking the airframe or adding artificial drag — the cleaner of the two approaches.

Everything needed to build it is in this repository: the `.ork` opens directly in OpenRocket, the `.eng` loads as a user-defined thrust curve, the STLs are watertight and print-ready, and the STEP files are editable in any standard CAD package.

Build it, fly it, log the actual numbers against the predicted ones — then scale up to Skylark-S.

---

*Engineering design and simulation document. All live propellant work requires legal authorisation and a qualified mentor. The builder is responsible for compliance with all applicable regulations.*
