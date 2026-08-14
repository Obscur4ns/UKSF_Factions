# UKSF_Factions — TNP Organisation, Roles & Equipment Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** TNP Organisation, Roles & Equipment Standard  
**Status:** Research / Design Standard  
**Created:** 2026-08-09  
**Faction:** Takistani National Police (`TNP`)  
**Faction type:** `SECURITY / LAW ENFORCEMENT`  
**Default side:** BLUFOR / WEST  
**Time period:** Contemporary / approximately 2026  

---

## 1. Purpose

This document defines the contemporary **Takistani National Police** as an Arma faction and establishes the boundary between:

- ordinary policing;
- rural/high-threat policing;
- gendarmerie-style security;
- border security;
- military activity.

The central design rule is:

> **TNP is a police service first.**

The faction must not become a second Takistani National Army wearing blue uniforms.

---

# PART I — DESIGN BASIS

## 2. Post-Conflict Police Role

The 2026 Takistani state requires visible civilian law-enforcement institutions in:

- Rasman;
- Bastam;
- other towns;
- local police stations;
- road checkpoints;
- government facilities;
- markets and transport areas.

Police are one of the most important visual signals that the government still functions outside military bases.

---

## 3. Real-World Reference Principle

NATO's historical police-development work is used only as a structural reference.

Relevant lessons include:

- police and army development should remain institutionally distinct;
- policing requires specialist training and a civilian-oriented mindset;
- gendarmerie-type forces can bridge the capability gap between ordinary police and military forces;
- excessive militarisation can undermine the normal policing role.

These principles support a layered Takistani police service.

---

# PART II — ORGANISATIONAL MODEL

## 4. TNP Capability Layers

For `UKSF_Factions`, TNP is divided into three practical layers.

### Layer A — Local / Urban Police

Routine law enforcement and government presence.

### Layer B — High-Threat / Rural Police

Police operating in insecure areas with greater protection and long arms.

### Layer C — Gendarmerie

Paramilitary police for situations beyond normal policing but below routine Army employment.

These are project implementation categories, not claimed canonical Takistani structures.

---

# PART III — LAYER A: LOCAL / URBAN POLICE

## 5. Role

Local/Urban Police should dominate ordinary towns and cities.

Typical mission presence:

- police stations;
- vehicle patrols;
- traffic/security points;
- government buildings;
- markets;
- public events;
- crime scenes;
- civilian interaction.

---

## 6. Visual Identity

Typical:

- dark blue, slate or grey police uniform;
- soft cap common;
- police badge/patch;
- light load-bearing equipment;
- pistol;
- occasional rifle stored/carried in higher-risk environments;
- marked police vehicle.

This layer should immediately read as **police**, not infantry.

---

## 7. Body Armour

Routine duty:

| Equipment | Frequency |
|---|---|
| No overt body armour | `COMMON` |
| Concealable/light armour | `OCCASIONAL` |
| Tactical vest | `RARE` |

High-alert urban duty may increase armour.

---

## 8. Headgear

Soft cap:

`COMMON`

Bare head:

`OCCASIONAL`

Ballistic helmet:

`RARE`

Helmet use should rise during planned high-risk activity.

---

# PART IV — LAYER B: HIGH-THREAT / RURAL POLICE

## 9. Role

Represents police serving in areas where insurgent or criminal violence creates a genuine armed threat.

Typical:

- North Takistan rural stations;
- reinforced checkpoints;
- remote-road patrols;
- government-facility security;
- escort duties;
- police response in contested districts.

---

## 10. Visual Identity

Compared with urban police:

Increase:

- body armour;
- helmets;
- AK-family rifles;
- radios;
- utility vehicles;
- medical equipment.

Retain:

- police colour/patches;
- police vehicle markings;
- clear law-enforcement identity.

---

## 11. Body Armour

Ballistic vest:

`COMMON`

Plate carrier:

`OCCASIONAL`

No armour:

`OCCASIONAL`

---

## 12. Helmets

Composite helmet:

`OCCASIONAL`

Soft cap:

`COMMON`

Older ballistic helmet:

`OCCASIONAL`

---

# PART V — LAYER C: GENDARMERIE

## 13. Working Name

English:

```text
Takistani National Gendarmerie
```

