# RCandy-250 — Complete Build Guide
**Target: 200–300 m apogee · KNSB 65:35 · 18 mm airframe**
**Version:** 1.0 · 2026-06-16 · First build edition

---

## Before You Start

Read this entire document once before touching any material. Know where every step is going before you begin the first one. This is not a microwave — rocketry rewards patience and penalises rushing.

**What you need before Day 1:**

- An experienced rocketry mentor physically present — non-negotiable
- Legal clearance to build, cast, and fly a B-class sugar motor in your jurisdiction
- All materials sourced and verified (see BOM in README)
- Dedicated casting equipment that will never be used for food again
- A calibrated thermometer for propellant casting (type K thermocouple preferred)
- Remote electric ignition system — minimum 30 m of firing wire

---

## Phase 1 — Materials & Verification

### Step 1.1 — Weigh everything first

Before any cutting or gluing, weigh each material. The simulation was built around specific component masses. Deviations shift the CG and directly affect stability and apogee. Log every measured weight — you will need these numbers when you re-simulate the finished rocket.

Target component masses (RCandy-250):

| Component | Target mass |
|---|---|
| Nose cone (3D-printed PLA, ~70 mm) | 5–8 g |
| Body tube (phenolic, 210 mm, 18 mm ID) | 12–16 g |
| 3 fins (birch ply, 2.0 mm) | 3–5 g total |
| Motor mount tube (70 mm, 18 mm OD inner fit) | 3–5 g |
| Kevlar shock cord (40 cm) | ~1 g |
| Streamer (5×70 cm Mylar) | ~2 g |
| Launch lug (3D-printed) | ~2 g |
| KNSB grain + casing | ~12–15 g |

Total all-up weight should be in the range of **40–55 g unfuelled**. The simulation assumed ~48 g wet. If your build is significantly heavier, re-simulate before committing to the motor.

### Step 1.2 — Inspect all materials

- Body tube: check for ovality. Roll it on a flat surface — any wobble indicates a warped tube that will cause fin alignment problems. Reject and replace.
- Plywood: look for voids in the ply layers. Hold it up to a light. A void in the fin root zone is a stress concentration that will fail under fin loads. Reject if voids present.
- Nose cone print: check shoulder fit in tube — it should slide with light hand pressure, not rattle, not require force.

---

## Phase 2 — Tube Preparation

### Step 2.1 — Cut body tube

Cut the body tube to exactly **210 mm**. Use a tube-cutting jig (a hobby miter box works) or wrap a strip of paper tightly around the tube as a cutting guide and score with a razor knife, rotating slowly. The cut face must be square — check with a machinist's square.

**Alternatives if you don't have a miter box:** wrap a square piece of paper tightly at the cut line; the paper edge becomes your guide. Rotate the tube while scoring with one light pass per revolution, deepening gradually. Never try to cut through in one pass — it crushes phenolic tubes.

### Step 2.2 — Seal and finish the bore

Sand the outer surface to 220 grit, then to 400. Apply one thin coat of sanding sealer or diluted PVA glue (3:1 PVA:water) — this closes the cardboard pores and gives the paint a solid base. Let dry completely (~2 hours). Sand lightly to 400 again when dry.

Do not seal the inner bore — motor mount needs bare cardboard for adhesion.

---

## Phase 3 — Fin Fabrication

### Step 3.1 — Lay out the fin shape

This pack doesn't ship a printable paper template — laying the fin out by hand from the dimensions below takes a few minutes and is just as accurate.

Fin dimensions (trapezoidal, airfoil section):
- Root chord: 45 mm
- Tip chord: 20 mm
- Sweep length: 25 mm (leading edge offset)
- Semi-span (height): 30 mm
- Thickness: 2.0 mm birch ply

On a piece of stiff card (cereal-box weight or heavier):

1. Draw a 45 mm baseline — this is the root chord.
2. At the leading-edge end of the baseline, draw a line perpendicular to it, 30 mm long — this is the span line.
3. From the top of the span line, measure 25 mm in the sweep direction, then draw a 20 mm tip chord parallel to the root.
4. Join the four corners (root leading edge → tip leading edge → tip trailing edge → root trailing edge) to close the trapezoid.
5. Cut out the card template and check all four edge lengths with a ruler before tracing it onto the ply — small errors here multiply across three fins.

If you have access to a 3D printer or CAD software, `step/fin.step` has the exact geometry and can be sliced flat for a precise printed template instead.

### Step 3.2 — Cut fins from ply

Trace the template onto 2.0 mm birch plywood, grain running parallel to the root chord (stronger in the bending direction). Cut with a fine-tooth saw or sharp hobby knife and straightedge. Cut all three from the same sheet for consistent grain.

