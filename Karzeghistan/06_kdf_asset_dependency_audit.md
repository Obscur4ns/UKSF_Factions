# UKSF_Factions — KDF Asset & Dependency Audit

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** KDF Asset & Dependency Audit  
**Status:** Active / Pre-production Audit  
**Created:** 2026-08-09  
**Faction:** Karzeghistani Defence Forces (`KDF`)  
**Related design standard:** `05_kdf_organisation_roles_equipment_standard.md`

---

# 1. Purpose

This document maps the agreed KDF equipment requirements against the currently identified project source pools:

- Arma 3 vanilla;
- RHS: USAF;
- RHS: AFRF;
- RHS: GREF;
- 3CB BAF;
- CUP;
- future private/donated/original assets.

It is intended to answer four questions for every major KDF asset:

1. **What asset family best fits the KDF design?**
2. **Where can it come from?**
3. **Should that source remain a runtime dependency or be adapted/internalised?**
4. **Is the dependency cost justified by the gameplay value?**

This is a source-selection audit, not yet the final implementation classname list.

Exact `CfgPatches.requiredAddons[]` names must be confirmed from the actual selected classes/PBOs before config implementation.

---

# PART I — AUDIT TERMINOLOGY

## 2. Integration Routes

### `VANILLA`

Use an Arma 3 asset directly or through a lightweight project retexture/config variant.

No third-party runtime dependency.

### `RUNTIME`

Reference/inherit the source mod's public class at runtime.

The source mod remains required.

### `INTERNALISE`

Use an asset as an authorised source/adaptation base and place the resulting approved project-owned runtime asset inside `UKSF_Factions`.

This route requires:

- project permission/provenance record;
- source-file audit;
- dependency removal check;
- config cleanup;
- optimisation review;
- complete credits.

### `REFERENCE`

Use only as visual/technical reference.

Do not ship its data.

### `DEFER`

No sufficiently good or dependency-efficient candidate is currently selected.

---

## 3. Candidate Grades

### `A — Preferred`

Strong visual/technical fit with acceptable dependency cost.

### `B — Good`

Useful but requires adaptation, further inspection or a design compromise.

### `C — Fallback`

Technically usable but weak visual fit or high dependency cost.

### `REJECT`

Do not use for this role unless the design changes substantially.

---

# PART II — EXECUTIVE DEPENDENCY DECISION

## 4. Recommended KDF Runtime Dependency Core

### Hard content dependencies

Recommended:

```text
RHS: USAF
RHS: AFRF
```

plus:

```text
Arma 3 base game
UKSF_Factions internal PBOs
```

This pair can cover most of the first-release KDF weapon and major vehicle requirements.

---

## 5. Recommended Non-Dependencies

Do **not** make KDF require, by default:

```text
RHS: GREF
3CB BAF Vehicles
3CB infantry/equipment packs
CUP Weapons
CUP Units
CUP Vehicles
ACE3
ACRE2
```

Those packages may still be:

- source references;
- adaptation sources where permission allows;
- optional compatibility targets.

---

## 6. Why RHS USAF + AFRF

KDF deliberately uses a mixed:

```text
Western 5.56 / support weapons
+
AK / PKM / RPG legacy
```

inventory.

RHS USAF publicly contains weapon families including:

```text
M16A4
M4
M249
M240
Mk-14 EBR
SR-25
M136 AT-4
FGM-148 Javelin
FIM-92F Stinger
```

and includes major KDF-relevant vehicles such as:

```text
M113A3
UH-60M
M1025A2 HMMWV
```

RHS AFRF supplies the Eastern weapon families needed for the KDF legacy/regional component.

Because the wider `UKSF_Factions` project is also likely to use RHS heavily for Takistani/NTEF/TNR equipment, the dependency cost is shared across multiple factions rather than being KDF-only.

---

# PART III — RHS GREF DECISION

## 7. Default Status

```text
RHS GREF → DO NOT REQUIRE FOR KDF
```

---

## 8. Reason

RHS GREF itself requires both:

```text
RHS AFRF
RHS USAF
```

Therefore adding GREF after those two packages is justified only where it supplies a genuinely valuable asset that cannot be reproduced more cleanly elsewhere.

For the current KDF requirement list, no such mandatory asset has yet been identified.

---

## 9. Policy

If a useful GREF asset appears later:

1. determine whether it is genuinely unique;
2. check whether the project has permission to adapt/internalise it;
3. compare against vanilla/RHS USAF/AFRF/private alternatives;
4. add a GREF runtime dependency only if the gameplay value clearly outweighs the package cost.

---

# PART IV — CUP DECISION

## 10. Default Status

```text
CUP → AVOID AS KDF RUNTIME DEPENDENCY
```

---

## 11. Dependency Cost

CUP's own FAQ states:

```text
Weapons requires CBA_A3
Units requires Weapons
Vehicles requires Units
```

Therefore:

```text
ONE CUP VEHICLE
```

can imply the runtime stack:

```text
CBA_A3
+
CUP Weapons
+
CUP Units
+
CUP Vehicles
```

This is contrary to the project's dependency-reduction objective where an equivalent KDF role can be filled from RHS, vanilla or an authorised internal asset.

---

## 12. CUP Repacking

