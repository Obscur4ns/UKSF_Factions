# UKSF_Factions — Asset Register

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Project Asset Register  
**Status:** Active  
**Created:** 2026-08-09  

---

## 1. Purpose

This document is the master provenance, permission and integration register for assets used by `UKSF_Factions`.

It should be updated whenever a new external, donated, adapted or original asset is accepted for use in the project.

The register exists to answer four questions for every asset:

1. **What is it?**
2. **Where did it come from?**
3. **Do we have permission to use and redistribute it?**
4. **Where and how is it used inside `UKSF_Factions`?**

This is a project-wide document and is not limited to a single faction.

---

## 2. Scope

Track assets such as:

- 3D models;
- textures;
- materials;
- normal maps;
- RVMATs;
- animations;
- sounds;
- icons;
- insignia;
- flags;
- UI elements;
- weapon assets;
- vehicle assets;
- uniforms;
- vests;
- helmets;
- headwear;
- facewear;
- backpacks;
- props;
- source files;
- adapted config components where provenance matters.

Do **not** create a separate register entry for every ordinary config class created from scratch inside `UKSF_Factions`.

---

## 3. Asset ID Convention

Every incorporated or tracked asset receives a unique internal ID.

Format:

```text
UKSFF-<TYPE>-<NUMBER>
```

Suggested type codes:

| Code | Type |
|---|---|
| `MDL` | 3D model |
| `TEX` | Texture |
| `MAT` | Material / RVMAT |
| `ANM` | Animation |
| `SND` | Sound |
| `UI` | UI / icon |
| `WPN` | Weapon asset set |
| `VEH` | Vehicle asset set |
| `UNI` | Uniform asset set |
| `VST` | Vest / load-bearing equipment |
| `HDG` | Helmet / headgear |
| `FCE` | Facewear |
| `BPK` | Backpack |
| `PRP` | Prop / environmental object |
| `SRC` | Source package / donor set |
| `OTH` | Other |

Examples:

```text
UKSFF-VEH-0001
UKSFF-UNI-0001
UKSFF-HDG-0003
UKSFF-UI-0002
```

Numbers should never be reused, even if an asset is later rejected.

---

## 4. Status Codes

Use one of the following values.

| Status | Meaning |
|---|---|
| `PROPOSED` | Candidate asset identified but not yet reviewed |
| `PENDING_PERMISSION` | Asset is useful but permission/licence is unresolved |
| `PENDING_REVIEW` | Permission is sufficient; technical/visual review still required |
| `APPROVED` | Approved for project use |
| `INTEGRATED` | Present in the project and actively used |
| `HOLD` | Temporarily paused |
| `REJECTED` | Not suitable or permission insufficient |
| `REPLACED` | Previously used but superseded by another asset |
| `REMOVED` | Removed from the project |

---

## 5. Source Categories

Use one of these source categories where possible.

| Category | Description |
|---|---|
| `ORIGINAL` | Created specifically for UKSF_Factions |
| `RHS` | Sourced from or derived from RHS content |
| `3CB` | Sourced from or derived from 3CB content |
| `CUP` | Referenced or sourced from CUP where permitted |
| `VANILLA` | Arma 3 / official DLC dependency reference |
| `DONATED` | Supplied directly by another creator |
| `PRIVATE_MOD` | Obtained from a private/non-public Arma mod |
| `OTHER_GAME` | Originates from another game or official game source package |
| `OPEN_SOURCE` | Public permissively licensed source asset |
| `PURCHASED` | Commercial asset purchased with appropriate use rights |
| `OTHER` | Other provenance |

---

## 6. Permission Basis

Record the actual reason the project may use the asset.

Examples:

```text
Original UKSF work
Full permission granted directly by author
Full permission granted by 3CB
Full permission granted by RHS
CC BY 4.0
CC BY-SA 4.0
APL-SA
Commercial licence
Public-domain dedication
Dependency/reference only
```

Do not write:

```text
Found online
Downloaded from Discord
Was in another mod
We own the game
```

Those describe access, not permission.

---

## 7. Permission Evidence

Where permission is granted privately, the repository does not need to contain private correspondence.

Record enough information to establish that evidence exists.

Example:

```text
Permission granted directly to UKSF Surplus by author.
Evidence retained privately.
```

If public evidence exists, record its location.

Example:

```text
Licence included in source package: LICENSE.txt
```

Do not commit:

- private email addresses;
- personal phone numbers;
- private Discord invite links;
- purchase receipts;
- private download links;
- other unnecessary personal information.

