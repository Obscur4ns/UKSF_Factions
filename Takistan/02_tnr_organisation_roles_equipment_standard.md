# UKSF_Factions — TNR Organisation, Roles & Equipment Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** TNR Organisation, Roles & Equipment Standard  
**Status:** Research / Design Standard  
**Created:** 2026-08-09  
**Faction:** Takistani National Resistance (`TNR`)  
**Native project name:** `د تکستان ملي مقاومت`  
**Operational romanisation:** `Da Takistan Milli Muqawamat`  
**Faction type:** `INSURGENT / NATIONALIST / LOCAL`  
**Default side:** INDEPENDENT / GUER  
**Time period:** Contemporary / approximately 2026  

---

## 1. Purpose

This document defines the practical Arma organisation, role catalogue and equipment distribution for the **Takistani National Resistance**.

It converts the faction research brief into:

- capability tiers;
- unit roles;
- editor-visible classes;
- weapon distribution;
- armour prevalence;
- helmet prevalence;
- radio distribution;
- night capability;
- medical capability;
- technical variants;
- vehicle distribution;
- group templates;
- visual differentiation rules;
- first-release scope;
- future asset requirements.

The central implementation goal is:

> **TNR should feel like a persistent, locally rooted resistance movement with uneven but coherent capability.**

It must not feel like:

- NTEF with different insignia;
- TNA with worse equipment;
- random civilian units with guns.

---

# PART I — ORGANISATIONAL PHILOSOPHY

## 2. Structure

TNR should be represented as a loose resistance network rather than a conventional military hierarchy.

Recommended gameplay layers:

```text
TIER 1 — LOCAL FIGHTER
TIER 2 — CORE RESISTANCE FIGHTER
TIER 3 — VETERAN
TIER 4 — SPECIALIST / COMMAND
```

These are project design categories only.

They are not claimed as an in-universe formal rank system.

---

## 3. Distinction from NTEF

TNR and NTEF may use many of the same weapon families.

Faction differentiation comes from:

- clothing;
- headwear;
- national symbolism;
- armour prevalence;
- face-covering prevalence;
- equipment quality;
- group composition;
- vehicle presentation;
- political context.

TNR should generally appear:

```text
more locally embedded
less austere
less masked
less ideologically uniform
more openly Takistani
```

than NTEF.

---

# PART II — TIER 1: LOCAL FIGHTER

## 4. Role

Tier 1 represents community-linked armed members who are not full-time or highly equipped fighters.

Typical characteristics:

- local clothing;
- basic rifle;
- little armour;
- little specialist equipment;
- limited communications.

This tier should remain **visibly common**.

---

## 5. Clothing

Typical:

- civilian/regional clothing;
- old military jacket;
- workwear;
- traditional clothing;
- mixed footwear.

Camouflage may appear but should not dominate.

---

## 6. Armour

| Equipment | Frequency |
|---|---|
| No armour | `COMMON` |
| Chest rig / webbing | `COMMON` |
| Ballistic vest | `RARE` |
| Plate carrier | `EXCEPTIONAL` |

---

## 7. Headgear

Typical:

- pakol-style hat;
- scarf;
- knit cap;
- bare head;
- simple patrol cap.

Helmet:

`RARE`

Face covering:

`RARE`

---

## 8. Weapons

Primary families:

- AKM;
- AK-74;
- older AK;
- rare FAL.

Optic:

`EXCEPTIONAL`

Sidearm:

`NONE`

---

## 9. Communications

Individual radio:

`RARE`

Leader access:

`OCCASIONAL`

---

## 10. Night Capability

NVG:

`EXCEPTIONAL`

Thermal:

`NONE`

---

# PART III — TIER 2: CORE RESISTANCE FIGHTER

## 11. Role

Tier 2 is the normal active TNR combat baseline.

It should make up the majority of organised TNR combat groups.

Typical:

- AK-family rifle;
- chest rig;
- more consistent combat equipment;
- occasional ballistic armour;
- clearer group leadership;
- technical support.

---

## 12. Clothing

Mix:

- regional clothing;
- surplus military uniform pieces;
- old camouflage;
- civilian trousers/jackets;
- faction/national patch where appropriate.

