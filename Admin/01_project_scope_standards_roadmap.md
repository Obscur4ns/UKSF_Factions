# UKSF_Factions — Project Scope, Standards & Development Roadmap

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Project Scope, Standards & Development Roadmap  
**Status:** Active / Pre-production  
**Created:** 2026-08-09  

---

## 1. Purpose

This document defines the project-wide direction for `UKSF_Factions` before asset production and configuration work begins.

It exists to keep future factions consistent in:

- lore;
- naming;
- editor presentation;
- equipment philosophy;
- dependency strategy;
- quality;
- documentation;
- release structure.

It is intentionally broader than any one faction.

Faction-specific research should live in separate documents under:

```text
docs/factions/<region_or_faction>/
```

---

## 2. Project Goal

`UKSF_Factions` is intended to become a coherent collection of **current-day Armaverse factions** designed primarily for UKSF mission making.

The project should provide:

- believable insurgent and irregular forces;
- contemporary conventional or quasi-conventional opponents where useful;
- regional civilian and militia ecosystems;
- British military training OPFOR / EXFOR;
- consistent editor organisation;
- high visual quality;
- controlled dependencies;
- credible Armaverse lore;
- faction identities that do not simply copy real organisations.

The project should feel as though the factions belong in the same fictional world as Arma, while still reflecting the appearance and capability of modern conflict.

---

## 3. Time Period

The working setting is:

**Contemporary / approximately 2026**

This is a deliberate project choice.

`UKSF_Factions` is not required to reproduce the full Arma 3 2035 technological setting.

Instead:

- Armaverse geography and historical events remain useful background;
- factions use contemporary weapons, clothing, vehicles and technology;
- older Arma events may be treated as historical events in the project's continuity;
- exact calendar reconciliation should remain loose unless a campaign requires a date.

The purpose is gameplay and world coherence rather than constructing a rigid alternate-history chronology.

---

## 4. Armaverse Lore Policy

Use official Armaverse countries wherever they provide a strong fit.

Current confirmed useful settings include:

### Takistan

Established in *Arma 2: Operation Arrowhead*.

Official post-war material establishes a major guerrilla insurgency following the defeat of the Takistani regime.

This makes Takistan particularly suitable for:

- insurgency;
- counter-insurgency;
- state instability;
- tribal conflict;
- cross-border armed groups;
- extremist splinter movements.

### Karzeghistan

Established in official *Arma 2: British Armed Forces* material.

Official material places the disputed Sharig Plateau and Shapur area around the Takistan/Karzeghistan border and describes Takistani insurgent activity there.

Useful for:

- border conflict;
- safe-haven lore;
- cross-border militant networks;
- regional proxy activity.

### Ardistan

Established in official BAF-era material.

Useful as a wider regional state whose exact modern political role can be developed carefully when required.

Do not define its current government or strategic alignment until a faction needs it.

### Argana

Established by *Arma 3 Creator DLC: Western Sahara*.

Sefrou-Ramal is described officially as a province in northeastern Argana, with long-running conflict involving rival tribes, insurgents, peacekeepers and foreign forces.

Useful for:

- Sahel-style insurgency;
- tribal conflict;
- peacekeeping;
- civil conflict;
- African conventional and irregular factions.

### Livonia

Established by *Arma 3 Contact* as a fictional Polish-speaking Eastern European NATO member.

Useful for:

- European security scenarios;
- territorial defence;
- proxy activity;
- paramilitary or sabotage scenarios if future lore justifies them.

Do not invent a large internal insurgency merely to create another OPFOR faction.

### Chernarus

Established Armaverse Eastern European state with a long history of internal conflict.

Potentially useful for future:

- nationalist armed groups;
- separatists;
- criminal-paramilitary networks;
- post-conflict irregular forces.

Detailed modern Chernarus research should be completed before committing to a new faction.

---

## 5. Fictional Country Policy

New fictional countries may be created when:

- no established Armaverse country fits the intended geography;
- existing lore would be distorted by forcing the faction into it;
- a new country creates significant reusable mission-making value.

Do not create a new country simply to avoid doing research.

Every new country should eventually have:

- official name;
- short name;
- demonym;
- capital;
- language profile;
- broad geography;
- government type;
- regional relationships;
- military/security background;
- flag;
- map position;
- Armaverse relationship notes.

---

## 6. Real-World Inspiration Policy

Real forces and conflicts may be used as research references.

They should inform:

- visual style;
- broad equipment patterns;
- organisational flavour;
- technology level;
- vehicle mix;
- regional plausibility;
- mission atmosphere.

They should **not** automatically supply:

- names;
- flags;
- exact insignia;
- slogans;
- propaganda;
- real commanders;
- direct reproductions of extremist organisations;
- one-to-one recreations of specific terrorist incidents.

The objective is:

> **realistic fictionalisation**

rather than simple renaming.

---

## 7. Faction Identity Standard

Every major faction should eventually have a complete identity package.

Required:

1. full name;
2. short name;
3. acronym;
4. faction type;
5. country/region;
6. one-paragraph overview;
7. extended lore;
8. friend/enemy relationships;
9. visual identity;
10. equipment philosophy;
11. vehicle philosophy;
12. capability tiers;
13. faction emblem;
14. flag where appropriate;
15. editor icon;
16. class-name namespace;
17. credits/provenance records.

Optional:

- vehicle markings;
- patches;
- graffiti;
- intelligence graphics;
- fictional documents;
- environmental propaganda;
- fictional radio/media material.

---

## 8. Faction Type Taxonomy

Use the following broad categories when designing factions.

### `INSURGENT`

Locally rooted armed movement conducting irregular warfare.

### `EXTREMIST`

Ideologically driven irregular movement with strong organisational identity and limited interest in political compromise.

NTEF belongs here.

### `MILITIA`

Armed non-state or semi-state group whose organisation may be tribal, political, ethnic, commercial or local.

### `PARAMILITARY`

More organised armed group with military characteristics but outside normal conventional armed forces.

### `PROXY`

Externally supported force whose capability and organisation exceed typical local militia.

### `CONVENTIONAL`

Recognisable national or organised military force.

### `SECURITY`

Police, gendarmerie, internal-security or border force.

### `CIVILIAN`

Regional civilian population / professions.

### `TRAINING_OPFOR`

Purpose-built exercise enemy representing different threat types.

---

## 9. Capability Tier Standard

Where appropriate, irregular factions should use a common conceptual capability ladder.

### Tier 1 — Local / Auxiliary

Characteristics:

- basic weapons;
- little armour;
- limited communications;
- primarily civilian or regional clothing;
- minimal optics;
- limited specialist equipment.

### Tier 2 — Core Fighter

Characteristics:

- better load-bearing equipment;
- more coherent weapons;
- occasional armour;
- limited optics;
- basic radios.

### Tier 3 — Veteran / Assault

Characteristics:

- better weapons;
- armour;
- optics;
- communications;
- occasional helmets;
- limited night capability.

### Tier 4 — Specialist

Examples:

- machine gunner;
- marksman;
- anti-armour;
- medic;
- engineer;
- drone operator;
- communications specialist;
- vehicle crew.

### Tier 5 — Leadership / Security

Examples:

- cell leader;
- commander;
- senior political figure;
- bodyguard;
- security detail.

Not every faction must use all five tiers.

---

## 10. Current Planned Faction Roadmap

This roadmap defines development priority, not final release order.

---

### Phase 1 — Northern Takistan Deployment

## Faction 01 — Northern Takistan Emirate Front

**Working acronym:** `NTEF`  
**Type:** `EXTREMIST`  
**Region:** North Takistan  
**Priority:** `IMMEDIATE`  
**Development state:** Research / pre-production  

Primary design reference:

- ISIS-K-style contemporary transnational jihadist threat;
- fictional organisation;
- no real extremist branding.

Purpose:

- primary hostile force for the next UKSF deployment;
- establish the technical and artistic standards for the rest of the mod.

Existing documents:

```text
docs/factions/north_takistan/
├── 01_north_takistan_extremist_research_brief.md
└── 02_ntef_asset_dependency_audit.md
```

Next non-model tasks:

- naming/lore refinement;
- faction organisation and editor role list;
- equipment distribution rules;
- vehicle distribution rules;
- mission-maker guidance;
- faction relationship matrix;
- emblem/flag brief;
- config/class naming specification.

---

### Phase 2 — British Training Enemy

## Faction 02 — UK Exercise Force / OPFOR

**Final name:** TBD  
**Type:** `TRAINING_OPFOR`  
**Region:** UK / exercise environments  
**Priority:** `HIGH`  
**Development state:** Research required  

Real-world basis:

British Army collective training regularly uses dedicated or temporarily assigned OPFOR configured to represent realistic enemy forces.

Recent public examples include:

- Task Force Hannibal on Exercise Iron Storm, Salisbury Plain;
- UK troops trained specifically to act like Russian ground forces;
- vehicle simulation systems configured to represent opposing equipment;
- established training centres maintaining in-house enemy forces capable of representing military, militia or civilian roles.

Project purpose:

Create a flexible faction specifically suited to UKSF training scenarios.

Likely subtypes:

- conventional near-peer;
- irregular;
- militia;
- civilian role-player;
- vehicle crews;
- training controllers / exercise staff if useful.

Design rule:

This faction should **not** represent a real country politically.

It represents an **exercise threat**, allowing mission makers to simulate different enemy types without introducing unnecessary campaign lore.

---

### Phase 3 — Takistan Regional Ecosystem

## Faction 03 — Traditional Takistani Insurgents

**Name:** TBD  
**Type:** `INSURGENT`  
**Region:** Takistan  
**Priority:** `MEDIUM`  

Purpose:

Represent a more traditional/local insurgency distinct from NTEF.

Identity:

- nationalist/local;
- tribal influence;
- pragmatic;
- less ideologically rigid;
- potentially hostile to both state forces and NTEF.

This faction provides important three-sided mission opportunities.

---

## Faction 04 — Regional Proxy Force

**Name:** TBD  
**Type:** `PROXY`  
**Region:** Takistan / Karzeghistan / Ardistan  
**Priority:** `MEDIUM`  

Purpose:

Provide a better-equipped non-state enemy between insurgent and conventional capability.

Possible identity:

- external backing;
- better radios;
- more coherent uniforms;
- more modern anti-armour;
- better vehicles;
- stronger command structure.

Do not assign a sponsor until regional lore is researched.

---

### Phase 4 — Africa

## Faction 05 — Arganan / Sahel-Style Insurgency

**Name:** TBD  
**Type:** `INSURGENT` or `EXTREMIST`  
**Region:** Argana  
**Priority:** `MEDIUM`  

Design inspiration:

- contemporary Sahel;
- highly mobile irregular forces;
- motorcycles;
- pickups;
- mixed regional weapons;
- captured state equipment;
- sparse advanced equipment.

Must remain visually distinct from NTEF.

---

## Faction 06 — African Political / Warlord Militia

**Name:** TBD  
**Type:** `MILITIA`  
**Region:** Argana or future fictional African country  
**Priority:** `MEDIUM/LOW`  

Purpose:

Support African scenarios that are **not** jihadist counter-terrorism.

Potential mission themes:

- civil conflict;
- political violence;
- resource conflict;
- coup scenarios;
- peacekeeping;
- evacuation;
- local power struggles.

---

### Phase 5 — Europe

## Faction 07 — Chernarussian Paramilitary

**Name:** TBD  
**Type:** `PARAMILITARY`  
**Region:** Chernarus  
**Priority:** `LOW/MEDIUM`  

