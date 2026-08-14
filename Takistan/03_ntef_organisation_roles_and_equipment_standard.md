# UKSF_Factions — NTEF Organisation, Roles & Equipment Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** NTEF Organisation, Roles & Equipment Standard  
**Status:** Research / Design Standard  
**Created:** 2026-08-09  
**Faction:** Northern Takistan Emirate Front (`NTEF`)  
**Faction type:** `EXTREMIST`  
**Theatre:** North Takistan  
**Related documents:**
- `01_north_takistan_extremist_research_brief.md`
- `02_ntef_asset_dependency_audit.md`
- `../../project/01_project_scope_standards_roadmap.md`
- `../../assets/asset_register.md`

---

## 1. Purpose

This document defines what the Northern Takistan Emirate Front should contain as an Arma faction.

It is the bridge between:

```text
LORE
  ↓
FACTION DESIGN
  ↓
ASSET SELECTION
  ↓
CONFIG
```

It locks the intended:

- capability tiers;
- unit roles;
- broad equipment distribution;
- weapon-family distribution;
- armour and headgear prevalence;
- optics and accessory prevalence;
- radio distribution;
- night capability;
- specialist capability;
- vehicle hierarchy;
- editor unit catalogue;
- editor group catalogue.

It does **not** lock individual Arma class names, model choices or exact third-party assets.

Those decisions will be made later when the physical asset pool is available.

---

## 2. Research Handling

NTEF is inspired by the contemporary threat identity of ISIS-K but is a fictional Armaverse organisation.

Current public assessments support several broad design conclusions:

- ISIS-K remains active and strategically relevant in 2026;
- Afghanistan remains an important recruitment and organisational hub;
- the organisation has a transnational outlook rather than a purely local-nationalist identity;
- contemporary terrorist organisations increasingly exploit commercial communications, digital media and unmanned systems;
- sustained counter-terrorism pressure has reduced or disrupted capabilities without eliminating the threat.

These points justify:

- mixed local and more committed core personnel;
- uneven equipment quality;
- a smaller veteran/specialist element;
- commercial communications;
- limited drone capability;
- stronger organisational identity than traditional Takistani militia.

### Important limitation

Public research does **not** justify presenting a detailed real-world ISIS-K squad structure as fact.

Therefore:

> All group sizes, unit-role distributions and equipment percentages in this document are **UKSF_Factions gameplay design values**, not estimates of real-world ISIS-K organisation.

This distinction should be preserved in future documentation.

---

## 3. Core Design Principle

NTEF should look like:

> **an irregular force with pockets of modern capability**

It should **not** look like:

> a conventional army wearing insurgent clothing.

The faction's threat should come from the mixture of:

- large numbers of relatively basic fighters;
- competent core fighters;
- better-equipped veteran elements;
- specialist weapons;
- mobility;
- occasional modern technology.

Advanced equipment should be memorable because it is not universal.

---

# PART I — ORGANISATIONAL ABSTRACTION

## 4. Organisational Layers

For gameplay, NTEF is divided into five broad personnel layers.

These are not intended as literal real-world organisational terminology.

---

## 4.1 Local / Auxiliary Layer

**Internal design tier:** `TIER_1`

Represents:

- locally recruited fighters;
- recently joined members;
- personnel with limited access to high-quality equipment;
- security/checkpoint manpower;
- local armed supporters incorporated into NTEF formations.

### Visual identity

- strongly civilian/regional;
- traditional clothing;
- civilian jackets;
- older webbing;
- simple chest rigs;
- minimal armour;
- minimal optics;
- older weapons.

### Gameplay identity

These should form much of the visible manpower in:

- rural areas;
- checkpoints;
- village security;
- static positions;
- large insurgent groups.

They should not be helpless, but they should visibly sit below veteran personnel in equipment quality.

---

## 4.2 Core Fighter Layer

**Internal design tier:** `TIER_2`

Represents the faction's normal committed fighting personnel.

### Visual identity

- still irregular;
- better load-bearing equipment;
- more coherent colours;
- some camouflage;
- occasional armour;
- better rifles;
- more radios;
- more optics than Tier 1.

### Gameplay identity

Core Fighters should be the faction's default combat unit.

If a mission maker places a generic NTEF combat group, most personnel should come from this tier.

---

## 4.3 Veteran / Assault Layer

**Internal design tier:** `TIER_3`

Represents:

- experienced personnel;
- trusted assault/security elements;
- better-equipped fighters;
- personnel assigned to higher-value tasks or leadership security.

### Visual identity

- darker or more coordinated clothing;
- modern chest rigs or plate carriers;
- greater use of helmets;
- modernised AK-pattern rifles;
- optics;
- radios;
- occasional night equipment.

### Gameplay identity

Veterans should be noticeably more capable but significantly less numerous than Tier 1 or Tier 2.

The entire faction should never become Tier 3 by default.

---

## 4.4 Specialist Layer

**Internal design tier:** `TIER_4`

Specialists may originate from any of the first three equipment tiers but possess a specialist role.

Examples:

- machine gunner;
- automatic rifleman;
- marksman;
- anti-armour gunner;
- medic;
- engineer;
- drone operator;
- communications specialist;
- vehicle crew.

A specialist is **not automatically an elite fighter**.

Example:

A local RPG gunner may visually remain Tier 1.

A veteran drone operator may visually belong to Tier 3.

---

## 4.5 Leadership / Security Layer

**Internal design tier:** `TIER_5`

Represents:

- team/cell leadership;
- senior field leadership;
- high-value personnel;
- bodyguards/security personnel.

### Design rule

Leadership should be visually identifiable through **quality and detail**, not theatrical costumes.

Avoid:

- ornate "warlord" outfits;
- excessive black clothing;
- unrealistic gold weapons;
- costume-like religious imagery.

Preferred indicators:

- better clothing;
- cleaner equipment;
- radio;
- sidearm;
- more modern rifle;
- small security element.

---

# PART II — EDITOR UNIT CATALOGUE

## 5. Required Infantry Roles

The following unit roles should be supported in the first complete NTEF release.

---

## 5.1 Fighter

**Working internal role:** `Fighter`

**Tier:** 1  
**Purpose:** Baseline low-tier combatant.

Typical characteristics:

- regional/civilian clothing;
- simple chest rig;
- AKM-family weapon;
- iron sights;
- no body armour;
- no NVG;
- no specialist equipment.

This should be one of the most visually varied classes.

---

## 5.2 Fighter (Light)

**Working internal role:** `Fighter_Light`

**Tier:** 1  
**Purpose:** Very lightly equipped auxiliary.

Typical characteristics:

- minimal load-bearing equipment;
- lighter ammunition load;
- civilian/regional appearance;
- older rifle.

Useful for:

- local security;
- loosely organised groups;
- ambient insurgent presence.

---

## 5.3 Rifleman

**Working internal role:** `Rifleman`

**Tier:** 2  
**Purpose:** Standard NTEF combatant.

Typical characteristics:

- more coherent clothing;
- proper chest rig;
- AKM/AK-74/modern AK pool;
- occasional optic;
- limited armour chance.

This should become the primary "normal" NTEF class.

---

## 5.4 Veteran Rifleman

**Working internal role:** `Rifleman_Veteran`

**Tier:** 3  
**Purpose:** Better-equipped assault/security combatant.

Typical characteristics:

- modern chest rig or plate carrier;
- better rifle;
- optic common;
- radio possible;
- helmet possible;
- NVG possible but not guaranteed.

---

## 5.5 Team Leader

**Working internal role:** `TeamLeader`

**Tier:** 2–3  
**Purpose:** Leader for small editor groups.

Typical characteristics:

- radio;
- better rifle than baseline;
- optic likely;
- sidearm optional;
- visually slightly better equipped than surrounding fighters.

Do not make every Team Leader visually elite.

---

## 5.6 Cell Leader

**Working internal role:** `CellLeader`

**Tier:** 3 / 5  
**Purpose:** More senior field leader.

Typical characteristics:

- radio;
- better equipment;
- sidearm;
- modern rifle;
- armour likely;
- small security element when placed in groups.

---

## 5.7 Automatic Rifleman

**Working internal role:** `AutomaticRifleman`

**Tier:** 1–2  
**Purpose:** Mobile automatic-fire support role.

Likely weapon families:

- RPK;
- RPD;
- similar regionally appropriate automatic rifle.

Visual quality should follow the parent tier rather than making the role elite.

---

## 5.8 Machine Gunner

**Working internal role:** `MachineGunner`

**Tier:** 2  
**Purpose:** General-purpose machine-gun role.

Preferred visual weapon family:

- PKM;
- related PK-pattern weapons.

The PKM should be one of the faction's strongest recurring weapon signatures.

---

## 5.9 Assistant Machine Gunner

**Working internal role:** `AssistantMG`

**Tier:** 1–2  
**Purpose:** Group support role.

Gameplay equipment may include:

- additional ammunition;
- ordinary rifle;
- binoculars where appropriate.

The assistant should not carry implausibly excessive ammunition solely because Arma permits it.

---

## 5.10 Marksman

**Working internal role:** `Marksman`

**Tier:** 2–3  
**Purpose:** Limited precision capability.

Likely weapon family:

- SVD;
- older scoped rifle;
- occasional captured marksman rifle for veteran variants.

### Design rule

Precision capability should remain relatively uncommon.

Avoid making a marksman mandatory in every small group.

---

## 5.11 Anti-Armour Fighter

**Working internal role:** `AT`

**Tier:** 1–3  
**Purpose:** Basic anti-vehicle capability.

Primary visual family:

- RPG-7-pattern launcher.

Possible limited secondary pool:

- older disposable launchers;
- captured disposable systems.

### Design rule

Modern guided anti-tank weapons are **not baseline NTEF equipment**.

If later lore introduces them, they should be a distinct high-value capability.

---

## 5.12 Grenadier

**Working internal role:** `Grenadier`

**Tier:** 2–3  
**Purpose:** Optional specialist rifle role.

