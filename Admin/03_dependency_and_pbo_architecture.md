# UKSF_Factions — Dependency & PBO Architecture Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Dependency & PBO Architecture Standard  
**Status:** Active / Pre-implementation  
**Created:** 2026-08-09  
**Related documents:**
- `01_project_scope_standards_roadmap.md`
- `02_class_and_editor_naming_standard.md`
- `../assets/asset_register.md`
- `../factions/north_takistan/01_north_takistan_extremist_research_brief.md`
- `../factions/north_takistan/02_ntef_asset_dependency_audit.md`
- `../factions/north_takistan/03_ntef_organisation_roles_and_equipment_standard.md`

---

## 1. Purpose

This document defines how `UKSF_Factions` should be divided into addons/PBOs and how dependencies are allowed to flow between those components.

The architecture is intended to support:

- a growing multi-faction project;
- shared character assets;
- shared vehicle assets;
- selected 3CB/RHS-derived source assets under granted permissions;
- optional ACE integration;
- minimal unnecessary dependencies;
- straightforward Mikero PBOProject builds;
- clean Eden/Zeus behaviour;
- long-term class-name stability;
- future removal of much of the large 3CB Factions infantry/gear dependency.

The architecture should remain simple enough to maintain.

This project should **not** become a collection of dozens of tiny compatibility PBOs unless a genuine technical reason appears.

---

# PART I — ARCHITECTURE DECISION

## 2. Chosen Direction

`UKSF_Factions` will use a **small modular multi-PBO architecture**.

The initial architecture is:

```text
uksf_factions_core
uksf_factions_characters
uksf_factions_vehicles
uksf_factions_ntef
```

with:

```text
uksf_factions_ace
```

as an **optional compatibility/feature PBO**.

Future faction PBOs will be added only when the faction reaches implementation.

Example:

```text
uksf_factions_exfor
uksf_factions_tak_ins
uksf_factions_arg_ins
```

Potential shared asset PBOs such as:

```text
uksf_factions_weapons
uksf_factions_props
```

are **reserved but not created yet**.

---

## 3. Why Not One Large PBO

A single PBO would initially be simple, but the project is expected to contain:

- several factions;
- a growing shared gear library;
- vehicles;
- faction-specific config;
- optional compatibility;
- potentially substantial source assets.

Keeping all of this inside one PBO would make it harder to:

- determine dependencies;
- update one content area independently;
- remove or replace individual components;
- keep optional integration optional;
- diagnose config/load-order problems;
- package future subsets.

A multi-PBO architecture is therefore preferable from the beginning.

---

## 4. Why Not Many Small PBOs

Do not create separate PBOs for every:

- uniform family;
- vest;
- helmet;
- rifle;
- vehicle;
- faction subcategory;
- ACE feature.

Examples of architecture to avoid:

```text
uksf_factions_uniforms_ntef
uksf_factions_uniforms_exfor
uksf_factions_vests_ntef
uksf_factions_headgear_ntef
uksf_factions_hilux
uksf_factions_land_rover
uksf_factions_ntef_ace
uksf_factions_ntef_medical
```

unless later development provides a strong reason.

Excessive splitting produces:

- dependency complexity;
- more build targets;
- more signing/admin work;
- harder release management;
- greater chance of incorrect `requiredAddons[]`.

The project should remain modular at **meaningful functional boundaries**.

---

# PART II — DESIGN PRINCIPLES

## 5. Dependency Direction

Dependencies should flow:

```text
SHARED / GENERIC
        ↓
FACTION-SPECIFIC
        ↓
OPTIONAL COMPATIBILITY
```

Never the reverse.

A generic character asset must not depend on NTEF.

A generic vehicle must not depend on EXFOR.

`core` must not depend on any faction.

---

## 6. Leaf Dependency Principle

Third-party and framework-specific dependencies should be pushed as far toward the **leaf components** as practical.

Example:

```text
Core
  ↓
Characters
  ↓
NTEF
  ↓
RHS weapon classes if required
```

rather than:

```text
Core
  ↓
RHS
  ↓
ACE
  ↓
3CB
  ↓
everything else
```

The first approach keeps shared components reusable and prevents one faction's requirements propagating through the entire project.

---

## 7. Optional Framework Principle

A framework such as ACE should not become a requirement of unrelated content solely because one optional feature uses it.

Therefore:

```text
uksf_factions_ace
```

is separate from:

```text
uksf_factions_core
uksf_factions_characters
uksf_factions_vehicles
uksf_factions_ntef
```

unless a future project-wide ACE requirement is deliberately approved.