Potential inspiration:

- contemporary Eastern European volunteer/irregular forces;
- mixed commercial and surplus equipment;
- modern drones;
- civilian SUVs/vans;
- Eastern and Western small arms.

Requires a dedicated modern Chernarus lore pass before approval.

---

## Livonian Armed Group

**Status:** `CONCEPT ONLY`

Do not create yet.

Livonia is an established NATO member and should not be given a major internal insurgency without a strong lore reason.

Possible future uses:

- foreign-backed sabotage network;
- criminal-paramilitary organisation;
- separatist fringe;
- exercise/training scenarios.

Research first.

---

## 11. Development Priority

Current order:

```text
1. NTEF
2. British Training OPFOR
3. Traditional Takistani Insurgents
4. Takistan Regional Proxy
5. Argana / Sahel Insurgents
6. African Political Militia
7. Chernarussian Paramilitary
8. Further factions only after demonstrated need
```

Do not build factions merely to increase the faction count.

Each faction should solve a distinct mission-making need.

---

## 12. Release Philosophy

Prefer:

**fewer complete factions**

over:

**many shallow factions**

A faction is not considered complete merely because it contains riflemen and vehicles.

A release-ready faction should have:

- coherent lore;
- consistent gear;
- believable weapon distribution;
- appropriate vehicles;
- sensible unit roles;
- usable editor groups;
- Zeus compatibility;
- faction icon;
- clean editor presentation;
- tested dependencies;
- tested multiplayer behaviour;
- documented credits.

---

## 13. Editor Naming Standard

Top-level editor presentation should remain consistent.

Proposed faction display format:

```text
UKSF - Northern Takistan Emirate Front
UKSF - Exercise Force
UKSF - Takistani Insurgents
```

Alternative compact format:

```text
NTEF
UKSF EXFOR
Takistani Insurgents
```

Final display format remains TBD until the first faction is configured.

### Internal faction IDs

Prefer short stable identifiers:

```text
NTEF
EXFOR
TAK_INS
TAK_PROXY
ARG_INS
AFR_MIL
CHR_PARAMIL
```

Internal IDs should not change merely because a display name receives minor wording changes.

---

## 14. Class Namespace Standard

All project-owned classes should begin with:

```text
UKSF_Factions_
```

Examples:

```cpp
UKSF_Factions_NTEF_Rifleman
UKSF_Factions_NTEF_MG
UKSF_Factions_NTEF_TeamLeader
```

For shared assets:

```cpp
UKSF_Factions_Uniform_Regional_01
UKSF_Factions_Vest_ChestRig_01
UKSF_Factions_Helmet_Surplus_01
```

Exact conventions will be formalised in a dedicated config naming document before implementation.

---

## 15. Asset Reuse Policy

The project should avoid duplicating identical assets per faction.

Example:

A plain tan regional uniform may be used by:

- NTEF;
- traditional Takistani insurgents;
- civilians;
- regional proxy forces.

It should exist once as a shared asset.

Faction identity should come from:

- combinations;
- equipment distribution;
- insignia;
- headwear;
- vest choice;
- weapon choice;
- vehicle choice;
- role composition;

rather than creating duplicate models unnecessarily.

---

## 16. Gear Dependency Policy

Project goal:

**UKSF_Factions should replace much of the gear/unit role currently supplied by the large 3CB Factions package.**

Therefore:

### Do not require 3CB for:

- core faction uniforms;
- core vests;
- core helmets;
- core infantry units.

### May use/adapt 3CB for:

- vehicles;
- weapons;
- technicals;
- regional transport;
- selected supporting assets.

The project owner has confirmed full permission from 3CB to use required source assets.

---

## 17. RHS Policy

RHS remains a high-value source for:

- Eastern weapons;
- regional weapons;
- launchers;
- selected vehicles;
- supporting equipment.

The project owner has confirmed full permission to use required RHS assets.

Decision whether to:

- reference RHS directly;
- adapt an RHS asset;
- incorporate a permitted source asset;

should be made case-by-case based on dependency weight and maintainability.

---

## 18. External Asset Policy

External assets are expected.

Potential sources include:

- private mods;
- donated assets;
- permitted assets from other games;
- commercial assets;
- open-source assets;
- original UKSF work.

All incorporated external assets must be entered in:

```text
docs/assets/asset_register.md
```

before public release.

---

## 19. Performance Standard

Performance is a project requirement, not a late optimisation task.

Where possible:

- avoid unnecessary hidden-selection complexity;
- avoid excessive material sections;
- use sensible texture resolutions;
- preserve useful LODs;
- create missing LODs where required;
- avoid loading large dependency packs for a handful of assets;
- share common assets across factions;
- avoid enormous config duplication;
- avoid unnecessary scripts on every unit.

The decision to reduce reliance on the full 3CB Factions package is consistent with this goal.

A dedicated performance checklist should be written before asset integration begins.

---

## 20. Faction Config Philosophy

Faction config should be as data-driven and repetitive-safe as practical within Arma config limitations.

Avoid:

- dozens of nearly identical hand-written unit classes where inheritance can solve the problem;
- duplicate loadout logic;
- faction classes that depend on unnecessary scripts;
- hardcoded content that prevents later gear replacement.

Prefer:

- clear base classes;
- consistent inheritance;
- faction-specific base soldiers;
- centralised identity settings;
- predictable class names;
- loadout structure that can be reviewed easily.

Exact config architecture will be designed after NTEF's role list is locked.

---

## 21. Unit Role Standard

Common roles should use consistent terminology across factions where appropriate.

Suggested baseline:

```text
Fighter / Rifleman
Team Leader
Cell Leader / Squad Leader
Automatic Rifleman
Machine Gunner
Assistant Machine Gunner
Marksman
Anti-Armour
Medic
Engineer
Drone Operator
Driver
Crew
Commander / Senior Leader
Bodyguard
```

Not every faction needs every role.

Faction-specific names may be used for display text while internal role naming stays consistent.

---

## 22. Group Standard

Every faction should include useful prebuilt groups.

Minimum target for major combat factions:

### Infantry

- basic small group;
- standard combat group;
- weapons/support group;
- leadership/security group where appropriate.

### Motorised

- vehicle patrol;
- motorised infantry group;
- technical patrol where appropriate.

### Specialist

Only create specialist groups that mission makers are likely to use.

Avoid filling Eden with dozens of marginally different groups.

---

## 23. Relationship Standard

Every faction brief should define likely relationships with:

- national government;
- foreign forces;
- local civilians;
- rival insurgents;
- criminal networks;
- regional state actors;
- other `UKSF_Factions` factions.

This is lore guidance.

Actual Arma side relationships remain mission-maker configurable unless a strong reason exists otherwise.

---

## 24. Faction Sides

Likely defaults:

### OPFOR / EAST

- NTEF;
- hostile insurgent factions;
- hostile paramilitaries;
- training OPFOR.

### INDEPENDENT

Potential use for:

- local militias;
- regional security actors;
- rival insurgents;
- politically ambiguous factions.

### BLUFOR / WEST

Potential use for:

- friendly host-nation security forces;
- specific training forces.

Do not force every non-Western faction onto OPFOR.

---

## 25. Lore Writing Standard

Faction lore should be written in two layers.

### Layer 1 — Editor / public overview

Approximately:

**50–150 words**

Purpose:

- tell mission makers what the faction is;
- explain region and broad identity;
- avoid unnecessary detail.

### Layer 2 — Research / intelligence brief

Long-form document covering:

- origin;
- ideology/politics;
- relationships;
- capability;
- appearance;
- geographic context;
- campaign hooks.

Do not overload config display text with lore.

---

## 26. Canon vs UKSF-Created Lore

Mark important lore statements internally as:

### `CANON`