---

## 8. Master Asset Register

> Add new entries at the bottom. Do not renumber existing Asset IDs.

| Asset ID | Asset / Set | Type | Source | Original Creator / Rightsholder | Permission Basis | Redistribution | Modification | GitHub Source | Intended Use | Current Path | Status | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| `UKSFF-SRC-0001` | RHS source asset pool | Source set | RHS | Red Hammer Studios / respective contributors | Full permission granted to project owner | Approved under granted permission | Approved under granted permission | Record per incorporated asset | Weapons, vehicles, supporting assets | N/A | `APPROVED` | Project owner has confirmed full permission to take apart and use required RHS assets. Individual incorporated assets should still receive their own entries. |
| `UKSFF-SRC-0002` | 3CB source asset pool | Source set | 3CB | 3 Commando Brigade / respective contributors | Full permission granted to project owner | Approved under granted permission | Approved under granted permission | Record per incorporated asset | Primarily vehicles, weapons and selected supporting assets | N/A | `APPROVED` | Do not make UKSF_Factions dependent on 3CB uniforms, vests or helmets. 3CB infantry gear is intended to be replaced by this project. |

---

## 9. Individual Asset Entry Template

For significant assets, especially anything physically incorporated into the mod, add both a master-table row and a detailed record below.

Copy this block:

```md
### UKSFF-XXX-0000 — Asset Name

**Status:** `PROPOSED`  
**Type:**  
**Source category:**  
**Original work/mod/game:**  
**Original creator/rightsholder:**  
**Source location:**  
**Source version/build:**  

**Permission basis:**  
**Permission evidence:**  
**Modification permitted:**  
**Redistribution permitted:**  
**Public GitHub source permitted:**  
**Steam Workshop distribution permitted:**  
**Attribution required:**  

**Original files:**
- 

**UKSF changes:**
- 

**Intended factions:**
- 

**Intended roles:**
- 

**Project destination:**
```text
UKSF_Factions\
```

**Dependencies:**
- 

**Technical notes:**
- 

**Visual notes:**
- 

**Credits entry:**
```text
TBD
```

**Decision history:**
- YYYY-MM-DD — Asset proposed.
```

---

## 10. Detailed Asset Records

### UKSFF-SRC-0001 — RHS Source Asset Pool

**Status:** `APPROVED`  
**Type:** Source asset pool  
**Source category:** `RHS`  
**Original work/mod/game:** RHS Arma 3 content  
**Original creator/rightsholder:** Red Hammer Studios / respective contributors  

**Permission basis:** Full permission granted directly to project owner.  
**Permission evidence:** Retained privately by UKSF Surplus.  
**Modification permitted:** Yes, under granted permission.  
**Redistribution permitted:** Yes, under granted permission.  
**Public GitHub source permitted:** Record per incorporated asset and permission conditions.  
**Steam Workshop distribution permitted:** Record per incorporated asset and permission conditions.  
**Attribution required:** Yes; final wording to be recorded before release.  

**Intended factions:**
- NTEF
- future Middle Eastern factions
- future African factions
- future European factions
- training OPFOR where appropriate

**Intended roles:**
- weapons;
- vehicles;
- selected supporting equipment;
- source material for adapted assets where worthwhile.

**Technical notes:**
- Prefer direct class references where the dependency already exists and there is no benefit to incorporation.
- Incorporate/adapt only when it improves performance, independence, consistency or project maintainability.
- Every physically incorporated RHS asset or coherent asset set should receive its own register entry.

**Decision history:**
- 2026-08-09 — Full project permission confirmed by project owner.

---

### UKSFF-SRC-0002 — 3CB Source Asset Pool

**Status:** `APPROVED`  
**Type:** Source asset pool  
**Source category:** `3CB`  
**Original work/mod/game:** 3CB Arma 3 content  
**Original creator/rightsholder:** 3 Commando Brigade / respective contributors  

**Permission basis:** Full permission granted directly to project owner.  
**Permission evidence:** Retained privately by UKSF Surplus.  
**Modification permitted:** Yes, under granted permission.  
**Redistribution permitted:** Yes, under granted permission.  
**Public GitHub source permitted:** Record per incorporated asset and permission conditions.  
**Steam Workshop distribution permitted:** Record per incorporated asset and permission conditions.  
**Attribution required:** Yes; final wording to be recorded before release.  

**Intended roles:**
- vehicles;
- technicals;
- civilian/regional transport;
- weapons;
- selected supporting assets.