CUP also explicitly states that smaller custom CUP repacks are not permitted.

Therefore:

```text
DO NOT
```

plan to solve dependency size by extracting one CUP vehicle into a KDF "lite" pack.

CUP remains:

```text
OPTIONAL / REFERENCE / LAST-RESORT RUNTIME SOURCE
```

under its normal terms.

---

# PART V — 3CB DECISION

## 13. Default Status

```text
3CB → SOURCE / ADAPTATION POOL
NOT BASE KDF RUNTIME DEPENDENCY
```

The project has direct permission to use/adapt relevant 3CB material.

---

## 14. Strong 3CB Vehicle Candidates

Published 3CB BAF Vehicles content includes:

```text
Husky TSV
Panther CLV
MAN HX58 / HX60
Land Rover
Bulldog
Jackal / Coyote
Merlin
Wildcat
Offshore Raiding Craft
```

Several of these map well to KDF requirements.

---

## 15. Why Not Runtime 3CB

KDF should not inherit a large British-content pack simply to obtain one:

- truck;
- protected vehicle;
- boat.

Where technically clean and covered by the project's permission, selected assets should instead be evaluated for:

```text
INTERNALISE
```

after a complete source/dependency audit.

This keeps the actual KDF modset lighter and prevents British faction identity leaking into Karzeghistani classes/configs.

---

# PART VI — CHARACTER ASSET AUDIT

## 16. Standard KDF Field Uniform

**Requirement:** fictional muted olive/tan/grey-brown transitional camouflage.

### Preferred route

```text
INTERNALISE / ORIGINAL RETEXTURE
Grade: A
```

### Candidate source

A conventional modern combat-uniform model from an approved RHS/3CB/private source.

### Why

Directly placing KDF troops in an existing US/UK camouflage uniform would destroy the faction's visual identity.

The model may be shared, but:

```text
KDF CAMOUFLAGE MUST BE ORIGINAL
```

### Action

Inspect approved source uniform models for:

- clean UV;
- usable hidden selections or source textures;
- acceptable LODs;
- section count;
- normal/specular maps;
- standard Arma man skeleton;
- no external proxy/material dependency that prevents clean integration.

---

## 17. RHS ACU Model

RHS USAF documents the Army Combat Uniform family.

### Assessment

```text
SOURCE MODEL: B
DIRECT KDF CLASS: REJECT
```

The cut is plausible for a Western-assisted partner force, but a direct US ACU/OCP class would make KDF read as US Army.

Best use:

```text
authorised model/retexture source
```

if the technical/source audit is clean.

---

## 18. Standard KDF Helmet

**Requirement:** conventional composite combat helmet.

### Preferred

```text
RHS ACH / MICH-type source
Route: INTERNALISE or RUNTIME-derived appearance
Grade: A/B
```

The standard KDF helmet should be:

- current-day;
- conventional;
- not overly SOF;
- easy to recolour/cover.

### Avoid

Universal high-cut helmets on Regular KDF.

---

## 19. Rapid Response / SOF Helmet

**Requirement:** modern mid/high-cut family.

### Status

```text
DEFER EXACT MODEL
Grade: B
```

Potential approved private/RHS/3CB source should be selected after local source inspection.

Do not add a new external gear pack solely for one high-cut helmet.

---

## 20. Standard Plate Carrier

**Requirement:** modern but not SOF-only plate carrier.

### Preferred route

```text
INTERNALISE FROM APPROVED SOURCE
Grade: A
```

Reason:

This is a high-instance KDF visual asset.

A project-owned carrier variant:

- avoids direct US/UK markings;
- can use Karzeghistani pouch layouts;
- avoids unnecessarily tying character identity to another faction mod.

---

## 21. RRF / SOF Carrier

### Preferred

Use the same base carrier family with:

- more pouches;
- comms;
- medical equipment;
- alternate front panels;

before sourcing an entirely separate model.

```text
Grade: A
```

This improves consistency and reduces unique geometry.

---

# PART VII — WESTERN SMALL ARMS

## 22. Primary Western 5.56 Rifle

### Preferred candidate

```text
RHS M4 family
Source: RHS USAF
Route: RUNTIME
Grade: A
```

Rationale:

- current-day;
- widely recognisable partner-force weapon;
- extensive attachment ecosystem;
- already within likely project dependency set.

Do not create a redundant `UKSF_Factions_Weapon_M4` wrapper merely to rename an RHS rifle.

Use the selected RHS public class directly in KDF loadouts.

---

## 23. M16A4

### Candidate

```text
RHS M16A4
Route: RUNTIME
Grade: B
```

Useful as:

- older donor weapon;
- reserve/training weapon;
- limited Regular KDF rifle.

Do not make it the defining 2026 KDF rifle.

---

## 24. Squad Automatic Weapon

### Preferred candidate

```text
RHS M249
Route: RUNTIME
Grade: A
```

Good fit for Western-armed Regular/RRF fire teams.

---

## 25. Western GPMG

### Preferred candidate

```text
RHS M240
Route: RUNTIME
Grade: A
```

Use primarily in:

- Rapid Response;
- better-equipped Regular units;
- vehicles where appropriate.

---

## 26. Western DMR

### Candidate pool

RHS USAF publicly includes:

```text
Mk-14 EBR
SR-25
```

### Recommendation

```text
Regular Western DMR → Mk-14 EBR candidate
RRF/SOF precision → SR-25 candidate
Route: RUNTIME
Grade: A/B
```

Final role selection should be tested in-game rather than assigning both widely.

---

# PART VIII — EASTERN / LEGACY SMALL ARMS

## 27. AK-74 Family

### Preferred source

```text
RHS AFRF
Route: RUNTIME
Grade: A
```

Core legacy/regional rifle component.

---

## 28. Modern AK

### Preferred source

```text
RHS AFRF
Route: RUNTIME
Grade: A
```

Exact model should be chosen during local class audit.

Do not proliferate six visually near-identical AK classes in KDF loadouts.

---

## 29. AKM

### Source

```text
RHS AFRF / approved RHS family
Route: RUNTIME
Grade: B
```

Use as minority legacy weapon.

---

## 30. PKM

### Preferred

```text
RHS AFRF
Route: RUNTIME
Grade: A
```

Maintains continuity with regional supply and distinguishes older Regular KDF sections from RRF.

---

## 31. SVD

### Preferred

```text
RHS AFRF
Route: RUNTIME
Grade: A
```

Regular/legacy marksman weapon.

---

## 32. RPG-7

### Preferred

```text
RHS AFRF
Route: RUNTIME
Grade: A
```

Legacy anti-armour weapon.

Use less frequently than in TNA/TNR/NTEF.

---

# PART IX — ANTI-ARMOUR / AIR DEFENCE

## 33. Disposable AT

### Preferred

```text
RHS M136 AT-4
Source: RHS USAF
Route: RUNTIME
Grade: A
```

Strong KDF Regular/RRF fit.

---

## 34. Guided AT

### Preferred

```text
RHS FGM-148 Javelin
Source: RHS USAF
Route: RUNTIME
Grade: A
```

Distribution:

```text
Regular → limited specialist
RRF → supported
SOF → mission dependent
```

---

## 35. MANPADS

### Preferred

```text
RHS FIM-92F Stinger
Source: RHS USAF
Route: RUNTIME
Grade: A
```

Specialist role only.

---

# PART X — SIDEARM

## 36. Service Pistol

### Status

```text
SELECT FROM EXISTING RHSUSAF POOL AFTER LOCAL CLASS AUDIT
Grade: B
```

Requirements:

- conventional service handgun;
- common calibre;
- no unique new dependency;
- visually contemporary.

Do not commission or import a unique KDF pistol unless a broader project need appears.

---

# PART XI — OPTICS / ACCESSORIES

## 37. Optic Strategy

Use RHS USAF/AFRF attachment ecosystems already required by the weapon pool.

### Recommendation

```text
NO NEW OPTICS MOD
```

KDF identity does not require a unique scope package.

---

## 38. Distribution

Regular:

- simple red-dot/holographic;
- low-power optic.

RRF:

- modern optic widespread.

SOF:

- modern optics plus specialist capability.

Exact models should follow selected rifles.

---

# PART XII — NIGHT VISION

## 39. Regular NVG

### Preferred strategy

Use an existing RHS/vanilla current-day monocular/binocular model already present in the chosen dependency stack.

```text
Grade: A/B
```

Do not add a separate NVG mod solely for KDF.

---

## 40. RRF / SOF NVG

Higher-capability NVG may be selected from the same RHS ecosystem if suitable.

Thermal remains:

```text
RARE / SPECIALIST
```

---

# PART XIII — RADIO

## 41. Baseline Faction Config

Base KDF should not require ACRE2 merely to exist.

Recommended baseline:

```text
ItemRadio
```

or normal game radio handling.

---

## 42. ACRE Integration

If the UKSF unit build requires actual ACRE radios, implement this through:

- mission/loadout framework;
- optional compatibility;
- later dedicated integration decision.

Do not add a hard ACRE requirement to the faction before the project-wide radio policy is defined.

---

# PART XIV — UTILITY 4×4

## 43. RHS M1025A2 HMMWV

RHS documents the M1025A2 armament-carrier HMMWV.

### Assessment

```text
Route: RUNTIME
Grade: A
```

Strong candidate for:

- older donor utility vehicle;
- weapons carrier;
- command/support role.

### Limitation

It reads strongly American if used universally.

Recommended:

```text
MINORITY / DONOR FLEET
```

rather than the sole KDF utility vehicle.

---

## 44. 3CB Land Rover

3CB provides:

- hard top;
- soft top;
- ambulance;
- Snatch;
- WMIK;
- civilian variants.

### Assessment

```text
Route: INTERNALISE candidate
Grade: B
```

Potential uses:

- older KDF utility fleet;
- KBG/KNP later;
- ambulance;
- command/support.

A selected clean Land Rover family could provide unusually high reuse across the whole project.

---

## 45. Vanilla Offroad

### Assessment

```text
Route: VANILLA
Grade: C
```

Useful:

- reserve;
- base transport;
- civil-support role.

Not suitable as the defining professional KDF vehicle.

---

# PART XV — PROTECTED MOBILITY / MRAP

## 46. RHS M-ATV Family

RHS has fielded M1240/M1245 M-ATV content in the USAF package.

