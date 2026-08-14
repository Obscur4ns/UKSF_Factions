# UKSF_Factions — Class, Addon & Editor Naming Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Class, Addon & Editor Naming Standard  
**Status:** Active / Pre-implementation  
**Created:** 2026-08-09  

---

## 1. Purpose

This document defines naming conventions for every configuration-facing element in `UKSF_Factions`.

The goal is to ensure that future factions and shared assets use predictable, collision-resistant names from the first line of `config.cpp`.

This standard covers:

- project prefixes;
- addon/PBO names;
- `CfgPatches`;
- `CfgFactionClasses`;
- editor categories;
- editor subcategories;
- `CfgVehicles` unit and vehicle classes;
- `CfgWeapons` gear classes;
- `CfgMagazines`;
- `CfgAmmo`;
- functions;
- event handlers;
- scripted variables;
- model/texture paths;
- display names;
- group classes;
- compatibility components.

The standard should be followed unless an engine/framework constraint requires an exception.

---

# PART I — GLOBAL PREFIXES

## 2. Canonical Project Prefix

The canonical public project prefix is:

```text
UKSF_Factions
```

Use this for Arma config classes that are owned by the project.

Examples:

```cpp
UKSF_Factions_NTEF_Rifleman
UKSF_Factions_Uniform_Regional_01
UKSF_Factions_Vest_ChestRig_01
```

---

## 3. Script Namespace Prefix

For SQF globals and functions, use the shorter namespace:

```text
UKSF_Factions
```

Examples:

```sqf
UKSF_Factions_fnc_applyLoadout
UKSF_Factions_fnc_initUnit
UKSF_Factions_NTEF_enabled
```

Do not introduce unrelated abbreviations such as:

```text
UKSFF
UKF
UFAC
```

into public script/config namespaces.

`UKSFF` remains acceptable only as the **asset-register ID prefix** because those IDs are documentation identifiers rather than game classes.

---

## 4. Filesystem/Add-on Slug

For addon folders and PBO filenames, use lowercase:

```text
uksf_factions
```

Component suffixes should also be lowercase.

Examples:

```text
uksf_factions_core
uksf_factions_characters
uksf_factions_vehicles
uksf_factions_ntef
```

This keeps addon filenames compact and avoids mixed-case path inconsistencies.

---

# PART II — ADDON / PBO NAMING

## 5. Addon Naming Pattern

If the project becomes multi-PBO, use:

```text
uksf_factions_<component>
```

Examples:

```text
uksf_factions_core
uksf_factions_characters
uksf_factions_vehicles
uksf_factions_ntef
uksf_factions_exfor
uksf_factions_ace
```

Do not use:

```text
UKSF_Factions_Northern_Takistan_Emirate_Front
UKSFFacNTEF
Factions_NTEF_UKSF
```

---

## 6. Reserved Component Names

The following component names are reserved for future use:

| Addon | Purpose |
|---|---|
| `uksf_factions_core` | Shared definitions, editor categories, common functions |
| `uksf_factions_characters` | Shared uniforms, vests, helmets, facewear, backpacks |
| `uksf_factions_weapons` | Project-owned/adapted weapon assets if required |
| `uksf_factions_vehicles` | Shared project-owned/adapted vehicles |
| `uksf_factions_props` | Shared environmental/static assets |
| `uksf_factions_ntef` | Northern Takistan Emirate Front faction config |
| `uksf_factions_exfor` | British training OPFOR / EXFOR faction config |
| `uksf_factions_ace` | ACE-specific compatibility/integration where separation is useful |

These names are reserved only.

The actual PBO architecture remains subject to the future architecture document.

---

## 7. Single-PBO Compatibility

If the project initially uses one PBO, use:

```text
uksf_factions
```

with:

```cpp
class CfgPatches {
    class UKSF_Factions {};
};
```

Do not create fake component namespaces inside a single PBO solely to imitate a future split.

The naming standard should allow the project to move to multiple PBOs later without renaming public unit classes.

---

# PART III — CfgPatches

## 8. CfgPatches Class Pattern

