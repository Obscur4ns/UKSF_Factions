# UKSF_Factions — TNA Organisation, Roles & Equipment Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** TNA Organisation, Roles & Equipment Standard  
**Status:** Research / Design Standard  
**Created:** 2026-08-09  
**Faction:** Takistani National Army (`TNA`)  
**Faction type:** `CONVENTIONAL / HOST-NATION`  
**Default side:** BLUFOR / WEST  
**Time period:** Contemporary / approximately 2026  

---

## 1. Purpose

This document defines what the contemporary **Takistani National Army** should contain as an Arma faction.

It converts the established Takistani military history and the project's 2026 post-war continuity into:

- unit roles;
- capability tiers;
- equipment distribution;
- weapon-family distribution;
- armour and helmet prevalence;
- radio and night-equipment prevalence;
- vehicle hierarchy;
- mechanised capability;
- aviation boundaries;
- editor unit catalogue;
- editor group catalogue;
- asset requirements.

It does **not** lock exact third-party asset classnames yet.

Those are deferred until the actual asset pool is assembled.

---

# PART I — DESIGN BASIS

## 2. Canon Legacy

Official Bohemia material describes the old Takistani Revolutionary Army as using a broad Cold-War equipment mix including AKS-74, FN FAL, PKM, T-34, T-55, T-72, BRDM-2, UAZ, V3S, Mi-8, Mi-24, L-39 and Su-25.

The old force also used khaki and lizard-pattern clothing with steel helmets.

This provides the **legacy equipment layer** for the modern army.

## 3. Post-War Interpretation

`UKSF_Factions` treats the 2026 TNA as a reconstituted national force.

It inherited personnel, facilities, vehicles, weapons and maintenance culture from the old state, but underwent post-war restructuring and external assistance.

The modern force therefore should look like:

```text
OLD TAKISTANI MILITARY LEGACY
        +
POST-WAR REFORM
        +
SELECTIVE DONOR EQUIPMENT
        +
UNEQUAL MODERNISATION
```

not:

```text
NATO ARMY IN TAKISTANI CAMOUFLAGE
```

## 4. Real-World Reference Principle

NATO's historical partner-force experience is used only as a broad institutional reference.

Useful lessons include:

- local capacity matters;
- logistics and sustainment matter;
- institutional development matters;
- forces do not become sustainable merely by receiving modern equipment;
- specialist formations often receive disproportionately high investment.

This supports an army where modernisation is uneven.

---

# PART II — ORGANISATIONAL MODEL

## 5. Army Capability Layers

For game design, TNA personnel are divided into four main capability layers.

### Tier A — Regional Infantry

Ordinary line units.

### Tier B — Regular / Mechanised

Better-supported conventional units.

### Tier C — Rapid Reaction

More modern, mobile national response units.

### Tier D — Special Operations

TSOC.

These are **UKSF_Factions implementation categories**, not claimed real Takistani TO&E.

---

# PART III — TIER A: REGIONAL INFANTRY

## 6. Role

Regional Infantry should represent the most common TNA combat presence in North Takistan.

Typical duties may include garrisoning military compounds, supporting police, securing strategic sites and routine regional security.

## 7. Visual Identity

Typical Tier A appearance:

- standard TNA camouflage;
- mixed chest rigs and older plate carriers;
- composite helmets common but not universal;
- AK-family rifles;
- limited optics;
- leader radios;
- older trucks/pickups.

Some visible equipment age is desirable.

## 8. Armour

| Equipment | Frequency |
|---|---|
| No ballistic armour | `OCCASIONAL` |
| Basic ballistic vest | `COMMON` |
| Plate carrier | `OCCASIONAL` |
| Modern high-end carrier | `RARE` |

## 9. Helmets

Composite helmet: `COMMON`  
Older helmet: `OCCASIONAL`  
No helmet / soft cap: `OCCASIONAL`  
Steel helmet: `RARE`

---

# PART IV — TIER B: REGULAR / MECHANISED

## 10. Role

Represents the more conventional core of the army.

Typical assets:

- mechanised infantry;
- APC/IFV crews;
- better-maintained vehicle fleets;
- heavier support weapons;
- better communications.

## 11. Visual Identity

Compared with Regional Infantry:

Increase body armour, helmet consistency, radios, optics and uniform consistency.

Decrease obviously worn legacy gear.

## 12. Armour

