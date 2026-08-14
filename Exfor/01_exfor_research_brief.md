# UKSF_Factions — Faction Research Brief 02
## Exercise Force (EXFOR)

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Faction Research Brief 02  
**Status:** Research / Pre-production  
**Created:** 2026-08-09  
**Faction:** Exercise Force  
**Working acronym:** `EXFOR`  
**Faction type:** `TRAINING_OPFOR`  
**Primary use:** British military / UKSF exercise enemy  
**Intended default side:** OPFOR / EAST  
**Internal faction ID:** `EXFOR`

---

## 1. Purpose

This document defines the research and initial design direction for the second major faction in `UKSF_Factions`.

EXFOR is intended to provide a reusable **British military training enemy** for:

- UKSF training exercises;
- conventional force-on-force exercises;
- urban training;
- irregular-threat training;
- combined-arms scenarios;
- pre-deployment training;
- instructor-led serials;
- mission rehearsals.

The faction should not represent a real hostile country.

Instead, it represents an **exercise force configured to portray whatever threat the training audience is supposed to face**.

This makes EXFOR fundamentally different from NTEF.

NTEF is an in-universe hostile organisation.

EXFOR is a training construct.

---

# PART I — RESEARCH BASIS

## 2. British Army Collective Training

The British Army's current Land Warfare Centre describes Collective Training Group as the Field Army's training delivery arm.

The Army states that its collective training establishments, centres and command-and-staff training groups operate across multiple continents and are combined with a **Contemporary Operating Environment Force** to create challenging training against a well-equipped modern enemy.

This is the most important conceptual basis for EXFOR.

The enemy used in British training is not necessarily a permanent fictional country or force with one fixed order of battle.

It is an adaptable training capability.

---

## 3. Task Force Hannibal — Exercise Iron Storm 2025

A particularly useful recent example is **Task Force Hannibal** during Exercise Iron Storm on Salisbury Plain in 2025.

Approximately 250 personnel formed the OPFOR.

The force was led by personnel from 5th Battalion, The Rifles and was specifically prepared to represent contemporary Russian ground forces.

The training audience was The Queen's Royal Hussars Battlegroup.

Importantly, the exercise did not require the OPFOR's real British vehicles to physically become Russian vehicles.

The Army's Tactical Engagement Simulation system was used to configure Warriors to represent BMP-2 capabilities for the exercise.

This establishes a valuable design principle:

> **Exercise identity and simulated capability do not have to be identical to the physical equipment being worn or driven.**

For `UKSF_Factions`, that means EXFOR can be believable even when using:

- British training kit;
- repurposed vehicles;
- generic threat weapons;
- synthetic/editor-defined equipment;

provided the faction clearly represents a training enemy rather than a real national force.

---

## 4. Combat Ready Training Centre — Adaptable Enemy

British Army reporting from exercises in Germany provides another useful precedent.

During a 2023 battlegroup validation exercise, British troops worked alongside a German opposing force while a British infantry company also acted as the enemy.

The Army described the enemy force as using different equipment and tactics to challenge the training audience.

The exercise also incorporated synthetic surveillance and other simulated capabilities.

This reinforces that OPFOR should be designed around:

- training effect;
- adaptability;
- credible threat representation;

rather than strict visual impersonation of one real adversary.

---

## 5. CENZUB — Multi-Role Opposing Force

British Army/Soldier reporting from CENZUB in France provides an especially useful model for our wider EXFOR concept.

The facility maintains an in-house opposing force with:

- infantry;
- engineers;
- multiple vehicle types.

That same force can portray:

- a conventional combat formation;
- militia;
- civilians/refugees;

depending on the exercise requirement.

This strongly supports giving EXFOR **multiple threat profiles inside one training ecosystem**.

---

## 6. US National Training Centre Reference

In 2025, British troops training at the US National Training Centre faced the 11th Armoured Cavalry Regiment acting as a dedicated professional OPFOR configured to represent a realistic peer threat.

The British Army described this as a dedicated opposition force whose purpose was to provide a credible enemy against which new British concepts could be tested.

