# UKSF_Factions — 3CB MAN HX58/HX60 Source Inspection Preflight

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** 3CB MAN HX58/HX60 Source Inspection Preflight  
**Status:** Active / Awaiting Source PBO  
**Created:** 2026-08-09  
**Target asset:** 3CB BAF HX (MAN) Truck LSV family  
**Intended project role:** Shared conventional logistics vehicle family, initially for KDF  
**Parent audit:** `06_kdf_asset_dependency_audit.md`

---

# 1. Purpose

This document defines the exact source-inspection scope for the 3CB BAF MAN HX58/HX60 family.

The goal is to determine whether the MAN family can be cleanly adapted into:

```text
uksf_factions_vehicles
```

as a reusable project-owned logistics platform without requiring the full 3CB BAF Vehicles package at runtime.

No final integration decision should be made until the actual PBO/source data has been inspected.

---

# 2. Current Status

The actual MAN PBO/source files are not currently available in the accessible project files.

Therefore this document **does not** claim to have inspected:

- P3D LODs;
- selections;
- section counts;
- UVs;
- Geometry LOD;
- Fire Geometry;
- View Geometry;
- Roadway;
- Memory points;
- animation sources;
- RVMAT dependencies;
- texture dimensions;
- script contents;
- config inheritance;
- `requiredAddons[]`;
- external model proxies.

Current technical grade:

```text
GRADE B — HIGH-VALUE CANDIDATE, SOURCE INSPECTION REQUIRED
```

---

# 3. Why the MAN Family Is High Value

3CB's official vehicle documentation describes two MAN HX chassis:

```text
HX60 — 4×4
HX58 — 6×6
```

with multiple logistics variants:

```text
Cargo
Fuel
Container
Flatbed
Repair
Transport
```

The family therefore has unusually high reuse value for a conventional state faction.

A clean integration could provide one coherent vehicle family for:

- troop transport;
- general cargo;
- fuel support;
- repair support;
- container transport;
- logistics support.

---

# 4. Published HX58 Vehicle Classes

3CB's official class-name reference currently lists:

```text
UK3CB_BAF_MAN_HX58_Cargo_Green_A
UK3CB_BAF_MAN_HX58_Cargo_Green_B
UK3CB_BAF_MAN_HX58_Fuel_Green
UK3CB_BAF_MAN_HX58_Repair_Green
UK3CB_BAF_MAN_HX58_Transport_Green

UK3CB_BAF_MAN_HX58_Cargo_Sand_A
UK3CB_BAF_MAN_HX58_Cargo_Sand_B
UK3CB_BAF_MAN_HX58_Fuel_Sand
UK3CB_BAF_MAN_HX58_Repair_Sand
UK3CB_BAF_MAN_HX58_Transport_Sand
```

---

# 5. Published HX60 Vehicle Classes

```text
UK3CB_BAF_MAN_HX60_Cargo_Green_A
UK3CB_BAF_MAN_HX60_Cargo_Green_B
UK3CB_BAF_MAN_HX60_Fuel_Green
UK3CB_BAF_MAN_HX60_Repair_Green
UK3CB_BAF_MAN_HX60_Transport_Green

UK3CB_BAF_MAN_HX60_Cargo_Sand_A
UK3CB_BAF_MAN_HX60_Cargo_Sand_B
UK3CB_BAF_MAN_HX60_Fuel_Sand
UK3CB_BAF_MAN_HX60_Repair_Sand
UK3CB_BAF_MAN_HX60_Transport_Sand
```

---

# 6. Published Container Classes

## HX58 containers

```text
UK3CB_BAF_MAN_HX58_Container_Blue
UK3CB_BAF_MAN_HX58_Container_Green
UK3CB_BAF_MAN_HX58_Container_Sand
UK3CB_BAF_MAN_HX58_Container_ReArm
```

## HX60 containers