Use:

```text
UKSF_Factions_<Component>
```

Examples:

```cpp
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
UKSF_Factions_NTEF
UKSF_Factions_EXFOR
UKSF_Factions_ACE
```

The `CfgPatches` class should correspond directly to its addon/PBO component.

---

## 9. CfgPatches `units[]`

Every `CfgVehicles` class intended to be available in Eden/Zeus should be declared in the appropriate addon's `units[]`.

This includes:

- soldiers;
- vehicles;
- static weapons;
- placeable explosive helper objects where applicable;
- other editor-placeable objects.

Bohemia's Curator documentation notes that Zeus addon availability depends on properly configured objects and addon/unit declarations, so `units[]` should be treated as part of release correctness rather than administrative decoration.

---

## 10. CfgPatches `weapons[]`

Project-owned `CfgWeapons` classes should be listed in the owning addon's `weapons[]` where appropriate.

Examples include:

- uniforms;
- vests;
- headgear;
- facewear when implemented as `CfgWeapons`;
- backpacks if applicable to the engine class used;
- detonators/items;
- project-owned weapons.

Keep lists accurate.

Do not leave copied example class names in them.

---

## 11. `requiredAddons[]`

Only list genuine runtime/config inheritance requirements.

Avoid adding a dependency merely because an asset was present during development.

Example conceptual dependency tree:

```text
UKSF_Factions_NTEF
    ↓
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
ACE/RHS/etc. only where actually referenced
```

Bohemia's configuration guidance treats `CfgPatches` and addon requirements as core config structure, so dependency declarations should be maintained deliberately.

---

# PART IV — FACTION IDENTIFIERS

## 12. Faction Internal ID Standard

Each faction receives a short stable identifier.

Current reserved faction IDs:

| ID | Faction |
|---|---|
| `NTEF` | Northern Takistan Emirate Front |
| `EXFOR` | British training exercise OPFOR |
| `TAK_INS` | Future traditional Takistani insurgents |
| `TAK_PROXY` | Future Takistani regional proxy force |
| `ARG_INS` | Future Arganan insurgents |
| `AFR_MIL` | Future African political/warlord militia |
| `CHR_PARAMIL` | Future Chernarussian paramilitary |

These are internal design IDs.

Future display-name changes should not force class renaming.

---

## 13. `CfgFactionClasses` Pattern

Use:

```text
UKSF_Factions_<FactionID>
```

Examples:

```cpp
class UKSF_Factions_NTEF;
class UKSF_Factions_EXFOR;
```

Current NTEF faction class:

```text
UKSF_Factions_NTEF
```

### NTEF Display Name

Working display name:

```text
Northern Takistan Emirate Front
```

Do not prepend `UKSF -` inside the actual faction name unless editor testing later shows a practical sorting benefit.

The mod/addon branding already provides project identity.

---

## 14. Faction Side

Default NTEF side:

```text
EAST / OPFOR
```

The internal faction ID should not encode side.

Do not use:

```text
UKSF_Factions_OPFOR_NTEF
```

because side can conceptually change without faction identity changing.

---

# PART V — EDITOR CATEGORIES

## 15. Project Editor Category

If a custom project-wide editor category is useful, use:

```text
UKSF_Factions
```

Display name:

```text
UKSF Factions
```

However, do not force all soldiers/vehicles into a custom `CfgEditorCategories` tree if standard faction sorting already produces a cleaner Eden experience.

This decision should be tested with NTEF before being finalised.

---

## 16. Editor Subcategory Class Pattern

Use:

```text
UKSF_Factions_EdSubcat_<Name>
```

Examples:

```cpp
UKSF_Factions_EdSubcat_Infantry
UKSF_Factions_EdSubcat_InfantryVeteran
UKSF_Factions_EdSubcat_Specialists
UKSF_Factions_EdSubcat_Cars
UKSF_Factions_EdSubcat_ArmedCars
UKSF_Factions_EdSubcat_Trucks
UKSF_Factions_EdSubcat_Captured
UKSF_Factions_EdSubcat_Drones
```