This reinforces another important principle:

> The training enemy should be competent enough to genuinely challenge the training audience.

EXFOR should therefore not be designed as disposable target troops.

---

# PART II — CORE FACTION CONCEPT

## 7. Working Name

**Exercise Force**

Short form:

**EXFOR**

This should be treated as a functional title rather than the name of a permanent military formation.

### Why this name works

It is:

- short;
- obvious to mission makers;
- politically neutral;
- not tied to one country;
- suitable for conventional and irregular training;
- compatible with the already-reserved internal ID `EXFOR`.

### Current decision

**Working name:** `Exercise Force`

**Display name:** `Exercise Force (EXFOR)`

This remains subject to later editor testing.

---

## 8. What EXFOR Represents

EXFOR is a standing **mission-making training faction** representing personnel assigned to act as the enemy during exercises.

In lore terms, the force can be understood as being assembled from:

- British Army personnel;
- other UK military personnel;
- allied personnel;
- dedicated training staff;
- exercise role-players;
- training vehicles and equipment.

The exact composition is scenario-dependent.

EXFOR therefore does **not** need:

- a homeland;
- a government;
- a political ideology;
- a war flag;
- territorial objectives;
- diplomatic relationships.

Its purpose is training.

---

## 9. Relationship to Real British Training Organisations

EXFOR is **inspired by**, but should not claim to be a direct digital recreation of:

- the British Army Contemporary Operating Environment Force;
- Task Force Hannibal;
- Combat Ready Training Centre OPFOR;
- BATUS-era OPFOR;
- CENZUB opposing forces;
- the US 11th Armoured Cavalry Regiment.

Those organisations/examples inform the concept.

The Arma faction remains a UKSF-created training abstraction.

---

# PART III — DESIGN PRINCIPLE

## 10. Threat-Adaptive Rather Than Country-Specific

The central design rule is:

> **EXFOR portrays a threat profile, not a nationality.**

The same faction should be capable of representing:

- generic peer enemy;
- Eastern-style conventional enemy;
- irregular enemy;
- militia;
- lightly equipped regional force;
- urban adversary;
- hybrid threat.

The mission briefing defines what the training audience is meant to interpret EXFOR as.

---

## 11. Physical Equipment vs Simulated Capability

Real training can use simulation to make one platform represent another.

For Arma we have two approaches.

### Direct Representation

Use the actual game asset closest to the simulated threat.

Example:

```text
Eastern-pattern rifle
Eastern-pattern armoured vehicle
```

### Exercise Representation

Use a training/UK vehicle but describe or configure it as representing another capability.

Example concept:

```text
Warrior / training IFV
      ↓
Exercise role:
"Enemy IFV"
```

Both approaches should be supported.

EXFOR should not force mission makers into either one.

---

# PART IV — THREAT PROFILES

## 12. EXFOR Baseline

The **baseline EXFOR** represents the training cadre itself.

This is the most important sub-profile.

Appearance:

- British/NATO-style training clothing;
- exercise identifiers;
- normal tactical equipment;
- potentially British weapons;
- no attempt to portray a specific foreign country visually.

Use:

- force-on-force UK exercises;
- CQB/FIBUA training;
- generic enemy serials;
- range/training missions.

---

## 13. Profile A — Conventional / Peer

Working profile ID:

```text
EXFOR_PEER
```

Purpose:

Represent a modern conventional enemy.

Visual direction:

- coherent camouflage;
- helmets;
- body armour;
- modern rifles;
- machine guns;
- anti-armour;
- drones;
- conventional vehicles.

The profile should remain **generic enough** that it does not permanently represent Russia, China or another named real state.

For a particular exercise, mission designers can decide what the threat represents.

---

## 14. Profile B — Irregular

Working profile ID:

```text
EXFOR_IRREGULAR
```

Purpose:

Represent irregular combatants during UK exercises.

Visual direction:

- mixed civilian/military clothing;
- chest rigs;
- older weapons;
- pickups;
- technicals;
- little standardisation.

This profile may reuse many shared `UKSF_Factions` character assets also used by NTEF or future insurgent factions.