This unit should only be retained if the chosen weapon pool contains a visually appropriate under-barrel or rifle-grenade capability.

**Status:** `OPTIONAL`

Do not force this role merely to mirror NATO squad structures.

---

## 5.13 Medic / First Aider

**Working internal role:** `Medic`

**Tier:** 2–3  
**Purpose:** ACE-compatible medical support.

Visual characteristics:

- standard fighter appearance;
- small medical identifier if desired;
- medical backpack/pouches where suitable.

### Design rule

Do not make the unit look like a conventional Western combat medic unless assets justify it.

ACE medical capability will be defined later.

---

## 5.14 Engineer

**Working internal role:** `Engineer`

**Tier:** 2–3  
**Purpose:** Technical/engineering mission role.

Potential gameplay uses:

- repair;
- mine detection/defusal if appropriate;
- ACE engineering capability;
- carrying toolkits.

No special visual stereotype is required.

---

## 5.15 Drone Operator

**Working internal role:** `DroneOperator`

**Tier:** 2–3  
**Purpose:** Contemporary commercial-UAS capability.

Default implementation direction:

- commercial observation quadcopter;
- controller/tablet;
- rifle;
- radio;
- no specialised futuristic uniform.

### Important rule

The baseline NTEF drone role should represent **observation/reconnaissance**.

Do not make weaponised commercial drones part of the default unit class purely because real-world groups have experimented with weaponised UAS.

Mission-specific capabilities can be considered separately if ever required.

---

## 5.16 Communications Specialist

**Working internal role:** `RadioOperator`

**Tier:** 2–3  
**Purpose:** Optional visible communications specialist.

Potential characteristics:

- better radio;
- radio backpack if a suitable contemporary asset exists;
- standard rifle.

**Status:** `OPTIONAL`

If ACRE implementation makes a dedicated role unnecessary, do not create one solely for editor clutter.

---

## 5.17 Driver

**Working internal role:** `Driver`

**Tier:** 1–2  
**Purpose:** Civilian/technical vehicle driver.

Appearance:

- lighter equipment;
- no large backpack;
- compact or ordinary rifle.

---

## 5.18 Vehicle Crew

**Working internal role:** `Crew`

**Tier:** 2  
**Purpose:** Captured protected/military vehicle crew.

Appearance:

- simple practical clothing;
- reduced equipment;
- optional helmet depending on vehicle;
- compact weapon.

This role should be uncommon because NTEF is not a mechanised force.

---

## 5.19 Bodyguard

**Working internal role:** `Bodyguard`

**Tier:** 3 / 5  
**Purpose:** Security for senior leadership/HVT scenarios.

Typical characteristics:

- high equipment quality;
- armour common;
- optic common;
- radio common;
- modern rifle.

Bodyguards are one of the few roles where a consistently high equipment standard is desirable.

---

## 5.20 Senior Leader

**Working internal role:** `SeniorLeader`

**Tier:** 5  
**Purpose:** HVT / command figure.

Typical characteristics:

- high-quality regional clothing;
- discreet armour optional;
- radio;
- sidearm;
- rifle or no long gun depending on final design;
- visually distinct through clothing/equipment quality rather than fictional religious costume.

Create several visual variants later if practical.

---

# PART III — ROLES NOT INCLUDED BY DEFAULT

## 6. Deliberate Exclusions

The following should **not** be standard editor classes in the first release.

---

## 6.1 Dedicated Suicide Bomber

**Decision:** `EXCLUDE`

Reason:

- unnecessary as a permanent faction class;
- potentially encourages repetitive stereotype-driven mission design;
- specific scenarios can implement special behaviour separately if genuinely required;
- provides no useful reusable gear role.

NTEF lore may acknowledge extremist violence without requiring a dedicated editor unit.

---

## 6.2 Civilian-Disguised Combatant

**Decision:** `EXCLUDE AS A PREBUILT CLASS`

Reason:

The normal Fighter classes already use civilian/regional clothing.

A dedicated "civilian disguise" unit would create unnecessary ambiguity and mission-design problems.

---

## 6.3 Child Soldier

**Decision:** `EXCLUDE`

No child-combatant assets or classes should be created for NTEF.

---

## 6.4 Heavy Infantry / Conventional Assault Trooper

**Decision:** `EXCLUDE`

NTEF should not receive a conventional heavy-infantry class with universal helmets, full body armour and advanced weapons.

Veteran Rifleman fills the upper infantry tier.

---

## 6.5 Dedicated Sniper

**Decision:** `DEFER`

A Marksman is sufficient for the initial faction.

A dedicated specialist sniper may be added later only if:

- suitable assets exist;
- there is a clear mission-making need;
- the role remains rare.

---

# PART IV — EQUIPMENT PREVALENCE STANDARD

## 7. Prevalence Bands

All percentages in this section are **faction-design targets**, not real-world intelligence estimates.

Use these bands consistently:

| Band | Design Frequency |
|---|---:|
| `UBIQUITOUS` | 70–100% |
| `COMMON` | 35–69% |
| `OCCASIONAL` | 15–34% |
| `RARE` | 5–14% |
| `EXCEPTIONAL` | 1–4% |
| `NONE` | 0% |