These may be shared across factions.

Do not create faction-specific copies of identical subcategories unless Eden requires it.

---

## 17. NTEF Preferred Editor Subcategories

Initial recommendation:

```text
Men
Men (Veteran)
Cars
Cars (Armed)
Trucks
Captured Vehicles
Drones
```

Possible class mapping:

```cpp
UKSF_Factions_EdSubcat_Infantry
UKSF_Factions_EdSubcat_InfantryVeteran
UKSF_Factions_EdSubcat_Cars
UKSF_Factions_EdSubcat_ArmedCars
UKSF_Factions_EdSubcat_Trucks
UKSF_Factions_EdSubcat_Captured
UKSF_Factions_EdSubcat_Drones
```

Avoid excessive subcategories such as:

```text
Men (Tier 1)
Men (Tier 2)
Men (Tier 3)
Men (Leaders)
Men (Machine Guns)
Men (AT)
```

The editor should remain usable.

---

# PART VI — UNIT CLASSNAMES

## 18. Unit Class Pattern

Use:

```text
UKSF_Factions_<FactionID>_<Role>
```

Examples:

```cpp
UKSF_Factions_NTEF_Fighter
UKSF_Factions_NTEF_Rifleman
UKSF_Factions_NTEF_MachineGunner
UKSF_Factions_NTEF_TeamLeader
```

---

## 19. Role Token Rules

Use PascalCase role tokens.

Preferred:

```text
Fighter
FighterLight
Rifleman
RiflemanVeteran
TeamLeader
CellLeader
AutomaticRifleman
MachineGunner
AssistantMG
Marksman
AT
Medic
Engineer
DroneOperator
Driver
Crew
Bodyguard
SeniorLeader
```

Avoid unnecessary underscores inside the role token.

Preferred:

```cpp
UKSF_Factions_NTEF_RiflemanVeteran
```

Not:

```cpp
UKSF_Factions_NTEF_Rifleman_Veteran
```

The faction boundary already provides enough structure.

---

## 20. NTEF Reserved Unit Classes

Reserve the following names:

```cpp
UKSF_Factions_NTEF_Fighter
UKSF_Factions_NTEF_FighterLight
UKSF_Factions_NTEF_Rifleman
UKSF_Factions_NTEF_RiflemanVeteran
UKSF_Factions_NTEF_TeamLeader
UKSF_Factions_NTEF_CellLeader
UKSF_Factions_NTEF_AutomaticRifleman
UKSF_Factions_NTEF_MachineGunner
UKSF_Factions_NTEF_AssistantMG
UKSF_Factions_NTEF_Marksman
UKSF_Factions_NTEF_AT
UKSF_Factions_NTEF_Medic
UKSF_Factions_NTEF_Engineer
UKSF_Factions_NTEF_DroneOperator
UKSF_Factions_NTEF_Driver
UKSF_Factions_NTEF_Crew
UKSF_Factions_NTEF_Bodyguard
UKSF_Factions_NTEF_SeniorLeader
```

Optional/deferred:

```cpp
UKSF_Factions_NTEF_Grenadier
UKSF_Factions_NTEF_RadioOperator
UKSF_Factions_NTEF_Sniper
UKSF_Factions_NTEF_ExplosiveVest
```

The final `ExplosiveVest` token is reserved only if a pre-equipped unit is eventually created.

---

## 21. Base Classes

Non-editor base classes should use a `_Base` suffix.

Examples:

```cpp
UKSF_Factions_NTEF_Base
UKSF_Factions_NTEF_FighterBase
UKSF_Factions_NTEF_VeteranBase
UKSF_Factions_NTEF_CrewBase
```

If multiple inheritance layers become necessary:

```cpp
UKSF_Factions_NTEF_Tier1_Base
UKSF_Factions_NTEF_Tier2_Base
UKSF_Factions_NTEF_Tier3_Base
```

### Scope rule

Do not create a deep inheritance tree just because the naming standard allows one.

The actual config should remain as shallow as practical.

---

## 22. Hidden Base Classes