### Important distinction

EXFOR Irregular is **training equipment**, not NTEF.

It should avoid:

- NTEF insignia;
- NTEF flag;
- permanent NTEF identity elements.

---

## 15. Profile C — Militia / Hybrid

Working profile ID:

```text
EXFOR_HYBRID
```

Purpose:

Represent a force between irregular militia and conventional military.

Possible visual traits:

- mixed military clothing;
- more body armour than irregular profile;
- modern radios;
- mixed Eastern/Western weapons;
- SUVs;
- pickups;
- selected protected vehicles;
- drone capability.

This is useful for contemporary training without tying the scenario to one real country.

---

## 16. Role-Player / Civilian Profile

Working concept:

```text
EXFOR_ROLEPLAY
```

Status:

`DEFER / POSSIBLE FUTURE COMPONENT`

Research supports training forces being able to portray civilian populations and other non-combatant roles.

However, this is not required for the first EXFOR release.

If later implemented, role-player civilians should probably be:

- CIVILIAN side;
- separate from hostile EXFOR combat units;
- clearly organised in the editor.

Do not place armed and unarmed role-players into one confusing faction category.

---

# PART V — VISUAL IDENTITY

## 17. Training Force Look

EXFOR needs enough visual identity that UKSF players immediately understand:

> "This is the exercise enemy."

It should **not** resemble a fictional foreign army during every scenario.

The strongest baseline is:

```text
British / NATO training equipment
+
visible exercise identifier
```

---

## 18. Exercise Identifiers

Potential project-created identifiers:

- coloured arm bands;
- helmet bands;
- removable shoulder patches;
- coloured tape;
- simple EXFOR patch;
- small vehicle panels/markings.

### Current preferred colour

**Red** is the obvious candidate because of conventional "Red Force" terminology.

However, the faction should not hardcode all visual assets around red until tested against:

- MTP;
- woodland environments;
- urban environments;
- night/NVG use.

Possible alternate/secondary training colours:

- yellow;
- orange;
- blue;

for different exercise roles.

---

## 19. EXFOR Insignia

Unlike NTEF, EXFOR does not need an ideological emblem.

The insignia should look like a military training identifier.

Potential design:

- simple geometric shield;
- `EXFOR` text;
- stylised opposing arrows;
- red field;
- white/black detail.

Avoid:

- fake foreign heraldry;
- aggressive ideological imagery;
- skull-heavy "PMC" aesthetics.

---

## 20. Flag

A physical faction flag is **optional**.

EXFOR is a training construct, not a state.

If a flag is created, it should be treated as an:

```text
Exercise Control / OPFOR identification flag
```

rather than a national banner.

---

# PART VI — EQUIPMENT PHILOSOPHY

## 21. Baseline EXFOR Equipment

Baseline EXFOR should be capable of using standard UK training equipment.

Potential appearance:

- MTP or other unit-owned training uniform;
- helmet;
- plate carrier/webbing;
- eye protection;
- exercise identifier;
- British/NATO weapon.

This closely reflects the fact that real British soldiers assigned to OPFOR do not always receive completely foreign-looking clothing and equipment.

---

## 22. Threat Equipment

Threat-profile variants may use actual threat-representative equipment.

Examples:

### Peer

- Eastern-pattern rifles;
- Eastern-pattern machine guns;
- modern anti-armour;
- appropriate vehicles.

### Irregular

- AK family;
- chest rigs;
- mixed clothing;
- technical vehicles.

### Hybrid

- mixed Eastern/Western weapons;
- modern commercial equipment;
- varied vehicles.

These profiles should reuse assets already maintained elsewhere in `UKSF_Factions`.

---

# PART VII — WEAPON POLICY

## 23. Exercise Weapons

EXFOR should support two broad weapon families.

### Training-Cadre Weapons

British/NATO-style weapons.

Purpose:

- generic exercise enemy;
- UK-on-UK force-on-force;
- easier unit training setups.

### Threat-Profile Weapons

Weapons selected to represent the scenario threat.

Purpose:

- peer;
- irregular;
- hybrid exercise scenarios.