---

## 8. Performance Principle

PBO modularity is primarily a **dependency and maintenance strategy**.

Do not claim that dividing the same content into more PBOs inherently improves server FPS.

The meaningful performance/footprint objectives are:

- avoid requiring the full 3CB Factions package;
- avoid loading unused large content libraries where possible;
- keep runtime scripts minimal;
- avoid per-unit loops/PFHs unless genuinely required;
- maintain sensible model LODs;
- maintain sensible texture sizes;
- avoid excessive material/section complexity;
- avoid unnecessary duplicate config/content;
- keep AI and mission design concerns separate from addon architecture.

The PBO architecture enables content to be removed or packaged independently; the actual performance benefit comes from what is **not loaded or executed**.

---

# PART III — DEPENDENCY GRAPH

## 9. Initial Dependency Graph

Recommended Phase 1 topology:

```text
                         Arma 3
                            │
                            ▼
                  uksf_factions_core
                     /            \
                    /              \
                   ▼                ▼
      uksf_factions_characters   uksf_factions_vehicles
                   \                /
                    \              /
                     ▼            ▼
                    uksf_factions_ntef
                             │
                             │ exact external weapon
                             │ dependencies only if used
                             ▼
                       RHS / others
```

Optional ACE branch:

```text
Arma 3
  │
  ├──────────────► CBA_A3
  │                  │
  │                  ▼
  │                 ACE
  │                  │
  ▼                  │
uksf_factions_core    │
  │                   │
  ▼                   │
uksf_factions_characters
          │           │
          └──────┬────┘
                 ▼
         uksf_factions_ace
```

Important:

`uksf_factions_ace` should **not require `uksf_factions_ntef`** for the initial explosive-vest feature.

That keeps the explosive vest reusable for:

- NTEF;
- training OPFOR;
- mission-specific characters;
- future factions.

---

# PART IV — CORE PBO

## 10. `uksf_factions_core`

### `CfgPatches`

```cpp
UKSF_Factions_Core
```

### Purpose

Contains only genuinely project-wide definitions.

Expected content:

- common project metadata;
- shared editor categories/subcategories;
- common functions if required;
- common macros/includes;
- shared scripted constants;
- common UI/icon resources where genuinely project-wide;
- base config definitions that do not belong to an asset/faction PBO.

### Must not contain

- NTEF soldiers;
- NTEF faction class;
- EXFOR soldiers;
- physical uniform models;
- large vehicle assets;
- ACE-only functionality;
- faction-specific insignia.

### Dependency target

Prefer:

```text
Arma 3 base addons only
```

Do **not** make `core` depend on:

```text
ACE
3CB Factions
RHS
CUP
```

unless a future unavoidable requirement is approved.

---

## 11. Core Runtime Behaviour

`core` should contain as little automatic runtime behaviour as practical.

Preferred:

```text
config definitions
small shared functions
explicit calls
```

Avoid:

```text
global per-frame handlers
loops started for every unit
automatic scanning of all factions
```

A faction mod should not have a permanent runtime cost simply because it is loaded.

---

# PART V — CHARACTERS PBO

## 12. `uksf_factions_characters`

### `CfgPatches`

```cpp
UKSF_Factions_Characters
```

### Requires

```text
UKSF_Factions_Core
relevant Arma character/gear addons
```

Exact vanilla patch names will be entered only when the first config is written.

### Purpose

Own all **shared project character assets**.

Expected content:

- generic regional uniform models;
- generic uniform textures;
- chest rigs;
- webbing;
- plate carriers;
- helmets;
- regional headwear;
- facewear;
- backpacks;
- common character materials;
- hidden/shared model base classes where required.

---

## 13. Character Asset Rule

If an asset can reasonably be used by multiple factions, it belongs here.

Example:

```text
Tan regional tunic
AK chest rig
Pakol
Surplus helmet
Plain plate carrier
```

These are shared.

A permanent NTEF-specific uniform texture containing an NTEF marking does **not** belong here by default.

That variant belongs to:

```text
uksf_factions_ntef
```

while inheriting from the shared asset.

---

## 14. 3CB Infantry Dependency Rule

`uksf_factions_characters` must **not require the full 3CB Factions addon** for:

- uniforms;
- vests;
- helmets;
- core infantry gear.

Where a 3CB-origin asset is specifically useful and the project chooses to adapt/incorporate it under the permission granted to UKSF Surplus:

- the source provenance is recorded;
- the approved derivative becomes a `UKSF_Factions` asset;
- the final class lives under the `UKSF_Factions_` namespace;
- the class should not unnecessarily inherit from a 3CB config class if this would preserve an otherwise avoidable 3CB runtime dependency.

This is one of the main architectural goals of the project.

---

## 15. RHS-Derived Character Assets

The same principle applies where an RHS-origin character asset is physically incorporated/adapted under granted permission.

If using the model independently is technically sensible:

- make it project-owned at config level;
- retain provenance/credit in the asset register;
- avoid a runtime RHS dependency solely because of source provenance.

If it relies materially on RHS:

- inherited classes;
- skeletons;
- proxies;
- materials;
- scripts;
- other runtime data;

then use an explicit RHS dependency instead of forcing a fragile partial extraction.

Technical correctness takes priority over dependency removal.

---

# PART VI — VEHICLES PBO

## 16. `uksf_factions_vehicles`

### `CfgPatches`

```cpp
UKSF_Factions_Vehicles
```

### Requires

```text
UKSF_Factions_Core
relevant Arma vehicle base addons
exact external addons only where actually referenced
```

### Purpose

Own shared vehicle assets and generic vehicle base classes.

Expected candidates:

- Hilux/pickup family;
- Land Rover family;
- SUVs;
- vans;
- utility trucks;
- technical base models;
- motorcycles;
- selected civilian/regional vehicles;
- adapted 3CB vehicle source assets;
- selected RHS-derived assets where useful.

---

## 17. Vehicle Model vs Faction Variant

Shared model/base:

```cpp
UKSF_Factions_Vehicle_Hilux
```

Potential faction variant:

```cpp
UKSF_Factions_NTEF_Hilux
UKSF_Factions_NTEF_Hilux_PKM
```

The generic model and common vehicle configuration belong in:

```text
uksf_factions_vehicles
```

NTEF:

- crew;
- faction;
- side;
- editor placement;
- faction-specific markings;
- faction-specific inventory;

belong in:

```text
uksf_factions_ntef
```

where practical.

---

## 18. Weaponised Vehicle Dependencies

A vehicle model may be independent while a turret weapon uses an external weapon/ammo ecosystem.

Do not automatically drag those external dependencies into `core`.

Possible approaches:

### Preferred where simple

Use a project-owned/adapted vehicle with the existing weapon class it genuinely needs.

Then:

```text
uksf_factions_vehicles
```

depends on the exact required weapon addon.

### Alternative

Keep generic unarmed vehicle base classes dependency-light and define armed faction variants in:

```text
uksf_factions_ntef
```

where the weapon dependency already exists.

This is preferable if adding a PKM/SPG-9 class would otherwise cause every user of the generic vehicle library to require an unrelated weapon pack.

### Decision rule

Push weapon-specific dependencies toward the faction/armed variant unless doing so creates significant duplicate config.

---

# PART VII — NTEF PBO

## 19. `uksf_factions_ntef`

### `CfgPatches`

```cpp
UKSF_Factions_NTEF
```

### Requires

Minimum project dependencies:

```text
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
```

External dependencies:

```text
TBD by final weapon/vehicle class audit
```

### Must not require

```text
3CB Factions
ACE
```

by default.

This is a locked architectural objective.

---

## 20. NTEF Content Ownership

`uksf_factions_ntef` contains:

- `CfgFactionClasses` NTEF definition;
- NTEF soldier classes;
- NTEF vehicle variants;
- NTEF groups;
- NTEF editor-facing faction config;
- faction-specific insignia;
- faction-specific flag;
- faction-specific editor icon;
- NTEF-only textures/markings;
- NTEF-specific loadout definitions;
- NTEF-specific lightweight scripts only where necessary.

It should not contain:

- generic uniform models;
- generic shared vehicle models;
- generic common functions;
- ACE explosive framework integration.

---

## 21. NTEF Weapon Dependency Strategy

The NTEF research already establishes that its weapon requirement is well covered by existing RHS/3CB-derived families.

### Initial preference

Use existing high-quality weapon classes where the unit already carries the required dependency.

For NTEF, likely examples include:

- AKM;
- AK-74;
- AK-100 family;
- PKM;
- SVD;
- RPG-7.

### Do not create wrapper weapons only for namespace purity

If:

```cpp
rhs_weap_akm
```

already provides exactly what we want, use it.

Do not create:

```cpp
UKSF_Factions_Weapon_AKM
```

that inherits from it and changes nothing.

### Future dependency reduction

If the project later incorporates a selected weapon source under granted permission for a genuine reason, that weapon should move into:

```text
uksf_factions_weapons
```