| Equipment | Frequency |
|---|---|
| Plate carrier / ballistic vest | `COMMON` |
| Basic armour | `OCCASIONAL` |
| No armour | `RARE` |
| Modern carrier | `OCCASIONAL` |

## 13. Night Equipment

NVG: `OCCASIONAL`  
Leader/specialist NVG: `COMMON`  
Thermal: `RARE`

---

# PART V — TIER C: RAPID REACTION

## 14. Working Designation

English:

```text
Rapid Reaction Force
```

Pashtu:

```text
د چټک غبرګون ځواک
```

Operational romanisation:

```text
Da Chatak Ghbargun Zwak
```

## 15. Role

Rapid Reaction represents the best conventional TNA element short of TSOC.

It should be suitable for national crisis response, reinforcement of threatened regions, strategic-site security and higher-risk combat.

## 16. Visual Identity

- modern plate carrier;
- modern composite helmet;
- optic-equipped rifle;
- modern radio;
- improved medical kit;
- protected mobility;
- more consistent clothing.

## 17. Armour

Modern ballistic armour: `UBIQUITOUS`  
Helmet: `UBIQUITOUS`  
Eye protection: `COMMON`

## 18. Night Capability

NVG: `COMMON`  
Leader/specialist NVG: `UBIQUITOUS`  
Thermal: `RARE` to `OCCASIONAL`

---

# PART VI — TIER D: TSOC

## 19. Takistani Special Operations Command

TSOC is a TNA subcomponent and should be the principal high-end host-nation partner for UKSF.

It should **not** be a separate `CfgFactionClasses` faction initially.

## 20. TSOC Visual Identity

- modern plate carriers;
- modern helmets;
- individual radios;
- NVGs;
- optics;
- gloves/eye protection;
- modern AK-family rifles;
- meaningful minority of Western carbines.

## 21. TSOC Equipment Standard

Body armour: `UBIQUITOUS`  
Helmet: `COMMON` to `UBIQUITOUS`  
Individual radio: `UBIQUITOUS`  
NVG: `UBIQUITOUS`  
Thermal: `OCCASIONAL`  
Suppressor: `OCCASIONAL`  
Sidearm: `COMMON`

---

# PART VII — CORE INFANTRY ROLES

## 22. Rifleman

Working class token: `Rifleman`

Tier: A / B

Primary normal combat class.

Typical equipment:

- AK-family rifle;
- standard uniform;
- helmet;
- armour appropriate to tier;
- basic individual medical equipment.

## 23. Rifleman (Light)

Working token: `RiflemanLight`

Tier: A

Useful for lighter garrison/security units and driver-compatible dismounts.

Status: `OPTIONAL`

## 24. Team Leader

Working token: `TeamLeader`

Tier: A / B

Typical:

- radio;
- optic;
- binoculars;
- improved armour.

## 25. Section Commander

Working token: `SectionCommander`

Tier: B / C

Leader for standard section-sized groups.

## 26. Automatic Rifleman

Working token: `AutomaticRifleman`

Potential weapon:

- RPK family.

## 27. Machine Gunner

Working token: `MachineGunner`

Primary weapon family:

```text
PKM
```

PKM should remain a major visual signature of the TNA.

## 28. Assistant Machine Gunner

Working token: `AssistantMG`

Carries a rifle and additional ammunition.

## 29. Grenadier

Working token: `Grenadier`

Tier: B / C

Status: `LIKELY`

Retain if suitable AK-compatible grenade-launcher assets are available.

## 30. Marksman

Working token: `Marksman`

Potential:

- SVD;
- modernised SVD-family rifle.

Rapid Reaction/TSOC may use a more modern precision rifle.

## 31. Anti-Armour

Working token: `AT`

Regional/Regular:

- RPG-7;
- older disposable launcher.

Rapid Reaction:

- modern disposable or limited guided system.

Modern guided systems should remain concentrated.

## 32. Medic

Working token: `Medic`

ACE-compatible medical specialist.

## 33. Engineer

Working token: `Engineer`

Purpose:

- repair;
- engineering;
- ACE capability;
- toolkit carrying.

## 34. Drone Operator

Working token: `DroneOperator`

Tier: B / C

Purpose:

- small UAS operation;
- reconnaissance.

## 35. Radio Operator

Working token: `RadioOperator`

Status: `OPTIONAL`

May be unnecessary if ACRE distribution and leader radios adequately cover communications.

---

# PART VIII — CREW / SUPPORT ROLES

