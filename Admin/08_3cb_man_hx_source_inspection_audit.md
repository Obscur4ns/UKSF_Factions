# UKSF_Factions — 3CB MAN HX58/HX60 Source Inspection Audit

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** 3CB MAN HX58/HX60 Source Inspection Audit  
**Status:** Technical Audit / Internalisation Approved with Rework  
**Created:** 2026-08-09  
**Source PBO:** `uk3cb_baf_vehicles_MAN.pbo`  
**Source prefix:** `uk3cb_baf_vehicles\addons\uk3cb_baf_vehicles_MAN`  
**Target project PBO:** `uksf_factions_vehicles`  
**Initial user:** Karzeghistani Defence Forces (`KDF`)  
**Parent documents:**
- `06_kdf_asset_dependency_audit.md`
- `07_3cb_man_hx_source_inspection_preflight.md`
- `04_performance_and_asset_optimisation_standard.md`

---

# 1. Executive Decision

## Final technical recommendation

# APPROVE FOR INTERNALISATION

with:

```text
Grade B — Worth Reworking
```

The MAN HX58/HX60 family is a strong candidate for conversion into a shared `UKSF_Factions` logistics family.

The reasons are unusually favourable:

- the truck P3Ds are contained in the MAN PBO;
- the truck-specific textures and RVMATs are contained in the MAN PBO;
- P3D external model/proxy references observed during the audit are vanilla Arma 3;
- RVMAT external texture references are vanilla Arma 3;
- the full truck models have sensible visible LOD progression;
- geometry complexity is reasonable for the project;
- HX58 and HX60 cover several useful logistics roles from one common platform;
- most removable third-party coupling is in config/functions rather than model geometry;
- the core container load/unload mechanism is mostly engine-native;
- the hard `UK3CB_BAF_Vehicles_Weapons` dependency is not required for the core truck geometry;
- ACE/ACRE/TFAR/CBA coupling can be removed or moved to optional compatibility.

The main reasons this is **Grade B rather than Grade A** are:

1. the source configuration needs dependency cleanup;
2. the MAN post-init/function layer contains CBA/ACE/3CB integration that should not be inherited;
3. radio/intercom configuration should be separated;
4. the texture set is substantially heavier than the UKSF runtime target;
5. the special 3CB servicing/logistics containers should be dropped or redesigned rather than copied wholesale;
6. final in-game/PBOProject validation is still required.

---

# 2. PBO Extraction Result

The supplied PBO unpacked normally.

Observed:

```text
Payload files: 203
Payload size: 235,491,528 bytes
Approx. payload size: 224.58 MiB
PBO prefix: uk3cb_baf_vehicles\addons\uk3cb_baf_vehicles_MAN
PBO Mikero metadata: DePbo.dll.6.46
PBO metadata version: 22010511
```

The payload is dominated by texture data.

| Type | Count | Approx. size |
|---|---:|---:|
| `.paa` | 100 | 194.44 MiB |
| `.p3d` | 12 | 28.53 MiB |
| `.jpg` | 34 | 1.21 MiB |
| `.ogg` | 3 | 0.19 MiB |
| `.bin` | 2 | 0.13 MiB |
| `.rvmat` | 37 | 0.06 MiB |
| `.sqf` | 11 | 0.02 MiB |
| `.rtm` | 3 | <0.01 MiB |
| `.hpp` | 1 | <0.01 MiB |

The JPGs are primarily editor/arsenal preview imagery and are not required for a cleaned project runtime package unless equivalent previews are desired.

---

# 3. P3D Inventory

The PBO contains twelve ODOL v73 models.

## HX60 / 4×4

```text
uk3cb_man_4x4_cargo.p3d
uk3cb_man_4x4_container.p3d
uk3cb_man_4x4_fake_container.p3d
uk3cb_man_4x4_fuel.p3d
uk3cb_man_4x4_repair.p3d
uk3cb_man_4x4_transport.p3d
```

## HX58 / 6×6

```text
uk3cb_man_6x6_cargo.p3d
uk3cb_man_6x6_container.p3d
uk3cb_man_6x6_fake_container.p3d
uk3cb_man_6x6_fuel.p3d
uk3cb_man_6x6_repair.p3d
uk3cb_man_6x6_transport.p3d
```

The models are Arma 3-era ODOL v73.

For this audit, their header/LOD metadata was parsed directly. The current UKSFTA P3D tooling independently documents support for Arma 3 ODOL v73–v75 and can be used later for editable MLOD recovery and deeper selection/section inspection.

---

# 4. LOD Structure

All full truck models contain four normal visible resolution entries:

```text
1
2
3
4
```

plus multiple special/functional LOD entries.

The normal cargo/fuel/repair trucks have:

```text
14 total LOD slots
```

The transport variants have:

```text
16 total LOD slots
```

The additional transport entries reflect extra special LOD content.

This is a good starting point: the source is not a single-high-detail model with token distant LODs.

---

# 5. Visual LOD Geometry — HX60 4×4

The source stores direct face/vertex metadata for the first three visible LODs.

## HX60 Cargo

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 32,173 | 52,682 |
| 2 | 16,440 | 31,632 |
| 3 | 6,760 | 15,208 |
| 4 | permanent LOD; direct header count not stored | — |

Reduction:

```text
LOD1 → LOD2: ~51% of faces retained
LOD2 → LOD3: ~41% of faces retained
```

---

## HX60 Fuel

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 36,766 | 57,115 |
| 2 | 18,643 | 33,619 |
| 3 | 7,603 | 16,052 |
| 4 | permanent LOD | — |

---

## HX60 Repair

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 32,502 | 56,214 |
| 2 | 16,431 | 33,085 |
| 3 | 7,004 | 16,256 |
| 4 | permanent LOD | — |

---

## HX60 Transport

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 43,952 | 67,256 |
| 2 | 21,908 | 40,639 |
| 3 | 10,180 | 21,713 |
| 4 | permanent LOD | — |

The transport model is naturally heavier because of the troop body/tarp/interior geometry.

Its visible reduction remains healthy.

---

# 6. Visual LOD Geometry — HX58 6×6

## HX58 Cargo

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 34,679 | 57,403 |
| 2 | 18,318 | 36,010 |
| 3 | 7,090 | 16,023 |
| 4 | permanent LOD | — |

---

## HX58 Fuel

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 39,272 | 61,836 |
| 2 | 20,521 | 37,988 |
| 3 | 7,933 | 16,853 |
| 4 | permanent LOD | — |

---

## HX58 Repair

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 35,837 | 60,184 |
| 2 | 18,804 | 38,505 |
| 3 | 7,631 | 17,731 |
| 4 | permanent LOD | — |

---

## HX58 Transport

| LOD | Faces | Vertices |
|---:|---:|---:|
| 1 | 52,051 | 75,714 |
| 2 | 26,184 | 48,997 |
| 3 | 11,414 | 24,127 |
| 4 | permanent LOD | — |

This is the heaviest visible MAN variant observed.

The LOD1 face count remains reasonable for a current vehicle model and the reduction chain is strong:

```text
52,051
↓
26,184
↓
11,414
↓
LOD4
```

This is substantially healthier than an asset that carries near-identical geometry through its first several LODs.

---

# 7. Functional LOD Evidence

The full models contain numerous special-resolution entries in addition to the visible 1–4 LODs.

The exact semantic label of every encoded special-resolution value is not necessary for the integration decision, but the models clearly contain a developed functional LOD set rather than only visual geometry.

The config/P3D strings also expose expected vehicle systems including:

- hit selections;
- wheel/suspension selections;
- cargo proxies;
- driver proxies;
- gunner/top-cover proxy;
- damage-wheel proxies;
- memory points;
- lighting;
- mirrors/PiP;
- sling-load memory points.

Final editable-source inspection should still visually confirm:

- Geometry;
- Fire Geometry;
- View Geometry;
- LandContact;
- Memory;
- HitPoints;
- shadow LODs.

No evidence in the supplied PBO suggests those are missing.

---

# 8. Material Complexity

A string-level material audit of the normal visible LOD blocks shows the following **unique RVMAT names**.

This is not identical to actual render-section count, but it is a useful material-complexity indicator.

## Typical cargo model

```text
LOD1: 19 unique RVMATs
LOD2: 17
LOD3: 15
LOD4: 12
```

## Fuel

```text
LOD1: 17
LOD2: 16
LOD3: 14
LOD4: 12
```

## Repair

HX60:

```text
18 / 16 / 14 / 12
```

HX58:

```text
19 / 18 / 15 / 13
```

## Transport

```text
17 / 16 / 14 / 12
```

The first visible LOD therefore sits close to, but generally below, the project's aggressive material/section review region.

Because **unique material count is not the same thing as section count**, actual sections should still be counted once an editable MLOD/source model is available.

---

# 9. Main Material Families

Repeated truck material families include:

```text
man_body
man_chassis
man_container
man_glass
man_interior
man_parts
man_rear
man_tarp
man_wheel
number
numberDecal
numberDecalCon
```

Variant-specific families include:

```text
t810_fueltank
ural_repair
mtvr_interior
crane
```

Vanilla materials are used for generic engine functions such as:

- mirrors;
- headlights;
- rear lights;
- clan/sign handling;
- generic/default materials.

This is acceptable.

---

# 10. RVMAT Dependency Audit

The PBO contains:

```text
37 RVMAT files
```

MAN RVMAT references resolve overwhelmingly to:

```text
uk3cb_baf_vehicles\addons\uk3cb_baf_vehicles_MAN\...
```

The non-MAN texture/material references observed are vanilla Arma 3 paths, including families under:

```text
a3\data_f\
a3\weapons_f\
```

Examples include:

```text
a3\data_f\env_land_co.paa
a3\data_f\destruct\...
a3\data_f\default_vehicle_ti_ca.paa
a3\data_f\default_glass_ti_ca.paa
a3\weapons_f\data\detailmaps\metal_detail_dt.paa
```

No external 3CB material/texture PBO path was found in the RVMAT reference audit.

This is a major positive result.

---

# 11. P3D External Path Audit

The visible P3Ds primarily reference:

```text
MAN-local data
+
vanilla Arma 3 data/proxies
```

Vanilla proxy examples include:

```text
\a3\data_f\proxies\hemtt\driver
\a3\data_f\proxies\hemtt\cargo
\a3\data_f\proxies\gunner_hunter\gunner
\a3\data_f\proxies\damagewheel\damagewheel_1
\a3\data_f\volumelight
```

Vanilla penetration surfaces/materials are also referenced.

No non-MAN 3CB model/proxy path was identified in the P3D string audit.

Therefore the **model geometry itself is not materially tied to another 3CB vehicle PBO**.

---

# 12. Texture Inventory

The PBO contains:

```text
100 PAA files
```

Approximate PAA payload:

```text
194.44 MiB
```

Top-level resolution distribution:

| Resolution | Count |
|---|---:|
| 4096×4096 | 39 |
| 2048×2048 | 20 |
| 1024×1024 | 13 |
| 512×512 | 4 |
| 256×256 | 2 |
| 128×128 | 14 |
| 128×64 | 8 |

The texture set is the largest optimisation opportunity in the source.

---

# 13. 4K Texture Families

The 4096×4096 group includes extensive maps for:

```text
man_body
man_chassis
man_container
man_interior
man_parts
```

with combinations of:

```text
_co
_nohq
_smdi
_as
_mc
_ti_ca
```

and multiple colour variants.

Examples include:

```text
man_body_green_co.paa
man_body_sand_co.paa
man_body_nohq.paa
man_body_smdi.paa
man_body_as.paa
man_body_mc.paa
man_body_ti_ca.paa

man_chassis_green_co.paa
man_chassis_sand_co.paa
...

man_container_green_co.paa
man_container_sand_co.paa
man_container_blue_co.paa
multiple servicing/logistics container colour textures
...
```

---

# 14. Texture Optimisation Decision

The current UKSF project standard treats 2048 as the normal major vehicle-texture target and 4K as selective.

Therefore the MAN should **not** be copied unchanged into the runtime package.

Recommended production approach:

## Preserve as source masters

Retain the original 4K textures in source/archive material where permitted.

## Runtime review

Test major visible surfaces at:

```text
2048×2048
```

first.

Keep 4K only where an in-game A/B comparison shows a meaningful close-range quality benefit.

Particular candidates for reduction:

- AS maps;
- MC maps;
- TI masks where 4K provides no useful visible gain;
- secondary/interior maps;
- redundant source colour variants not shipped by UKSF.

Do not mechanically downscale every map without checking the visual result.

---

# 15. Immediate PBO Size Reduction Opportunity

The UKSF build does not need to ship every original 3CB variant.

For KDF/shared use, the first pass can omit:

- original green/sand faction presentation where replaced by UKSF textures;
- unused blue/red containers;
- 3CB editor preview JPGs;
- special servicing/logistics container textures if those variants are deferred;
- unused UI pictures;
- unused source colour variants.

The result should be substantially smaller than the original ~225 MiB payload even before texture-resolution optimisation.

---

# 16. Config Hard Dependency

The binarised config declares:

```text
CfgPatches
class UK3CB_BAF_Vehicles_MAN
```

and the observed hard addon dependency is:

```text
UK3CB_BAF_Vehicles_Weapons
```

This is the key external 3CB config dependency in the MAN package.

The source contains direct calls into that addon for:

```text
air servicing
ground servicing
logistics
vehicle light switching
```

These are not required to preserve the basic truck models.