The silhouette remains irregular.

---

## 13. Armour

| Equipment | Frequency |
|---|---|
| No armour | `OCCASIONAL` |
| Chest rig / webbing | `COMMON` |
| Ballistic vest | `OCCASIONAL` |
| Plate carrier | `RARE` |

---

## 14. Headgear

Soft/regional headwear:

`COMMON`

Helmet:

`OCCASIONAL`

Face covering:

`OCCASIONAL`

---

## 15. Weapons

AK-family:

`UBIQUITOUS`

Optics:

`RARE` to `OCCASIONAL`

Automatic weapons:

normal in role-specific classes.

---

## 16. Communications

Leader radio:

`COMMON`

Individual radio:

`RARE`

---

## 17. Night Capability

NVG:

`RARE`

Thermal:

`EXCEPTIONAL`

---

# PART IV — TIER 3: VETERAN

## 18. Role

Veterans represent experienced fighters, former security personnel, former militia commanders and long-serving resistance members.

They should be:

- better equipped;
- more likely to carry armour;
- more likely to have optics;
- more likely to carry radios;
- less visually uniform than TNA.

---

## 19. Armour

| Equipment | Frequency |
|---|---|
| Chest rig | `COMMON` |
| Ballistic vest | `COMMON` |
| Plate carrier | `OCCASIONAL` |
| No armour | `RARE` |

---

## 20. Helmets

Helmet:

`OCCASIONAL`

Soft headwear:

`COMMON`

Face covering:

`OCCASIONAL`

---

## 21. Weapons

Potential:

- AK-74;
- AK-103 / modern AK;
- AKM;
- captured TNA rifle;
- rare Western rifle.

Optic:

`COMMON`

Weapon light:

`RARE`

Suppressor:

`EXCEPTIONAL`

---

## 22. Communications

Personal/team radio:

`OCCASIONAL`

Leader radio:

`UBIQUITOUS`

---

## 23. Night Capability

NVG:

`OCCASIONAL`

Thermal:

`EXCEPTIONAL`

---

# PART V — TIER 4: SPECIALIST / COMMAND

## 24. Scope

Tier 4 is not an elite combat tier.

It covers role-specific personnel such as:

- marksman;
- medic;
- technical gunner;
- drone operator;
- local commander;
- senior commander.

Their equipment depends on role rather than a universal high-end standard.

---

# PART VI — CORE UNIT ROLES

## 25. Fighter

Working token:

```text
Fighter
```

Tier:

1 / 2

Standard irregular combatant.

---

## 26. Fighter (Light)

Working token:

```text
FighterLight
```

Tier:

1

Purpose:

- lightly equipped local member;
- security/dismount role;
- common low-tier unit.

---

## 27. Veteran Fighter

Working token:

```text
FighterVeteran
```

Tier:

3

Purpose:

- experienced fighter;
- better armour/optic;
- stronger group member.

---

## 28. Team Leader

Working token:

```text
TeamLeader
```

Tier:

2 / 3

Typical:

- radio;
- binoculars;
- optic optional;
- better chest rig/armour.

---

## 29. Local Commander

Working token:

```text
LocalCommander
```

Tier:

4

Purpose:

- group/cell commander;
- local political/military figure;
- motorised group leader.

Visual:

- distinctive but not luxurious;
- sidearm optional;
- radio common;
- optic common.

---

## 30. Senior Commander

Working token:

```text
SeniorCommander
```

Status:

`OPTIONAL`

Use only if editor/lore requires a higher-level leader distinct from Local Commander.

---

# PART VII — SUPPORT WEAPONS

## 31. Automatic Rifleman

Working token:

```text
AutomaticRifleman
```

Primary:

- RPK;
- RPD if suitable.

Tier:

2 / 3

---

## 32. Machine Gunner

Working token:

```text
MachineGunner
```

Primary:

```text
PKM
```

Tier:

2 / 3

---

## 33. Assistant Machine Gunner

Working token:

```text
AssistantMG
```

Carries:

- rifle;
- additional ammunition.

---

## 34. Marksman