### Assessment

```text
Route: RUNTIME
Grade: A
```

Strong candidate for:

- Rapid Response;
- Sharig patrol;
- protected mobility;
- high-threat convoy.

This is the clearest first-release protected vehicle if the current local RHS build contains the required variants.

### Required check

Confirm exact stable classnames locally before config work.

---

## 47. Vanilla Hunter

Arma 3's NATO Hunter is an M-ATV-like protected vehicle.

### Assessment

```text
Route: VANILLA / RETEXTURE
Grade: A-
```

Advantages:

- zero external dependency;
- strong current-day visual plausibility;
- hidden-selection/retexture potential;
- appropriate KDF role.

Disadvantage:

- strongly associated with vanilla NATO;
- near-future fittings may need art/config restraint.

### Recommendation

Keep as a serious alternative to direct RHS M-ATV inheritance.

---

## 48. 3CB Husky TSV

3CB describes the Husky as a medium-armoured tactical support vehicle with logistics/passenger and multiple protected-weapon-station variants.

### Assessment

```text
Route: INTERNALISE candidate
Grade: A/B
```

Very good Karzeghistani protected-mobility candidate if:

- British-specific markings/equipment can be cleanly removed;
- model dependencies can be separated;
- source package permissions cover required data.

---

## 49. 3CB Panther CLV

3CB Panther includes a protected 4×4 command/liaison vehicle with an RWS.

### Assessment

```text
Route: INTERNALISE candidate
Grade: A for command/recon
```

Excellent possible:

- command vehicle;
- reconnaissance vehicle;
- RRF liaison platform.

Do not use it as the universal troop carrier.

---

# PART XVI — LOGISTICS TRUCK

## 50. Preferred KDF Truck Direction

A single coherent medium-truck family is strongly preferred.

---

## 51. 3CB MAN HX58 / HX60

3CB provides:

```text
HX58
HX60
cargo
fuel
repair
transport
container/logistics variants
```

### Assessment

```text
Route: INTERNALISE candidate
Grade: A
```

This is one of the strongest 3CB source candidates in the entire KDF audit.

Why:

- contemporary;
- neutral enough to plausibly export;
- extensive logistics variants;
- strong reuse across KDF and potentially other future state factions.

### Recommendation

**Highest-priority 3CB source inspection.**

---

## 52. RHS FMTV Family

### Status

```text
Route: RUNTIME candidate
Grade: A/B
```

RHS USAF is expected to contain suitable US tactical-truck families.

Before locking this route:

- inspect current local RHS class list;
- compare cargo/fuel/repair/transport coverage;
- compare visual identity against MAN HX.

If 3CB MAN can be internalised cleanly, it is likely the better KDF-specific solution.

---

## 53. Vanilla HEMTT

### Assessment

```text
Route: VANILLA
Grade: C
```

Technically excellent but visually extremely US/NATO and heavier than KDF needs.

Use only as fallback/support if no better truck family is available.

---

# PART XVII — APC

## 54. First-Release Recommendation

### Preferred first-release APC

# RHS M113A3

```text
Route: RUNTIME
Grade: A
```

RHS documents:

- transport variant;
- M2 armament;
- capacity for 11 soldiers;
- M113 support-family potential.

This fits the agreed KDF donor/Western-assistance history.

---

## 55. Why M113 Works

It provides:

- strong current-day plausibility;
- donor-force character;
- visual contrast with TNA BMP-2;
- lower technological level than a latest-generation IFV;
- recognisable regional export history.

---

## 56. KDF M113 Presentation

Prefer KDF-specific faction variant with:

- Karzeghistani paint;
- national rosette;
- tactical numbers;
- KDF crew.

Implementation route can be either:

```text
KDF class inheriting RHS M113
```

or, if authorised/technically justified later:

```text
internalised project variant
```

Initial recommendation:

```text
RUNTIME INHERITANCE
```

because tracked-vehicle source extraction is substantially more complex than a simple retexture model.

---

## 57. Wheeled APC

**Design requirement:** desired eventually.

### Current status

```text
DEFER
```

No identified candidate currently offers a sufficiently strong combination of:

- 2026 plausibility;
- KDF identity;
- low dependency cost;
- clean authorisation path.

Do not force a mediocre wheeled APC into first release.

---

## 58. Vanilla Marshall

### Assessment

```text
Grade: C
```

Reasons:

- very capable;
- zero external dependency;
- but heavily associated with vanilla 2035 NATO;
- visually too high-end/general-purpose IFV for the KDF's preferred donor-light character.

Keep only as fallback.

---

## 59. CUP Wheeled APCs

CUP contains potentially useful vehicle families.

### Assessment

```text
Grade: REJECT FOR FIRST RELEASE
```

The dependency chain is too large for a role already covered adequately by the M113.

---

# PART XVIII — ARMOURED RECONNAISSANCE

## 60. Vanilla Strider

The vanilla AAF Strider is visually analogous to a contemporary European light reconnaissance vehicle.

### Assessment

```text
Route: VANILLA / KDF RETEXTURE
Grade: A
```

Very strong candidate for:

- reconnaissance;
- command;
- border reinforcement;
- RRF patrol.

Benefits:

- zero third-party dependency;
- already Armaverse-native;
- distinguishes KDF from TNA.