---

## 24. No Artificial Weapon Restriction

EXFOR should not have one fixed "canonical rifle."

That would undermine the faction's purpose.

Instead, weapon selection is part of the **threat profile**.

---

# PART VIII — VEHICLE POLICY

## 25. Training Vehicle Principle

Task Force Hannibal provides direct real-world precedent for representing enemy vehicle capabilities using British training vehicles and TES configuration.

Therefore EXFOR should support:

### Training Vehicles

British/UKSF-held vehicles acting as enemy vehicles.

### Threat Vehicles

Actual appropriate game assets representing the simulated enemy.

---

## 26. Conventional Vehicle Pool

Potential categories:

- light utility vehicle;
- protected mobility;
- APC;
- IFV;
- reconnaissance vehicle;
- logistic vehicle;
- tank where assets and exercise requirements justify it.

Do not lock a specific national vehicle family into EXFOR.

---

## 27. Irregular Vehicle Pool

Potential categories:

- pickup;
- technical;
- SUV;
- van;
- motorcycle;
- cargo truck.

These may share the generic vehicle library used by NTEF.

---

## 28. Simulated Vehicle Designations

A later optional mission-making system could provide description/attribute support such as:

```text
Physical asset:
Warrior

Exercise representation:
Enemy IFV
```

This is conceptually similar to TES capability representation.

### Status

`IDEA / NOT REQUIRED`

Do not write a scripting system until a clear usability need exists.

---

# PART IX — TECHNOLOGY

## 29. Drones

Modern British training increasingly incorporates UAS and counter-UAS threats.

Therefore peer/hybrid EXFOR profiles should support:

- reconnaissance drones;
- appropriate small UAS;
- simulated drone threat.

NTEF and EXFOR may share generic drone assets where suitable.

---

## 30. Electronic / Synthetic Effects

Real collective training can introduce synthetic capabilities that are not physically represented by the equipment in front of the trainee.

In Arma, examples may eventually include:

- simulated artillery;
- simulated electronic effects;
- Zeus-controlled sensor effects;
- scripted training injects.

These belong primarily to **mission design**, not EXFOR unit config.

The faction should not accumulate scripts trying to simulate every possible training effect.

---

# PART X — PERSONNEL STRUCTURE

## 31. Baseline Exercise Personnel

Recommended initial roles:

```text
Rifleman
Team Leader
Section Commander
Automatic Rifleman
Machine Gunner
Anti-Armour
Marksman
Medic
Engineer
Drone Operator
Driver
Crew
Commander
```

Exact naming will be aligned with the project-wide role standard.

---

## 32. Peer Profile Personnel

Potential editor classes:

```text
Peer Rifleman
Peer Team Leader
Peer Machine Gunner
Peer Anti-Armour
Peer Marksman
Peer Medic
Peer Engineer
Peer Drone Operator
Peer Crew
```

### Concern

This can quickly create editor clutter.

Preferred solution:

Do **not** create a complete duplicate role list for every profile until we know how we will implement loadout variants.

Possible future options include:

- separate subcategories;
- controlled profile scripts;
- a smaller set of preconfigured variants.

---

## 33. Irregular Profile Personnel

Potential roles:

```text
Irregular Fighter
Irregular Leader
Irregular Automatic Rifleman
Irregular Machine Gunner
Irregular Anti-Armour
Irregular Marksman
```

Again, keep the editor list restrained.

---

# PART XI — EDITOR DESIGN

## 34. Recommended Faction

`CfgFactionClasses`:

```cpp
UKSF_Factions_EXFOR
```

Display name:

```text
Exercise Force (EXFOR)
```

Default side:

```text
OPFOR
```

---

## 35. Recommended Editor Subcategories

Initial proposal:

```text
Men (Exercise)
Men (Peer)
Men (Irregular)
Vehicles (Exercise)
Vehicles (Peer)
Vehicles (Irregular)
Drones
```

This may still be too many.

### Lean alternative

```text
Men
Men (Irregular)
Vehicles
Drones
```

with peer/conventional as the standard baseline.