Working token:

```text
Marksman
```

Primary:

```text
SVD
```

Potential veteran alternative:

- improved SVD;
- captured precision rifle.

---

## 35. Anti-Armour

Working token:

```text
AT
```

Primary:

```text
RPG-7
```

This should remain the normal TNR anti-armour identity.

---

## 36. Assistant AT

Working token:

```text
AssistantAT
```

Status:

`OPTIONAL`

Create only if ammunition/loadout design makes the role useful.

---

# PART VIII — MEDICAL / SPECIALIST ROLES

## 37. Field Medic

Working token:

```text
Medic
```

Visual:

- ordinary TNR fighter;
- medical bag/pouches;
- faction-neutral medical marker if desired.

Should not look like a formal TNA medic.

---

## 38. Engineer

Working token:

```text
Engineer
```

Status:

`OPTIONAL / LIKELY`

Purpose:

- repair;
- toolkit;
- ACE engineering role.

Do not define complex real-world explosive procedures.

---

## 39. Drone Operator

Working token:

```text
DroneOperator
```

Status:

`OPTIONAL / LOW FREQUENCY`

Commercial observation-UAS specialist.

---

## 40. Driver

Working token:

```text
Driver
```

Useful for:

- pickup;
- SUV;
- truck;
- technical.

---

## 41. Technical Gunner

Working token:

```text
TechnicalGunner
```

Useful if dedicated crew improves vehicle composition.

---

# PART IX — WEAPON DISTRIBUTION

## 42. Core Rifle Philosophy

TNR should predominantly use:

```text
AKM
AK-74
older AK variants
```

Modern AKs exist but do not dominate.

---

## 43. Tier 1 Rifle Distribution

**UKSF project design targets**

| Family | Share |
|---|---:|
| AKM / older AK | 55% |
| AK-74 family | 30% |
| FAL / old Western rifle | 8% |
| modern AK | 5% |
| other | 2% |

---

## 44. Tier 2 Rifle Distribution

| Family | Share |
|---|---:|
| AKM family | 40% |
| AK-74 family | 40% |
| modern AK | 12% |
| FAL / legacy Western | 5% |
| captured/other | 3% |

---

## 45. Tier 3 Rifle Distribution

| Family | Share |
|---|---:|
| AK-74 family | 35% |
| modern AK | 30% |
| AKM family | 25% |
| Western/captured | 7% |
| other | 3% |

---

## 46. Western Rifles

Frequency:

`RARE`

Possible:

- M16;
- M4-type carbine;
- other donor/captured weapon.

These should be status-signalling exceptions.

---

# PART X — OPTICS

## 47. Tier 1

Optic:

`EXCEPTIONAL`

---

## 48. Tier 2

Optic:

`RARE`

---

## 49. Tier 3

Optic:

`COMMON`

---

## 50. Leaders / Marksmen

Optic:

`COMMON` to `UBIQUITOUS`

---

# PART XI — SIDEARMS

## 51. Fighters

Usually:

`NONE`

---

## 52. Leaders

Sidearm:

`OCCASIONAL`

---

## 53. Commanders

Sidearm:

`COMMON`

---

# PART XII — RADIOS

## 54. Tier 1

Individual radio:

`RARE`

---

## 55. Tier 2

Leader radio:

`COMMON`

Individual radio:

`RARE`

---

## 56. Tier 3

Leader radio:

`UBIQUITOUS`

Individual radio:

`OCCASIONAL`

---

## 57. Command / Specialist

Radio:

`COMMON` to `UBIQUITOUS`

---

# PART XIII — NIGHT EQUIPMENT

## 58. Tier 1

NVG:

`EXCEPTIONAL`

---

## 59. Tier 2

NVG:

`RARE`

---

## 60. Tier 3

NVG:

`OCCASIONAL`

---

## 61. Command / Specialist

NVG:

`OCCASIONAL`

---

## 62. Thermal

Faction-wide:

`EXCEPTIONAL`

Should appear only in unusual captured/specialist cases.

---

# PART XIV — CLOTHING DISTRIBUTION

## 63. Tier 1

Primary:

- regional civilian clothing;
- traditional clothing;
- workwear.

Military uniform pieces:

`OCCASIONAL`

---

## 64. Tier 2

Mix:

- civilian/regional;
- surplus camouflage;
- mixed military clothing.

No one uniform should dominate completely.

---

## 65. Tier 3

Increase:

- surplus military clothing;
- old TNA pieces;
- higher-quality footwear;
- tactical outerwear.

Still avoid full TNA uniform sets.

---

# PART XV — HEADWEAR DISTRIBUTION

## 66. Tier 1

Dominant:

- pakol;
- scarf;
- knit cap;
- bare head.

Helmet:

`RARE`

---

## 67. Tier 2

Soft/regional headwear:

`COMMON`

Helmet:

`OCCASIONAL`

---

## 68. Tier 3

Helmet:

`OCCASIONAL`

Soft headwear remains common.

---

# PART XVI — FACE COVERINGS

## 69. Baseline

Face covering:

`OCCASIONAL`

TNR should show more visible faces than NTEF.

---

## 70. High-Threat / Veteran

Face covering may increase but should never become universal faction identity.

---

# PART XVII — BODY ARMOUR

## 71. Tier 1

Plate carrier:

`EXCEPTIONAL`

Ballistic vest:

`RARE`

---

## 72. Tier 2

Ballistic vest:

`OCCASIONAL`

Plate carrier:

`RARE`

---

## 73. Tier 3

Ballistic vest:

`COMMON`

Plate carrier:

`OCCASIONAL`

---

# PART XVIII — MEDICAL STANDARD

## 74. Ordinary Fighter

Individual medical supplies:

`BASIC`

---

## 75. Field Medic

Dedicated medical backpack/pouches.

ACE medical class:

likely.

Exact item quantities deferred.

---

# PART XIX — DRONE CAPABILITY

## 76. Commercial Observation Drone

Status:

`RARE`

Use:

- observation;
- reconnaissance.

---

## 77. Weaponised Drones

Status:

`NOT BASELINE`

Do not create default TNR weaponised-UAS classes.

---

# PART XX — VEHICLE PHILOSOPHY

## 78. Mobility Backbone

TNR should rely on:

```text
civilian pickups
SUVs
vans
light trucks
motorcycles
```

---

## 79. Vehicle Condition

Mix:

- worn;
- repaired;
- civilian paint;
- improvised faction markings;
- old government paint on captured assets.

---

# PART XXI — PICKUPS

## 80. Clean Pickup

Purpose:

- transport;
- civilian-looking movement;
- cargo.

---

## 81. Worn Pickup

Purpose:

- rural cells;
- logistical use;
- general resistance identity.

---

## 82. Technical — Light MG

Status:

`CORE`

Potential:

- RPK/PKM-class or mounted light/heavy MG depending asset.

---

## 83. Technical — Heavy MG

Status:

`CORE / LESS COMMON`

Useful as the faction's heavier mobile fire-support identity.

---

# PART XXII — SUVs / VANS / TRUCKS

## 84. SUV

Use:

- commander;
- transport;
- liaison.

---

## 85. Van

Use:

- personnel;
- logistics;
- civilian cover.

---

## 86. Light Truck

Use:

- supply;
- motorised group;
- rural transport.

---

# PART XXIII — MOTORCYCLES

## 87. Status

`OPTIONAL`

Use only if a technically good shared asset exists.

---

# PART XXIV — ARMOURED VEHICLES

## 88. BRDM-Type Vehicle

Status:

`RARE / SUPPORTED`

Potential:

- captured;
- inherited;
- local warlord asset.

---

## 89. Other Armoured Vehicles

BMP/APC:

`MISSION-SPECIFIC`

Tank:

`NOT BASELINE`

Do not create standard TNR armoured groups.

---

# PART XXV — VEHICLE MARKINGS

## 90. Philosophy

TNR vehicle markings should remain inconsistent.

Possible:

- national flag;
- local emblem;
- small TNR mark;
- no marking.

Avoid uniform military numbering across the whole faction.

---

# PART XXVI — NATIONAL SYMBOLISM

## 91. National Flag