```text
UK3CB_BAF_MAN_HX60_Container_Blue
UK3CB_BAF_MAN_HX60_Container_Green
UK3CB_BAF_MAN_HX60_Container_Sand
UK3CB_BAF_MAN_HX60_Container_ReArm

UK3CB_BAF_MAN_HX60_Container_Servicing_Air_Green
UK3CB_BAF_MAN_HX60_Container_Servicing_Air_Sand
UK3CB_BAF_MAN_HX60_Container_Servicing_Ground_Green
UK3CB_BAF_MAN_HX60_Container_Servicing_Ground_Sand
UK3CB_BAF_MAN_HX60_Container_Logistics_Green
UK3CB_BAF_MAN_HX60_Container_Logistics_Sand
```

---

# 7. Published Feature Set

3CB's official MAN documentation identifies:

- HX60 4×4 chassis;
- HX58 6×6 chassis;
- fuel variants;
- container variants;
- flatbed variants;
- repair variants;
- transport variants;
- European/green and desert paint schemes;
- loadable/unloadable containers;
- ACE-compatible service/resupply containers;
- TFAR and ACRE radio/intercom support.

The user guide confirms that container loading/unloading is implemented through vehicle interaction logic and can be accessed through ACE interaction or vanilla action-menu behaviour.

---

# 8. Immediate Technical Risk Flags

The public feature set suggests several areas that must be checked carefully before internalisation.

## 8.1 Container system

Inspect for:

- custom functions;
- event handlers;
- UserActions;
- animation sources;
- attach/detach logic;
- object-position assumptions;
- external container classes;
- external modules;
- locality/multiplayer handling.

The project does not need to inherit a large logistics framework merely to use the truck geometry.

---

## 8.2 ACE integration

3CB documents ACE-compatible container functions.

Determine whether ACE support is:

```text
OPTIONAL DETECTION
```

or:

```text
HARD CONFIG/SCRIPT DEPENDENCY
```

Project requirement:

> Base `uksf_factions_vehicles` must not require ACE.

If the useful feature requires ACE, either:

1. reproduce only an engine-native equivalent;
2. move optional support to `uksf_factions_ace`;
3. omit the feature.

---

## 8.3 ACRE / TFAR integration

3CB documents both ACRE and TFAR vehicle radio/intercom support.

Inspect whether this comes from:

- MAN config;
- common 3CB vehicle base class;
- event handlers;
- compatibility scripts.

Project requirement:

> The shared vehicle model must not require either radio mod.

Radio compatibility can be re-added separately if genuinely useful.

---

## 8.4 Shared 3CB base classes

The most important config question is whether MAN classes inherit deeply from a 3CB common vehicle hierarchy.

Record every parent from:

```text
UK3CB_BAF_MAN_...
```

back to the first vanilla Arma class.

If substantial behaviour lives in a 3CB parent class, determine whether it is:

- required engine configuration;
- generic reusable config;
- British-specific decoration;
- optional script behaviour.

---

# 9. Provenance Review

3CB's official credits identify the original MAN truck source as:

```text
Bravo93 (16AA) — Original MAN truck from TurboSquid
```

This is a critical provenance item.

The project already has explicit permission from 3CB to use/adapt relevant material, but before **redistributing an internalised MAN model**, the source/permission record must also establish that the underlying original-model rights permit the intended redistribution/adaptation route.

Required asset-register status until that is verified:

```text
PENDING_PROVENANCE_REVIEW
```

Do not interpret this as a claim that the asset cannot be used.

It means the underlying source chain must be recorded rather than assumed.

---

# 10. Exact Input Needed for the Next Inspection Pass

Preferred:

```text
the MAN-specific 3CB vehicle PBO
```

or, better:

```text
the original/unpacked MAN source folder supplied under the project's 3CB permission
```

If the MAN config references files in other 3CB PBOs, those dependencies can then be requested individually.

There is no need to begin with the entire 3CB mod.

---

# 11. Mikero Extraction Workflow

For an installed PBO, make a working copy outside the live mod folder.

Example working layout:

```text
_external_staging/
└── pending/
    └── 3cb_man_hx/
        ├── original_pbo/
        ├── extracted/
        ├── analysis/
        └── permission/
```

Use the project's normal Mikero tooling to unpack/debin config data.

The source PBO itself should remain untouched.

---

# 12. First Config Inspection

After extraction, identify:

```text
config.cpp
config.bin
model.cfg
```

and all included headers.

Record:

```text
CfgPatches class:
requiredAddons[]:
CfgVehicles base classes:
model paths:
hiddenSelections[]:
hiddenSelectionsTextures[]:
animationList / AnimationSources:
EventHandlers:
UserActions:
class ACE_Actions:
transportSoldier:
maximumLoad:
fuelCapacity:
transportFuel:
transportRepair:
transportAmmo:
slingLoadCargoMemoryPoints[]:
```

Not every field will exist.

---

# 13. Dependency Path Audit

For every file reference in config/model/material data, classify it as:

```text
VANILLA
MAN-LOCAL
3CB-COMMON
3CB-WEAPONS
3CB-EQUIPMENT
ACE
ACRE
TFAR
OTHER
```

Target:

```text
MAN-LOCAL + VANILLA
```

for the eventual internal vehicle.

Anything else requires a decision.

---

# 14. P3D Model Audit

Inspect every visible P3D used by the truck family.

Record:

```text
Model:
Role:
Chassis:
Resolution LOD count:
Resolution LOD face/triangle counts:
Geometry:
Fire Geometry:
View Geometry:
Roadway:
LandContact:
Memory:
HitPoints:
Shadow LOD:
Sections/materials:
Named selections:
Animation selections:
Proxies:
```

---

# 15. Resolution LOD Standard

Compare the source against the active `UKSF_Factions` performance standard.

Desired vehicle behaviour:

- meaningful LOD progression;
- substantial reduction between visible LODs;
- no nearly identical high-detail LOD chain;
- clean distant silhouette.

The project standard recommends aggressive review for a light vehicle around the existing soft trigger range, but no triangle count is treated as an Arma engine hard limit.

---

# 16. Section / Material Audit

For each visible LOD record:

```text
number of sections
number of unique RVMATs
number of unique texture sets
```

Particular concern:

- British-specific accessories with separate materials;
- duplicate green/sand material families;
- tiny unique materials for decals;
- repeated cabin/interior sections.

Potential optimisation route:

```text
atlas / combine
```

only where it does not damage UV quality or retexturability.

---

# 17. Texture Audit

Record every texture with:

```text
path
resolution
suffix/type
usage
shared/unique
British-specific?
reusable?
```

Look especially for:

```text
_co
_nohq
_smdi
_as
_mc
```

and any custom non-standard suffixes.

---

# 18. KDF Retexture Feasibility

Determine whether KDF can achieve its visual identity using:

```text
hiddenSelectionsTextures[]
```

without editing the P3D.

Ideal:

```text
CAB
CHASSIS
CARGO BODY
CONTAINER
DECALS
```

as independently controllable selections.

If British markings are baked directly into base colour textures, replacement textures are acceptable.

If British markings are geometry/proxy based, note the required model edits.

---

# 19. British-Specific Components

Identify all visual elements that should be removed or neutralised for KDF.

Potential examples:

- UK registration plates;
- British tactical signs;
- Union flags;
- BOWMAN-specific visual kit;
- UK-specific labels;
- British unit markings;
- UK cargo labels.

Do not remove generic real MAN/RMMV vehicle features merely because the source asset was used by Britain.

---

# 20. Vehicle Identification Plates

3CB's vehicle system includes automatic vehicle identification/serial behaviour elsewhere in the vehicle package.

Check whether MAN inherits or calls any such common system.

For UKSF integration, prefer:

```text
STATIC / CONFIG-DRIVEN KDF NUMBERING
```

or a lightweight optional system.

Do not inherit a permanent script merely to generate British-style registrations.

---

# 21. Suspension / Wheel Animation

The official feature list describes dynamic/realistic vehicle behaviour across the pack.

For MAN inspect:

- wheel bones;
- suspension selections;
- steering axes;
- dampers;
- wheel destruction;
- wheel proxies;
- physX configuration.

Preserve working vehicle physics unless a demonstrable problem exists.

---

# 22. Damage / Hitpoints

Inspect:

```text
HitHull
HitEngine
HitFuel
HitLFWheel
HitLF2Wheel
...
```

and all custom hit selections.