**Stack-sand the three fins together:** clamp all three on top of each other with the root edges aligned, then sand as a stack on a flat surface with 80-grit paper. This guarantees all three fins are dimensionally identical — critical for symmetric stability.

### Step 3.3 — Airfoil the leading and trailing edges

Clamp each fin upright in a vise. Using 120-grit sandpaper on a flat block:
- Leading edge: round to a roughly elliptical cross-section — about 40% round from the front
- Trailing edge: taper to a fine edge (2:1 taper), stopping at about 0.3 mm thickness — do not feather to zero or it will chip
- Root chord: leave flat and square — this is the gluing surface

Smooth all surfaces to 220 grit.

**Alternative if you lack a vise:** hold the fin flat on the table, sand the edges freehand with a sanding block. Takes more care to keep the sanding symmetric, but works.

---

## Phase 4 — Marking the Tube

### Step 4.1 — Make a tube wrap from a paper strip

No printable template ships with this pack either — a hand-made paper strip works just as well.

1. Cut a strip of paper exactly as long as the tube's circumference (π × 18 mm ≈ 56.5 mm) and at least 30 mm wide.
2. Mark the strip into three equal segments of 56.5 / 3 ≈ **18.8 mm** each — these become the three 120°-spaced fin lines.
3. Add a fourth mark for the launch lug line, positioned between any two fin lines.
4. Wrap the strip snugly around the tube and confirm the two ends meet cleanly with no gap or overlap. If they don't line up, your circumference measurement was off — remeasure the tube's actual outer diameter and recut the strip.

### Step 4.2 — Transfer fin lines

Wrap the strip around the tube with its base at the aft end of the tube. Tape in place. Use a sharp pencil or fine marker to transfer the three fin station marks and the launch lug mark onto the tube. Remove the strip. Use a long ruler or a straightedge to extend each fin line all the way down the tube — fins must align with the body axis, not cant.

Double-check the spacing once the lines are drawn: measuring around the tube's surface, each fin line should land ~18.8 mm from the next. Confirm this before gluing anything.

---

## Phase 5 — Motor Mount Assembly

### Step 5.1 — Prepare the motor mount tube

The motor mount tube (inner tube, ~70 mm long, OD to fit inside body tube) should slide into the aft end of the body tube until it is flush with the aft face. Mark this position.

### Step 5.2 — Positive motor retention

**Critical:** you need a way to prevent the motor from ejecting forward under thrust, and another to prevent it from sliding back during coast. The aft face of the motor tube is the aft mechanical stop. For forward retention: a small peg through the tube wall (a toothpick stub with epoxy) or a commercial retainer ring is fine for this motor class.

For a first build: a tightly-fitting friction plug made from a short tube-within-tube arrangement with a wrapping of masking tape around the motor casing to achieve a snug fit is acceptable — **but** it must not slip under motor thrust.

### Step 5.3 — Glue motor mount into body tube

Apply a ring of 30-minute epoxy around the outside of the motor mount tube at the aft end. Slide it into position — aft face flush with aft end of body tube. Hold in a vertical jig (a piece of foam or V-block works) for the full 30-minute cure time. Do not use fast-set epoxy for structural joints.

---

## Phase 6 — Fin Attachment

### Step 6.1 — Set up the alignment jig

Print `fin_alignment_jig.stl`. Slide the body tube into the jig — it holds the tube in a fixed position while allowing you to press fins against it at the correct angle.

Alternatively (no printer): make a fin-bonding jig from two right-angle blocks clamped to a table, with the tube resting in a V-groove between them. The right angles ensure fins go on perpendicular to the body axis.

### Step 6.2 — First epoxy pass — tack bond

Mix a small amount of epoxy. Apply a thin bead to the fin root chord surface. Press the fin against the tube on the marked line, perpendicular to the body axis. Check squareness from the front (fin should be in the plane containing the tube axis, not canted). Hold for the full cure time.

Apply all three fins in the same session if possible — it forces you to maintain consistent technique.

### Step 6.3 — Root fillets — structural bond