### Recommendation

**Preferred first-release armoured reconnaissance vehicle.**

---

## 61. 3CB Panther Alternative

If the Panther can be internalised cleanly, it is also excellent.

Choice should eventually compare:

```text
Strider → dependency-free / Armaverse
Panther → contemporary bespoke visual / more production work
```

---

# PART XIX — UTILITY HELICOPTER

## 62. RHS UH-60M

RHS documents an armed transport UH-60M and unarmed MEDEVAC variant.

### Assessment

```text
Route: RUNTIME
Grade: A
```

This is the strongest KDF utility-helicopter candidate.

It supports:

- troop movement;
- casualty evacuation;
- sling loading;
- partner-force identity.

---

## 63. Why Not Vanilla Ghost Hawk

### Assessment

```text
Grade: C
```

The UH-80 Ghost Hawk is too strongly associated with Arma 3's 2035 NATO aesthetic.

If RHS USAF is already required, the real-world UH-60M is a better 2026 fit.

---

## 64. 3CB Wildcat

3CB Wildcat supports transport and armed variants.

### Assessment

```text
Route: INTERNALISE candidate
Grade: B
```

Better suited to:

- light utility;
- reconnaissance;
- future armed helicopter.

It is not the preferred primary troop-lift helicopter.

---

## 65. 3CB Merlin

### Assessment

```text
Route: INTERNALISE candidate
Grade: B/C
```

Excellent aircraft but likely too large and too distinctly British for the KDF core fleet.

Could later represent:

- small heavy-lift fleet;
- government/VIP transport;
- specialised donor aircraft.

Not first-release priority.

---

# PART XX — LIGHT / ARMED HELICOPTER

## 66. Current Status

```text
DEFER
```

Potential future sources:

- authorised 3CB Wildcat adaptation;
- private/donated light helicopter;
- another project-owned source.

Do not add Apache solely because it exists in RHS/3CB.

KDF is not intended to field a major attack-helicopter fleet.

---

# PART XXI — UAS

## 67. Small Reconnaissance Drone

### Preferred

```text
Vanilla AR-2 Darter family
Route: VANILLA
Grade: A
```

Advantages:

- zero dependency;
- compact;
- reconnaissance-oriented;
- easy to faction-colour/configure.

This role does not require a unique KDF model.

---

## 68. 3CB Reaper

### Assessment

```text
Grade: REJECT FOR CORE KDF
```

Too high-end for the initial KDF UAS identity.

Could appear as foreign-partner capability in missions instead.

---

# PART XXII — MORTAR

## 69. RHS M252

RHS documents an M252 81 mm mortar.

### Assessment

```text
Route: RUNTIME
Grade: A
```

Good partner-force mortar and already contained in the proposed USAF dependency.

---

## 70. Vanilla Mk6 Mortar

### Assessment

```text
Route: VANILLA
Grade: A-
```

A strong zero-extra-dependency fallback.

### Recommendation

If no special RHS mortar behaviour is needed:

```text
prefer whichever integrates most cleanly with unit mission standards
```

Do not create a new KDF mortar model.

---

# PART XXIII — ARTILLERY

## 71. RHS M109A6

RHS provides the M109A6 Paladin.

### Assessment

```text
Route: RUNTIME
Grade: C
```

Technically high quality, but:

- visually very US-specific;
- heavier/more modern than KDF needs;
- artillery is already low priority.

### Decision

```text
NOT FIRST RELEASE
```

---

## 72. Towed Artillery

### Status

```text
DEFER
```

A future donor/legacy towed gun would fit KDF better than making the Paladin its standard artillery identity.

---

# PART XXIV — PATROL BOAT

## 73. 3CB Offshore Raiding Craft

3CB's ORC is a small fast craft carrying crew/passengers and GPMG/HMG variants.

### Assessment

```text
Route: INTERNALISE candidate
Grade: B
```

Potentially useful for:

- coastal patrol;
- harbour security;
- light maritime insertion.

### Limitation

It reads as a military raiding craft more than an ordinary coast-guard patrol boat.

---

## 74. Vanilla Boats

### Assessment

```text
Route: VANILLA
Grade: B
```

A vanilla RHIB/assault-boat solution is sufficient for first release if maritime content is included at all.

### Decision

```text
BOATS SHOULD NOT DELAY KDF RELEASE
```

---

# PART XXV — VEHICLE SUMMARY MATRIX

## 75. Recommended First-Release Vehicle Stack

| Role | Preferred | Route | Grade |
|---|---|---|---|
| Utility 4×4 | RHS HMMWV / later project utility | Runtime | A/B |
| Protected 4×4 | RHS M-ATV or vanilla Hunter | Runtime / Vanilla | A |
| Command/recon | Vanilla Strider | Vanilla | A |
| Logistics truck | 3CB MAN HX if cleanly internalised | Internalise | A |
| APC | RHS M113A3 | Runtime | A |
| Wheeled APC | Deferred | — | — |
| Utility helicopter | RHS UH-60M | Runtime | A |
| Light helicopter | Deferred / 3CB Wildcat candidate | Internalise | B |
| Small UAS | Vanilla AR-2 | Vanilla | A |
| Mortar | RHS M252 / vanilla Mk6 | Runtime / Vanilla | A |
| Patrol boat | Vanilla / 3CB ORC candidate | Vanilla / Internalise | B |
| Tank | Deferred | — | — |
| SP artillery | Deferred | — | — |