rather than being buried inside NTEF.

---

# PART VIII — WEAPONS PBO

## 22. `uksf_factions_weapons`

### Status

```text
RESERVED / NOT CREATED
```

Create only if the project begins to own or adapt enough weapon content to justify it.

Reasons that would justify creation:

- dependency reduction;
- substantial modifications;
- new textures/models;
- magazine ecosystem changes;
- weapon families reused by multiple factions;
- maintaining adapted 3CB/RHS-derived weapons independently.

Do not create the PBO merely because the naming standard reserved it.

---

# PART IX — ACE PBO

## 23. `uksf_factions_ace`

### `CfgPatches`

```cpp
UKSF_Factions_ACE
```

### Status

```text
OPTIONAL
```

### Requires

Expected:

```text
UKSF_Factions_Core
UKSF_Factions_Characters
ACE explosives/framework patch classes required by implementation
CBA as required by ACE
```

Exact ACE `requiredAddons[]` names will be determined from the actual implementation, not guessed in advance.

---

## 24. Why ACE Is Separate

ACE is heavily integrated with CBA and explicitly documents optional compatibility components for third-party mods.

ACE's own modularity guidance recommends keeping dependencies narrow and providing compatibility PBOs for third-party integration when behaviour is not inert without ACE.

`UKSF_Factions` should follow that pattern for features that genuinely require ACE.

This prevents:

```text
uniform model
```

from requiring:

```text
ACE + CBA
```

merely because the project also contains an ACE explosive-vest feature.

---

# PART X — EXPLOSIVE VEST ARCHITECTURE

## 25. Physical Asset

The physical 3D vest model, textures and materials are a **character asset**.

Therefore source data should live under:

```text
uksf_factions_characters
```

Example path:

```text
\uksf_factions\characters\data\vests\explosive_01\
```

However, the public usable explosive-vest config item does not need to exist in `characters`.

---

## 26. Public Explosive Vest Item

Recommended:

Define the functional user-facing item in:

```text
uksf_factions_ace
```

Reserved public class:

```cpp
UKSF_Factions_Vest_Explosive_01
```

This class references the model stored in `characters`.

Without the optional ACE PBO:

- the model files can exist harmlessly;
- the functional explosive vest item is not exposed;
- users are not presented with a misleading inert "explosive" vest.

This is cleaner than defining an ordinary vest in `characters` and attempting to retrofit all functionality later.

---

## 27. ACE Explosive Objects

Reserved conceptual classes remain:

```cpp
UKSF_Factions_Vest_Explosive_01
UKSF_Factions_Mag_ExplosiveVest
UKSF_Factions_Ammo_ExplosiveVest
UKSF_Factions_ExplosiveVest_Place
```

These should live in:

```text
uksf_factions_ace
```

if all exist only to support the ACE feature.

ACE's public explosives framework currently provides trigger support including:

```text
Cellphone
DeadManSwitch
Command
Timer
```

and supports custom explosive configuration.

The future implementation should therefore integrate with ACE rather than reproduce its detonator UI/framework.

---

## 28. Explosive Vest Faction Independence

`uksf_factions_ace` should not require NTEF solely for the vest.

The item may later be used by:

- NTEF;
- EXFOR training scenarios;
- mission-scripted characters;
- other future irregular factions.

Therefore the vest is a **shared optional gameplay asset**.

---

## 29. Pre-Equipped NTEF Unit

Current decision:

```text
DO NOT CREATE INITIALLY
```

Mission makers can equip the functional item as required.

If a pre-equipped editor unit later proves genuinely useful, do **not** make the entire NTEF PBO depend on ACE.

Options then:

1. define the extra unit inside `uksf_factions_ace` using the NTEF faction;
2. create a tiny faction compatibility PBO only if several ACE-specific NTEF classes eventually exist.

Do not create:

```text
uksf_factions_ntef_ace
```

for one unit.

---

# PART XI — EXFOR PBO

## 30. `uksf_factions_exfor`

### Status

```text
FUTURE
```

### Likely requires

```text
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
```

plus exact weapon dependencies selected during EXFOR research.

### Must not require

```text
NTEF
```

The factions should coexist but remain structurally independent.

---

# PART XII — FUTURE FACTION RULE

## 31. Each Major Faction Gets Its Own PBO

When implemented:

```text
uksf_factions_<factionid>
```

Examples:

```text
uksf_factions_ntef
uksf_factions_exfor
uksf_factions_tak_ins
uksf_factions_tak_proxy
uksf_factions_arg_ins
```

A faction PBO contains faction configuration and faction-specific identity, **not duplicated shared models**.