Final choice should be made after the first actual unit catalogue exists.

---

# PART XII — GROUPS

## 36. Baseline Groups

EXFOR should include immediately useful training groups.

Possible first release:

```text
Fire Team
Section
Weapons Team
Peer Section
Irregular Cell
Vehicle Patrol
Motorised Section
```

---

## 37. No Fixed Real-World Enemy TO&E Claim

EXFOR groups are **exercise templates**.

They should not be described as:

> "the Russian squad structure"

or:

> "the ISIS section structure."

Mission designers may use them to portray those threats, but `UKSF_Factions` should not claim detailed fidelity where the group is deliberately generic.

---

# PART XIII — TRAINING EFFECTS

## 38. Tactical Engagement Simulation Inspiration

The British Army's Tactical Engagement Simulation system allows exercise equipment and personnel to be instrumented for simulated combat effects.

For Arma, the engine itself already provides the principal simulation.

Therefore EXFOR does **not** need a complete TES recreation.

What we may want visually:

- exercise sensor harness;
- weapon training marker;
- helmet sensor;
- coloured exercise identifier.

These would be **cosmetic training assets**.

---

## 39. TES Visual Asset

Potential future bespoke asset:

```text
Training sensor harness / TES vest
```

This could become one of EXFOR's strongest visual identifiers.

### Value

It would make screenshots immediately read as:

```text
training exercise
```

rather than:

```text
actual combat
```

### Priority

`MEDIUM / HIGH`

This is likely more valuable than producing many unique EXFOR uniforms.

---

# PART XIV — DEAD / CASUALTY PRESENTATION

## 40. Exercise Casualties

EXFOR units should use normal Arma damage mechanics unless a future training mission system requires otherwise.

Do not build:

- artificial invulnerability;
- automatic revive;
- bespoke casualty scripting;

into the faction.

Exercise-control behaviour belongs to the mission/framework layer.

---

# PART XV — EXERCISE CONTROL

## 41. EXCON

A future role-player/support component could include:

- Exercise Controller;
- Observer/Mentor;
- Safety Staff;
- Range Staff.

### Status

`OPTIONAL / FUTURE`

These should not be hostile OPFOR classes.

If created, they may belong on:

```text
BLUFOR
CIVILIAN
```

depending on use.

---

# PART XVI — FRIEND/FOE RELATIONSHIPS

## 42. Default Relationship

EXFOR:

```text
OPFOR / EAST
```

Training audience:

```text
typically BLUFOR / WEST
```

This makes ordinary Arma AI behaviour useful without mission scripting.

---

## 43. Political Neutrality

EXFOR has **no political hostility** toward BLUFOR in lore.

The OPFOR relationship is purely an exercise mechanic.

Documentation and faction descriptions should make this clear.

---

# PART XVII — DEPENDENCIES

## 44. PBO

Future addon:

```text
uksf_factions_exfor
```

Patch class:

```cpp
UKSF_Factions_EXFOR
```

Expected project dependencies:

```text
UKSF_Factions_Core
UKSF_Factions_Characters
UKSF_Factions_Vehicles
```

---

## 45. External Dependencies

EXFOR should avoid adding unique large dependencies where possible.

It should primarily reuse:

- project shared characters;
- project shared vehicles;
- weapons already used by the UKSF modset.

Because EXFOR is a training faction, it is particularly well suited to asset reuse.

---

# PART XVIII — ASSET REQUIREMENTS

## 46. Essential New Assets

EXFOR does **not** need a huge original gear library.

Most important bespoke assets are likely:

### 1. Exercise identification system

- arm bands;
- helmet bands;
- patches;
- tape.

### 2. EXFOR patch/icon

- simple;
- military;
- non-political.

### 3. Training/TES-style harness

Optional but high value.

### 4. Vehicle exercise markings

- removable panels;
- small red-force marks;
- exercise numbers.

---

## 47. Shared Assets

EXFOR should make heavy use of:

```text
uksf_factions_characters
uksf_factions_vehicles
```

This makes it a highly efficient second faction.

It can reuse:

- helmets;
- plate carriers;
- uniforms;
- Eastern weapons;
- pickups;
- technicals;
- conventional vehicles;

with different combinations and markings.

---

# PART XIX — TRAINING PROFILE MATRIX

## 48. Baseline Exercise

| Attribute | Baseline |
|---|---|
| Clothing | British/NATO training |
| Armour | Common |
| Helmet | Common |
| Weapon | British/NATO |
| NVG | Scenario dependent |
| Radios | Normal military |
| Vehicles | UK/training fleet |
| Identifier | Strong |
| Political identity | None |

---

## 49. Peer Threat

| Attribute | Peer |
|---|---|
| Clothing | coherent military |
| Armour | common |
| Helmet | common |
| Weapon | scenario threat |
| Optics | common |
| NVG | available |
| Drones | available |
| Vehicles | conventional |
| Identifier | optional exercise mark |
| Political identity | none |

---

## 50. Irregular Threat

| Attribute | Irregular |
|---|---|
| Clothing | mixed civilian/military |
| Armour | limited |
| Helmet | uncommon |
| Weapon | AK/regional |
| Optics | limited |
| NVG | rare |
| Drones | optional |
| Vehicles | pickup/technical |
| Identifier | exercise mark recommended |
| Political identity | none |

---

## 51. Hybrid Threat

| Attribute | Hybrid |
|---|---|
| Clothing | mixed military |
| Armour | moderate/common |
| Helmet | moderate |
| Weapon | mixed |
| Optics | moderate |
| NVG | limited/moderate |
| Drones | available |
| Vehicles | mixed civilian/protected |
| Identifier | exercise mark |
| Political identity | none |

---

# PART XX — VISUAL DIFFERENTIATION FROM UKSF

## 52. Problem

If baseline EXFOR uses British-style gear, it must remain immediately distinguishable from the UKSF training audience.

This is crucial in Arma because:

- uniform silhouettes may be similar;
- weapon silhouettes may be similar;
- AI side alone is not enough for human recognition.

---

## 53. Required Identification Layer

Baseline EXFOR should therefore use at least two consistent visual identifiers.

Examples:

```text
red arm band
+
EXFOR shoulder patch
```

or:

```text
helmet band
+
vest identifier
```

At night, mission makers may choose identifiers appropriate to the training scenario.

Do not create glowing markers that destroy realistic night training unless intentionally enabled by the mission.

---

# PART XXI — VEHICLE DIFFERENTIATION

## 54. Exercise Vehicle Markings

When EXFOR uses the same base vehicle family as BLUFOR:

use visible temporary-style markings.

Possible design:

- red rectangle;
- red circle;
- EXFOR stencil;
- numbered exercise panel.

Avoid permanent-looking enemy camouflage if the vehicle is meant to represent a British training fleet asset.

---

# PART XXII — FACTION DESCRIPTION

## 55. Working Editor/Public Description

Suggested:

> **Exercise Force (EXFOR)** is a configurable opposing force used to represent contemporary threats during British military training. EXFOR personnel and equipment can portray conventional, irregular and hybrid adversaries depending on the exercise scenario. The faction has no fixed national or political identity.

This is concise enough for README/editor documentation.

---

# PART XXIII — LORE STATUS

## 56. Classification

EXFOR is not normal Armaverse geopolitical lore.

Use:

```text
REAL-WORLD TRAINING INSPIRATION:
British collective training / OPFOR concepts.

UKSF PROJECT ABSTRACTION:
Exercise Force (EXFOR).
```

Do not try to integrate EXFOR into Takistani or Chernarussian political history.

---

# PART XXIV — RELATIONSHIP TO NTEF

## 57. Reuse

NTEF assets may inform or support EXFOR irregular scenarios.

Possible shared items:

- regional uniforms;
- chest rigs;
- AKs;
- pickups;
- technicals.

---

## 58. Separation

Never give EXFOR Irregular:

- NTEF insignia;
- NTEF flag;
- NTEF faction-specific vehicle markings.

The exercise profile should remain politically generic.

---

# PART XXV — EXFOR-SPECIFIC ORIGINAL ART