TNR may display the Takistani flag.

Frequency:

`OCCASIONAL`

Do not put it on every fighter.

---

## 92. TNR Patch

TNR-specific patch/emblem:

`SUPPORTED`

Likely more common among organised Tier 2/3 groups.

---

## 93. Royalist Symbolism

Possible in subgroups.

Not faction-wide.

---

# PART XXVII — GROUP DESIGN PRINCIPLES

## 94. Group Size

TNR groups should feel smaller and looser than TNA sections.

Typical:

```text
4–8 personnel
```

depending on group.

---

## 95. Group Balance

Most groups should contain:

- one leader;
- several riflemen;
- one support role.

Do not place:

```text
MG + marksman + AT + medic + drone
```

inside every small cell.

---

# PART XXVIII — GROUP CATALOGUE

## 96. Local Fighter Cell

Suggested:

```text
Local Commander / Team Leader
3–5 Fighters
```

Low-tier, lightly equipped.

---

## 97. Resistance Cell

Suggested:

```text
Team Leader
2–3 Fighters
Automatic Rifleman
```

Core combat group.

---

## 98. Weapons Cell

Suggested:

```text
Team Leader
Machine Gunner
Assistant MG
Anti-Armour
1–2 Fighters
```

---

## 99. Veteran Cell

Suggested:

```text
Veteran Team Leader
3–4 Veteran Fighters
Marksman / Automatic Rifleman
```

---

## 100. Technical Patrol

Suggested:

```text
Technical
Driver
Gunner
2–4 Fighters
```

---

## 101. Motorised Cell

Suggested:

```text
Pickup / SUV / truck
Team Leader
4–6 Fighters
```

---

## 102. Commander Security Detail

Suggested:

```text
Local Commander
2–4 Veteran Fighters
SUV / pickup optional
```

---

## 103. Drone Team

Status:

`OPTIONAL`

Suggested:

```text
Drone Operator
1–2 Fighters
```

---

# PART XXIX — EDITOR UNIT CATALOGUE

## 104. First Release

Recommended visible classes:

```text
Fighter
Fighter (Light)
Veteran Fighter
Team Leader
Local Commander
Automatic Rifleman
Machine Gunner
Assistant Machine Gunner
Marksman
Anti-Armour
Field Medic
Driver
Technical Gunner
```

---

## 105. Optional / Deferred

```text
Senior Commander
Engineer
Drone Operator
Assistant AT
```

Only add if useful.

---

# PART XXX — EDITOR SUBCATEGORIES

## 106. Recommended

```text
Men
Cars
Technicals
```

Potential later:

```text
Captured Vehicles
```

---

# PART XXXI — CLASS NAMING

## 107. Pattern

```text
UKSF_Factions_TNR_<Role>
```

Examples:

```cpp
UKSF_Factions_TNR_Fighter
UKSF_Factions_TNR_FighterLight
UKSF_Factions_TNR_FighterVeteran
UKSF_Factions_TNR_TeamLeader
UKSF_Factions_TNR_LocalCommander
UKSF_Factions_TNR_AutomaticRifleman
UKSF_Factions_TNR_MachineGunner
UKSF_Factions_TNR_AssistantMG
UKSF_Factions_TNR_Marksman
UKSF_Factions_TNR_AT
UKSF_Factions_TNR_Medic
UKSF_Factions_TNR_Driver
UKSF_Factions_TNR_TechnicalGunner
```

Potential:

```cpp
UKSF_Factions_TNR_Engineer
UKSF_Factions_TNR_DroneOperator
UKSF_Factions_TNR_SeniorCommander
```

---

# PART XXXII — CAPABILITY DISTRIBUTION

## 108. Suggested Overall Mix

Mission-authoring target:

| Tier | Design share |
|---|---:|
| Tier 1 Local | 30% |
| Tier 2 Core | 50% |
| Tier 3 Veteran | 15% |
| Tier 4 Specialist / Command | 5% |

These are project targets only.

---

# PART XXXIII — FIGHTER APPEARANCE MIX

## 109. Headwear

Overall target:

| Category | Approx. design share |
|---|---:|
| Regional/soft headwear | 55% |
| Bare head | 15% |
| Helmet | 20% |
| Other | 10% |

---

## 110. Armour

Overall target:

| Category | Approx. design share |
|---|---:|
| No ballistic armour | 45% |
| Basic ballistic vest | 25% |
| Plate carrier | 10% |
| Chest rig/webbing only | 20% |

These are visual authoring targets, not statistical claims.

---

# PART XXXIV — WEAPON MIX SUMMARY

## 111. Faction-Wide Rifle Character

Overall:

```text
AKM + AK-74
```

should remain the dominant visual identity.

Modern AK:

minority.

FAL:

rare historical flavour.

Western rifles:

rare captured/status equipment.

---

# PART XXXV — DIFFERENTIATION FROM NTEF

## 112. Visual

TNR:

- more colour;
- more visible faces;
- more national/local symbols;
- more old military surplus;
- fewer all-black combinations.

NTEF:

- darker/austere palette;
- more face coverings;
- more ideologically coherent appearance.

---

## 113. Equipment

TNR:

- more legacy/local;
- fewer specialist optics;
- fewer modern helmets;
- lower overall night capability.

NTEF:

- similar common weapons;
- more deliberate tiered extremist specialist capability.

---

## 114. Vehicles

Both may use pickups/technicals.

TNR can show:

- national flags;
- local commander vehicles;
- old government/captured markings.

NTEF uses its own faction-specific markings and more austere identity.

---

# PART XXXVI — DIFFERENTIATION FROM TNA

## 115. Clothing

TNA:

- standard camouflage;
- institutional markings;
- more helmets/armour.

TNR:

- irregular clothing;
- mixed surplus;
- traditional headwear.

---

## 116. Equipment

TNA:

- radios more common;
- optics more common;
- armour more common;
- vehicles more standardised.

TNR:

- variable quality;
- lighter logistics;
- more civilian-derived mobility.

---

# PART XXXVII — POLITICAL GAMEPLAY IMPLICATIONS

## 117. No Dedicated "Friendly TNR" Classes

Do not create separate BLUFOR TNR unit copies.

Faction relationships should be controlled at mission level.

---

## 118. Negotiation / Ceasefire

TNR's faction design should remain compatible with scenarios where:

- TNR is temporarily friendly;
- TNR remains neutral;
- TNR cooperates only against NTEF.

No config duplication is required.

---

# PART XXXVIII — CIVILIAN PROXIMITY

## 119. Visual Ambiguity

TNR's locally rooted design means some fighters may resemble civilians at a glance.

Mission makers must use this carefully.

The faction itself should still provide enough cues through:

- weapon carrying;
- chest rigs;
- patches;
- group behaviour;
- vehicles.

Do not deliberately design indistinguishable civilian-combatant models as a gameplay gimmick.

---

# PART XXXIX — EXPLOSIVE VEST POLICY

## 120. Baseline

No dedicated explosive-vest TNR unit.

---

## 121. Generic Mission Asset

The project's generic ACE explosive vest remains usable manually if a mission requires it.

It does not become TNR's identity.

---

# PART XL — DEPENDENCY / ASSET POLICY

## 122. Character Reuse

TNR should heavily reuse:

```text
uksf_factions_characters
```

Neutral assets:

- regional clothing;
- chest rigs;
- headwear;
- scarves;
- backpacks.

---

## 123. Vehicle Reuse

Use:

```text
uksf_factions_vehicles
```

for generic:

- pickups;
- SUVs;
- vans;
- trucks.

Faction PBO owns:

- TNR markings;
- armed variants where faction-specific;
- faction unit config.

---

# PART XLI — PERFORMANCE

## 124. High-Instance Assets

Most important to optimise:

- common regional clothing;
- pakol/headwear;
- AK rifles;
- chest rigs;
- pickups.

These will appear repeatedly.

---

# PART XLII — FIRST RELEASE SCOPE

## 125. Infantry

Must include:

```text
Fighter
Fighter (Light)
Veteran Fighter
Team Leader
Local Commander
Automatic Rifleman
Machine Gunner
Assistant MG
Marksman
Anti-Armour
Field Medic
Driver
Technical Gunner
```