Working acronym:

```text
TNG
```

Status:

`TNP SUBCOMPONENT`

Do not create a separate `CfgFactionClasses` faction initially.

---

## 14. Role

Gendarmerie bridges the gap between routine police work and Army intervention.

Potential responsibilities:

- high-threat public security;
- reinforcement of police stations;
- protection of strategic government sites;
- major checkpoint operations;
- response to armed criminal groups;
- security during periods of serious unrest;
- selected counter-insurgency support.

It remains a **police/security service**, not manoeuvre infantry.

---

## 15. Visual Identity

Typical:

- darker tactical police uniform or standard TNP uniform;
- plate carrier;
- composite helmet;
- police/gendarmerie identifiers;
- rifle;
- team radio;
- protected pickup/SUV;
- occasional light armoured vehicle.

---

## 16. Equipment

Body armour:

`UBIQUITOUS`

Helmet during operational deployment:

`COMMON`

Rifle:

`UBIQUITOUS`

Optic:

`COMMON`

Radio:

`COMMON`

NVG:

`RARE` to `OCCASIONAL`

Thermal:

`EXCEPTIONAL`

---

# PART VI — CORE TNP ROLES

## 17. Police Officer

Working token:

```text
Officer
```

Primary ordinary police class.

Typical:

- police uniform;
- soft cap;
- pistol;
- radio;
- light equipment.

---

## 18. Armed Police Officer

Working token:

```text
ArmedOfficer
```

Typical:

- police uniform;
- AK-family rifle;
- pistol optional;
- basic ballistic vest.

Useful for North Takistan without making every police officer rifle-equipped.

---

## 19. Senior Police Officer

Working token:

```text
SeniorOfficer
```

Purpose:

- station commander;
- patrol supervisor;
- government-building supervisor.

Typical:

- radio;
- pistol;
- distinctive rank/insignia;
- rifle optional depending scenario.

---

## 20. Police Patrol Leader

Working token:

```text
PatrolLeader
```

High-threat/rural role.

Typical:

- rifle;
- radio;
- armour;
- binoculars optional.

---

## 21. Police Rifleman

Working token:

```text
Rifleman
```

Status:

`HIGH-THREAT SUBCATEGORY ONLY`

Do not make this the base identity of TNP.

---

## 22. Police Medic

Working token:

```text
Medic
```

Status:

`OPTIONAL`

Could represent trained tactical/high-threat police medical support.

Ordinary police do not need a dedicated medic class if mission design does not benefit from it.

---

## 23. Police Driver

Working token:

```text
Driver
```

Optional if dedicated crew class becomes useful.

---

# PART VII — GENDARMERIE ROLES

## 24. Gendarmerie Officer

Baseline tactical member.

---

## 25. Gendarmerie Team Leader

- radio;
- optic;
- improved armour;
- sidearm.

---

## 26. Gendarmerie Machine Gunner

Status:

`LIMITED`

Potential light/medium machine gun.

Do not make PKM teams routine urban-police equipment.

---

## 27. Gendarmerie Marksman

Status:

`OPTIONAL`

Only if mission demand justifies it.

---

## 28. Gendarmerie Breacher / Engineer

Status:

`OPTIONAL`

May be useful for ACE interaction/engineering capability.

Keep implementation abstract and game-oriented.

---

## 29. Gendarmerie Medic

Useful high-threat role.

---

# PART VIII — WEAPONS

## 30. Sidearm Identity

Ordinary uniformed police should primarily carry a handgun.

Exact model:

`TBD`

Prefer a broadly plausible service pistol already present in the project/modset.

Do not create a unique pistol dependency just for TNP.

---

## 31. Rifle Identity

High-threat police:

```text
AKM
AK-74
modern AK
```

Primary rifle family should remain compatible with the country's broader logistics.

---

## 32. Western Carbines

Possible in:

- specialist police;
- donor-trained units;
- selected gendarmerie.

Frequency:

`RARE` to `OCCASIONAL`

Do not make TNP an M4-based force by default.

---

## 33. Shotguns

Useful potential police asset.

Status:

`OPTIONAL`

Good for visual differentiation if a suitable existing weapon is already available.

---

## 34. SMGs

Status:

`OPTIONAL / LOW PRIORITY`

Do not add a dedicated SMG family merely because police are stereotypically associated with one.

---

# PART IX — SUPPORT WEAPONS

## 35. Machine Guns

Ordinary TNP:

`NONE`

High-threat police:

`RARE`

Gendarmerie:

`OCCASIONAL`

Potential family:

```text
PKM or lighter squad automatic weapon
```

---

## 36. Anti-Armour

Ordinary TNP:

`NONE`

High-threat police:

`NONE`

Gendarmerie:

`EXCEPTIONAL / MISSION-SPECIFIC`

The Army handles military anti-armour threats.

---

## 37. Grenade Launchers

Gendarmerie:

`RARE`

Ordinary police:

`NONE`

---

# PART X — OPTICS & ACCESSORIES

## 38. Ordinary Police

Optics:

`NONE`

Weapon light on pistol/rifle:

`OCCASIONAL`

Radio:

`COMMON`

---

## 39. High-Threat Police

Optics:

`OCCASIONAL`

Weapon light:

`OCCASIONAL`

Radio:

`COMMON`

---

## 40. Gendarmerie

Optics:

`COMMON`

Weapon light:

`COMMON`

Laser:

`RARE`

Suppressor:

`EXCEPTIONAL`

---

# PART XI — NIGHT CAPABILITY

## 41. Ordinary Police

NVG:

`NONE`

---

## 42. High-Threat Police

NVG:

`RARE`

---

## 43. Gendarmerie

NVG:

`RARE` to `OCCASIONAL`

Night capability should remain substantially below TSOC.

---

# PART XII — UNIFORM SYSTEM

## 44. Base TNP Uniform

Preferred colours:

```text
dark blue
slate
charcoal-grey
```

with:

- national flag patch;
- TNP badge;
- rank/identifier;
- optional high-visibility elements.

---

## 45. Rural Police Variant

Can use:

- same shirt/trouser family;
- tactical vest;
- different jacket;
- more practical field footwear.

Do not change into TNA camouflage merely because the unit carries a rifle.

---

## 46. Gendarmerie Uniform

Preferred:

- same institutional colour family;
- darker tactical variant;
- stronger body armour;
- helmet.

This preserves TNP institutional identity.

---

# PART XIII — BODY ARMOUR

## 47. Ordinary Police

Prefer:

- duty belt;
- light vest;
- concealable armour where modelled.

---

## 48. High-Threat Police

Prefer:

- ballistic police vest;
- simple plate carrier.

---

## 49. Gendarmerie

Prefer:

- modern plate carrier;
- police/gendarmerie marking panel.

Avoid using the exact TNA Rapid Reaction vest texture without police markings.

---

# PART XIV — HEADGEAR

## 50. Soft Cap

High priority.

A good police cap provides more visual value than creating many tactical helmet variants.

---

## 51. Ballistic Helmet

Use existing shared helmet family where possible.

Police identity comes from:

- colour;
- cover;
- badge;
- markings.

---

## 52. Beret

Status:

`OPTIONAL`

Only if visual research/lore later gives it a clear role.

---

# PART XV — COMMUNICATIONS

## 53. Ordinary Police

Handheld/personal radio:

`COMMON`

ACRE implementation may use a simple handheld radio where appropriate.

---

## 54. High-Threat Police

Personal/team radio:

`COMMON`

Vehicle radio:

common in patrol vehicles.

---

## 55. Gendarmerie

Individual/team communications:

`COMMON`

Do not give police the same communications architecture as TSOC by default.

---

# PART XVI — VEHICLES

## 56. Vehicle Philosophy

Police vehicles are an important part of the faction's identity.

Priority should be:

```text
MARKED CIVILIAN-DERIVED VEHICLES
```

rather than military vehicles painted blue.

---

## 57. Patrol Sedan

Status:

`DESIRABLE`

Useful for:

- Rasman;
- urban policing;
- government scenes.

Do not create one if no technically acceptable asset exists.

---

## 58. Police SUV

Priority:

`HIGH`

Useful across urban and rural environments.

---

## 59. Police Pickup

Priority:

`HIGH`

Especially suitable for:

- rural stations;
- checkpoints;
- North Takistan roads;
- armed high-threat patrols.