**Explicit project rule:**

`UKSF_Factions` must **not rely on 3CB uniforms, vests or helmets as its core infantry gear dependency**.

The unit is considering reducing the 3CB Factions footprint and retaining primarily its useful weapon and vehicle content. `UKSF_Factions` is intended to replace much of the gear/faction/unit side.

Existing 3CB infantry assets may still be inspected as:

- visual reference;
- donor/source material where there is a specific reason to adapt an asset;
- temporary development placeholders.

They should not become a permanent dependency simply because they already exist.

**Decision history:**
- 2026-08-09 — Full project permission confirmed by project owner.
- 2026-08-09 — Infantry-gear dependency exclusion established.

---

## 11. External Asset Intake Workflow

When a new asset is received:

### Step 1 — Identify

Record:

- what the asset is;
- where it came from;
- who created/owns it;
- what version/source package it belongs to.

### Step 2 — Permission

Determine:

- modification rights;
- redistribution rights;
- public repository rights;
- release-platform rights;
- required attribution.

### Step 3 — Register

Assign the next Asset ID and create a `PROPOSED`, `PENDING_PERMISSION` or `PENDING_REVIEW` entry.

### Step 4 — Stage

Keep unapproved source material outside public Git history.

Recommended local structure:

```text
_external_staging/
├── pending/
├── approved/
└── rejected/
```

The entire staging directory should remain ignored by Git.

### Step 5 — Technical review

Check:

- model quality;
- polygon/section count;
- texture resolution;
- material setup;
- LODs;
- selections;
- skeleton/animation compatibility;
- clipping;
- performance;
- hidden selections;
- licence metadata;
- whether conversion effort is justified.

### Step 6 — Visual review

Check whether the asset actually fits:

- faction;
- theatre;
- period;
- capability tier;
- visual style.

### Step 7 — Integrate

Only after approval:

- move approved source into the project;
- record the final project path;
- record modifications;
- add credits;
- change status to `INTEGRATED`.

---

## 12. Other-Game Asset Workflow

Assets from other games require particularly careful provenance tracking.

For each candidate, record:

```text
Game:
Developer:
Publisher:
Asset creator if known:
How source files were obtained:
Official modding/source package:
Relevant licence:
Derivative works permitted:
Cross-game use permitted:
Redistribution permitted:
Public source release permitted:
Workshop release permitted:
```

If any of the permission fields are uncertain:

```text
Status: PENDING_PERMISSION
```

Do not put the asset in the release tree until resolved.

---

## 13. Donated Asset Workflow

For directly donated assets, record:

```text
Creator:
Date received:
Original or derivative:
Permission to modify:
Permission to redistribute:
Permission to publish source:
Required credit:
Restrictions:
Evidence retained:
```

Preferred permission wording should clearly establish the intended use.

Example record:

```text
Creator granted UKSF Surplus permission to modify, incorporate and redistribute
the supplied asset as part of UKSF_Factions, including public mod releases.
Evidence retained privately.
```

If GitHub source publication is intended, ensure that is also covered.

---

## 14. Original UKSF Asset Workflow

Assets made specifically for the project should still receive Asset IDs when they are significant reusable assets.

Examples:

- NTEF emblem;
- NTEF flag;
- faction patch;
- vehicle markings;
- custom uniform model;
- custom vest;
- custom helmet;
- custom technical model.

Permission basis:

```text
Original UKSF_Factions asset
```

Record the primary creator where relevant.

This helps credits and later asset reuse.

---

## 15. Adapted Asset Workflow

When adapting an existing asset, keep provenance explicit.

Example:

```text
Source:
UKSFF-VEH-0012 — 3CB Hilux source

Derived asset:
UKSFF-VEH-0021 — NTEF Hilux Technical
```

The derived asset's record should state:

- parent/source Asset ID;
- geometry changes;
- texture changes;
- material changes;
- config changes;
- optimisation changes;
- new authors/contributors.

Do not erase the original provenance just because the final asset is heavily modified.

---

## 16. Credits Workflow

Every `APPROVED` or `INTEGRATED` external asset should have a credits line before release.

Suggested credits categories:

```text
## Original UKSF_Factions Assets

## 3 Commando Brigade Assets

## Red Hammer Studios Assets

## Donated Assets

## Other Licensed Assets

## Additional Contributors
```

Exact credits should be generated from this register rather than maintained independently where possible.

---

## 17. Repository Rules

### Never commit