---

# PART XXVI — WEAPON SUMMARY MATRIX

## 76. Recommended First-Release Weapon Stack

| Role | Preferred source | Route | Grade |
|---|---|---|---|
| Western rifle | RHS M4 family | Runtime | A |
| Older Western rifle | RHS M16A4 | Runtime | B |
| Automatic rifle / SAW | RHS M249 | Runtime | A |
| Western GPMG | RHS M240 | Runtime | A |
| Regular DMR | RHS Mk-14 / SVD mix | Runtime | A/B |
| RRF precision | RHS SR-25 | Runtime | A |
| AK-74 | RHS AFRF | Runtime | A |
| Modern AK | RHS AFRF | Runtime | A |
| PKM | RHS AFRF | Runtime | A |
| SVD | RHS AFRF | Runtime | A |
| RPG-7 | RHS AFRF | Runtime | A |
| Disposable AT | RHS M136 AT-4 | Runtime | A |
| Guided AT | RHS FGM-148 | Runtime | A |
| MANPADS | RHS FIM-92F | Runtime | A |
| Pistol | existing RHSUSAF service pistol | Runtime | B |

---

# PART XXVII — PBO OWNERSHIP

## 77. `uksf_factions_characters`

Should own project-created reusable KDF-capable:

- uniform models/textures where generic;
- helmet models/textures where generic;
- plate carriers where generic.

It should **not** inherit external faction unit classes.

---

## 78. `uksf_factions_vehicles`

Should own genuinely internalised reusable vehicle assets such as a future:

- MAN HX family;
- generic utility vehicle;
- project-owned protected vehicle.

Do not place RHS-derived runtime inheritance here if that would force every faction using the shared vehicle PBO to load RHS unnecessarily.

---

## 79. `uksf_factions_kdf`

Should own:

- KDF faction config;
- KDF units/groups;
- KDF loadouts;
- KDF vehicle faction variants;
- KDF camouflage;
- KDF insignia/flag;
- classes inheriting directly from RHS/vanilla vehicles where appropriate.

This keeps third-party dependencies at the faction/leaf layer.

---

# PART XXVIII — PROBABLE DEPENDENCY GRAPH

## 80. Recommended

```text
Arma 3
   │
   ├── uksf_factions_core
   │
   ├── uksf_factions_characters
   │
   └── uksf_factions_vehicles
            │
            └────────────┐
                         │
RHS USAF ────────────────┤
RHS AFRF ────────────────┤
                         ▼
                  uksf_factions_kdf
```

Optional compatibility should sit outside this base chain where possible.

---

# PART XXIX — WHAT NOT TO DO

## 81. No External Wrapper Spam

Do not create:

```text
UKSF_Factions_Weapon_M4
UKSF_Factions_Weapon_M249
UKSF_Factions_Weapon_M240
```

if those classes are merely aliases of RHS public classes.

Reference the real weapon class in the KDF loadout.

---

## 82. Do Not Make Shared PBOs Carry Faction Dependencies

Avoid:

```text
uksf_factions_characters
requiredAddons[] += RHSUSAF
```

just because one KDF class uses an RHS rifle.

The KDF leaf PBO should own that dependency.

---

## 83. Do Not Add CUP for One Vehicle

The CUP dependency chain makes this particularly poor value.

---

## 84. Do Not Add GREF by Habit

RHS GREF is useful, but KDF does not currently need it.

---

## 85. Do Not Add Full 3CB Runtime for MAN HX

If the selected MAN source can be internalised cleanly under the project's permission, that is preferable.

If it cannot, compare RHS/vanilla alternatives before accepting a full 3CB vehicle dependency.

---

# PART XXX — SOURCE INSPECTION PRIORITY

## 86. Highest Priority Local PBO/Source Inspection

When the actual mod source pool is assembled, inspect in this order:

### 1. 3CB MAN HX58/HX60

Goal:

```text
Can this become the project-owned KDF logistics family?
```

### 2. Protected 4×4

Compare:

```text
RHS M-ATV
vanilla Hunter
3CB Husky
3CB Panther
```

### 3. Standard KDF uniform model

Need clean custom-camouflage base.

### 4. Standard helmet

Need regular non-SOF composite family.

### 5. Standard plate carrier

Need reusable KDF base carrier.

### 6. M113 implementation

Confirm:

```text
inherit RHS
vs
any authorised internalised alternative
```

### 7. UH-60M

Confirm exact transport/MEDEVAC classes and texture strategy.

---

# PART XXXI — LOCAL CONFIG AUDIT REQUIRED

## 87. Do Not Guess Exact `requiredAddons[]`

Before writing KDF `config.cpp`:

1. inspect selected public class with config viewer/dump;
2. identify its defining `CfgPatches` addon;
3. record that exact patch;
4. inspect weapon magazine dependencies;
5. inspect crew/proxy dependencies for vehicles;
6. add only actual required patches.

---

## 88. Classname Verification

The 3CB website provides exact current published class examples for MAN vehicles such as:

```text
UK3CB_BAF_MAN_HX58_Cargo_Green_A
UK3CB_BAF_MAN_HX58_Fuel_Green
UK3CB_BAF_MAN_HX58_Repair_Green
UK3CB_BAF_MAN_HX58_Transport_Green

UK3CB_BAF_MAN_HX60_Cargo_Green_A
UK3CB_BAF_MAN_HX60_Fuel_Green
UK3CB_BAF_MAN_HX60_Repair_Green
UK3CB_BAF_MAN_HX60_Transport_Green
```

These are **audit references**, not yet KDF implementation choices.

RHS exact classnames should likewise be read from the local current build rather than copied from an old third-party class list.

---

# PART XXXII — DEPENDENCY RISK TABLE

## 89. Packages

| Package | KDF status | Dependency risk | Reason |
|---|---|---:|---|
| Arma 3 vanilla | Required | None | Base game |
| RHS USAF | Hard candidate | Medium | High asset value across weapons/vehicles |
| RHS AFRF | Hard candidate | Medium | Core AK/PKM/SVD/RPG pool |
| RHS GREF | Avoid | Medium/High | Adds little mandatory KDF value |
| 3CB BAF Vehicles | Source candidate | High if runtime | Excellent selected assets, avoid full runtime where possible |
| CUP Weapons | Avoid | High | Begins CUP dependency chain |
| CUP Units | Avoid | High | Requires CUP Weapons |
| CUP Vehicles | Avoid | Very High | Requires Units → Weapons → CBA |
| ACE3 | Optional | Low/Medium | Gameplay compatibility, not KDF identity |
| ACRE2 | Optional | Low/Medium | Radio integration, not base faction requirement |

---

# PART XXXIII — FIRST-RELEASE MINIMUM

## 90. Characters

First release should not wait for every specialist gear model.

Minimum:

```text
1 KDF field uniform
1 standard helmet
1 standard plate carrier
1 RRF gear variant
1 SOF gear combination
```

---

## 91. Weapons

Minimum can be satisfied almost entirely through RHS:

```text
M4 family
M249
M240
AK-74 / modern AK
PKM
SVD / DMR
RPG-7
AT-4
Javelin
service pistol
```

---

## 92. Vehicles

Recommended minimum:

```text
1 utility 4×4
1 protected 4×4
1 armoured recon vehicle
1 logistics truck family
1 M113 APC
1 UH-60M utility helicopter
1 small UAS
1 mortar
```

No tank, fast jet or SP artillery is needed to call the KDF faction complete.

---

# PART XXXIV — CURRENT RECOMMENDED SOLUTION

## 93. KDF v1 Candidate Stack

### Characters

```text
Project-owned KDF uniform texture/model variant
Project-owned regular helmet variant
Project-owned plate-carrier variants
RHS/approved source geometry where technically appropriate
```

### Weapons

```text
RHS USAF
+
RHS AFRF
```

### Light vehicles

```text
RHS HMMWV
+
vanilla Strider
+
RHS M-ATV or vanilla Hunter
```

### Logistics

Preferred:

```text
internalised 3CB MAN HX family
```

Fallback:

```text
RHS tactical truck family
```

### APC

```text
RHS M113A3
```

### Air

```text
RHS UH-60M
```

### UAS

```text
Vanilla AR-2
```

### Mortar

```text
RHS M252
or
vanilla Mk6
```

---

# PART XXXV — LOCKED AUDIT DECISIONS

## 94. Locked

- KDF should target RHS USAF + RHS AFRF as its only hard third-party content dependencies.
- Exact RHS `CfgPatches` addon names remain deferred until selected classes are inspected locally.
- RHS GREF is not a default KDF dependency.
- CUP is not a default KDF dependency.
- CUP Vehicles is especially poor value for KDF because it requires CUP Units, which requires CUP Weapons, which requires CBA.
- Do not create a custom stripped CUP package.
- 3CB BAF Vehicles is treated primarily as an authorised source/adaptation pool rather than a KDF runtime requirement.
- The 3CB MAN HX58/HX60 family is the highest-priority 3CB source candidate.
- 3CB Husky and Panther are strong protected-vehicle/command-vehicle source candidates.
- 3CB ORC is an optional maritime source candidate.
- KDF character identity should use project-owned camouflage/markings rather than direct US/UK uniform classes.
- RHS M4 is the preferred Western rifle family.
- RHS M249 is preferred Western squad automatic weapon.
- RHS M240 is preferred Western GPMG.
- RHS AFRF supplies the preferred AK/PKM/SVD/RPG legacy family.
- RHS AT-4 is preferred disposable AT.
- RHS Javelin is preferred guided AT.
- RHS Stinger is preferred MANPADS.
- RHS M113A3 is the preferred first-release KDF APC.
- A wheeled APC is deferred rather than forcing a poor dependency/design choice.
- Vanilla Strider is the preferred dependency-free armoured reconnaissance candidate.
- RHS UH-60M is the preferred utility helicopter.
- Small UAS should initially use vanilla assets.
- Tanks, fast jets and SP artillery are not first-release requirements.
- Base KDF should not hard-require ACE3 or ACRE2.
- Third-party dependencies should remain at the KDF/leaf PBO level wherever practical.
- Shared project PBOs should not gain RHS/3CB dependencies merely because KDF uses those mods.
- Do not make redundant UKSF wrapper classes for third-party weapons solely for renaming.