---

## 60. Police Van

Priority:

`MEDIUM`

Potential uses:

- personnel transport;
- detention/utility;
- urban police scenes.

---

## 61. Gendarmerie Protected Vehicle

Priority:

`MEDIUM`

Potential:

- armoured SUV;
- protected pickup;
- light patrol MRAP.

Do not duplicate the full TNA protected-mobility fleet.

---

# PART XVII — VEHICLE MARKINGS

## 62. TNP Vehicle Identity

Required:

- TNP badge;
- Pashtu police wording;
- optional `POLICE`;
- unit number;
- simple stripe/panel system.

---

## 63. Colour Scheme

Initial preference:

```text
white / dark blue
```

or:

```text
dark blue with white markings
```

Exact design should be tested against available vehicle UV layouts.

---

## 64. Rural Vehicle Wear

Police vehicles can show:

- dust;
- repaired panels;
- older paint;
- mixed vehicle generations.

They should not all look factory-new.

---

# PART XVIII — CHECKPOINTS

## 65. Ordinary Police Checkpoint

Suggested visual personnel mix:

- 2–4 officers;
- one senior/patrol leader;
- one or two rifles;
- police pickup/SUV;
- barriers/signage.

This is a mission-making template, not operational doctrine.

---

## 66. High-Threat Checkpoint

Increase:

- armour;
- rifles;
- helmet use;
- gendarmerie support.

Do not automatically add machine guns or heavy weapons.

---

# PART XIX — POLICE STATIONS

## 67. Small Station

Suggested editor population:

- senior officer;
- officers;
- armed officer;
- patrol vehicle.

---

## 68. Regional Station

May include:

- local police;
- high-threat patrol;
- several vehicles;
- gendarmerie reinforcement space.

---

# PART XX — GENDARMERIE VEHICLE GROUPS

## 69. Patrol Team

Potential:

- protected SUV/pickup;
- 4–6 gendarmerie personnel.

---

## 70. Response Team

Potential:

- protected vehicle;
- team leader;
- several gendarmerie officers;
- medic.

Keep groups simple and Zeus-friendly.

---

# PART XXI — EDITOR UNIT CATALOGUE

## 71. Core Police

Recommended first release:

```text
Police Officer
Police Officer (Armed)
Senior Police Officer
Patrol Leader
High-Threat Police Officer
```

Optional:

```text
Police Medic
Police Driver
```

---

## 72. Gendarmerie

Recommended:

```text
Gendarmerie Officer
Gendarmerie Team Leader
Gendarmerie Machine Gunner
Gendarmerie Medic
```

Optional:

```text
Gendarmerie Marksman
Gendarmerie Engineer
```

---

# PART XXII — EDITOR SUBCATEGORIES

## 73. Recommended

```text
Police
Police (High Threat)
Gendarmerie
Cars
Protected Vehicles
```

If this becomes too fragmented:

```text
Men
Men (Gendarmerie)
Cars
```

is sufficient.

---

# PART XXIII — GROUPS

## 74. Foot Patrol

Suggested:

```text
3–4 police officers
```

---

## 75. Armed Patrol

Suggested:

```text
Patrol Leader
2–3 Armed / High-Threat Officers
```

---

## 76. Vehicle Patrol

Suggested:

```text
Police SUV/Pickup
2–4 officers
```

---

## 77. Gendarmerie Team

Suggested:

```text
Team Leader
2–4 Gendarmerie Officers
Medic or specialist optional
```

---

## 78. Gendarmerie Motorised Team

Suggested:

```text
Protected vehicle
Gendarmerie Team
```

---

# PART XXIV — RELATIONSHIP WITH TNA

## 79. Clear Institutional Boundary

TNP handles:

- law enforcement;
- routine public security;
- local police presence.

TNA handles:

- military combat;
- major conventional threats;
- heavy weapons;
- sustained combat operations.

Gendarmerie covers the intermediate security space.

---

## 80. Joint Presence

At major incidents, mission makers may combine:

```text
TNP
+
TNG
+
TNA
```

without needing to pretend they are one organisation.

---

# PART XXV — RELATIONSHIP WITH TBG

## 81. Border Guard