- unknown-permission assets;
- private download packages;
- licence-incompatible source;
- confidential correspondence;
- unnecessary personal information;
- purchased source files whose licence forbids source redistribution.

### May commit when permitted

- approved source models;
- approved textures;
- approved materials;
- permission-safe documentation;
- original project assets;
- derivative assets whose permission allows repository distribution.

### Binary history caution

Large binary source files are difficult to remove from Git history once committed.

If permission or suitability is unresolved, keep the files outside the repository until the decision is final.

---

## 18. Recommended Project Paths

Suggested eventual structure:

```text
UKSF_Factions/
├── docs/
│   ├── assets/
│   │   ├── asset_register.md
│   │   ├── credits.md
│   │   └── permissions/
│   └── factions/
├── UKSF_Factions/
│   ├── data/
│   │   ├── factions/
│   │   ├── uniforms/
│   │   ├── vests/
│   │   ├── headgear/
│   │   ├── weapons/
│   │   ├── vehicles/
│   │   ├── props/
│   │   └── ui/
│   ├── model.cfg
│   └── config.cpp
└── .gitignore
```

This is only a planning structure. Actual addon/PBO architecture should be decided separately before implementation.

---

## 19. Git Ignore Recommendation

Recommended entries:

```gitignore
# External asset staging
_external_staging/

# Temporary exports
_temp/
_exports/

# Arma build output
*.pbo
*.bisign

# Local tool output / logs
*.log
*.rpt
```

Do not blindly use this block if the existing repository already has build/output conventions.

---

## 20. Review Checklist

Before changing an asset to `APPROVED`:

- [ ] Asset ID assigned.
- [ ] Original source identified.
- [ ] Original creator/rightsholder identified.
- [ ] Permission basis recorded.
- [ ] Modification right confirmed.
- [ ] Redistribution right confirmed.
- [ ] GitHub/source-publication right checked.
- [ ] Release-platform right checked.
- [ ] Attribution requirement recorded.
- [ ] Technical quality reviewed.
- [ ] Performance suitability reviewed.
- [ ] Visual suitability reviewed.
- [ ] Intended faction/role recorded.
- [ ] Final path planned.
- [ ] Any parent/derived asset relationship recorded.

Before changing an asset to `INTEGRATED`:

- [ ] Files are in final project location.
- [ ] Config references use final paths.
- [ ] Credits entry exists.
- [ ] No unapproved source files were accidentally committed.
- [ ] Asset works in-game.
- [ ] Asset has acceptable LOD/material performance.
- [ ] Asset register reflects all meaningful modifications.

---

## 21. Immediate Next Entries

The first practical asset entries should be created when actual source candidates are selected for NTEF.

Likely first categories:

1. traditional/regional uniform set;
2. civilian/traditional trousers;
3. simple AK chest rig;
4. older webbing;
5. pakol/regional headwear;
6. scarf/wrap set;
7. face-covering set;
8. veteran plate carrier;
9. captured/surplus helmet;
10. technical vehicle family;
11. motorcycle;
12. NTEF emblem;
13. NTEF flag;
14. NTEF editor icon.

Do not create placeholder Asset IDs for assets that have not yet been identified.

---

## 22. Current Project-Level Asset Decisions

### 22.1 RHS

The project owner has confirmed full permission to use required RHS assets.

RHS may therefore be used as:

- an installed dependency;
- a source library;
- an adaptation base;
- an incorporated asset source,

depending on what produces the cleanest implementation.

### 22.2 3CB

The project owner has confirmed full permission to use required 3CB assets.

The preferred project direction is:

- retain/adapt useful **vehicles**;
- retain/adapt useful **weapons**;
- use other supporting assets selectively;
- avoid reliance on 3CB **uniforms, vests and helmets**;
- replace much of the 3CB faction/unit/gear role with `UKSF_Factions`.

### 22.3 External sources

External assets are expected to become a significant part of the project.

They should be judged individually on:

- visual quality;
- performance;
- suitability;
- provenance;
- permission;
- conversion effort;
- long-term maintainability.

### 22.4 Bespoke faction identity

Faction-specific branding should preferably be original `UKSF_Factions` work.

This includes:

- emblems;
- flags;
- patches;
- editor icons;
- vehicle markings;
- environmental faction graphics.

---

## 23. Register Maintenance Rule

This file is the **single source of truth for asset provenance**.

If an asset enters, leaves or materially changes within `UKSF_Factions`, update this register in the same commit whenever practical.

When uncertain:

**do not delete history — update the status and add a decision-history note.**