Base classes that should not appear in the editor must be configured accordingly.

The class name alone does not imply hidden status.

---

# PART VII — VEHICLE CLASSNAMES

## 23. Vehicle Class Pattern

Faction-owned vehicle variants use:

```text
UKSF_Factions_<FactionID>_<VehicleName>_<Variant>
```

Examples:

```cpp
UKSF_Factions_NTEF_Hilux
UKSF_Factions_NTEF_Hilux_PKM
UKSF_Factions_NTEF_Hilux_SPG9
UKSF_Factions_NTEF_SUV
```

For vehicle classnames, underscores between **major semantic vehicle/variant blocks** are acceptable and preferred for readability.

---

## 24. Shared Vehicle Base Assets

A project-owned base vehicle that is not faction-specific uses:

```text
UKSF_Factions_Vehicle_<Name>
```

Examples:

```cpp
UKSF_Factions_Vehicle_Hilux
UKSF_Factions_Vehicle_LandRover
```

Faction-specific configured variants may inherit from those classes.

---

## 25. Captured Vehicle Naming

Use the vehicle's identity rather than the word `Captured` in the classname where possible.

Prefer:

```cpp
UKSF_Factions_NTEF_UAZ
```

Display/editor placement may identify it as captured.

Only use:

```cpp
UKSF_Factions_NTEF_Captured_UAZ
```

if there are both native and captured variants whose distinction matters in config.

---

# PART VIII — UNIFORMS

## 26. Shared Uniform Class Pattern

Use:

```text
UKSF_Factions_Uniform_<Family>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Uniform_Regional_01
UKSF_Factions_Uniform_Regional_02
UKSF_Factions_Uniform_Field_01
UKSF_Factions_Uniform_Assault_01
```

Do not put `NTEF` in a plain reusable uniform classname unless that uniform is genuinely faction-specific.

---

## 27. Uniform Item vs Soldier Model Class

Where Arma requires both a `CfgWeapons` uniform item and a hidden `CfgVehicles` uniform base/man class, distinguish them clearly.

Conceptual pattern:

```text
UKSF_Factions_Uniform_Regional_01
UKSF_Factions_UniformBase_Regional_01
```

or another consistent implementation chosen when the first actual uniform is integrated.

Do not improvise a different naming pattern per asset.

---

## 28. Faction-Specific Uniforms

Only use:

```text
UKSF_Factions_NTEF_Uniform_<Name>
```

for assets that contain permanent NTEF-specific markings or identity.

Example:

```cpp
UKSF_Factions_NTEF_Uniform_Commander
```

A generic tan regional outfit should remain shared.

---

# PART IX — VESTS / LOAD-BEARING GEAR

## 29. Vest Class Pattern

Use:

```text
UKSF_Factions_Vest_<Family>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Vest_ChestRig_01
UKSF_Factions_Vest_ChestRig_02
UKSF_Factions_Vest_Webbing_01
UKSF_Factions_Vest_PlateCarrier_01
```

Where armour level matters:

```text
UKSF_Factions_Vest_PlateCarrier_Light_01
UKSF_Factions_Vest_PlateCarrier_Heavy_01
```

Use functional descriptors only when they correspond to genuine config/visual differences.

---

# PART X — HEADGEAR / FACEWEAR

## 30. Headgear Pattern

Use:

```text
UKSF_Factions_Headgear_<Family>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Headgear_Pakol_01
UKSF_Factions_Headgear_Wrap_01
UKSF_Factions_Headgear_HelmetSurplus_01
UKSF_Factions_Headgear_HelmetModern_01
```

Do not call every head item a `Helmet`.

---

## 31. Facewear Pattern

Use:

```text
UKSF_Factions_Facewear_<Family>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Facewear_Scarf_01
UKSF_Factions_Facewear_Balaclava_01
```

Implementation may ultimately live in `CfgGlasses`, but project naming remains consistent.

---

# PART XI — BACKPACKS

## 32. Backpack Pattern

Use:

```text
UKSF_Factions_Backpack_<Family>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Backpack_Field_01
UKSF_Factions_Backpack_Medical_01
UKSF_Factions_Backpack_Radio_01
```

Faction markings should only enter the classname when permanently faction-specific.

---

# PART XII — WEAPONS

## 33. Project-Owned Weapon Pattern

Use:

```text
UKSF_Factions_Weapon_<Name>_<Variant>
```

Examples:

```cpp
UKSF_Factions_Weapon_AKM_01
UKSF_Factions_Weapon_RPK_01
```

However, if the project merely references an existing RHS/3CB weapon class, do **not** create a wrapper class solely to rename it.

Wrapper classes should solve an actual problem:

- changed model;
- changed texture;
- changed magazines;
- changed handling;
- changed attachment support;
- dependency reduction;
- compatibility.

---

## 34. Weapon Display Names

Use the real weapon designation where the weapon itself is real.

Example:

```text
AKM
PKM
SVD
```

Do not rename a real firearm to a fictional designation merely because the faction is fictional.

Faction fiction applies to organisations, not necessarily to globally common weapon models.

---

# PART XIII — MAGAZINES / AMMO

## 35. Magazine Pattern

Only create project magazine classes where necessary.

Use:

```text
UKSF_Factions_Mag_<Name>
```

Examples:

```cpp
UKSF_Factions_Mag_ExplosiveVest
```

Do not wrap standard RHS/vanilla magazines without a technical reason.

---

## 36. Ammo Pattern

Use:

```text
UKSF_Factions_Ammo_<Name>
```

Example:

```cpp
UKSF_Factions_Ammo_ExplosiveVest
```

Ammo classes are technical internal names and should remain descriptive.

---

# PART XIV — EXPLOSIVE VEST NAMING

## 37. Feature Status

Explosive vests are a **future supported gameplay asset**.

ACE currently exposes abstract trigger types including:

```text
Cellphone
DeadManSwitch
```

so the project should integrate with ACE's existing explosives framework rather than create a competing trigger system.

---

## 38. Explosive Vest Item Names

Reserved conceptual names:

### Wearable vest item

```cpp
UKSF_Factions_Vest_Explosive_01
```

Display name:

```text
Explosive Vest
```

### Explosive magazine/charge representation

```cpp
UKSF_Factions_Mag_ExplosiveVest
```

### Ammo representation

```cpp
UKSF_Factions_Ammo_ExplosiveVest
```

### Place/helper object if ACE implementation requires one

```cpp
UKSF_Factions_ExplosiveVest_Place
```

Actual classes may change when we prototype against ACE.

---

## 39. Explosive Vest Compatibility Component

If the feature requires scripting/config beyond ordinary character gear, reserve:

```text
uksf_factions_ace
```

and:

```cpp
UKSF_Factions_ACE
```

Potential script namespace:

```sqf
UKSF_Factions_fnc_explosiveVestInit
UKSF_Factions_fnc_explosiveVestConnect
```

These names are **reserved only**.

No implementation is locked yet.

### Safety/design rule

The feature must remain an Arma gameplay abstraction.

Do not encode or document real-world explosive construction or circuitry.

---

# PART XV — FUNCTIONS

## 40. Function Naming

All project functions use:

```text
UKSF_Factions_fnc_<functionName>
```

Examples:

```sqf
UKSF_Factions_fnc_applyLoadout
UKSF_Factions_fnc_randomiseAppearance
UKSF_Factions_fnc_initFactionUnit
```

Function names use lower camel case after `fnc_`.

---

## 41. Function Files

Preferred filename pattern:

```text
fn_<functionName>.sqf
```

Examples:

```text
fn_applyLoadout.sqf
fn_randomiseAppearance.sqf
```

This follows the existing UKSF coding style and CBA/Arma conventions cleanly.

---

## 42. Faction-Specific Functions

Only prefix the faction into the function name when the function truly cannot be shared.

Prefer:

```sqf
UKSF_Factions_fnc_applyLoadout
```

with faction data.

Instead of immediately creating:

```sqf
UKSF_Factions_fnc_ntefApplyLoadout
UKSF_Factions_fnc_exforApplyLoadout
```

Data-driven reuse is preferred where practical.

---

# PART XVI — GLOBAL VARIABLES

## 43. Global Variable Pattern

Use:

```text
UKSF_Factions_<name>
```

Examples:

```sqf
UKSF_Factions_debug
UKSF_Factions_version
UKSF_Factions_NTEF_enabled
```

Avoid generic globals:

```sqf
debug
factionEnabled
units
```

---

## 44. Object Variables

Use:

```text
UKSF_Factions_<purpose>
```

Examples:

```sqf
_unit setVariable ["UKSF_Factions_tier", 2];
_unit setVariable ["UKSF_Factions_factionId", "NTEF"];
```

Only persist/network variables where actually required.

Do not attach metadata to every unit merely because the naming standard exists.

---

# PART XVII — CBA SETTINGS / KEYBINDS

## 45. CBA Setting IDs

If future settings are added:

```text
UKSF_Factions_<category>_<setting>
```

Examples:

```text
UKSF_Factions_core_debug
UKSF_Factions_ntef_randomisation
```

Display categories:

```text
UKSF Factions
```

Subcategories may use faction display names.

---

## 46. Keybind Category

If the mod ever requires keybinds:

```text
UKSF Factions
```

Avoid faction-specific keybind categories unless there are many binds.

At present, no NTEF keybind requirement exists.

---

# PART XVIII — DISPLAY NAMES

## 47. Display Name Style

Player-facing names should be natural English, not class-like labels.

Preferred:

```text
Rifleman
Veteran Rifleman
Machine Gunner
Cell Leader
Senior Leader
```

Avoid:

```text
NTEF_Rifleman_01
Rifleman T2
Veteran Unit
```

Tier names are internal design terminology.

---

## 48. Faction Prefix in Unit Display Names

Do **not** prefix every unit display name with `NTEF`.

Within the faction browser, this creates clutter.

Preferred:

```text
Rifleman
Machine Gunner
Team Leader
```

Not:

```text
NTEF Rifleman
NTEF Machine Gunner
NTEF Team Leader
```

Faction context already supplies identity.

---

## 49. Variant Display Names

Use parentheses only for meaningful variants.

Examples:

```text
Fighter (Light)
Pickup (PKM)
Pickup (SPG-9)
```

Avoid arbitrary numeric variant names in the editor unless visual selection genuinely requires them.

---

# PART XIX — GROUP CLASSNAMES

## 50. Group Root Pattern

Use faction ID under the faction's group tree.

Conceptually:

```text
UKSF_Factions_NTEF
```

Group class tokens:

```text
Infantry
Motorised
Special
```

Individual group IDs:

```text
UKSF_Factions_NTEF_FighterCell
UKSF_Factions_NTEF_CoreCell
UKSF_Factions_NTEF_WeaponsCell
UKSF_Factions_NTEF_VeteranCell
UKSF_Factions_NTEF_LeadershipDetail
UKSF_Factions_NTEF_TechnicalPatrol
UKSF_Factions_NTEF_MotorisedCell
UKSF_Factions_NTEF_DroneTeam
```

---

## 51. Group Display Names

Recommended:

```text
Fighter Cell
Core Combat Cell
Weapons Cell
Veteran Assault Cell
Leadership Security Detail
Technical Patrol
Motorised Fighter Cell
Drone Team
```

Do not encode exact group size in the display name unless multiple sizes are intentionally provided.

---

# PART XX — MODELS / TEXTURES / MATERIAL PATHS

## 52. Addon Root

When final PBO architecture is chosen, all project-owned paths should remain under:

```text
\uksf_factions\
```

or component roots consistently derived from it.

Avoid source paths containing spaces.

---

## 53. Data Folder Pattern

Recommended logical structure:

```text
data\
    characters\
    vehicles\
    weapons\
    props\
    ui\
    factions\
```

Subfolders should use lowercase snake_case where multiple words are needed.

Example:

```text
data\characters\headgear\pakol_01\
```

---