Directly supported by official Armaverse material.

### `EXTENSION`

UKSF-created material designed to continue or fill gaps in established lore.

### `ORIGINAL`

Entirely new UKSF-created faction/country/event.

Example:

```text
CANON:
A large guerrilla insurgency followed the defeat of the Takistani regime.

EXTENSION:
NTEF emerged years later from extremist splinters within the continuing instability.
```

This distinction will make future lore maintenance significantly easier.

---

## 27. Naming Rules

Faction names should:

- be memorable;
- be pronounceable by English-speaking mission makers;
- fit the setting;
- avoid unnecessary similarity to real extremist organisations;
- avoid parody names;
- support a sensible acronym;
- not require fictional-language text merely to appear authentic.

Where appropriate, use:

1. local/self-designation;
2. English translation;
3. NATO/intelligence designation.

Do not create all three unless they add genuine value.

---

## 28. Language Policy

Do not add pseudo-Arabic, pseudo-Persian, pseudo-Russian or other decorative text.

If non-English text is eventually used:

- identify the fictional/real language convention first;
- have wording checked;
- keep faction identity fictional;
- avoid real extremist slogans.

Until then, use symbols and English-language intelligence names.

---

## 29. Imagery Policy

Faction artwork should be original wherever possible.

Priority assets:

- emblem;
- flag;
- editor icon;
- patch;
- vehicle stencil.

Avoid direct copies of:

- extremist flags;
- national military insignia;
- real militia patches;
- propaganda logos.

Real visual material may be used as compositional research only.

---

## 30. Documentation Structure

Proposed current structure:

```text
UKSF_Factions/
└── docs/
    ├── assets/
    │   └── asset_register.md
    ├── project/
    │   └── 01_project_scope_standards_roadmap.md
    └── factions/
        └── north_takistan/
            ├── 01_north_takistan_extremist_research_brief.md
            └── 02_ntef_asset_dependency_audit.md
```

Future project documents may include:

```text
02_class_and_editor_naming_standard.md
03_dependency_and_pbo_architecture.md
04_performance_standard.md
05_release_checklist.md
06_credits_and_attribution_standard.md
```

---

## 31. PBO Architecture

**Not yet locked.**

Possible eventual structures:

### Single PBO

Advantages:

- simple;
- easy to manage initially.

Disadvantages:

- increasingly poor modularity as the asset library grows.

### Multiple PBOs inside UKSF_Factions

Possible example:

```text
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
UKSF_Factions_NTEF
UKSF_Factions_EXFOR
```

Advantages:

- modular updates;
- clearer dependencies;
- easier optional components;
- potentially better long-term maintenance.

Disadvantages:

- more config/PBO management.

Do not decide until we know the expected asset volume.

---

## 32. Development Method

Continue the established UKSF workflow:

- one file at a time;
- one clearly defined change at a time;
- research before implementation;
- test before moving on;
- whole-file replacements rather than fragmented patch snippets where practical;
- keep configs compact and PBOProject-safe;
- multiplayer validation late in the faction-development cycle after solo/Eden checks.

---

## 33. Quality Gates

Every faction passes through the following stages.

### Gate 1 — Concept

Required:

- role/use case;
- region;
- faction type;
- real-world inspiration if applicable.

### Gate 2 — Lore

Required:

- name;
- background;
- relationships;
- visual concept;
- capability concept.

### Gate 3 — Asset Audit

Required:

- uniforms;
- vests;
- headwear;
- weapons;
- vehicles;
- permissions;
- dependencies.

### Gate 4 — Configuration

Required:

- faction class;
- unit classes;
- role classes;
- groups;
- editor categories.

### Gate 5 — Visual Review

Required:

- consistent silhouette;
- no obvious clipping;
- coherent colour/equipment distribution;
- no accidental dependency gaps.

### Gate 6 — Functional Test

Required:

- Eden;
- Zeus;
- inventory/loadouts;
- vehicle crews;
- group spawning;
- respawn where applicable.