## 36. Driver

Working token: `Driver`

Appearance:

- lighter armour;
- standard helmet or soft cap;
- compact rifle.

## 37. Crewman

Working token: `Crew`

Purpose:

- APC;
- IFV;
- tank.

## 38. Pilot

Working token: `Pilot`

Purpose:

- helicopter;
- fixed-wing where required.

## 39. Helicopter Crew

Working token: `HelicopterCrew`

Status: `OPTIONAL`

---

# PART IX — RAPID REACTION ROLES

## 40. Recommended Visible Classes

Use a restrained set:

```text
Rapid Reaction Rifleman
Rapid Reaction Team Leader
Rapid Reaction Machine Gunner
Rapid Reaction Anti-Armour
Rapid Reaction Medic
Rapid Reaction Drone Operator
```

Do not duplicate every TNA role.

---

# PART X — TSOC ROLES

## 41. Recommended Visible Classes

```text
TSOC Operator
TSOC Team Leader
TSOC Automatic Rifleman
TSOC Marksman
TSOC Medic
TSOC Engineer
TSOC Drone Operator
```

This is enough to build useful teams without editor bloat.

---

# PART XI — WEAPON DISTRIBUTION

## 42. Core Weapon Identity

The army remains primarily AK-family armed.

Recommended hierarchy:

```text
AK-74 family
AKM / improved AKM
modern AK / AK-100 family
```

## 43. Regional Infantry Rifle Pool

**Project design weights — not real-world statistics**

| Family | Target share |
|---|---:|
| AK-74 family | 45% |
| AKM / improved AKM | 30% |
| modern AK / AK-100 | 15% |
| FAL / legacy Western rifle | 7% |
| other appropriate rifle | 3% |

## 44. Regular / Mechanised Rifle Pool

| Family | Target share |
|---|---:|
| AK-74 family | 40% |
| modern AK / AK-100 | 35% |
| AKM family | 18% |
| legacy/other | 5% |
| Western carbine | 2% |

## 45. Rapid Reaction Rifle Pool

| Family | Target share |
|---|---:|
| modern AK / AK-100 | 55% |
| AK-74 family | 25% |
| Western carbine | 15% |
| other | 5% |

## 46. TSOC Rifle Pool

| Family | Target share |
|---|---:|
| modern AK | 50% |
| Western carbine | 35% |
| modernised AK-74 | 10% |
| specialist/other | 5% |

This preserves Takistani identity even at the top end.

---

# PART XII — OPTICS & ACCESSORIES

## 47. Regional Infantry

Optics: `OCCASIONAL`  
Weapon lights: `RARE`  
Lasers: `RARE`  
Suppressors: `EXCEPTIONAL`

## 48. Regular / Mechanised

Optics: `COMMON`  
Weapon lights: `OCCASIONAL`  
Lasers: `RARE` to `OCCASIONAL`  
Suppressors: `RARE`

## 49. Rapid Reaction

Optics: `UBIQUITOUS`  
Weapon lights: `COMMON`  
Lasers: `OCCASIONAL`  
Suppressors: `RARE`

## 50. TSOC

Optics: `UBIQUITOUS`  
Weapon lights: `COMMON`  
Lasers: `COMMON`  
Suppressors: `OCCASIONAL`

---

# PART XIII — SIDEARMS

## 51. Distribution

Regional Infantry: generally `NONE`  
Leaders/Crew: `OCCASIONAL`  
Rapid Reaction leaders: `COMMON`  
TSOC: `COMMON`

Do not issue pistols universally.

---

# PART XIV — LOAD-BEARING EQUIPMENT

## 52. Regional Infantry

Mix:

- older chest rigs;
- basic ballistic vests;
- simple plate carriers;
- older webbing.

## 53. Regular / Mechanised

Mix:

- standardised chest rigs;
- plate carriers;
- limited legacy gear.

## 54. Rapid Reaction

Primarily:

- modern plate carriers;
- modern chest rigs;
- consistent pouch systems.

## 55. TSOC

Modern tactical equipment.

Avoid copying UKSF's exact vest/helmet combination.

---

# PART XV — UNIFORM / HEADGEAR STANDARD

## 56. Modern TNA Camouflage

The modern army should use a distinct fictional contemporary arid/transitional camouflage.

The old khaki/lizard appearance should not be standard 2026 issue.

## 57. Regional Infantry

May show:

- faded uniforms;
- mixed generations;
- field repairs;
- old equipment.

The uniform itself should still be recognisably standard TNA issue.

## 58. Rapid Reaction / TSOC

More consistent and cleaner equipment.

## 59. Standard Helmet

A modern composite helmet should become the normal TNA combat identity.

## 60. Soft Headgear

Potential:

- patrol cap;
- winter cap;
- beret only if later lore supports it.

Do not make regional civilian headwear the standard Army combat silhouette.

---

# PART XVI — COMMUNICATIONS & NIGHT CAPABILITY

## 61. Regional Infantry

Leader radio: `COMMON`  
Individual radio: `RARE` to `OCCASIONAL`  
NVG: `RARE`

## 62. Mechanised

Leader radio: `UBIQUITOUS`  
Individual radio: `OCCASIONAL`  
NVG: `OCCASIONAL`

## 63. Rapid Reaction

Individual/team radio: `COMMON`  
Leader radio: `UBIQUITOUS`  
NVG: `COMMON`

## 64. TSOC

Individual radio: `UBIQUITOUS`  
NVG: `UBIQUITOUS`  
Thermal: `OCCASIONAL`

Exact ACRE implementation remains separate work.

---

# PART XVII — MEDICAL & UAS

## 65. Medical

Ordinary soldiers should have better-standardised individual medical equipment than NTEF.

Medics receive dedicated medical loads.

TSOC Medic may receive enhanced ACE capability.

## 66. TNA UAS

Modern TNA should possess limited small-UAS capability.

Distribution:

Regional Infantry: `RARE`  
Regular: `OCCASIONAL`  
Rapid Reaction: `COMMON AS SPECIALIST CAPABILITY`  
TSOC: `COMMON AS SPECIALIST CAPABILITY`

Do not give every section a drone.

---

# PART XVIII — VEHICLE FLEET

## 67. Vehicle Design Principle

The vehicle fleet should visibly show:

```text
LEGACY EASTERN
+
POST-WAR DONOR
+
LIMITED MODERN PROCUREMENT
```

## 68. Utility Vehicles

Potential:

- UAZ family;
- pickups;
- SUVs;
- military utility vehicles;
- HMMWV-type/donor vehicles;
- light protected mobility.

## 69. Trucks

Potential:

- V3S;
- Ural;
- modern commercial/military truck.

Legacy trucks should remain common enough to preserve visual continuity.

## 70. BMP-2

**Status:** `CORE LEGACY VEHICLE`

Strong candidate for regular/mechanised TNA.

## 71. M113

**Status:** `PLAUSIBLE / DONOR OR LEGACY WESTERN`

Useful as APC/support platform.

## 72. Modern Wheeled APC

**Status:** `OPTIONAL`

Add only if a strong asset exists.

---

# PART XIX — TANKS / PROTECTED MOBILITY

## 73. T-72

**Status:** `PRIMARY ACTIVE TANK FAMILY`

Best baseline for remaining conventional armour.

## 74. T-55

**Status:** `RESERVE / SECONDARY`

May appear in reserve or mission-specific mobilisation.

## 75. T-34

**Status:** `NOT NORMAL COMBAT EQUIPMENT`

Potential use:

- monument;
- museum;
- training hulk;
- ceremonial display;
- exceptional scenario.

## 76. MRAP-Type Vehicles

Concentrate in:

- Rapid Reaction;
- TSOC;
- high-threat security.

Do not make them standard rural-infantry mobility.

---

# PART XX — ARTILLERY / AIR DEFENCE / AVIATION

## 77. Artillery

Initial scope should remain restrained.

Potential:

- mortar;
- towed artillery;
- limited self-propelled system.

Exact systems are deferred.

## 78. Air Defence

Potential:

- MANPADS;
- older gun/missile systems.

Status: `LIMITED / MISSION-SPECIFIC`

## 79. Air Corps

The Takistani Air Corps remains a TNA component.

### Mi-8 / Mi-17

Priority: `HIGH`

Best fit for transport/logistics/CASEVAC/government movement.

### Mi-24

Priority: `MEDIUM`

Limited attack capability if suitable assets exist.

### L-39

Priority: `OPTIONAL`

Training/light attack.

### Su-25

Status: `LIMITED / POSSIBLY RETIRED`

Do not assume a large combat fast-jet fleet.

---

# PART XXI — EDITOR UNIT CATALOGUE