## 59. Artwork Priority

Suggested order:

1. EXFOR patch;
2. arm-band/tape identification texture;
3. editor icon;
4. helmet-band variant;
5. vehicle training stencil;
6. TES-style sensor harness if modelled;
7. optional exercise flag.

This is considerably lighter than the NTEF art requirement.

---

# PART XXVI — IMPLEMENTATION STRATEGY

## 60. First Release Scope

The first EXFOR release should be intentionally small.

Recommended initial scope:

### Infantry

- Rifleman;
- Team Leader;
- Automatic Rifleman;
- Machine Gunner;
- Anti-Armour;
- Marksman;
- Medic;
- Drone Operator.

### Vehicles

- utility vehicle;
- protected vehicle;
- conventional transport;
- optional IFV depending on available assets.

### Visuals

- EXFOR identifier set;
- EXFOR patch/icon.

### Groups

- Fire Team;
- Section;
- Weapons Team;
- Vehicle Patrol.

---

## 61. Irregular Profile Timing

Do not prioritise EXFOR irregular assets until NTEF shared character assets are available.

Once NTEF gear exists, EXFOR irregular becomes comparatively cheap to implement through:

- neutral combinations;
- removal of faction insignia;
- exercise identifiers.

---

# PART XXVII — WHAT EXFOR SHOULD NOT BECOME

## 62. Fake Russian Army

Do not make the faction permanently:

- Russian camouflage;
- Russian equipment;
- Russian insignia substitute;
- Russian-only vehicle pool.

Task Force Hannibal represented Russia for one specific exercise.

EXFOR should represent **the function**, not that specific scenario.

---

## 63. Second UKSF Faction

Do not simply duplicate the UKSF player faction and change the side to OPFOR.

EXFOR needs:

- clear exercise markings;
- distinct groups;
- training-focused identity;
- optional threat profiles.

---

## 64. PMC Faction

Avoid:

- baseball caps everywhere;
- black multicam;
- skull insignia;
- private-contractor aesthetics.

This is a military training enemy, not a mercenary group.

---

## 65. Target Dummies

EXFOR must not be designed to lose.

The point of credible OPFOR is to challenge the training audience.

That is one of the clearest themes in current British and allied collective-training reporting.

---

# PART XXVIII — CURRENT LOCKED DECISIONS

## 66. Locked

- Working faction name is `Exercise Force`.
- Acronym/internal ID is `EXFOR`.
- Faction is a training construct, not a fictional country.
- Default Arma side is OPFOR/EAST.
- EXFOR has no political ideology.
- EXFOR should be threat-adaptive.
- Baseline EXFOR represents the training cadre.
- Peer, Irregular and Hybrid profiles are supported conceptually.
- Civilian/role-player capability is deferred.
- EXFOR can use British/NATO-style gear.
- Physical equipment does not need to exactly match the simulated threat.
- Exercise identifiers are required where EXFOR resembles BLUFOR.
- Red is the current preferred exercise identifier colour.
- Conventional peer profile must remain politically generic.
- Irregular profile must not reuse NTEF-specific insignia.
- Drones are appropriate for contemporary peer/hybrid training.
- TES itself will not be recreated as a complex gameplay system.
- A TES-style visual harness is a worthwhile future asset.
- `uksf_factions_exfor` will be a separate faction PBO.
- EXFOR should primarily reuse shared project assets rather than create a second gear library.

---

# PART XXIX — OPEN DECISIONS

## 67. Resolve Before Config

- [ ] Confirm `Exercise Force (EXFOR)` as final display name.
- [ ] Decide final editor subcategories.
- [ ] Decide whether Peer is the baseline profile or a separate profile.
- [ ] Decide exact baseline uniform family.
- [ ] Decide exact exercise identifier colour.
- [ ] Decide whether identifiers are arm bands, helmet bands, patches, tape or combination.
- [ ] Design EXFOR patch.
- [ ] Design EXFOR editor icon.
- [ ] Decide whether vehicle exercise markings are hidden-selection variants.
- [ ] Decide baseline British/NATO weapon pool.
- [ ] Decide Peer threat weapon pool.
- [ ] Decide whether peer vehicle classes use actual threat vehicles or exercise-simulated UK vehicles.
- [ ] Decide whether a TES-style sensor harness is worth modelling.
- [ ] Decide whether Observer/Mentor/EXCON personnel belong in this project.
- [ ] Decide whether civilian role-players become a separate future faction/category.
- [ ] Define first-release group catalogue.
- [ ] Define EXFOR asset/dependency audit after NTEF asset collection begins.