---

## 126. Vehicles

Must include at least:

```text
Pickup
SUV
Light Technical
Heavy Technical
Motorised Transport
```

Optional:

```text
BRDM-type captured vehicle
Van
Motorcycle
```

---

## 127. Groups

Must include:

```text
Local Fighter Cell
Resistance Cell
Weapons Cell
Veteran Cell
Technical Patrol
Motorised Cell
Commander Security Detail
```

---

# PART XLIII — LOCKED DECISIONS

## 128. Locked

- TNR uses four gameplay capability layers.
- Tier 2 Core Resistance Fighter is the normal combat baseline.
- Tier 1 Local Fighters remain visibly common.
- Tier 3 Veterans are a minority.
- Tier 4 is specialist/command, not an elite universal gear tier.
- TNR remains INDEPENDENT/GUER.
- TNR is locally rooted and politically distinct from NTEF.
- AKM and AK-74 are the dominant rifle families.
- Modern AKs are a minority.
- FN FAL is rare legacy equipment.
- Western rifles are rare captured/status equipment.
- PKM is the core GPMG.
- RPK/RPD-type weapon is appropriate for automatic-rifle role.
- SVD is the core marksman family.
- RPG-7 is the baseline anti-armour weapon.
- Guided AT is exceptional and mission-specific.
- Body armour is limited overall.
- Helmets are uncommon overall.
- Regional/soft headwear is dominant.
- Face coverings are occasional and less common than NTEF.
- Individual radios are uncommon outside leaders/veterans.
- NVGs are rare overall.
- Thermal equipment is exceptional.
- Commercial observation drones are rare.
- Civilian pickups/SUVs/vans/trucks form the mobility backbone.
- Light and heavy technicals are core vehicle variants.
- BRDM-type vehicles are rare/captured, not normal mechanised force structure.
- TNR does not field tanks or baseline mechanised formations.
- Takistani national symbolism may appear.
- Royalist symbolism remains subgroup-specific.
- No dedicated explosive-vest class belongs in baseline TNR.
- TNR group sizes are generally 4–8 fighters.
- Do not duplicate every role across every capability tier.
- No separate BLUFOR-friendly TNR faction copy should be created.

---

# PART XLIV — OPEN DECISIONS

## 129. Before Config

- [ ] Select exact common regional clothing family.
- [ ] Select exact pakol/headwear assets.
- [ ] Select common chest rigs.
- [ ] Select ballistic vest candidates.
- [ ] Select captured/legacy helmet candidates.
- [ ] Lock AKM source classes.
- [ ] Lock AK-74 source classes.
- [ ] Lock modern AK source classes.
- [ ] Decide FAL source.
- [ ] Lock PKM source.
- [ ] Select RPK/RPD option.
- [ ] Lock SVD source.
- [ ] Lock RPG-7 source.
- [ ] Select handgun options for leaders.
- [ ] Select radio family.
- [ ] Select NVG options.
- [ ] Select commercial drone if used.
- [ ] Select pickup family.
- [ ] Select SUV family.
- [ ] Select van/truck family.
- [ ] Define light/heavy technical armament.
- [ ] Decide BRDM inclusion in initial release.
- [ ] Design TNR emblem.
- [ ] Decide national flag patch frequency.
- [ ] Create TNR asset/dependency audit after source asset review.

---

# PART XLV — CURRENT CONCLUSION

TNR should occupy the middle of the North Takistan conflict spectrum:

```text
TNA
standardised state military

        ↕

TNR
local / irregular / nationalist resistance

        ↕

NTEF
hardline transnational extremist movement
```

Its combat identity is:

```text
AKM / AK-74
+
PKM / RPG-7
+
regional clothing
+
soft headwear
+
limited armour
+
light civilian mobility
+
local / national symbolism
```

The faction should be immediately recognisable as a **Takistani resistance movement**, not as a generic insurgent pack.

The next logical production step is an **asset/dependency audit for TNR**, but that should wait until the available regional clothing, vest, vehicle and weapon source pool is physically reviewed.