## 80. Core TNA Units

Recommended:

```text
Rifleman
Rifleman (Light)
Team Leader
Section Commander
Automatic Rifleman
Machine Gunner
Assistant Machine Gunner
Grenadier
Marksman
Anti-Armour
Medic
Engineer
Drone Operator
Driver
Crewman
Pilot
```

Potential:

```text
Radio Operator
Assistant AT
Helicopter Crew
```

## 81. Rapid Reaction

Recommended limited visible classes:

```text
Rapid Reaction Rifleman
Rapid Reaction Team Leader
Rapid Reaction Machine Gunner
Rapid Reaction Anti-Armour
Rapid Reaction Medic
Rapid Reaction Drone Operator
```

## 82. TSOC

Recommended:

```text
TSOC Operator
TSOC Team Leader
TSOC Automatic Rifleman
TSOC Marksman
TSOC Medic
TSOC Engineer
TSOC Drone Operator
```

---

# PART XXII — EDITOR SUBCATEGORIES & GROUPS

## 83. Recommended Subcategories

```text
Men
Men (Rapid Reaction)
Men (Special Operations)
Cars
Trucks
APCs
Armour
Air
```

Add `Artillery` only if actual assets justify it.

## 84. Infantry Fire Team

Target: 4

Suggested:

- Team Leader;
- Rifleman;
- Automatic Rifleman;
- Rifleman / Grenadier.

## 85. Infantry Section

Target: 8

Suggested:

- Section Commander;
- Team Leader;
- Riflemen;
- Automatic Rifleman;
- Machine Gunner or Grenadier;
- AT depending variant.

Gameplay abstraction only.

## 86. Mechanised Section

One APC/IFV plus crew and infantry section.

## 87. Motorised Section

Transport vehicle plus infantry group.

## 88. Rapid Reaction Team

Target: 5–6.

## 89. TSOC Team

Target: 4–6.

Do not recreate UKSF's exact team structure.

---

# PART XXIII — FORCE MIX

## 90. North Takistan Army Mix

Mission-authoring target:

| Category | Design share |
|---|---:|
| Regional Infantry | 55% |
| Regular / Mechanised | 25% |
| Rapid Reaction | 15% |
| TSOC | 5% |

TSOC should remain uncommon.

---

# PART XXIV — ASSET REQUIREMENTS

## 91. Uniforms

Need:

- one strong standard TNA camouflage uniform family;
- worn/texture variants;
- possible specialist variant only if necessary.

## 92. Vests

Need:

- basic ballistic vest;
- transitional/older plate carrier;
- modern plate carrier;
- modern chest rig.

## 93. Helmets

Need:

- standard composite helmet;
- legacy helmet;
- modern high-cut/equivalent for TSOC/RRF if appropriate.

## 94. Vehicles

High priority:

- UAZ-type utility;
- pickup;
- truck;
- BMP-2;
- M113 or equivalent;
- T-72;
- protected patrol/MRAP;
- Mi-8/Mi-17.

---

# PART XXV — DESIGN RED LINES

## 95. Do Not Make TNA a NATO Clone

Avoid:

- universal M4;
- universal high-cut helmets;
- identical modern plate carriers;
- universal NVGs;
- all-MRAP mobility.

## 96. Do Not Freeze TNA in 2010

Avoid:

- steel helmets everywhere;
- lizard camouflage everywhere;
- T-34 combat formations;
- zero modern optics/radios.

## 97. Do Not Make TNA an Incompetent Ally Stereotype

The army needs:

- weaker units;
- ordinary units;
- genuinely capable units.

TSOC and Rapid Reaction should be credible partners.

---

# PART XXVI — CONFIG IMPLICATIONS

## 98. Base Classes

Conceptually:

```text
TNA_Base
├── TNA_Regional_Base
├── TNA_Regular_Base
├── TNA_RRF_Base
├── TNA_TSOC_Base
├── TNA_Crew_Base
└── TNA_Pilot_Base
```

Actual inheritance should remain as shallow as practical.

## 99. Naming

Public pattern:

```text
UKSF_Factions_TNA_<Role>
```

Examples:

```cpp
UKSF_Factions_TNA_Rifleman
UKSF_Factions_TNA_MachineGunner
UKSF_Factions_TNA_Medic
UKSF_Factions_TNA_Crew
```

Potential specialised pattern:

```cpp
UKSF_Factions_TNA_RRF_Rifleman
UKSF_Factions_TNA_TSOC_Operator
```