Therefore:

# `UK3CB_BAF_Vehicles_Weapons` SHOULD NOT BE RETAINED AS A UKSF RUNTIME DEPENDENCY

for the generic MAN family.

---

# 17. Base Vehicle Heritage

The config contains the vanilla chain:

```text
Car_F
Truck_F
Truck_01_base_F
```

alongside the MAN bases:

```text
UK3CB_BAF_MAN_HX60_Base
UK3CB_BAF_MAN_HX58_Base
```

The P3D proxy strategy also makes extensive use of vanilla HEMTT cargo/driver proxies.

For the UKSF version, the intended cleaned base should ultimately derive from an appropriate vanilla truck base after the original config is fully de-rapified/reconstructed and tested.

Do not retain an unnecessary 3CB public parent merely for convenience.

---

# 18. Hidden Selections / Retexture Support

The binarised config exposes:

```text
hiddenSelections
cargoId1
cargoId2
camo1
camo2
camo3
camo4
camo5
camo6
```

This is excellent for the project.

It strongly supports a faction-neutral shared MAN base with separate faction texture classes.

The truck does **not** need a P3D edit merely to obtain a new KDF paint scheme.

---

# 19. Number / ID System

The source includes:

```text
Number0_co.paa
...
Number9_co.paa
```

and number materials/selections.

`fn_init_EH.sqf` also assigns sequential vehicle IDs using a missionNamespace variable.

For UKSF:

```text
DROP THE 3CB AUTOMATIC NUMBERING SYSTEM
```

in the generic truck base.

Retain the underlying number selections if useful.

KDF numbering can later be:

- static config texture;
- Eden-selectable;
- lightweight faction-specific randomisation;

without a permanent common-vehicle script requirement.

---

# 20. Function Inventory

The MAN PBO contains eleven SQF functions:

```text
fn_can_load_container.sqf
fn_can_unload_container.sqf
fn_init_EH.sqf
fn_load_container.sqf
fn_load_container_remote.sqf
fn_play_warning_sound.sqf
fn_set_cargo_id.sqf
fn_transfer_container_ownership.sqf
fn_unload_container.sqf
fn_unload_container_remote.sqf
fn_vehicle_init.sqf
```

---

# 21. Container Eligibility Functions

## `fn_can_load_container.sqf`

Uses:

```text
CBA_fnc_currentUnit
```

to identify the current player/unit.

The rest of the check is normal engine logic around:

- proximity;
- container state;
- selection position.

## `fn_can_unload_container.sqf`

Likewise uses:

```text
CBA_fnc_currentUnit
```

for the actor check.

### Decision

```text
REWRITE
```

The CBA dependency is trivial to remove.

The UKSF function should receive or resolve the interaction caller explicitly rather than requiring `CBA_fnc_currentUnit`.

---

# 22. Core Container Load Function

`fn_load_container.sqf` is a locality wrapper around the remote load function.

`fn_load_container_remote.sqf` uses normal engine functionality including:

- nearest-object selection;
- `attachTo`;
- texture copying;
- damage transfer;
- animation source control;
- vehicle-in-vehicle cargo state;
- sound playback.

No structural ACE/ACRE/TFAR requirement was identified in the core remote load mechanism.

### Decision

```text
RETAINABLE AFTER NAMESPACE/CODE CLEANUP
```

if the project wants the container feature.

---

# 23. Core Container Unload Function

The unload system uses normal engine operations including:

- temporary fake-container object;
- obstacle checking;
- temporary driver lock;
- object ownership handling;
- position/orientation transfer;
- damage protection during transition;
- animation;
- sounds;
- cleanup.

The ownership helper uses server-side:

```text
setOwner
```

logic.

### Decision

```text
RETAINABLE AFTER CLEANUP
```

The mechanism is more complex than the load function but is not fundamentally tied to the wider 3CB framework.

One cleanup task is to remove/restructure global helper-function definitions created during the unload routine.

---

# 24. `fn_init_EH.sqf`

This function combines several unrelated behaviours.

It:

- adds top-cover/crew animation event handlers;
- assigns automatic number plates;
- optionally detects ACE;
- conditionally loads ACE wheel/track items;
- adds toolkits;
- adjusts vehicle-in-vehicle cargo state for container variants.

### Decision

```text
SPLIT
```

For UKSF:

### Retain if needed

- MAN-specific top-cover crew handling;
- container-related ViV state logic.

### Remove

- 3CB automatic registration numbering.

### Move to optional ACE compatibility

- ACE spare wheel/track cargo behaviour.

### Keep simple vanilla loadout config