TBG remains a separate conceptual function.

TNP may operate near borders, but the dedicated Border Guard owns routine:

- border posts;
- border patrol;
- customs-security support.

Do not make TNP responsible for every government-security task.

---

# PART XXVI — RELATIONSHIP WITH NTEF

## 82. Police Vulnerability

TNP is one of the most exposed state institutions in the NTEF conflict because officers remain present among the civilian population.

This justifies:

- armed rural police;
- reinforced stations;
- gendarmerie.

It does not justify transforming the whole service into military infantry.

---

# PART XXVII — CORRUPTION / QUALITY VARIATION

## 83. Uneven Quality

TNP may contain:

- professional officers;
- poorly trained local officers;
- corrupt individuals;
- strong regional commanders;
- weak stations.

Do not make corruption a universal faction trait.

---

# PART XXVIII — WOMEN IN TNP

## 84. Female Police

The project should support female police personnel if suitable character assets are available.

This is useful for:

- civilian policing;
- searches/interaction;
- government scenes;
- broader visual credibility.

Do not make implementation dependent on creating bespoke female character models immediately.

---

# PART XXIX — CIVILIAN INTERACTION

## 85. Police-Civilian Visual Language

Police should appear in places where civilians plausibly expect government services.

Examples:

- markets;
- roads;
- government offices;
- police compounds;
- transport points.

This helps the theatre feel governed rather than militarily occupied.

---

# PART XXX — ASSET REQUIREMENTS

## 86. High Priority

1. TNP uniform texture/model solution.
2. TNP soft cap.
3. TNP badge/shoulder patch.
4. Basic police ballistic vest.
5. TNP-marked pickup.
6. TNP-marked SUV.

---

## 87. Medium Priority

1. tactical/gendarmerie vest;
2. ballistic helmet markings;
3. police van;
4. protected gendarmerie vehicle;
5. station signage.

---

## 88. Low Priority

1. bespoke riot gear;
2. shields;
3. specialist crowd-control equipment;
4. unique police weapons.

Do not commission expensive specialist assets before missions require them.

---

# PART XXXI — PERFORMANCE / REUSE

## 89. Reuse Shared Models

Prefer retexturing/shared assets for:

- helmets;
- armour;
- pickups;
- SUVs;
- radios.

The TNP's uniqueness should come primarily from:

- uniform colours;
- badges;
- vehicle markings;
- equipment distribution.

---

# PART XXXII — CONFIG IMPLICATIONS

## 90. Faction

Proposed:

```cpp
UKSF_Factions_TNP
```

Display:

```text
Takistani National Police
```

Side:

```text
BLUFOR
```

---

## 91. Potential Class Pattern

```text
UKSF_Factions_TNP_<Role>
```

Examples:

```cpp
UKSF_Factions_TNP_Officer
UKSF_Factions_TNP_ArmedOfficer
UKSF_Factions_TNP_SeniorOfficer
UKSF_Factions_TNP_PatrolLeader
```

Gendarmerie:

```cpp
UKSF_Factions_TNP_Gendarmerie
UKSF_Factions_TNP_Gendarmerie_TeamLeader
UKSF_Factions_TNP_Gendarmerie_Medic
```

Exact naming should be aligned with the project naming standard during config work.

---

# PART XXXIII — DESIGN RED LINES

## 92. Do Not Make TNP a Second Army

Avoid:

- RPGs on ordinary patrols;
- machine guns at every checkpoint;
- helmets and plate carriers on every city officer;
- mechanised infantry vehicles as normal police transport;
- universal rifles.

---

## 93. Do Not Make TNP Unarmed British-Style Policing

North Takistan is a high-threat post-conflict environment.

It is reasonable for:

- police stations to hold rifles;
- rural officers to carry rifles;
- some patrols to wear armour.

The faction should sit between unrealistic extremes.

---

## 94. Do Not Create a Giant Specialist Catalogue

Initial release does not need:

- SWAT snipers;
- EOD squads;
- riot companies;
- K9 units;
- traffic-police variants;
- detective models.

Add specialist roles only where mission demand emerges.

---

# PART XXXIV — LOCKED DECISIONS

## 95. Locked