Final implementation should be checked against the project naming standard.

---

# PART XXVII — LOCKED DECISIONS

## 100. Locked

- TNA uses four capability layers: Regional, Regular/Mechanised, Rapid Reaction, TSOC.
- Regional Infantry is the most common combat layer.
- TNA remains primarily AK-family armed.
- PKM remains the main GPMG identity.
- RPG-7 remains common at lower/mid tiers.
- Modern guided anti-armour is concentrated in higher-tier units.
- Composite helmets are the normal active standard.
- Steel helmets are legacy/rare.
- Modern TNA uses a new camouflage rather than old lizard/khaki as standard.
- Body armour is common but quality varies by tier.
- NVGs are rare in ordinary regional infantry.
- Rapid Reaction has substantial night capability.
- TSOC has routine night capability.
- TSOC remains a TNA subcategory, not a separate faction.
- T-72 is the principal active tank family.
- T-55 is reserve/secondary.
- T-34 is not standard 2026 combat equipment.
- BMP-2 remains a core mechanised candidate.
- Mi-8/Mi-17 is a high-priority aviation family.
- The vehicle fleet visibly mixes legacy and donor equipment.
- Protected modern mobility is concentrated in better units.
- The editor catalogue should avoid duplicating every role for every capability tier.
- TNA groups are gameplay abstractions, not claimed canonical TO&E.

---

# PART XXVIII — OPEN DECISIONS

## 101. Before Config

- [ ] Select final TNA camouflage pattern.
- [ ] Select uniform model.
- [ ] Select standard composite helmet.
- [ ] Select legacy helmet.
- [ ] Select standard body armour.
- [ ] Select modern plate carrier.
- [ ] Select TSOC helmet/armour.
- [ ] Lock exact AK-family rifle pool.
- [ ] Decide whether FAL remains in active line service.
- [ ] Decide Western-carbine pool.
- [ ] Select grenadier weapon.
- [ ] Select guided anti-armour option, if any.
- [ ] Select NVG models.
- [ ] Select TNA radio family.
- [ ] Select RRF/TSOC radio family.
- [ ] Select drone asset.
- [ ] Select UAZ/pickup/truck family.
- [ ] Confirm BMP-2 source.
- [ ] Confirm M113 or replacement.
- [ ] Confirm T-72 source.
- [ ] Select protected mobility vehicle.
- [ ] Confirm Mi-8/Mi-17 family.
- [ ] Decide Mi-24 status.
- [ ] Decide L-39 status.
- [ ] Decide Su-25 status.
- [ ] Decide artillery scope.
- [ ] Decide air-defence scope.
- [ ] Design TNA emblem and patches.
- [ ] Complete asset/dependency audit once source assets are assembled.

---

# PART XXIX — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## Bohemia Interactive — Takistan Army Deployed

Official source for the old Takistani Army's equipment and visual identity.

```text
https://www.bohemia.net/en/blog/takistan-army-deployed
```

## NATO — NATO and Afghanistan

Used as a broad institutional reference for security-force development and partner-force lessons.

```text
https://www.nato.int/en/what-we-do/operations-and-missions/nato-and-afghanistan
```

## NATO — Inteqal / Transition to Afghan Lead

Used as a broad reference for the principle that host-nation security responsibility depends on sustainable local capability.

```text
https://www.nato.int/en/what-we-do/operations-and-missions/inteqal-transition-to-afghan-lead-2011-2014
```

## NATO — Resolute Support Mission

Used as a broad reference for training/advising institutional security forces.

```text
https://www.nato.int/en/what-we-do/operations-and-missions/resolute-support-mission-in-afghanistan-2015-2021
```

---

# PART XXX — CURRENT CONCLUSION

The TNA should look like a state military that has survived several political and military eras.

A normal 2026 formation should visually communicate:

```text
AK / PKM / RPG LEGACY
       +
STANDARD NATIONAL UNIFORM
       +
COMPOSITE HELMET / ARMOUR
       +
OLDER VEHICLES
       +
SELECTIVE MODERN EQUIPMENT
```

The top end should communicate genuine post-war modernisation without turning the whole army into a Western force.

This creates a stable North Takistan friendly-force spectrum:

```text
Regional TNA
      ↓
Regular / Mechanised
      ↓
Rapid Reaction
      ↓
TSOC
      ↓
UKSF partner operations
```