- ToolKits can be handled through normal `TransportItems` rather than delayed init logic.

---

# 25. `fn_vehicle_init.sqf`

This is the clearest function to **not carry forward**.

It uses:

```text
CBA_fnc_addEventHandler
CBA_fnc_addKeybind
ACE cargo events/functions
UK3CB_BAF_Vehicles_Weapons_fnc_switch_lights
```

It therefore couples MAN to:

- CBA;
- ACE;
- 3CB Vehicles Weapons.

### Decision

# DROP FROM THE BASE UKSF MAN PACKAGE

Any useful optional behaviour can be reintroduced deliberately elsewhere.

The truck itself does not need this function.

---

# 26. ACE Configuration

The binarised vehicle config contains ACE-specific properties such as:

```text
ace_refuel_fuelCargo
ace_refuel_hooks
ace_repair_canRepair
ace_cargo_space
```

and ACE interaction classes for container actions.

### Decision

Base `uksf_factions_vehicles`:

```text
NO ACE DEPENDENCY
```

Use standard Arma properties for:

- fuel;
- repair;
- cargo.

If enhanced ACE behaviour is needed later:

```text
uksf_factions_ace
```

should add compatibility separately.

---

# 27. ACRE Configuration

The MAN base includes an `AcreRacks` configuration with references including:

```text
ACRE_VRC110
ACRE_VRC103
ACRE_PRC117F
```

### Decision

# STRIP FROM THE GENERIC MAN BASE

The physical logistics truck does not need ACRE to exist.

If a KDF/UKSF radio fit is desired later, add it in a faction/compatibility layer.

This also prevents obsolete British-specific radio-fit assumptions from becoming embedded in the shared vehicle.

---

# 28. TFAR Configuration

The source includes TFAR properties and ACE self-actions for TFAR intercom slot handling.

Examples include:

```text
tfar_hasIntercom
tfar_additionalLR_cargo
TFAR_IntercomChannel
TFAR_IntercomSlot_...
```

### Decision

# STRIP

There is no reason for a shared UKSF_Factions truck model to hard-code both ACRE and TFAR systems.

---

# 29. Special Servicing Containers

The following source variants call `UK3CB_BAF_Vehicles_Weapons` functions directly:

```text
HX60 Container Servicing Air
HX60 Container Servicing Ground
HX60 Container Logistics
```

These integrate into 3CB's wider servicing/logistics framework.

### Decision for UKSF v1

# DEFER / DO NOT INTERNALISE FUNCTIONALLY

Their geometry may be reusable later, but the 3CB functionality should not be copied into the initial shared vehicle package.

The KDF does not need those specialist containers to justify the MAN family.

---

# 30. ReArm Container

The generic rearm container may also imply broader ammunition/service behaviour.

### Decision

```text
DEFER
```

until the basic truck/container family is stable.

A normal Arma ammunition support vehicle/container can be created later without importing the entire 3CB logistics system.

---

# 31. Fuel Truck

The fuel variant is a strong first-release candidate.

### UKSF target

Use standard engine fuel support.

Strip optional ACE-specific properties from the base and re-add through compatibility only if desired.

### Grade

```text
A- model
B integration
```

---

# 32. Repair Truck

The repair variant is also worthwhile.

It has more material/functional geometry than the cargo/fuel versions, especially HX58 repair.

### UKSF target

Use standard engine repair support.

Do not preserve:

- delayed ACE spare-part loading;
- unrelated 3CB logistics hooks.

### Grade

```text
B+
```

---

# 33. Transport Truck

The transport models are the heaviest members of the family.

HX58 Transport LOD1:

```text
52,051 faces
75,714 vertices
```

HX60 Transport LOD1:

```text
43,952 faces
67,256 vertices
```

Both show good reduction at LOD2/LOD3.

### Decision

```text
APPROVE
```

No geometry-reduction emergency is indicated.

Optimisation effort should focus on texture/material/runtime cleanup first.

---

# 34. Cargo / Container Truck

The cargo variant has two major values:

1. ordinary cargo/logistics truck;
2. optional removable-container system.

### Recommendation

For the initial project family:

```text
CARGO TRUCK → APPROVE
CONTAINER SCRIPT FEATURE → OPTIONAL SECOND PASS
```

Do not make the entire MAN integration wait on the container logic.

---

# 35. Container Models

The actual HX58/HX60 container models are lightweight.

First three visible counts are approximately:

```text
LOD1: 2,436 faces
LOD2: ~1,532 faces
LOD3: 616 faces
```

They are not a geometry concern.

The heavy cost of the container family is mainly its 4K texture set and optional logistics behaviour.