---

## 32. When Two Factions Share Gear

Do not make:

```text
uksf_factions_tak_ins
```

depend on:

```text
uksf_factions_ntef
```

merely because both use the same tunic.

Move the shared tunic to:

```text
uksf_factions_characters
```

Faction-to-faction dependencies should be avoided.

---

# PART XIII — PROPS PBO

## 33. `uksf_factions_props`

### Status

```text
RESERVED / NOT CREATED
```

Create only once there is enough reusable environmental content.

Possible future content:

- faction flags as placeable objects;
- roadblocks;
- regional props;
- training props;
- signage;
- environmental graffiti objects;
- static faction objects.

Small faction-specific images should remain in the faction PBO unless a true shared props library develops.

---

# PART XIV — SOURCE TREE

## 34. Recommended Git Repository Layout

```text
UKSF_Factions/
├── addons/
│   ├── core/
│   │   ├── config.cpp
│   │   ├── functions/
│   │   └── data/
│   ├── characters/
│   │   ├── config.cpp
│   │   ├── model.cfg
│   │   └── data/
│   ├── vehicles/
│   │   ├── config.cpp
│   │   ├── model.cfg
│   │   └── data/
│   ├── ntef/
│   │   ├── config.cpp
│   │   └── data/
│   └── ace/
│       ├── config.cpp
│       └── functions/
├── docs/
│   ├── assets/
│   ├── factions/
│   └── project/
├── optionals/
├── tools/
├── .gitignore
├── LICENSE
└── README.md
```

`weapons`, `props`, `exfor`, etc. should only be added when implementation begins.

---

## 35. Mikero/P Drive Layout

Suggested source-drive layout:

```text
P:\
└── uksf_factions\
    ├── core\
    ├── characters\
    ├── vehicles\
    ├── ntef\
    └── ace\
```

Target virtual prefixes:

```text
\uksf_factions\core\
\uksf_factions\characters\
\uksf_factions\vehicles\
\uksf_factions\ntef\
\uksf_factions\ace\
```

Exact PBOProject project-root configuration will be established when the first addon skeleton is created.

The important rule is that cross-PBO resource paths use stable virtual prefixes and never depend on local Windows drive paths.

---

# PART XV — BUILD OUTPUT

## 36. Normal Release Layout

Recommended:

```text
@UKSF_Factions/
├── addons/
│   ├── uksf_factions_core.pbo
│   ├── uksf_factions_core.pbo.<key>.bisign
│   ├── uksf_factions_characters.pbo
│   ├── uksf_factions_characters.pbo.<key>.bisign
│   ├── uksf_factions_vehicles.pbo
│   ├── uksf_factions_vehicles.pbo.<key>.bisign
│   ├── uksf_factions_ntef.pbo
│   └── uksf_factions_ntef.pbo.<key>.bisign
├── optionals/
│   ├── uksf_factions_ace.pbo
│   └── uksf_factions_ace.pbo.<key>.bisign
├── keys/
│   └── <public-key>.bikey
├── mod.cpp
└── README.txt
```

This layout is provisional until release tooling is written.

---

## 37. Unit Internal ACE Deployment

Because the UKSF unit already uses ACE in normal operations, its internal modpack may choose to deploy:

```text
uksf_factions_ace.pbo
```

directly inside:

```text
@UKSF_Factions\addons\
```

for convenience.

The public package may leave it under:

```text
optionals\
```

or publish it as a clearly labelled optional component.

ACE itself documents the pattern of distributing optional compatibility PBOs separately from core content.

---

# PART XVI — CfgPatches / LOAD ORDER

## 38. Every PBO Requires Correct `CfgPatches`

Each addon/PBO must have an intentional `CfgPatches` class.

Bohemia documentation identifies `CfgPatches` as the addon header used to describe:

- dependencies;
- content;
- metadata.

Do not rely on accidental load order.

---

## 39. `requiredAddons[]`

`requiredAddons[]` should contain the patch classes that must load first.

Use it to express real inheritance/config requirements.

Example conceptual structure:

```cpp
class CfgPatches {
    class UKSF_Factions_NTEF {
        requiredAddons[] = {
            "UKSF_Factions_Core",
            "UKSF_Factions_Characters",
            "UKSF_Factions_Vehicles"
        };
    };
};
```

External patch names will be added only when known.

Do not add entire mod families speculatively.

---

## 40. Zeus `units[]`

Every editor/Zeus-placeable `CfgVehicles` class should appear in the correct PBO's:

```cpp
units[] = {};
```