---

# PART XXX — RESEARCH SOURCES

Research reviewed 2026-08-09.

## British Army — Land Warfare Centre

The current Land Warfare Centre page describes Collective Training Group as the Field Army's training delivery arm and states that collective training facilities, together with the Contemporary Operating Environment Force and training fleet, create training against a well-equipped modern enemy.

```text
https://www.army.mod.uk/learn-and-explore/about-the-army/formations-divisions-and-brigades/land-warfare-centre/
```

---

## Soldier / British Army — Task Force Hannibal

Current Soldier reporting from September 2025 describes approximately 250 personnel acting as OPFOR during Exercise Iron Storm on Salisbury Plain.

Task Force Hannibal was prepared to represent Russian ground forces and used Warriors whose capabilities were represented through the Tactical Engagement Simulation system as BMP-2s.

```text
https://soldier.army.mod.uk/issues/september-2025/update/global-sitrep/uk
```

and:

```text
https://soldier.army.mod.uk/issues/september-2025/update/ex-iron-storm
```

---

## British Army — Combat Ready Training Centre Exercise, Germany

British Army reporting from 2023 describes a combined German opposing force and British infantry company acting as the enemy, with different equipment/tactics and synthetic surveillance effects used to test the training audience.

```text
https://www.army.mod.uk/news/1-royal-welsh-battlegroup-tackles-demands-of-training-areas-in-germany/
```

---

## Soldier / British Army — CENZUB

2026 Soldier reporting describes CENZUB's in-house opposing force as a mixed company with infantry, engineers and several platform types.

The force can portray:

- combat formations;
- militia;
- civilians/refugees;

depending on the exercise requirement.

```text
https://soldier.army.mod.uk/issues/jan-26/soldier-life/cenzub
```

---

## Soldier / British Army — US National Training Centre

2025 Soldier reporting describes the US 11th Armoured Cavalry Regiment as a dedicated professional OPFOR at the National Training Centre, configured to represent a realistic peer threat during British experimentation.

```text
https://soldier.army.mod.uk/issues/may-2025/updates/rise-of-the-machines
```

---

## British Army — Exercise Gaulish / CENZUB

British Army reporting from February/March 2026 describes British and French force-on-force urban training using the Tactical Engagement Simulation System and drone capability.

```text
https://www.army.mod.uk/news/british-and-french-allies-ready-to-defend-nato-territory/
```

```text
https://www.army.mod.uk/news/teenage-female-infanteer-trains-new-leadership-role-in-warfighting-exercise/
```

---

# PART XXXI — CURRENT CONCLUSION

EXFOR should be built around the principle:

```text
EXERCISE FORCE
      │
      ├── Baseline Training Cadre
      │
      ├── Peer Threat Profile
      │
      ├── Irregular Threat Profile
      │
      └── Hybrid Threat Profile
```

rather than:

```text
FAKE COUNTRY ARMY
```

The key real-world lesson from contemporary British training is that the opposing force is configured to provide the **required training effect**.

Personnel may use their existing equipment.

Vehicles may be simulated as different threat platforms.

The force may portray conventional formations, militia or civilians depending on the training objective.

That makes EXFOR extremely well suited to `UKSF_Factions` because it can reuse the project's shared asset library while providing a completely different mission-making role.

The next EXFOR document should eventually be an **asset/dependency audit**, but it is sensible to defer that until more of the shared NTEF/character asset library is known.

For the immediate research/admin phase, the strongest next task is either:

1. deepen NTEF lore and North Takistan theatre research; or
2. create the project-wide release/credits/documentation standard.