---

# 36. RTM / Crew Animation Assets

The PBO contains three MAN-local RTMs:

```text
uk3cb_baf_man_driver.rtm
uk3cb_baf_man_topCover_in.rtm
uk3cb_baf_man_topCover_in_kia.rtm
```

These are valuable and should be retained if permitted by the source/permission chain.

They support the MAN-specific cab/top-cover presentation without introducing another runtime PBO.

---

# 37. Source `model.cfg`

A standalone `model.cfg` is not present in the packed addon.

That is normal for a binarised runtime PBO.

The relevant skeleton/animation structure is represented in the ODOL data/config.

### Preferred route

If 3CB can supply the original editable source under the existing permission, use that source.

### Fallback

Recover editable model structure from the authorised ODOL using an Arma 3 v73-compatible P3D debinarisation tool, then rebuild/verify the project `model.cfg`.

The current UKSFTA P3D tool documents ODOL v73–v75 conversion, LOD auditing, material extraction and skeleton export.

---

# 38. Physics / Wheel Configuration

The binarised config contains detailed wheel configuration including:

```text
wheel bones
wheel axes
wheel boundaries
suspension force application points
tire force application points
suspension travel direction
spring strength
spring damping
brake torque
handbrake torque
lateral stiffness
longitudinal stiffness
friction/slip graph
```

### Decision

Preserve the proven MAN physics configuration initially.

Do not rewrite suspension/PhysX values merely for namespace purity.

Only change them if in-game testing reveals a real problem.

---

# 39. Damage / Hitpoint Configuration

The source exposes conventional hitpoint groups including:

```text
HitBody
HitEngine
HitFuel
HitHull
HitGlass1–4
wheel hitpoints
```

and corresponding P3D selections.

### Decision

Preserve the functional hitpoint structure during the first conversion.

Remove only 3CB-specific scripting around it, not the working vehicle damage model.

---

# 40. Cargo / Crew Proxies

The models use vanilla proxies including HEMTT cargo/driver positions and a Hunter gunner proxy.

This is a positive dependency result:

```text
NO EXTERNAL CREW-PROXY MODEL PACK REQUIRED
```

Transport variants should still be checked in game for:

- clipping;
- entry/exit;
- FFV if present;
- animation compatibility.

---

# 41. British-Specific Presentation

The source naturally includes British configuration/presentation elements such as:

- British editor names/descriptions;
- 3CB author metadata;
- radio rack assumptions;
- vehicle identification logic;
- green/sand British paint;
- British tactical/registration presentation.

The underlying MAN visual model itself is sufficiently generic to be useful for Karzeghistan.

### KDF conversion

Remove/replace:

```text
3CB/BAF editor identity
British registration presentation
British radio racks
British faction UI
3CB preview images
```

Add:

```text
KDF green/grey paint
Karzeghistani national rosette
KDF tactical numbers
KDF crew
KDF inventory/loadouts
```

---

# 42. Recommended Shared UKSF Family

The generic shared vehicle PBO should initially contain:

## HX60 4×4

```text
UKSF_Factions_Vehicle_MAN_HX60_Transport
UKSF_Factions_Vehicle_MAN_HX60_Cargo
UKSF_Factions_Vehicle_MAN_HX60_Fuel
UKSF_Factions_Vehicle_MAN_HX60_Repair
```

## HX58 6×6

```text
UKSF_Factions_Vehicle_MAN_HX58_Transport
UKSF_Factions_Vehicle_MAN_HX58_Cargo
UKSF_Factions_Vehicle_MAN_HX58_Fuel
UKSF_Factions_Vehicle_MAN_HX58_Repair
```

Avoid creating public generic container classes until the container feature is actually retained.

---

# 43. KDF Leaf Classes

`uksf_factions_kdf` should own faction-specific variants, for example:

```text
UKSF_Factions_KDF_MAN_HX60_Transport
UKSF_Factions_KDF_MAN_HX60_Cargo
UKSF_Factions_KDF_MAN_HX60_Fuel
UKSF_Factions_KDF_MAN_HX60_Repair

UKSF_Factions_KDF_MAN_HX58_Transport
UKSF_Factions_KDF_MAN_HX58_Cargo
UKSF_Factions_KDF_MAN_HX58_Fuel
UKSF_Factions_KDF_MAN_HX58_Repair
```

These should inherit from the neutral shared classes.

---

# 44. PBO Dependency Target

The cleaned shared vehicle PBO should target:

```text
Arma 3
+
UKSF_Factions Core only where genuinely necessary
```

It should **not** require:

```text
3CB
ACE
CBA
ACRE
TFAR
RHS
```

merely for the MAN family.

This makes the truck reusable by future factions regardless of their weapon/radio ecosystem.

---

# 45. Optional Compatibility

If later useful:

## `uksf_factions_ace`

May add:

- ACE repair capability;
- ACE spare wheel/track cargo;
- ACE refuel hooks;
- ACE container interactions.

## Future radio compatibility

May add:

- ACRE racks/intercom;
- other radio integrations.

Do not bake either into the geometry/shared base.

---

# 46. Container Feature Recommendation

The container mechanic is better separated into two phases.

## Phase 1 — vehicle family

Ship:

```text
Transport
Cargo
Fuel
Repair
```

with no custom container script dependency required.

## Phase 2 — generic container capability

If still useful, rewrite the 3CB MAN-local container system under the UKSF namespace using:

- explicit caller handling;
- engine-native interaction where possible;
- optional ACE actions;
- clean locality/ownership handling;
- no CBA requirement unless the project makes a deliberate CBA-wide decision.

This avoids turning an otherwise straightforward logistics vehicle into a scripting dependency project.

---

# 47. Performance Remediation Priority

Optimise in this order:

## 1. Texture payload

Highest priority.

Reason:

```text
~194 MiB of the ~225 MiB PBO is PAA
```

## 2. Remove unused variants/data

Especially:

- unused container textures;
- preview JPGs;
- special service variants;
- original faction UI assets.

## 3. Material/section review

Count actual render sections from editable MLOD.

Potentially merge only where it gives real value.

## 4. Geometry

Low priority.

Existing visible LOD progression is already good.

## 5. Scripts

Retain only features the project actually needs.

---

# 48. Proposed Runtime Texture Strategy

Initial test target:

### Major exterior

```text
body CO/NOHQ/SMDI: 2048
chassis CO/NOHQ/SMDI: 2048
parts CO/NOHQ/SMDI: 2048
rear/tarp: 2048 or existing 2048
```

### Interior

```text
2048
```

unless close-range testing demonstrates a clear reason for 4K.

### Containers

```text
2048
```

for normal first-release variants.

### AS / MC / TI

Review individually.

Do not assume they need the same resolution as the colour map.

The 4K originals should remain available as source masters.

---

# 49. Estimated Runtime Savings

No final PBO-size figure should be promised before conversion, but there is substantial headroom.

The current source package includes:

```text
39 × 4K textures
multiple original colour variants
multiple specialist container variants
34 preview JPGs
```

A KDF/shared release that ships only required variants at reviewed runtime resolutions should be much smaller.

Actual memory/performance impact must be benchmarked in game.

---

# 50. Provenance

3CB's published credits identify the original MAN truck source as:

```text
Bravo93 (16AA)
Original MAN truck from TurboSquid
```

The project has permission from 3CB to use/adapt relevant material.

Before final redistribution, the asset register should attach the exact permission/provenance evidence covering this underlying model chain.

### Current project status

```text
TECHNICALLY APPROVED
PROVENANCE RECORD TO BE ATTACHED BEFORE RELEASE
```

This is an administrative gate, not a technical rejection.

---

# 51. Technical Grade by Component

| Component | Grade | Decision |
|---|---|---|
| HX60 base geometry | A- | Retain |
| HX58 base geometry | A- | Retain |
| Visible LOD progression | A | Retain |
| Functional LOD presence | A-/B+ | Verify visually, retain |
| Materials | B+ | Review sections |
| Texture runtime footprint | C+/B- | Optimise |
| Standard transport | A-/B+ | Internalise |
| Fuel variant | A-/B+ | Internalise |
| Repair variant | B+ | Internalise |
| Cargo variant | B+ | Internalise |
| Basic containers | B | Optional second phase |
| Container script system | B | Rewrite/clean if retained |
| Special servicing containers | C | Defer |
| 3CB logistics framework | Reject for base | Do not carry over |
| ACE integration | Optional | Move to compat |
| ACRE integration | Optional | Move to compat |
| TFAR integration | Reject for base | Strip |
| CBA keybind/postInit integration | Reject for base | Strip |
| Automatic 3CB numbering | C | Remove/rebuild if useful |

---

# 52. Overall Grade

## Source as supplied

```text
GRADE B — WORTH REWORKING
```

## Expected after UKSF cleanup

```text
TARGET GRADE A
```

The main models themselves are already close to integration-ready quality.

The B grade reflects the work required around:

- runtime texture footprint;
- configuration;
- scripts;
- optional framework integration;
- faction presentation.