Bohemia's Curator documentation specifically notes that Zeus addon availability uses objects declared in `CfgPatches.units[]`.

Therefore inaccurate `units[]` is a functional bug.

---

## 41. `weapons[]`

Keep:

```cpp
weapons[] = {};
```

accurate for project-owned public weapon/gear classes.

Do not treat the list as optional housekeeping.

---

# PART XVII — THIRD-PARTY DEPENDENCIES

## 42. 3CB

### Runtime policy

NTEF should not require the full 3CB Factions PBO stack for:

- units;
- uniforms;
- vests;
- helmets.

### Source policy

The project owner has confirmed full permission to use required 3CB assets.

Selected useful content may therefore be adapted into the appropriate project PBO, particularly:

- vehicles;
- technicals;
- weapons;
- supporting regional assets.

Record each incorporated source in:

```text
docs/assets/asset_register.md
```

---

## 43. RHS

### Initial runtime expectation

RHS is likely to remain an external dependency for many weapon classes because it already supplies the exact weapon ecosystem required by NTEF and is heavily used by UKSF.

### Source permission

The project owner has confirmed full permission to use required RHS assets.

### Architecture rule

Do not internalise an RHS weapon merely to remove the text `rhs_` from a class reference.

Internalise/adapt only where there is a real benefit:

- dependency reduction;
- performance/footprint;
- custom behaviour;
- maintenance;
- required visual changes.

---

## 44. CUP

No core `UKSF_Factions` component should require CUP at this stage.

If one future asset requires CUP:

- evaluate whether the asset is valuable enough;
- determine whether it belongs at the faction leaf;
- avoid propagating CUP into `core` or generic assets unnecessarily.

---

## 45. CBA

CBA is **not currently locked as a mandatory core dependency**.

If a shared runtime feature genuinely benefits from CBA:

- add the exact dependency to the component that uses it;
- do not automatically add it to all PBOs.

ACE already requires CBA, so the optional ACE component may rely on that framework chain.

---

# PART XVIII — MISSION DEPENDENCY BEHAVIOUR

## 46. Editor-Placed Classes

If a mission directly places a class from:

```text
uksf_factions_ntef
```

the mission naturally requires that addon on participants as normal Arma content.

This is expected.

Do not attempt to disguise faction dependencies.

---

## 47. Optional ACE Classes

A mission using:

```cpp
UKSF_Factions_Vest_Explosive_01
```

will require the optional ACE component.

Mission makers should therefore only use the item when the deployment/modset includes:

```text
uksf_factions_ace
ACE
CBA
```

---

# PART XIX — SERVER/CLIENT CONSISTENCY

## 48. Content PBOs

Content used by a multiplayer mission should be available consistently to required clients/server according to the unit's normal mod deployment.

Do not design client-only visual content where the underlying class is used by server-side mission logic unless carefully tested.

---

## 49. Optional Components

Optional does **not** mean:

> safe for half the players to omit while the mission actively uses its classes.

It means:

> the base mod does not require it, and modpacks/missions that need the feature enable it consistently.

---

# PART XX — BUILD ORDER

## 50. Development Build Order

Once implementation begins:

```text
1. uksf_factions_core
2. uksf_factions_characters
3. uksf_factions_vehicles
4. uksf_factions_ntef
5. uksf_factions_ace
```

`characters` and `vehicles` may develop in parallel once `core` exists.

NTEF should not be configured before enough shared base classes are stable.

---

## 51. Future Build Order

Example:

```text
core
├── characters
├── vehicles
├── weapons (if created)
├── props (if created)
│
├── ntef
├── exfor
├── tak_ins
└── arg_ins

ace
└── depends only on required shared components/frameworks
```

Faction PBOs should remain siblings, not chains.

---

# PART XXI — RELEASE VERSIONING

## 52. Project Version

The entire `UKSF_Factions` release should use one project version.

Do not independently version each PBO for public releases unless tooling later requires internal component version metadata.

Example:

```text
UKSF_Factions 0.1.0
```

contains matching builds of:

```text
core
characters
vehicles
ntef
ace optional
```

---

## 53. PBO Filename Stability

Do not add versions to PBO filenames.

Correct:

```text
uksf_factions_ntef.pbo
```

Incorrect:

```text
uksf_factions_ntef_0_1_0.pbo
```

This supports mission and server administration stability.

---

# PART XXII — CLASS MIGRATION

## 54. Moving a Class Between PBOs

Public classname stability matters more than which PBO contains it.

If:

```cpp
UKSF_Factions_Vehicle_Hilux
```