These figures describe desired visual/loadout variety when producing unit variants.

They do not need to be implemented using literal randomisation.

Fixed unit classes may simply be selected in proportions that produce the same overall effect.

---

## 8. Body Armour Distribution

### Tier 1

| Equipment | Frequency |
|---|---|
| No ballistic armour | `UBIQUITOUS` |
| Soft/basic armour | `RARE` |
| Plate carrier | `EXCEPTIONAL` |
| Military helmet | `EXCEPTIONAL` |

Tier 1 should mostly rely on chest rigs/webbing rather than armour.

---

### Tier 2

| Equipment | Frequency |
|---|---|
| No ballistic armour | `COMMON` |
| Basic armour | `OCCASIONAL` |
| Plate carrier | `OCCASIONAL` |
| Military helmet | `RARE` |

A standard Rifleman should still often have no armour.

---

### Tier 3

| Equipment | Frequency |
|---|---|
| Plate carrier / ballistic vest | `COMMON` |
| No armour | `OCCASIONAL` |
| Helmet | `OCCASIONAL` |
| Modern helmet | `RARE` |

Even the veteran layer should retain visual irregularity.

---

### Leadership / Bodyguards

| Equipment | Frequency |
|---|---|
| Bodyguards with armour | `COMMON` |
| Field leader with armour | `OCCASIONAL` |
| Senior leader with visible armour | `RARE` |

Leadership need not personally wear the heaviest equipment.

---

## 9. Helmet Distribution

Helmet usage should remain considerably lower than chest-rig usage.

### Visual categories

Potential future categories:

- no headwear;
- regional hat;
- scarf/wrap;
- civilian cap;
- surplus military helmet;
- modern commercial/military helmet.

### Design rule

For an ordinary NTEF group:

> Bare heads and regional/civilian headwear should remain more visually common than helmets.

This is important to preserve the faction silhouette.

---

## 10. Load-Bearing Equipment

### Tier 1

Primary:

- simple AK chest rig;
- old webbing;
- minimal harness;
- occasional no visible vest.

### Tier 2

Primary:

- improved chest rigs;
- surplus tactical rigs;
- light armour;
- simple plate carriers in minority.

### Tier 3

Primary:

- modern chest rigs;
- plate carriers;
- better pouch layouts;
- mixed captured/commercial equipment.

### Design rule

Do not issue one identical tactical vest to all NTEF fighters.

---

# PART V — WEAPON STANDARD

## 11. Rifle Family Hierarchy

The initial NTEF weapon identity should centre on AK-pattern rifles.

### Primary families

1. **AKM-pattern**
2. **AK-74-pattern**
3. **AK-100 / modern AK-pattern**

### Secondary minority families

Potentially:

- SKS;
- FN FAL;
- G3;
- older regional rifles;
- captured Western AR-pattern rifles.

### Design principle

Minority weapons exist for visual plausibility and narrative interest.

They should not dilute the faction's core AK identity.

---

## 12. Suggested Rifle Pool — Tier 1

These are **game design weights**, not real-world prevalence claims.

| Weapon family | Target share |
|---|---:|
| AKM / older 7.62 AK | 60% |
| AK-74 / similar | 20% |
| SKS / older regional rifle | 8% |
| FAL / G3 / regional minority rifle | 8% |
| Other appropriate captured rifle | 4% |

### Accessories

- iron sights overwhelmingly dominant;
- very limited optics;
- minimal rail accessories;
- suppressors absent.

---

## 13. Suggested Rifle Pool — Tier 2

| Weapon family | Target share |
|---|---:|
| AKM / improved AKM | 40% |
| AK-74 family | 30% |
| AK-100 / modern AK | 20% |
| regional minority rifle | 7% |
| captured Western rifle | 3% |

### Accessories

Optics become visible but remain a minority overall.

---

## 14. Suggested Rifle Pool — Tier 3

| Weapon family | Target share |
|---|---:|
| modern AK / AK-100 family | 40% |
| AK-74 family | 25% |
| improved AKM family | 20% |
| captured Western rifle | 10% |
| other selected weapon | 5% |

### Important rule

Even veteran fighters should remain predominantly Eastern/AK armed.

Captured Western rifles should look notable rather than normal.

---

## 15. Optics

### Tier 1

`EXCEPTIONAL` to `RARE`

Mostly iron sights.

### Tier 2

`OCCASIONAL`

Simple optics:

- red-dot style;
- low-magnification;
- appropriate older Eastern optics.

### Tier 3

`COMMON`

But do not give every veteran fighter a premium modern optic.

### Marksmen

Optic is effectively required by role.

---

## 16. Weapon Lights / Lasers

### Tier 1

`NONE` or `EXCEPTIONAL`

### Tier 2

`RARE`

### Tier 3

`OCCASIONAL`

Modern accessories should help distinguish the upper tier.

---

## 17. Suppressors

Suppressors should remain visually uncommon.

### Tier 1

`NONE`