---

# PART XXXVI — OPEN TECHNICAL AUDIT ITEMS

## 95. Required Before Asset Integration

- [ ] Inspect actual RHS USAF PBO/class tree.
- [ ] Inspect actual RHS AFRF PBO/class tree.
- [ ] Record exact selected weapon classnames.
- [ ] Record exact selected vehicle classnames.
- [ ] Record exact defining `CfgPatches` names.
- [ ] Inspect RHS M-ATV variants.
- [ ] Compare RHS M-ATV against vanilla Hunter.
- [ ] Inspect 3CB MAN source hierarchy/materials/scripts.
- [ ] Determine whether MAN HX can be cleanly internalised.
- [ ] Inspect 3CB Husky source dependencies.
- [ ] Inspect 3CB Panther source dependencies.
- [ ] Inspect potential KDF uniform source models.
- [ ] Inspect regular helmet source candidates.
- [ ] Inspect plate-carrier source candidates.
- [ ] Confirm M113 hidden selections/texture route.
- [ ] Confirm UH-60M texture/marking route.
- [ ] Decide exact service pistol.
- [ ] Decide exact western DMR.
- [ ] Decide exact modern AK model.
- [ ] Decide whether KDF uses RHS M252 or vanilla Mk6.
- [ ] Decide whether first release includes maritime craft.
- [ ] Add each selected/integrated asset to `asset_register.md`.

---

# PART XXXVII — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## Red Hammer Studios — Documentation Wiki

RHS official documentation identifies its major Arma 3 packages:

```text
RHS AFRF
RHS USAF
RHS GREF
RHS SAF
```

```text
https://www.rhsmods.org/w
```

---

## RHS USAF — Personal Weapons

Official RHS documentation lists KDF-relevant weapon families including:

- FGM-148 Javelin;
- FIM-92F Stinger;
- M136 AT-4;
- M16A4;
- M240;
- M249;
- M4;
- Mk-14 EBR;
- SR-25.

```text
https://www.rhsmods.org/w/Category%3Ausafweap
```

---

## RHS — M113A3

Official RHS documentation describes its M113A3 transport vehicle and support-family context.

```text
https://www.rhsmods.org/w/m113
```

---

## RHS — UH-60M

Official RHS documentation describes transport and MEDEVAC UH-60M variants and sling-load capability.

```text
https://www.rhsmods.org/w/uh60m
```

---

## RHS — M1025A2

Official RHS documentation describes its HMMWV armament-carrier vehicle.

```text
https://www.rhsmods.org/w/m1025
```

---

## RHS — M252

Official RHS documentation describes the M252 81 mm mortar.

```text
https://www.rhsmods.org/w/m252
```

---

## RHS Workshop Packages

Current Steam Workshop listing examined on 2026-08-09 identifies RHS Arma 3 release `0.5.6`.

The GREF listing states that RHS GREF requires:

```text
RHS AFRF
RHS USAF
```

RHS USAF:

```text
https://steamcommunity.com/sharedfiles/filedetails/?id=843577117
```

---

## 3CB BAF Vehicles

3CB publishes the vehicle families available in its BAF Vehicles package, including:

- Bulldog;
- Coyote/Jackal;
- Husky;
- Land Rover;
- MAN truck;
- Panther;
- ORC;
- Merlin;
- Wildcat.

```text
https://3cbmod.wordpress.com/released-mods/3cb-baf-vehicles/
```

---

## 3CB Vehicle Class Names

Published class list used as an audit reference for MAN HX and other candidate source vehicles.

```text
https://3cbmod.wordpress.com/released-mods/3cb-baf-vehicles/class-names-vehicles/
```

---

## CUP FAQ

CUP documents its package dependency chain as:

```text
CUP Weapons → CBA_A3
CUP Units → CUP Weapons
CUP Vehicles → CUP Units
```

It also states that custom smaller/repacked CUP packages are not permitted.

```text
https://www.cup-arma3.org/faq
```

---

# PART XXXVIII — CURRENT CONCLUSION

The KDF can achieve the intended:

```text
WESTERN-ASSISTED
+
REGIONAL-LEGACY
+
CURRENT-DAY
```

identity without accumulating a large stack of unrelated faction mods.

The recommended dependency philosophy is:

```text
VANILLA
   +
RHS USAF
   +
RHS AFRF
   +
PROJECT-OWNED / INTERNALISED SELECTED ASSETS
```

with:

```text
GREF → avoid unless unique need appears
3CB  → source/adaptation rather than runtime
CUP  → avoid for KDF runtime
ACE  → optional compatibility
ACRE → optional compatibility
```

The single highest-value asset investigation from here is:

# 3CB MAN HX58 / HX60

because a cleanly internalised MAN family could solve:

- troop transport;
- cargo;
- fuel;
- repair;
- logistics;

with one coherent platform and could potentially be reused by future conventional state factions.

After that, the priority is to choose the **protected 4×4** between:

```text
RHS M-ATV
vanilla Hunter
3CB Husky / Panther-derived project asset
```

before beginning actual KDF config work.