moves internally from one component to another later, preserve the classname where practical.

Update:

```text
requiredAddons[]
```

and build structure instead of renaming the public class.

---

## 55. Deprecation

If a public class must be replaced:

- preserve compatibility inheritance/alias where practical;
- document replacement;
- avoid breaking missions silently.

Do not delete public classes merely to make the internal folder structure prettier.

---

# PART XXIII — PERFORMANCE CONSEQUENCES

## 56. What This Architecture Helps

The architecture supports performance/footprint goals by making it possible to:

- exclude unused faction PBOs in tailored packages;
- avoid a full 3CB Factions gear dependency;
- keep ACE integration out of non-ACE content;
- isolate heavy vehicle assets;
- minimise runtime cross-component code;
- inspect dependencies clearly.

---

## 57. What This Architecture Does Not Solve

It does not automatically fix:

- badly optimised models;
- missing LODs;
- oversized textures;
- too many material sections;
- mission AI count;
- heavy mission scripts;
- poor server configuration;
- excessive per-frame code.

These require separate standards and testing.

---

# PART XXIV — TEST MATRIX

## 58. Core Load Test

Load:

```text
Arma 3
UKSF_Factions Core
```

Expected:

- no missing-addon errors;
- no ACE/RHS/3CB dependency;
- clean RPT.

---

## 59. Characters Load Test

Load:

```text
Core
Characters
```

Expected:

- generic gear available;
- no NTEF dependency;
- no 3CB Factions infantry dependency;
- clean RPT.

---

## 60. Vehicles Load Test

Load:

```text
Core
Vehicles
```

plus any explicitly required external patch.

Expected:

- generic vehicle assets function;
- no NTEF dependency;
- no unnecessary character dependency unless vehicle crew/config genuinely requires it.

---

## 61. NTEF Load Test

Load:

```text
Core
Characters
Vehicles
NTEF
required external weapon addons
```

without:

```text
3CB Factions
ACE
```

Expected:

- all standard NTEF infantry available;
- all standard NTEF vehicles available;
- groups spawn;
- Eden/Zeus categories work;
- no missing gear;
- no ACE requirement;
- no full 3CB Factions requirement.

This test is a **release gate**.

---

## 62. ACE Optional Test

Load:

```text
Core
Characters
ACE
CBA
UKSF_Factions ACE
```

Expected:

- ACE integration loads cleanly;
- explosive vest item exists;
- supported ACE triggers are available as configured;
- no NTEF requirement.

---

## 63. No-ACE Base Test

Load base `UKSF_Factions` without the optional ACE PBO.

Expected:

- no missing ACE config;
- no inert user-facing explosive vest;
- base factions function normally.

---

## 64. Full Unit Modset Test

Final validation also requires the actual UKSF deployment modset.

Purpose:

- detect inherited class conflicts;
- detect duplicate content;
- detect overwritten configs;
- validate load order;
- validate server RPT;
- assess actual memory/performance impact.

---

# PART XXV — PBO PROJECT / BUILD QUALITY

## 65. Mikero PBOProject

The project will continue to use Mikero PBOProject as the primary packing workflow unless a later build-system decision changes it.

Each source addon should be buildable as an intentional addon with:

- valid config;
- valid `CfgPatches`;
- correct virtual paths;
- explicit dependencies.

Mikero's current pboProject documentation emphasises valid config/`CfgPatches` structure and dependency-aware addon construction.

---

## 66. Build Failure Policy

Treat PBOProject warnings/errors as build issues to resolve, not messages to suppress casually.

Do not work around:

- missing dependencies;
- bad paths;
- duplicate classes;
- invalid config inheritance;

by weakening checks unless the root cause is understood.

---

# PART XXVI — LOCKED ARCHITECTURE DECISIONS

## 67. Locked

- `UKSF_Factions` starts as a small modular multi-PBO project.
- `uksf_factions_core` is mandatory shared infrastructure.
- `uksf_factions_characters` owns shared character gear/assets.
- `uksf_factions_vehicles` owns shared vehicle assets/base classes.
- `uksf_factions_ntef` owns NTEF faction configuration.
- `uksf_factions_ace` is optional.
- ACE does not become a requirement of NTEF's standard faction PBO.
- NTEF does not require full 3CB Factions.
- Shared assets do not depend on faction PBOs.
- Faction PBOs do not depend on one another.
- Exact external dependencies are declared only where genuinely used.
- `uksf_factions_weapons` is reserved but deferred.
- `uksf_factions_props` is reserved but deferred.
- The explosive vest's physical model may live in `characters`.
- The functional ACE explosive-vest classes live in `uksf_factions_ace`.
- Initial explosive-vest support does not require a pre-equipped NTEF unit.
- PBO splitting is not treated as an FPS optimisation by itself.
- Class names should remain stable even if internal PBO ownership changes later.