### Tier 2

`EXCEPTIONAL`

### Tier 3

`RARE`

### Specialists

Potentially higher for a future specialist role, but no dedicated suppressed-assault class is required initially.

---

## 18. Machine Guns

### Automatic rifle

Possible families:

- RPK;
- RPD.

### General-purpose machine gun

Primary family:

- PKM.

Secondary later possibilities:

- PKP;
- captured Western GPMG.

### Design rule

PKM should dominate the faction's GPMG identity.

Western GPMGs should be exceptional.

---

## 19. Precision Weapons

### Primary

- SVD family.

### Secondary

- older scoped regional rifle;
- occasional captured modern marksman weapon.

### Design rule

A Marksman should not automatically receive:

- suppressor;
- rangefinder;
- thermal optic;
- Western sniper camouflage.

Keep the role compatible with the faction's overall equipment level.

---

## 20. Anti-Armour

### Baseline

- RPG-7 family.

### Secondary

- limited older disposable launchers;
- limited captured disposable systems.

### Excluded baseline

- widespread modern guided missiles;
- large stocks of top-tier Western anti-armour weapons.

These may be introduced only by specific future faction-lore decisions.

---

## 21. Sidearms

### Fighters

Generally:

`NONE`

### Team / Cell Leaders

`OCCASIONAL`

### Vehicle Crew

`OCCASIONAL`

### Bodyguards

`COMMON`

### Senior Leaders

`COMMON`

Sidearms should not become a universal secondary weapon merely because Arma loadout capacity allows it.

---

# PART VI — COMMUNICATIONS & TECHNOLOGY

## 22. Radio Distribution

The final ACRE implementation will be designed separately.

This section defines the visual/conceptual hierarchy.

### Tier 1

Radio:

`RARE`

Most personnel should not visibly appear to carry advanced individual communications.

### Tier 2

Radio:

`OCCASIONAL`

At least leaders should have reliable communications.

### Tier 3

Radio:

`COMMON`

Veteran elements should appear better networked.

### Team Leader

Radio:

`UBIQUITOUS`

### Cell Leader

Radio:

`UBIQUITOUS`

### Bodyguard

Radio:

`COMMON`

### Senior Leader

Radio:

`UBIQUITOUS`

### Drone Operator

Radio:

`UBIQUITOUS`

Exact radio models and channel behaviour are outside the scope of this document.

---

## 23. Smartphones / Tablets

Commercial electronic devices are useful visual props for:

- leaders;
- drone operators;
- communications personnel;
- HVT scenarios.

Do not place a visible tablet on every fighter.

Use:

`RARE` overall.

---

## 24. Drone Capability

### Default NTEF capability

Commercial quadcopter reconnaissance.

### Unit

`DroneOperator`

### Frequency

`RARE` at faction level.

Drone Operators should appear as specialist assets rather than routine members of every group.

### Default gameplay role

- observation;
- reconnaissance;
- mission-maker intelligence tool.

Weaponised drone systems are **not part of the baseline faction catalogue**.

---

# PART VII — NIGHT CAPABILITY

## 25. NVG Distribution

Night equipment is deliberately uneven.

### Tier 1

`NONE`

### Tier 2

`EXCEPTIONAL`

### Tier 3

`OCCASIONAL`

Target visual effect:

A veteran group operating at night may contain some NVG-equipped personnel, but not necessarily all of them.

### Leaders

`RARE` to `OCCASIONAL`

### Specialists

Depending on role:

`RARE` to `OCCASIONAL`

---

## 26. Thermal Equipment

### Handheld / weapon thermal

`EXCEPTIONAL`

### Default unit classes

No baseline NTEF unit should require a thermal optic.

### Design principle

UKSF should retain a significant night-sensor advantage during ordinary missions.

NTEF night capability should complicate operations without erasing that advantage.

---

# PART VIII — MEDICAL & SUPPORT EQUIPMENT

## 27. Medical Equipment

### Ordinary fighters

Carry only limited individual medical supplies appropriate to the unit's ACE settings.

### Medic

Carries a substantially larger medical load.

Do not overequip all fighters to the point that the faction becomes unrealistically medically resilient.

Exact ACE medical inventories will be decided during config development.

---

## 28. Backpacks

### Tier 1

`RARE` to `OCCASIONAL`

Potential uses:

- ammunition;
- local supplies.

### Tier 2

`OCCASIONAL`

### Specialists

`COMMON` where role requires it.

Examples:

- Assistant MG;
- Medic;
- Engineer;
- Drone Operator;
- Radio Operator.

### Design rule

Backpacks should communicate role.

Avoid giving every fighter a large combat pack.

---

# PART IX — VEHICLE STANDARD

## 29. Vehicle Identity

NTEF is fundamentally a **light mobile irregular faction**.

Core mobility should come from:

- civilian pickups;
- SUVs;
- vans;
- utility trucks;
- motorcycles where available.

Technical variants provide most mobile heavy firepower.

---

## 30. Vehicle Capability Tiers

### Vehicle Tier A — Civilian Mobility

Most common.

Includes:

- pickup;
- SUV;
- van;
- motorcycle.

Appearance:

- civilian;
- worn;
- limited overt faction marking.

---

### Vehicle Tier B — Logistics

Includes:

- cargo pickup;
- van;
- utility truck;
- fuel/repair support if appropriate.

Use:

- logistics;
- transport;
- mission objectives.

---

### Vehicle Tier C — Technical

Includes armed pickup/utility variants.

Visual rule:

Technical vehicles should appear improvised/irregular rather than factory-standard military platforms.

Potential weapon categories:

- light/medium machine gun;
- heavy machine gun;
- recoilless weapon where suitable existing assets exist.

Exact vehicle weapons will be decided during asset selection.

---

### Vehicle Tier D — Captured Government Vehicle

Rare.

Possible categories:

- military utility vehicle;
- police pickup;
- light protected mobility vehicle;
- military cargo truck.

These should visually communicate that the faction has obtained government equipment.

---

### Vehicle Tier E — Captured Armour

**Not part of baseline NTEF.**

No default:

- tank;
- IFV;
- tracked APC fleet.

A mission maker may introduce a captured armoured vehicle for a specific scenario.

---

## 31. Vehicle Distribution Target

These are editor/catalogue design proportions, not real-world statistics.

For every ten broadly representative NTEF vehicles in the content pool:

```text
4 × civilian/unarmed pickup or utility vehicle
2 × SUV / van
2 × armed technical
1 × logistics truck
1 × motorcycle or captured government utility vehicle
```

This is a design reference only.

We do not need exactly ten vehicle classes.

---

## 32. Vehicle Markings

Most NTEF vehicles should use:

- no obvious markings;
- small faction marking;
- improvised stencil;
- flag only on selected faction-identified variants.

Do not apply a large faction logo to every vehicle.

This allows the same civilian base vehicles to remain reusable elsewhere.

---

# PART X — GROUP STANDARD

## 33. Group Philosophy

NTEF groups should be useful to Zeus and mission makers immediately.

They are **gameplay abstractions**.

Do not present them in documentation as a discovered real-world NTEF/ISIS-K order of battle.

---

## 34. Fighter Cell

**Target size:** 4

Suggested composition:

- 1 × Tier 1/2 leader;
- 3 × Fighters/Riflemen.

Purpose:

- patrol;
- checkpoint;
- ambient enemy presence;
- small contact.

---

## 35. Core Combat Cell

**Target size:** 6

Suggested composition:

- 1 × Team Leader;
- 3 × Riflemen;
- 1 × Automatic Rifleman;
- 1 × Anti-Armour Fighter or additional Rifleman.

Purpose:

- standard NTEF infantry group.

---

## 36. Weapons Cell

**Target size:** 5–6

Suggested composition:

- Team Leader;
- Machine Gunner;
- Assistant MG;
- Riflemen;
- optional specialist.

Purpose:

- heavier support group.

Avoid creating multiple nearly identical "weapons squad" variations.

---

## 37. Veteran Assault Cell

**Target size:** 5–6

Suggested composition:

- veteran leader;
- veteran riflemen;
- automatic weapon;
- optional specialist.

Visual characteristics:

- higher armour rate;
- higher optic rate;
- better radios;
- limited NVG chance.

Purpose:

- HVT protection;
- difficult raid target;
- higher-threat encounters.

---

## 38. Leadership Security Detail

**Target size:** 4–6 plus leader.

Suggested composition:

- Senior Leader or Cell Leader;
- Bodyguards;
- Driver if vehicle-based.

Purpose:

- HVT mission setup;
- command-group presence.

---

## 39. Technical Patrol

**Target:** 1–2 vehicles.

Possible composition:

- one armed technical;
- optional second pickup;
- drivers/gunners;
- small dismount element.

Do not make every NTEF motorised group a convoy of heavily armed vehicles.

---

## 40. Motorised Fighter Cell

**Target:** one transport vehicle plus 4–6 dismounts.

Vehicle:

- pickup;
- SUV;
- van.

Purpose:

- road patrol;
- reinforcement;
- mobile presence.

---

## 41. Drone Team

**Target size:** 2–3

Suggested composition:

- Drone Operator;
- Rifleman/security;
- optional Team Leader.

Purpose:

- scenario-specific reconnaissance element.

Do not place in the generic infantry group list if it causes editor clutter; this may be a specialist group.

---

# PART XI — FACTION THREAT MIX

## 42. Representative Force Mix

A generic NTEF mission area should **not** be populated entirely with a single tier.

Suggested broad design ratio:

| Personnel category | Target share |
|---|---:|
| Tier 1 Local / Auxiliary | 35% |
| Tier 2 Core | 45% |
| Tier 3 Veteran | 12% |
| Tier 4 Specialist roles | distributed within the above |
| Tier 5 Leadership/Security | 8% |

### Important note

Tier 4 specialists are not an additional 100%-sum category; they are roles drawn from Tiers 1–3.

The 8% leadership/security share includes bodyguards and leaders.

This ratio is a **mission-design target**, not a random spawn system requirement.