After the tack bonds are fully cured (minimum 4 hours, ideally overnight), apply the structural fillet. Mix a slightly thickened epoxy (add a small amount of microballoons, wood flour, or colloidal silica if available — thickened epoxy bridges better and doesn't run). Using a round rod or a gloved fingertip, run a 3 mm radius fillet along both sides of every fin root.

**The fillet is the primary load path** — do not skip it. A fin bonded only at the root face will peel off under aerodynamic load or land-impact shock.

Let fillet cure for at least 8 hours before handling.

---

## Phase 7 — Launch Lug

Print `launch_lug.stl` in PETG. Drill the hole to match your launch rail rod diameter (standard sizes: 6 mm or 8 mm rod; confirm with whoever owns the launcher).

Glue the lug to the tube on the marked lug line, approximately 1/3 of the way from the nose end. Two-part epoxy, full cure. Lug must be parallel to the tube axis — any angle and the rocket will jump sideways off the rail.

---

## Phase 8 — Recovery System

### Step 8.1 — Shock cord anchor

Tie the Kevlar shock cord to a sturdy anchor point at the top of the motor mount tube — around a motor mount ring or through a hole drilled in the tube wall. Kevlar handles the ejection shock; nylon cord (paracord) can be used for the outer streamer line.

### Step 8.2 — Streamer

Cut a 5×70 cm strip of Mylar film (available as gift wrapping or party supply). Crinkle it lightly — a crinkled streamer opens more reliably than a flat one and tumbles more dramatically to slow the descent.

Attach the streamer to the free end of the Kevlar cord with a lark's head knot or a small crimped loop.

### Step 8.3 — Nose cone fit

The nose cone should fit into the body tube shoulder with light friction — enough to hold it during high-speed flight without ejecting, but not so tight that it cannot be blown out by the ejection charge. Test fit dry first.

For a streamer-only recovery, the ejection charge (from the motor delay) must be timed to fire near apogee — when velocity is near zero — so that inertia does not prevent nose separation.

---

## Phase 9 — Finish

### Step 9.1 — Surface preparation

Sand the entire airframe to 400 grit. Apply a thin coat of sandable primer (rattle-can auto primer works). Let dry 2 hours, sand to 400 again. Apply final primer coat. Sand to 600.

### Step 9.2 — Paint and clear coat

Apply your chosen topcoat colour in 2–3 thin passes. A high-visibility orange or yellow is strongly recommended for easy recovery in grass. Apply 2 coats of clear coat. Sand lightly with 1500 wet-and-dry between clear coats. Polish with a fine cutting compound for minimum aerodynamic drag.

**Surface finish directly affects apogee** — a polished finish can gain 5–10% over a rough one on a small, slow rocket like this.

---

## Phase 10 — Pre-Flight Simulation

### Step 10.1 — Load motor thrust curve

In OpenRocket:
- Preferences → User-defined thrust curves → Add file
- Select `RCandy_B4_RC-B4.eng`
- Click OK and restart OpenRocket

### Step 10.2 — Open and update the design

- File → Open → `RCandy_250m.ork`
- Update any component masses to match your actual measured weights
- Check: is total rocket mass close to your weighed-up finished rocket?

### Step 10.3 — Run simulation and verify

Click Simulate. Check the two critical numbers:

**Stability margin: must be ≥ 1.5 cal** — if less, add nose ballast (a steel nut or two) until it meets the threshold.

**Rail-exit velocity: must be ≥ 15 m/s** — if less, use a longer rail or add a slightly larger motor. Below 15 m/s, wind can tip the rocket before the fins generate enough restoring force.

If both pass: you have a sim-verified design. Record the predicted apogee.

---

## Phase 11 — Propellant Casting

**This phase must be done with a qualified mentor present. No exceptions.**

### Step 11.1 — Equipment setup

You need: a dedicated stainless steel or aluminium pan (never used for food again), a stirring rod, a calibrated thermometer, the coring rod (8 mm diameter, pre-lubricated with release agent — petroleum jelly or Teflon spray), a motor casing pre-cleaned and dry, and a fire extinguisher within reach. Work outdoors or in a very well-ventilated space. No open flames within 3 metres.

### Step 11.2 — Measure and prepare

Weigh out exactly:
- KNO₃: **2.6 g** (potassium nitrate, ground to fine powder)
- Sorbitol: **1.4 g**

Grind the KNO₃ alone, separately — never grind the mixed propellant. Fine particle size improves mixing and burn consistency.

### Step 11.3 — Melt the sorbitol

Add sorbitol to the pan. Heat gently — keep the thermometer probe in the melt. Sorbitol melts cleanly at ~110 °C. Stop heat at 115 °C maximum. Do not overshoot: above 120 °C the sorbitol starts to caramelise and the mix becomes unpredictable.

### Step 11.4 — Add oxidiser and cast

With the pan off the heat source, stir in the KNO₃ powder gradually while stirring continuously. The mixture will become a smooth, uniform paste — the colour of milky coffee. If it smokes, browns sharply, or smells acrid: set it down, back away, let it cool completely, then dispose by dissolving in water. Do not try to salvage a bad batch.

Good batch: uniform paste, no streaks, no smoke. Pour into the motor casing around the coring rod. Tap the casing gently on the table several times to release bubbles. Do not compress or ram the propellant.

### Step 11.5 — Cure and inspect

Allow the grain to cool to room temperature (minimum 30 minutes). Extract the coring rod while still slightly warm — before the grain fully hardens. Inspect: no cracks, no voids, no bubbles in the core surface. Any crack is a pressure failure waiting to happen — discard and recast.

---

## Phase 12 — Motor Assembly

**All motor work with mentor present. Never use friction fit for propellant retention.**

1. Slide the cured grain into the motor casing, core facing aft toward the nozzle
2. Seat the graphite nozzle — 4 mm throat diameter — and secure per your casing design
3. Apply a short delay element (pre-made pyrotechnic delay, or timed ejection) calibrated to ~3–4 seconds — this fires the ejection charge near apogee
4. Seat the forward bulkhead / ejection charge housing
5. Fit the electric igniter (e-match) into the nozzle throat — do not short the leads, tape them together until range day

---

## Phase 13 — Range Day

### Checklist (complete in order, no shortcuts)

- [ ] Launch site: open field, no overhead hazards, informed bystanders cleared
- [ ] Rail set up: 1 m long, 5–10° from vertical, pointed downwind if any wind present
- [ ] All personnel briefed on safe distances and igniter discipline
- [ ] Motor installed, nose cone seated, recovery system packed and tangle-free
- [ ] Continuity check on igniter leads — go/no-go before arming
- [ ] All personnel ≥30 m behind cover
- [ ] Arm the firing circuit at the controller
- [ ] Count down verbally: 5-4-3-2-1-Ignition
- [ ] Fire, observe flight, note actual peak altitude if altimeter fitted

### Post-flight

- Recover the rocket — do not approach until it has been on the ground for 30+ seconds (motor cool-down)
- Check for fin damage, tube integrity, and motor retention
- Log: actual apogee (altimeter or visual estimate), motor burn appearance, recovery deployment
- Compare actual vs simulated apogee — the ratio tells you how accurate your mass estimate was

---

## Alternatives & Substitutions

| Original spec | Alternative | Notes |
|---|---|---|
| Phenolic cardboard tube | Mailing tubes, kraft tube | Check ID/OD — must match nose shoulder |
| 2.0 mm birch ply | 2.0 mm basswood sheet | Lower density — re-weigh and re-sim |
| PLA nose cone (printed) | Balsa nose cone (hand-carved) | Traditional method, lighter |
| Mylar streamer | Plastic bag cut into strip | Free — works fine for this altitude |
| Epoxy (30-min) | Epoxy (5-min) for tack only | Use 30-min for structural fillets |
| Graphite nozzle (machined) | Steel ERW nozzle (machined) | Graphite preferred; both are valid |
| OpenRocket (PC/Mac) | OR-Lite (Android) | Same calculation engine on mobile |

---

## Troubleshooting

**Rocket unstable in simulation (< 1.5 cal):** Add mass to the nose — steel nuts, lead shot, or modelling clay sealed inside the nose cone. Start with 2 g, re-simulate, repeat.

**Rail-exit velocity too low (< 15 m/s):** Use a longer rail (go to 1.5 m) or increase motor impulse (use Skylark motor RC-C6 instead of RC-B4 — apogee will rise to ~400–500 m).

**Fins not square:** The alignment jig prevents this. If you built without a jig and a fin is canted, carefully cut the fillet with a razor, re-square, and re-fillet. A canted fin causes a persistent roll or weathercock tendency.

**Nose cone too loose:** Wrap 1–2 layers of masking tape around the shoulder until friction fit is correct.

**Nose cone too tight:** Sand the shoulder lightly with 220 grit. Test frequently — you want a snug push-fit, not a permanent bond.

**Propellant batch looked good but didn't ignite:** Check e-match continuity. Check nozzle is not blocked by excess casting material. Do not disassemble a loaded motor at the range — consult your mentor.

---

## Contacts & Resources

- **OpenRocket:** openrocket.info (free, cross-platform)
- **UKRA / NAR / ISRO-affiliated clubs:** for legal launch sites and mentor network
- **Nakka Rocketry:** nakka-rocketry.net — the definitive reference for KNSB propellant theory
- **ThrustCurve.org:** community motor database and `.eng` format reference

---

*This document is an educational engineering reference. All live work must be conducted under appropriate legal authority with a qualified mentor. The builder assumes full responsibility for compliance with applicable laws and safety practices.*