## 54. Model Filenames

Use lowercase descriptive names.

Examples:

```text
pakol_01.p3d
chest_rig_01.p3d
hilux_technical.p3d
```

Do not use source-game filenames that are meaningless inside the project when a rename is practical and permitted.

Record original names in the asset register.

---

## 55. Texture Filenames

Suggested suffix convention:

```text
_co
_nohq
_smdi
_as
_mc
```

following the Arma material type being represented.

Base filenames should remain lowercase.

Example:

```text
pakol_01_co.paa
pakol_01_nohq.paa
```

---

# PART XXI — EVENT HANDLERS / XEH

## 56. CBA Extended Event Handler Naming

Where XEH is required, use project functions rather than large inline scripts.

Prefer:

```cpp
init = "(_this select 0) call UKSF_Factions_fnc_initFactionUnit";
```

or the appropriate CBA XEH mechanism.

Avoid large config-embedded code blocks.

---

## 57. Init Scope

Do not add per-unit init handlers unless the unit actually requires runtime behaviour.

Static loadout/identity configuration should remain config-only where possible.

This supports the project's performance goals.

---

# PART XXII — MACROS

## 58. Macro Prefix

If config macros are introduced, use:

```text
UKSF_FACTIONS_
```

Examples:

```cpp
#define UKSF_FACTIONS_AUTHOR "UKSF Surplus"
#define UKSF_FACTIONS_NTEF_SIDE 0
```

Keep macros uppercase.

Do not create macros for values used once.

---

# PART XXIII — STRINGTABLE

## 59. Stringtable Policy

If localisation is introduced, use keys beginning:

```text
STR_UKSF_Factions_
```

Examples:

```text
STR_UKSF_Factions_NTEF_Name
STR_UKSF_Factions_NTEF_Rifleman
```

A stringtable is not required for the first prototype unless localisation or centralised text management provides clear value.

Do not mix hardcoded and localised display names arbitrarily within the same mature component.

---

# PART XXIV — VERSIONING

## 60. Version Macros / Metadata

If version fields are added later, use the project name consistently.

Example conceptual values:

```text
major
minor
patch
build
```

Do not encode version numbers into public classnames or PBO filenames.

Correct:

```text
uksf_factions_ntef.pbo
```

Incorrect:

```text
uksf_factions_ntef_v1_2_3.pbo
```

---

# PART XXV — DEPRECATION

## 61. Public Class Stability

Once a class has shipped publicly or has been used in persistent unit missions, avoid renaming it casually.

If a class must be replaced:

- retain a compatibility alias where practical;
- mark it deprecated in documentation;
- migrate mission/config references;
- remove only during an intentional breaking release.

This is particularly important for:

- faction classes;
- unit classes;
- vehicle classes;
- gear classes.

---

# PART XXVI — CURRENT NTEF NAMING DECISIONS

## 62. Locked NTEF Names

### Faction

```cpp
UKSF_Factions_NTEF
```

Display:

```text
Northern Takistan Emirate Front
```

### Addon/PBO candidate

```text
uksf_factions_ntef
```

### `CfgPatches`

```cpp
UKSF_Factions_NTEF
```

### Core unit prefix

```text
UKSF_Factions_NTEF_
```

### Reserved roles

```text
Fighter
FighterLight
Rifleman
RiflemanVeteran
TeamLeader
CellLeader
AutomaticRifleman
MachineGunner
AssistantMG
Marksman
AT
Medic
Engineer
DroneOperator
Driver
Crew
Bodyguard
SeniorLeader
```

---

# PART XXVII — CURRENT SHARED ASSET NAMING DECISIONS

## 63. Locked Shared Asset Families

```text
UKSF_Factions_Uniform_
UKSF_Factions_Vest_
UKSF_Factions_Headgear_
UKSF_Factions_Facewear_
UKSF_Factions_Backpack_
UKSF_Factions_Vehicle_
UKSF_Factions_Weapon_
UKSF_Factions_Mag_
UKSF_Factions_Ammo_
```

These namespaces are reserved for project-owned classes.