---

## 43. Rural Variant

For rural North Takistan:

Increase:

- Tier 1;
- traditional clothing;
- older rifles;
- unarmoured pickup use.

Decrease:

- helmets;
- modern optics;
- plate carriers.

---

## 44. Urban Variant

For towns/urban areas:

Increase slightly:

- Tier 2;
- chest rigs;
- body armour;
- SUVs/vans;
- leadership/security roles.

Do not create a completely separate urban faction unless later asset volume justifies it.

---

## 45. Veteran / High-Value Site Variant

For major HVT or faction-command locations:

Increase:

- Tier 3;
- bodyguards;
- radios;
- optics;
- limited NVGs;
- captured government equipment.

Do not make this the baseline for normal NTEF presence.

---

# PART XII — EDITOR PRESENTATION

## 46. Proposed Editor Subcategories

Keep editor categories restrained.

Recommended:

```text
Men
Men (Veteran)
Cars
Cars (Armed)
Trucks
Captured Vehicles
Drones
```

Alternative:

```text
Men
Men (Specialists)
Vehicles
Drones
```

The second option may be cleaner.

Final decision belongs in the editor/class naming standard.

---

## 47. Proposed Initial Unit List

Minimum viable complete catalogue:

```text
Fighter
Fighter (Light)
Rifleman
Veteran Rifleman
Team Leader
Cell Leader
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
Bodyguard
Senior Leader
```

Optional later:

```text
Grenadier
Radio Operator
Sniper
```

This gives us **18 core infantry roles** without unnecessary duplication.

---

# PART XIII — CONFIG PREPARATION

## 48. Future Base-Class Logic

The later config should aim for a structure conceptually similar to:

```text
NTEF_Base
├── NTEF_Tier1_Base
├── NTEF_Tier2_Base
├── NTEF_Tier3_Base
├── NTEF_Specialist_Base
└── NTEF_Leadership_Base
```

Actual inheritance should follow Arma requirements and may not map literally to this tree.

The purpose is to centralise:

- faction;
- side;
- editor category;
- identity settings;
- generic linked items;
- common event/config behaviour.

---

## 49. Randomisation Policy

Do not assume that every visual difference needs a separate editor class.

Where technically sensible, later consider controlled randomisation for:

- headwear;
- facewear;
- uniform texture;
- minor equipment variation.

However:

- weapon role must remain predictable;
- armour level should remain predictable enough for mission balance;
- ACE medical role must remain predictable;
- NVG capability should not unexpectedly appear across all units.

Randomisation must never obscure the role of the unit.

---

## 50. Loadout Determinism

Mission makers should be able to place:

```text
NTEF Machine Gunner
```

and reliably receive:

- a machine gun;
- appropriate ammunition;
- the expected capability tier.

Visual details may vary.

Functional role should not.

---

# PART XIV — FUTURE ASSET SELECTION GUIDE

## 51. Uniform Assets Required

When model work begins, seek enough assets to support:

### Tier 1

- 4+ strong regional/traditional base looks;
- civilian layering;
- muted colour variants.

### Tier 2

- 3+ regional/military mixed looks;
- surplus camouflage options;
- field jackets.

### Tier 3

- 2+ contemporary assault looks;
- darker coordinated options;
- plate-carrier-compatible silhouettes.

These numbers refer to **base looks**, not textures.

Retextures can provide much more variety.

---

## 52. Vest Assets Required

Target source pool:

### Simple rigs

At least:

- 2–3 distinct AK chest-rig silhouettes.

### Older webbing

At least:

- 1–2 suitable designs.

### Modern chest rigs

At least:

- 2 designs.

### Plate carriers

At least:

- 2 visually distinct designs.

This is enough to create significant faction variety through combinations.

---

## 53. Headgear Assets Required

High priority.

Target:

- pakol/regional hat;
- wrapped scarf;
- head scarf;
- knit cap;
- civilian cap;
- older helmet;
- modern helmet;
- bare-head variants.

Headwear is likely to contribute more to NTEF's visual identity than adding additional rifle models.

---

# PART XV — DESIGN RED LINES

## 54. NTEF Must Not Become

### Generic Arma Insurgents

Avoid:

- one vest;
- one AK;
- one headscarf;
- identical units.

### Black-Clad Stereotype

Black is an accent/identity colour, not the universal uniform.

### Poorly Equipped Cannon Fodder

NTEF must contain enough modern capability to remain credible and dangerous.

### Western Special Forces in Local Clothing

Do not overuse:

- modern helmets;
- lasers;
- suppressors;
- premium optics;
- full plate carriers;
- NVGs.

### Conventional Army

No standardised full uniform across all troops.

No baseline armoured/mechanised fleet.

---

# PART XVI — CURRENT LOCKED DESIGN DECISIONS

## 55. Locked