- TNP is a separate BLUFOR faction.
- TNP is police first, not Army infantry.
- TNP has three capability layers: ordinary police, high-threat/rural police and gendarmerie.
- Gendarmerie remains a TNP subcomponent initially.
- Ordinary police are primarily pistol-equipped.
- Rifles become common in high-threat/rural policing.
- AK-family rifles are the primary police long-arm family.
- Ordinary police do not carry machine guns or anti-armour weapons.
- Gendarmerie may have limited support weapons.
- Ordinary urban police usually do not wear helmets.
- Body armour prevalence increases with threat level.
- Gendarmerie has modern armour but remains visually police.
- NVGs are rare throughout TNP and more likely in gendarmerie.
- Police vehicles should primarily be civilian-derived marked vehicles.
- Pickup and SUV are the highest-priority vehicle types.
- TNP and TNA remain visually and institutionally distinct.
- Border Guard remains conceptually separate.
- Female police are supported if suitable assets exist.
- The first release avoids expensive specialist police assets.

---

# PART XXXV — OPEN DECISIONS

## 96. Before Config / Art

- [ ] Lock exact TNP native Pashtu service name for final artwork.
- [ ] Design TNP badge.
- [ ] Select base police uniform model.
- [ ] Select dark blue/slate uniform colour.
- [ ] Select soft cap model.
- [ ] Select police vest.
- [ ] Select gendarmerie plate carrier.
- [ ] Select ballistic helmet.
- [ ] Select service pistol.
- [ ] Select exact AK-family police rifle pool.
- [ ] Decide shotgun inclusion.
- [ ] Decide gendarmerie automatic weapon.
- [ ] Select handheld radio.
- [ ] Select police pickup.
- [ ] Select police SUV.
- [ ] Decide whether patrol sedan is worth sourcing.
- [ ] Decide police van requirement.
- [ ] Select protected gendarmerie vehicle.
- [ ] Design vehicle marking system.
- [ ] Create police station/signage glossary assets.
- [ ] Decide whether `TNG` becomes a public acronym or remains internal.
- [ ] Create TNP asset/dependency audit after source assets are identified.

---

# PART XXXVI — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## NATO — 2009 Summit Declaration on Afghanistan

NATO committed to training and mentoring the Afghan National Police separately from the Army and specifically identified the potential role of the European Gendarmerie Force.

```text
https://www.nato.int/en/about-us/official-texts-and-resources/official-texts/2009/04/04/summit-declaration-on-afghanistan
```

## NATO — 2009 Press Conference

NATO publicly described gendarmerie training as part of police development and separately referenced equipment support for the police.

```text
https://www.nato.int/en/news-and-events/events/transcripts/2009/06/12/press-conference
```

## NATO — Assistance to Iraq

NATO describes gendarmerie-type training for Iraqi federal police as a means of bridging the gap between routine police work and military operations.

```text
https://www.nato.int/en/what-we-do/operations-and-missions/natos-assistance-to-iraq-2004-2011
```

## NATO Stability Policing Centre of Excellence — About Stability Policing

The Centre describes gendarmerie-type forces as military-status forces with full civil-police capabilities and explains their role in bridging the policing/security gap.

```text
https://www.nspcoe.org/about-us/about-stability-policing/
```

## NATO Stability Policing Centre of Excellence — Police in Conflict

The Centre's discussion of lessons from Afghanistan highlights the danger of excessive police militarisation at the expense of community-policing functions.

```text
https://www.nspcoe.org/presentation-of-the-sigar-report-police-in-conflict/
```

---

# PART XXXVII — CURRENT CONCLUSION

The TNP should create a visible **gradient of state security**:

```text
ORDINARY POLICE
      ↓
HIGH-THREAT / RURAL POLICE
      ↓
GENDARMERIE
      ↓
TNA
      ↓
RAPID REACTION / TSOC
```

That spectrum is more believable and more useful to mission makers than treating every government security actor as the same rifleman with a different patch.

In practical visual terms:

```text
Rasman street
    → normal uniformed police

North Takistan rural checkpoint
    → armed/armoured TNP

major high-threat incident
    → Gendarmerie

sustained military threat
    → TNA
```

This gives the Takistani state a genuine civilian-security presence while preserving clear roles for the Army and future Border Guard.