---

# PART XXVIII — NAMES RESERVED FOR FUTURE COMPONENTS

## 64. Reserved

```text
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Weapons
UKSF_Factions_Vehicles
UKSF_Factions_Props
UKSF_Factions_NTEF
UKSF_Factions_EXFOR
UKSF_Factions_ACE
```

and PBO equivalents:

```text
uksf_factions_core
uksf_factions_characters
uksf_factions_weapons
uksf_factions_vehicles
uksf_factions_props
uksf_factions_ntef
uksf_factions_exfor
uksf_factions_ace
```

Reservation does not mean every component will exist.

---

# PART XXIX — NAMING RED LINES

## 65. Do Not

Do not create classes such as:

```text
Insurgent1
NewVest
MyHelmet
UKSF_Unit1
NTEF_Guy
Test_Final
Final2
```

Do not encode source provenance in public classnames:

```text
UKSF_Factions_3CB_Hilux
UKSF_Factions_RHS_AKM
```

Provenance belongs in:

```text
docs/assets/asset_register.md
```

Public classnames should describe what the project class **is**, not where its model originated.

---

## 66. Temporary Development Classes

Temporary classes should be clearly marked:

```text
UKSF_Factions_DEV_<Name>
```

Example:

```cpp
UKSF_Factions_DEV_UniformTest
```

No `DEV_` class should ship in a public release unless intentionally exposed as a development utility.

---

# PART XXX — ACE COMPATIBILITY NAMING

## 67. ACE Integration

ACE-specific classes/functions should use ordinary project names unless they exist only because of ACE.

Example:

General item:

```cpp
UKSF_Factions_Vest_Explosive_01
```

ACE-only helper:

```cpp
UKSF_Factions_ACE_ExplosiveVestHelper
```

ACE-only function:

```sqf
UKSF_Factions_fnc_explosiveVestConnect
```

Do not place `ACE` into the user-facing item name.

---

## 68. Explosive Vest Future Design

ACE's public explosives framework currently supports trigger categories including:

- Cellphone;
- Dead Man Switch;
- Command;
- Timer.

Therefore the future project design should treat ACE as the authoritative gameplay framework for explosive activation/interaction.

`UKSF_Factions` should supply:

- wearable visual asset;
- safe game configuration;
- required helper/bridge behaviour;
- ACE compatibility;
- disarm/interaction support where practical.

It should not duplicate ACE detonator UI or create parallel firing-device systems without a demonstrated need.

---

# PART XXXI — SOURCE REFERENCES

Research checked 2026-08-09.

## Bohemia Interactive Community Wiki

### Characters and Gear Encoding Guide

Used as a current official reference for core Arma addon/config structure, including the central role of `CfgPatches`.

```text
https://community.bohemia.net/wiki/Arma_3:_Characters_And_Gear_Encoding_Guide
```

### Curator

Used as an official reference for the relationship between correctly configured addon objects and Zeus/Curator availability.

```text
https://community.bohemia.net/wiki/Arma_3:_Curator
```

---

## ACE3

### Explosives Framework

Current ACE documentation defines supported explosive-trigger types, including `Cellphone` and `DeadManSwitch`, and provides the framework for custom explosive items and detonators.

```text
https://ace3.acemod.org/wiki/framework/explosives-framework
```

### Explosives Feature

Current ACE documentation describes normal interaction, arming, active detonator and dead-man-switch gameplay behaviour.

```text
https://ace3.acemod.org/wiki/feature/explosives
```

---

# PART XXXII — CURRENT CONCLUSION

The public configuration namespace is now:

```text
UKSF_Factions_
```

The filesystem/PBO namespace is:

```text
uksf_factions_
```

The first faction ID is:

```text
NTEF
```

and its faction class is:

```cpp
UKSF_Factions_NTEF
```

This standard is sufficient to begin creating stable config classes later without improvising naming during implementation.

The next project-level admin task should be the **dependency and PBO architecture standard**, where we decide whether the project begins as one PBO or a modular set and how optional ACE/faction components depend on one another.