- NTEF uses a five-layer capability model.
- Tier 2 Core Fighter is the normal combat baseline.
- Tier 1 remains a substantial visible part of the faction.
- Tier 3 Veteran personnel are a minority.
- AK-pattern rifles dominate all infantry tiers.
- PKM is the preferred recurring GPMG identity.
- RPG-7 is the baseline anti-armour identity.
- Western rifles are minority/captured equipment.
- Body armour prevalence increases by tier.
- Helmets remain less common than non-helmet headwear.
- Radios are concentrated among leaders, veterans and specialists.
- NVGs are uncommon and concentrated in Tier 3.
- Thermal equipment is exceptional.
- Commercial observation drones are supported.
- Weaponised drones are not baseline faction classes.
- Civilian/light vehicles form the mobility backbone.
- Technicals provide the normal armed-vehicle identity.
- Heavy armour is not baseline.
- Dedicated suicide-bomber classes are excluded.
- Child-combatant classes are excluded.
- Exact editor groups are gameplay abstractions, not claimed real-world organisation.

---

# PART XVII — OPEN DECISIONS

## 56. To Resolve Before Config

- [ ] Final faction name: confirm `Northern Takistan Emirate Front`.
- [ ] Final internal faction ID: confirm `NTEF`.
- [ ] Confirm whether `Fighter` and `Rifleman` should both exist or whether editor naming can be simplified.
- [ ] Decide if Grenadier is required.
- [ ] Decide if Radio Operator is required once ACRE distribution is designed.
- [ ] Decide final ACE Medic capability.
- [ ] Decide final ACE Engineer capability.
- [ ] Select exact rifle classes.
- [ ] Select exact automatic rifle classes.
- [ ] Select exact PKM/PK-family classes.
- [ ] Select exact marksman weapons.
- [ ] Select exact launchers.
- [ ] Decide sidearm pool.
- [ ] Decide optic pool.
- [ ] Decide NVG models.
- [ ] Decide radio models.
- [ ] Decide commercial drone asset.
- [ ] Select civilian pickup family.
- [ ] Select technical family.
- [ ] Select SUV family.
- [ ] Select van family.
- [ ] Select truck family.
- [ ] Select motorcycle asset.
- [ ] Decide captured government vehicle pool.
- [ ] Establish actual uniform assets after source collection.
- [ ] Establish vest assets after source collection.
- [ ] Establish headgear assets after source collection.
- [ ] Decide whether visual randomisation is config-based or unit-variant-based.
- [ ] Lock class/editor naming standard.

---

# PART XVIII — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## United States National Counterterrorism Center / ODNI

**Counterterrorism Guide — ISIS-Khorasan**

Current public NCTC material identifies ISIS-K as a persistent ISIS branch with a transnational threat outlook.

Reference:

```text
https://www.dni.gov/nctc/terrorist_groups/isis_khorasan.html
```

The public profile was marked current to June 2026 when reviewed.

---

## Office of the Director of National Intelligence

**Annual Threat Assessment of the U.S. Intelligence Community — March 2026**

The 2026 assessment describes ISIS branches in South Asia as continuing efforts to rebuild and threaten interests beyond their immediate areas despite ISIS being weaker than at its territorial peak. It also highlights the continuing importance of information operations among terrorist actors.

Reference:

```text
https://www.dni.gov/files/ODNI/documents/assessments/ATA-2026-Unclassified-Report.pdf
```

---

## United Nations Security Council Monitoring Team

**S/2025/71/Rev.1**

The report states that Afghanistan remained the main hub for ISIL-K recruitment while the organisation maintained a wider regional presence.

Reference:

```text
https://digitallibrary.un.org/record/4076001/files/S_2025_71_Rev.1-EN.pdf
```

---

## United Nations — Threat Posed by ISIL/Da'esh

**Security Council briefing — 2026**

Current UN reporting continues to describe ISIL-K as one of the more capable ISIS affiliates and a serious threat in Afghanistan and beyond.

Reference:

```text
https://press.un.org/
```

Relevant 2026 Security Council coverage should be retained in the research archive if the project later creates a formal bibliography.

---

## United Nations Counter-Terrorism / Security Council

**Terrorist use of emerging technologies and unmanned systems — 2026**

UN material in 2026 describes increasing terrorist exploitation of commercially available unmanned systems and other emerging technologies.

This research is used only to justify the **limited commercial-drone capability** in the fictional NTEF design.

It is not used to reproduce real-world weaponisation methods or procedures.

References:

```text
https://www.un.org/counterterrorism/
https://press.un.org/
```

---

# PART XIX — CURRENT CONCLUSION

NTEF should be configured as a force with a **broad low-to-mid capability base and a narrow modern upper tier**.

A representative visual encounter should communicate:

```text
LOCAL / REGIONAL
        +
ORGANISATIONAL IDENTITY
        +
MIXED SURPLUS EQUIPMENT
        +
LIMITED MODERN CAPABILITY
```

not:

```text
POORLY EQUIPPED MOB
```

and not:

```text
UNIFORMED SPECIAL OPERATIONS FORCE
```

The faction is now defined sufficiently at the role/equipment level that future physical assets can be judged against a stable requirement rather than driving the faction design themselves.

The next useful admin/research task is to lock the **project-wide class and editor naming standard** before any `config.cpp` is created.