---

# 53. Final Dependency Graph

## Source

```text
UK3CB_BAF_Vehicles_MAN
        │
        ├── UK3CB_BAF_Vehicles_Weapons
        │      ├── servicing/logistics
        │      └── vehicle-light function
        │
        ├── CBA hooks
        ├── ACE optional/config hooks
        ├── ACRE racks
        └── TFAR intercom
```

## Target

```text
Arma 3
   │
   ▼
uksf_factions_vehicles
   │
   └── MAN HX58/HX60 generic family
            │
            ▼
     uksf_factions_kdf
```

Optional:

```text
uksf_factions_ace
        │
        └── enhanced ACE vehicle/container support
```

No 3CB runtime dependency is required by the intended target architecture.

---

# 54. Recommended Conversion Scope — Pass 1

Do **not** convert every source class at once.

First conversion pass:

```text
HX60 Transport
HX58 Transport
```

Reason:

- they prove chassis;
- suspension;
- damage;
- crew;
- cargo;
- textures;
- animations;
- faction inheritance.

Once both work dependency-free, extend to:

```text
Cargo
Fuel
Repair
```

Container functionality should come after the base truck family is stable.

---

# 55. Recommended First Technical File

For implementation, the first actual project source should be the **generic MAN vehicle config/base**, not KDF classes.

Suggested future file:

```text
uksf_factions_vehicles\man\config.cpp
```

or the equivalent layout chosen for the shared vehicle PBO.

First target:

```text
UKSF_Factions_Vehicle_MAN_HX60_Base
```

with only the minimum inherited/configured systems required to make the clean truck function.

Do not begin with all eight variants.

---

# 56. Acceptance Tests

Before the MAN family moves from `APPROVED` to `INTEGRATED`, test:

## Build

- [ ] PBOProject packs with no unexplained warnings/errors.
- [ ] No missing texture/material/model references.
- [ ] No hidden 3CB runtime dependency.

## Minimal modset

- [ ] Arma starts without 3CB.
- [ ] Truck can be placed in Eden.
- [ ] Truck can be placed by Zeus.
- [ ] Truck can be entered/exited.
- [ ] Driver animation works.
- [ ] Passenger animations work.
- [ ] Top-cover position works if retained.
- [ ] Wheels steer/animate.
- [ ] Suspension works.
- [ ] Wheel destruction works.
- [ ] Engine/hull/fuel/glass damage works.
- [ ] Lights work.
- [ ] Brake/reverse lights work.
- [ ] Mirrors/PiP behave acceptably.
- [ ] Audio works.
- [ ] Sling-load points work if retained.

## Multiplayer

- [ ] vehicle locality behaves normally;
- [ ] crew transitions replicate;
- [ ] damage replicates;
- [ ] container operations replicate if later retained.

## Performance

- [ ] no RPT spam;
- [ ] no permanent per-frame script;
- [ ] texture memory is reviewed after optimisation;
- [ ] LOD switching is visually acceptable.

---

# 57. Final Verdict

The source audit answers the preflight question:

> **Can the MAN model/config/material set be separated from British-specific 3CB frameworks cleanly enough to become a lightweight shared UKSF_Factions vehicle family?**

# YES.

The models and materials are substantially self-contained.

The unwanted dependencies are concentrated in removable config/script integration rather than baked into the physical asset.

The recommended path is therefore:

```text
3CB MAN SOURCE
      ↓
AUTHORised INTERNALISATION
      ↓
REMOVE 3CB / CBA / ACE / ACRE / TFAR BASE COUPLING
      ↓
PRESERVE WORKING MODEL / PHYSICS / DAMAGE / ANIMATIONS
      ↓
REDUCE RUNTIME TEXTURE FOOTPRINT
      ↓
CREATE NEUTRAL UKSF MAN BASE
      ↓
CREATE KDF PAINTED VARIANTS
      ↓
OPTIONAL CONTAINER / ACE / RADIO COMPATIBILITY LATER
```

This is a better long-term result than inheriting the 3CB MAN at runtime.

---

# 58. Technical Reference

For additional ODOL/MLOD auditing and source recovery, the current UKSFTA P3D project documents:

- Arma 3 ODOL v73–v75 support;
- LOD auditing;
- P3D forensics;
- material extraction;
- skeleton export;
- ODOL → editable MLOD conversion.

```text
https://github.com/UKSFTA/UKSFTA-P3D
```

Its format library:

```text
https://github.com/UKSFTA/UKSFTA-BIS
```

was used as a technical reference for interpreting ODOL v73 header/LOD metadata during this audit.