Verify selection names match the Geometry/HitPoints LOD.

Do not blindly inherit custom damage scripts where vanilla hit-point configuration is sufficient.

---

# 23. Cargo / FFV

For transport variants record:

```text
cargo seat count
FFV positions
cargo proxies
get-in/get-out points
door dependencies
```

KDF requirement:

- practical section/squad transport;
- sensible dismounting;
- no British-specific seating logic unless generic.

---

# 24. Fuel Variant

Determine whether:

```text
transportFuel
```

is sufficient or whether 3CB adds custom servicing logic.

Preferred UKSF route:

```text
VANILLA CONFIG SUPPORT FIRST
```

ACE compatibility can be added separately.

---

# 25. Repair Variant

Determine whether the repair truck uses:

```text
transportRepair
```

or a 3CB service framework.

Preferred:

```text
VANILLA REPAIR CAPABILITY
+
OPTIONAL ACE INTEGRATION
```

---

# 26. Cargo / Logistics Variant

Determine whether the cargo truck is useful without the 3CB logistics module.

If yes:

```text
retain truck
drop 3CB logistics framework
```

unless the feature provides exceptional value.

---

# 27. Container Variant Decision

The load/unload container system is useful but not mandatory for KDF v1.

Priority:

```text
TRUCK FAMILY
>
CONTAINER SCRIPT SYSTEM
```

If separating the system is expensive:

```text
DEFER CONTAINER FUNCTION
```

rather than forcing 3CB runtime dependencies.

---

# 28. model.cfg Audit

Inspect:

- skeleton definition;
- animation classes;
- source types;
- custom controller dependencies;
- wheel/suspension animation;
- doors;
- container equipment;
- mirrors/wipers if present.

Target:

```text
SELF-CONTAINED MODEL.CFG
```

for any internalised vehicle.

---

# 29. Script Audit

Search extracted source for:

```text
UK3CB
ACE_
acre_
ACRE
TFAR
TFAR_
task_force
CBA_
Extended_
addEventHandler
class EventHandlers
class UserActions
execVM
compile
preprocessFile
call
spawn
```

Classify each result:

```text
REQUIRED
OPTIONAL
BRITISH-SPECIFIC
LOGISTICS
RADIO
ACE
REMOVABLE
```

---

# 30. Config Inheritance Target

If internalised, the final project truck should ideally inherit from an appropriate vanilla vehicle base rather than a 3CB public class.

Conceptual structure:

```cpp
class Truck_F;

class UKSF_Factions_Vehicle_MAN_HX60_Base: Truck_F
{
    // project-clean vehicle base
};
```

The actual vanilla parent must be determined from the source config and tested.

Do not choose a parent before inspecting the original inheritance chain.

---

# 31. Proposed Project Class Family

Reserved concept only:

```text
UKSF_Factions_Vehicle_MAN_HX60_Transport
UKSF_Factions_Vehicle_MAN_HX60_Cargo
UKSF_Factions_Vehicle_MAN_HX60_Fuel
UKSF_Factions_Vehicle_MAN_HX60_Repair

UKSF_Factions_Vehicle_MAN_HX58_Transport
UKSF_Factions_Vehicle_MAN_HX58_Cargo
UKSF_Factions_Vehicle_MAN_HX58_Fuel
UKSF_Factions_Vehicle_MAN_HX58_Repair
```

Container variants should be added only if their functionality survives the dependency cleanup cleanly.

---

# 32. Shared vs Faction-Specific Ownership

Generic vehicle classes/models:

```text
uksf_factions_vehicles
```

KDF-specific painted variants:

```text
uksf_factions_kdf
```

Example:

```text
UKSF_Factions_Vehicle_MAN_HX60_Transport
    ↓
UKSF_Factions_KDF_MAN_HX60_Transport
```

This allows future conventional factions to reuse the generic MAN without inheriting KDF markings.

---

# 33. KDF Visual Variant

Initial KDF truck direction:

```text
muted olive / green-grey
```

with:

- KDF national rosette;
- tactical number;
- restrained unit markings;
- no British registration/tactical plates.

A sand variant may follow if genuinely useful.