### Gate 7 — Performance Review

Required:

- reasonable model/texture cost;
- no unnecessary scripts;
- dependency review;
- RPT review.

### Gate 8 — Multiplayer Test

Required before release candidate.

### Gate 9 — Release Review

Required:

- credits;
- asset register;
- icons;
- documentation;
- versioning;
- changelog.

---

## 34. Current Development State

### Complete / established

- project name: `UKSF_Factions`;
- author: `UKSF Surplus`;
- contemporary Armaverse direction;
- first faction concept: NTEF;
- NTEF first research brief;
- NTEF first asset/dependency audit;
- project asset register;
- 3CB/RHS permission position;
- rule against relying on 3CB infantry gear.

### Research/admin phase

Current work should focus on:

- NTEF lore and organisation;
- NTEF equipment distribution philosophy;
- class/editor naming;
- project architecture;
- performance rules;
- British training OPFOR research;
- future faction research backlog.

### Deliberately deferred

- model conversion;
- uniform production;
- texture sorting;
- retexturing;
- asset implementation;
- faction config;
- PBO build.

---

## 35. Recommended Next Research/Admin Documents

Recommended order:

### Next

`03_ntef_organisation_roles_and_equipment_standard.md`

Purpose:

Lock exactly what kinds of NTEF units exist and how equipment quality varies between them.

This should become the bridge between lore and later config work.

### Then

`docs/project/02_class_and_editor_naming_standard.md`

Purpose:

Lock namespaces and editor presentation before creating classes.

### Then

`docs/project/03_dependency_and_pbo_architecture.md`

Purpose:

Decide how `UKSF_Factions` should be split as it grows.

### Then

`docs/project/04_performance_standard.md`

Purpose:

Define model, texture and config expectations before asset conversion begins.

### In parallel after NTEF

British training OPFOR research brief.

---

## 36. Research References

Checked 2026-08-09.

### Bohemia Interactive — Arma 2: British Armed Forces Released

Official source establishing continued NATO deployment to Takistan following Operation Arrowhead and the large-scale guerrilla insurgency.

Source:
https://www.arma2.com/index.php/latest-news/arma-2-british-armed-forces-released

### Bohemia Interactive — New Intelligence Report From Takistan

Official source establishing Takistani insurgent activity in the disputed Sharig Plateau/Karzeghistan border area and the Shapur region.

Source:
https://arma2.com/latest-news/new-intelligence-report-from-takistan

### Bohemia Interactive — Arma 3 Contact

Official source establishing Livonia as a fictional Polish-speaking, landlocked NATO member in Eastern Europe.

Source:
https://arma3.com/contact

### Bohemia Interactive — Western Sahara

Official source establishing Sefrou-Ramal as a province in fictional Argana and describing the region's long-running conflict involving tribes, insurgents, peacekeepers and foreign forces.

Source:
https://arma3.com/news/arma-3-creator-dlc-western-sahara-is-out-now

### British Army / Soldier — Task Force Hannibal

Public British Army reporting describing approximately 250 personnel acting as OPFOR during Exercise Iron Storm on Salisbury Plain and being prepared to represent Russian ground forces.

Source:
https://soldier.army.mod.uk/issues/september-2025/update/global-sitrep/uk

### British Army / Soldier — CENZUB

Public reporting describing a permanent in-house opposing force able to represent conventional formations, militia or civilians according to training requirements.

Source:
https://soldier.army.mod.uk/issues/jan-26/soldier-life/cenzub

---

## 37. Current Project Direction

`UKSF_Factions` should develop as a **curated contemporary Armaverse faction ecosystem**, not as a miscellaneous unit pack.

The immediate goal is to make NTEF complete enough for the North Takistan deployment while establishing standards reusable by every faction that follows.

The next useful step is to define the **NTEF organisation, unit roles and equipment-distribution standard** before any physical assets are selected.