---

# PART XXVII — OPEN ARCHITECTURE DECISIONS

## 68. Resolve During Implementation

- [ ] Exact vanilla `requiredAddons[]` for Core.
- [ ] Exact vanilla `requiredAddons[]` for Characters.
- [ ] Exact vanilla/external `requiredAddons[]` for Vehicles.
- [ ] Exact RHS weapon patch dependencies used by NTEF.
- [ ] Whether NTEF ultimately needs RHS as a runtime dependency after asset selection.
- [ ] Whether selected 3CB technical weapon systems are internalised or reference another weapon addon.
- [ ] Exact ACE patch dependencies for explosive-vest support.
- [ ] Whether public releases ship ACE under `optionals/` or as a separate compatibility download.
- [ ] Whether a shared Weapons PBO becomes worthwhile.
- [ ] Whether a shared Props PBO becomes worthwhile.
- [ ] Exact `$PBOPREFIX$` / PBOProject project layout once the first source addon skeleton is created.
- [ ] Signing key/release signing workflow.
- [ ] Automated version metadata.
- [ ] Whether build output is automated later through scripts/CI.

---

# PART XXVIII — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## Bohemia Interactive Community Wiki — CfgPatches

Bohemia documents `CfgPatches` as the addon header containing addon requirements, content and metadata.

It is also used to define addon load dependencies through `requiredAddons[]`.

```text
https://community.bohemia.net/wiki/CfgPatches
```

---

## Bohemia Interactive Community Wiki — Creating an Addon

Current Bohemia guidance identifies `CfgPatches` as a minimum core component of an addon config and describes it as the place where external addon requirements and added content are declared.

```text
https://community.bohemia.net/wiki/Arma_3:_Creating_an_Addon
```

---

## Bohemia Interactive Community Wiki — Curator

Bohemia's Curator documentation states that community-addon objects available to Zeus depend on correct object configuration and the classes declared in the addon's `CfgPatches.units[]`.

```text
https://community.bohemia.net/wiki/Arma_3:_Curator
```

---

## Mikero Tools / Bohemia Community Wiki — pboProject

Current pboProject documentation emphasises valid addon configuration, `CfgPatches`, dependency checking and correct addon construction.

```text
https://community.bistudio.com/wiki/pboProject
```

---

## ACE3 — Modularity and PBO Structure

ACE's documented modularity principles recommend keeping module dependencies narrow and using compatibility PBOs for third-party integration where required.

ACE also notes that many inert config compatibility entries may exist without explicit ACE requirements, while behaviour that is not inert is better isolated into compatibility PBOs.

```text
https://ace3.acemod.org/wiki/development/modularity-and-pbo-structure
```

---

## ACE3 — Installation Guide

ACE documents CBA as a prerequisite and describes its own optional PBO/component installation pattern.

```text
https://ace3.acemod.org/wiki/user/installation-guide
```

---

## ACE3 — Explosives Framework

ACE documents custom explosives, place objects, detonators and supported triggers including:

- `DeadManSwitch`;
- `Cellphone`;
- `Command`;
- `Timer`.

This framework will be the basis of any future `UKSF_Factions` explosive-vest integration.

```text
https://ace3.acemod.org/wiki/framework/explosives-framework
```

---

# PART XXIX — CURRENT CONCLUSION

The project architecture is now:

```text
                 ┌──────────────────────────┐
                 │   uksf_factions_core     │
                 └────────────┬─────────────┘
                              │
                  ┌───────────┴───────────┐
                  ▼                       ▼
        ┌──────────────────┐    ┌──────────────────┐
        │    characters    │    │     vehicles     │
        └─────────┬────────┘    └─────────┬────────┘
                  │                       │
                  └──────────┬────────────┘
                             ▼
                  ┌──────────────────────┐
                  │ uksf_factions_ntef  │
                  └──────────────────────┘

             OPTIONAL / PARALLEL BRANCH

 CBA ──► ACE ───────────────┐
                            ▼
 characters ───────► uksf_factions_ace
 core ─────────────►
```

This gives `UKSF_Factions` a stable foundation for growing into multiple factions without recreating the large monolithic dependency structure that the project is intended to replace.

The next project-level admin document should define the **performance and asset optimisation standard** before model conversion begins.