---

# 34. Minimum Internalisation Gate

The MAN family can only be approved for `INTERNALISE` if all of the following are satisfied:

- [ ] Provenance/permission chain is recorded.
- [ ] Source P3Ds are legitimately available for modification.
- [ ] Core model works without 3CB runtime PBOs.
- [ ] Required textures/materials can be included legitimately.
- [ ] No mandatory ACE dependency.
- [ ] No mandatory ACRE dependency.
- [ ] No mandatory TFAR dependency.
- [ ] No mandatory 3CB weapon/equipment dependency.
- [ ] Required scripts are understood.
- [ ] British-specific scripts/markings can be removed.
- [ ] LOD structure meets or can reasonably be brought to project standard.
- [ ] Section/material count is acceptable or fixable.
- [ ] Geometry/Fire/View LODs are valid.
- [ ] PhysX/wheels/suspension work correctly.
- [ ] Transport/Fuel/Repair roles work in multiplayer.
- [ ] PBOProject packs cleanly.
- [ ] RPT remains clean in a dependency-minimal test modset.

---

# 35. Decision Outcomes

## Outcome A — Internalise

Use when:

```text
strong source quality
+
clean rights
+
manageable dependencies
+
reasonable optimisation effort
```

Action:

```text
ADAPT → CLEAN → OPTIMISE → UKSF_Factions_Vehicles
```

---

## Outcome B — Retexture / Runtime 3CB

Use only if:

- internalisation is legally/technically unsuitable;
- runtime dependency is acceptable;
- the vehicle remains strategically valuable.

This is not the preferred KDF architecture.

---

## Outcome C — Reject / Replace

Use if:

- source rights are unsuitable;
- dependency removal is impractical;
- P3D quality requires disproportionate rework;
- script framework is inseparable;
- a cleaner RHS/vanilla/private asset exists.

---

# 36. Current Provisional Verdict

Based on the public feature set alone:

```text
VISUAL / GAMEPLAY VALUE: A
FAMILY COVERAGE: A
DEPENDENCY-REDUCTION VALUE: A
KNOWN SCRIPT COMPLEXITY: B
PROVENANCE STATUS: REVIEW REQUIRED
TECHNICAL SOURCE QUALITY: UNKNOWN
OVERALL: B / HIGH-PRIORITY INSPECTION
```

The candidate remains worth pursuing.

The deciding evidence must come from the actual MAN source/PBO.

---

# 37. Required Next Input

For the next step, the useful file is the **MAN-specific 3CB BAF Vehicles PBO/source folder** containing the HX58/HX60 classes above.

Once available, the next document should replace the unknowns in this preflight with:

```text
actual CfgPatches
actual requiredAddons[]
actual inheritance
actual P3D list
actual RVMAT/texture list
actual scripts/functions
actual model LOD audit
actual dependency graph
final A/B/C/reject decision
```

---

# 38. Research References

Research reviewed 2026-08-09.

## 3 Commando Brigade — 3CB BAF Vehicles

Official 3CB documentation for the MAN family and its published features.

```text
https://3cbmod.wordpress.com/released-mods/3cb-baf-vehicles/
```

## 3 Commando Brigade — Vehicle Class Names

Official class-name list for HX58/HX60 trucks and containers.

```text
https://3cbmod.wordpress.com/released-mods/3cb-baf-vehicles/class-names-vehicles/
```

## 3 Commando Brigade — Vehicle User Guide

Official documentation for MAN container loading/unloading and wider vehicle integration behaviour.

```text
https://3cbmod.wordpress.com/released-mods/3cb-baf-vehicles/usage-vehicles/
```

---

# 39. Current Conclusion

The MAN family remains the most attractive KDF logistics candidate because one source family potentially covers:

```text
HX60 4×4
HX58 6×6

Transport
Cargo
Fuel
Repair
Container / logistics
```

The next decision is no longer conceptual.

It is a source-engineering question:

> **Can the MAN model/config/material set be separated from British-specific 3CB frameworks cleanly enough to become a lightweight shared UKSF_Factions vehicle family?**

That answer requires the actual MAN PBO/source.
