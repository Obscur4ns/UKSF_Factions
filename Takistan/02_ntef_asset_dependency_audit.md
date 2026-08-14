# UKSF_Factions — Asset & Dependency Audit 01
## Northern Takistan Emirate Front (NTEF)

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Asset & Dependency Audit 01  
**Status:** Research / Pre-production  
**Date:** 2026-08-09  
**Faction:** Northern Takistan Emirate Front (NTEF)  
**Related document:** `01_north_takistan_extremist_research_brief.md`

---

## 1. Purpose

This document audits the asset categories required to build the first `UKSF_Factions` faction and records likely existing sources before any faction configuration is written.

The aim is to determine:

- what can be referenced from mods already used by the unit;
- what can be sourced from established Arma 3 content packs;
- what would benefit from purpose-built or externally sourced assets;
- what should remain optional;
- what dependencies would be imposed on the final faction;
- whether each external asset is legally and technically suitable for redistribution.

This audit is deliberately **not Workshop-only**.

Assets may eventually come from:

- Arma 3 vanilla/DLC content;
- established Workshop mods used as dependencies;
- non-Workshop Arma mods;
- donated source assets;
- original `UKSF_Factions` work;
- appropriately licensed source packages;
- other games **only where the rightsholder or applicable licence explicitly permits the intended use and redistribution**.

No third-party asset should be committed to the public repository merely because it can be extracted or converted.

---

## 2. Dependency Philosophy

`UKSF_Factions` should avoid unnecessary mandatory dependencies.

The preferred order is:

1. use content already present in the unit's normal modset;
2. reference stable third-party classes where that dependency is already justified;
3. create or obtain permission for missing signature assets;
4. avoid introducing a large content pack for only one or two items;
5. keep faction config separate from third-party source data;
6. never repack another mod's PBOs into `UKSF_Factions`.

A dependency and an incorporated asset are **not the same thing**.

### Dependency

`UKSF_Factions` references a class supplied by another installed mod.

Example:

```cpp
weapons[] = {"rhs_weap_akm"};
```

The original mod remains installed separately.

### Incorporated asset

A model, texture, material, sound, animation or other source file is physically included inside `UKSF_Factions`.

This requires suitable redistribution and derivative-work rights or explicit permission.

---

## 3. Current Candidate Content Stacks

## 3.1 RHS

### Candidate packs

- RHS: Armed Forces of the Russian Federation (`RHSAFRF`)
- RHS: Green Forces (`RHSGREF`)
- RHS: United States Armed Forces (`RHSUSAF`)
- RHS: Serbian Armed Forces (`RHSSAF`)

### NTEF value

**Very high for weapons.**

RHS documentation currently lists several weapon families directly relevant to the NTEF design:

- AKM
- AK-74M
- AK-103
- PKM
- PKP
- RPG-7
- RPG-18
- RPG-26
- SVD

This is an excellent baseline for a contemporary regional arsenal.

### Proposed use

**Reference as dependency classes only.**

Do not copy RHS models, textures or other protected content into `UKSF_Factions` unless a specific file's licence permits that use or RHS grants permission.

### Licence note

The current RHS Arma 3 EULA states that most of the distribution is under **CC BY-NC-ND 4.0**, with separately listed PBOs under other licences.

It also prohibits third-party distribution of the package on Steam Workshop and places restrictions on derivatives/retextures.

Therefore:

**Status:** `REFERENCE ONLY BY DEFAULT`

---

## 3.2 3CB Factions

### Current dependency chain

The current 3CB Factions Workshop release lists:

- CBA_A3
- RHSAFRF
- RHSGREF
- RHSUSAF
- RHSSAF

as required items.

This makes 3CB Factions a substantial dependency if the unit is not already running that stack.

### NTEF value

**Extremely high.**

The current pack already contains complete factions relevant to our environment, including:

- Afghan National Army;
- Afghan police organisations;
- Ardistan Army;
- Karzeghistan Royal Guard;
- Middle East Civilians;
- Middle East Insurgents;
- Middle East Extremists;
- Takistan Civilians;
- Takistan National Army;
- Takistan police organisations;
- Takistan Tribal Fighters;
- Takistan Insurgents.

It also contains a large set of additional weapons, vehicles and reskins.

The published changelog specifically confirms weaponised variants of:

- Hilux;
- Pickup;
- Land Rover;

including SPG-9 configurations.

Other relevant additions across releases include:

- RPD;
- RPK variants;
- FN FAL variants;
- G3-related content;
- SKS-related content;
- motorcycles / motorbike work in the wider asset set;
- civilian and regional vehicles;
- multiple uniform, vest, headgear and facegear reskins.

### Proposed use

3CB Factions should be treated as a **high-value class dependency/reference**, especially if it is already part of the unit modset.

Potential roles:

- civilian/traditional clothing reference classes;
- Middle Eastern headwear and facewear;
- Hilux/Pickup/Land Rover technicals;
- civilian regional vehicles;
- selected weapons not provided by RHS;
- useful base classes for faction configuration where permitted.

### Important licence note

3CB states that its released work is licensed under **CC BY-NC-ND 4.0** and specifically asks users to contact them for permission to modify their work.

Therefore:

- referencing installed 3CB classes is acceptable as normal mod dependency use;
- copying/repacking 3CB source assets into `UKSF_Factions` should **not** be assumed permitted;
- retextures or derivatives should only be produced where the licence or explicit 3CB permission permits them.

**Status:** `HIGH-VALUE DEPENDENCY CANDIDATE — NO REPACKING`

---

## 3.3 CUP

### Candidate packs

- CUP Weapons
- CUP Units
- CUP Vehicles

### Dependency behaviour

CUP's current FAQ states:

- CUP Weapons requires CBA_A3;
- CUP Units requires CUP Weapons;
- CUP Vehicles requires CUP Units.

Therefore using a CUP vehicle effectively brings the Weapons → Units → Vehicles chain.

CUP also explicitly states that custom "light" repacks of CUP content are not permitted.

### NTEF value

Potentially high because CUP preserves and upgrades large amounts of earlier Armaverse content.

Relevant broad categories include:

- Takistani-era clothing;
- legacy regional weapons;
- civilian vehicles;
- pickups and utility vehicles;
- backpacks/headgear;
- props;
- earlier Arma 2/OA visual material.

CUP's asset list documents weapons, clothing, units, vehicles, items and props in a searchable catalogue.

### Proposed use

CUP should be treated as an **optional candidate**, not a baseline requirement yet.

Reason:

- it may contain individual assets we want;
- but the dependency chain is significant;
- much of its functional space overlaps with RHS + 3CB Factions;
- we should not make CUP mandatory merely for one vehicle or garment.

### Licence note

CUP Weapons/Units/Vehicles use the CUP licence, and the CUP FAQ expressly forbids custom repacks/light packages.

**Status:** `OPTIONAL — REVIEW ITEM BY ITEM`

---

## 3.4 Vanilla Arma 3 / official DLC

### NTEF value

Always consider vanilla first where visually suitable.

Potential categories:

- civilian clothing;
- civilian vehicles;
- backpacks;
- generic tactical equipment;
- radios/utility props;
- unarmed off-road vehicles;
- vans;
- SUVs;
- civilian headwear;
- selected plate carriers;
- simple optics;
- environmental props.

### Advantages

- no additional mod dependency;
- stable class names;
- easy Zeus/Eden support;
- good fallback equipment;
- useful for civilian and low-tier fighter variation.

### Limitation

Much of the vanilla 2035 military aesthetic is too futuristic for the intended contemporary 2026 appearance.

**Status:** `USE WHERE VISUALLY APPROPRIATE`

---

## 4. Initial Recommended Dependency Strategy

No dependency list is locked yet.

### Preferred strategy A — Existing unit stack

If the unit already runs:

- CBA_A3;
- RHSAFRF;
- RHSGREF;
- RHSUSAF;
- RHSSAF;
- 3CB Factions;

then NTEF should initially build on those assets and avoid CUP unless a clear gap appears.

This offers the strongest ready-made regional asset pool with the lowest **additional** burden.

### Preferred strategy B — Leaner custom faction

If 3CB Factions is not already part of the deployment modset:

- use RHS weapon classes;
- use vanilla civilian assets where suitable;
- add purpose-built / properly licensed external clothing and vehicle assets;
- avoid pulling in an entire faction pack solely for visual variety.

### Strategy C — CUP-backed

Only choose CUP as a core requirement if the actual asset audit shows that several essential NTEF categories depend on CUP content.

---

## 5. Asset Requirement Matrix

Legend:

- `READY` — obvious suitable source exists.
- `CANDIDATE` — likely source identified, needs in-game review.
- `GAP` — should actively seek/create an asset.
- `OPTIONAL` — useful but not necessary for first release.
- `TBD` — cannot decide until available assets are inspected.

| Category | Requirement | Initial source candidates | Status |
|---|---|---|---|
| Traditional male clothing | loose regional shirt/trousers | 3CB Factions, CUP, external | CANDIDATE |
| Civilian shirts | muted modern civilian tops | Vanilla, 3CB, external | READY |
| Civilian trousers | jeans/cargo/plain trousers | Vanilla, 3CB, external | READY |
| Field jackets | old military/civilian layers | RHS/3CB/external | CANDIDATE |
| Surplus camouflage uniforms | mixed regional surplus | RHS, 3CB, external | CANDIDATE |
| Dark assault clothing | veteran cadre | 3CB/external/original | CANDIDATE |
| Simple chest rigs | AK-centric | RHS, 3CB, external | READY |
| Old webbing | low-tier fighters | 3CB/CUP/external | CANDIDATE |
| Modern plate carriers | limited veteran use | Vanilla, RHS, 3CB | READY |
| Pakol/regional hats | visual priority | 3CB/CUP/external | CANDIDATE |
| Scarves/wraps | visual priority | 3CB/external | CANDIDATE |
| Face coverings | moderate variety | 3CB, RHS, external | READY |
| Knit caps | low-tier variation | Vanilla/3CB | READY |
| Civilian caps | limited | Vanilla/3CB | READY |
| Older helmets | captured/surplus | RHS, 3CB | READY |
| Modern helmets | rare veteran use | RHS/3CB/Vanilla | READY |
| Sandals | regional visual priority | external / existing regional pack | GAP |
| Trainers | civilian variation | Vanilla/3CB/external | CANDIDATE |
| Military boots | core/veteran | existing uniforms | READY |
| AKM family | primary rifle | RHS | READY |
| AK-74 family | secondary rifle family | RHS | READY |
| AK-100 family | veteran/core | RHS | READY |
| Compact AK | specialist/vehicle | RHS/3CB | CANDIDATE |
| PKM | primary GPMG | RHS | READY |
| RPK/RPD | automatic rifle role | RHS/3CB | READY |
| SVD | marksman | RHS | READY |
| Older bolt rifle | low-tier/marksman flavour | 3CB/CUP | OPTIONAL |
| SKS | low-tier flavour | 3CB/CUP/RHS-family review | CANDIDATE |
| FAL | captured/regional minority | 3CB/CUP | CANDIDATE |
| G3 | captured/regional minority | 3CB/CUP | CANDIDATE |
| Western AR | rare captured weapon | RHS/Vanilla/3CB | READY |
| RPG-7 | standard launcher | RHS | READY |
| Disposable launcher | limited specialist | RHS | READY |
| Pistols | leadership/specialist | RHS/3CB/Vanilla | READY |
| Basic optics | limited core use | RHS/3CB/Vanilla | READY |
| Modern optics | veteran only | RHS/3CB | READY |
| Suppressors | very limited | RHS/3CB | READY |
| Handheld radio prop/item | hierarchy indicator | ACRE/other existing content | TBD |
| NVGs | rare veteran/specialist | RHS/3CB/Vanilla | READY |
| Thermal devices | exceptional only | existing content | OPTIONAL |
| Civilian pickup | faction backbone | 3CB/Vanilla/CUP/external | READY |
| Armed technical | faction backbone | 3CB/CUP/external | READY |
| SUV | transport/leadership | Vanilla/3CB | READY |
| Van | logistics/civilian cover | Vanilla/3CB | READY |
| Utility truck | logistics | RHS/3CB/CUP | READY |
| Motorcycle | high-value regional asset | 3CB/external | CANDIDATE |
| Captured military utility | rare | RHS/3CB | READY |
| Captured protected vehicle | scenario-specific | RHS/3CB | OPTIONAL |
| Commercial quadcopter | atmosphere/recon role | Vanilla/mod dependency | CANDIDATE |
| Faction flag | bespoke | UKSF_Factions original | GAP |
| Faction patch | bespoke | UKSF_Factions original | GAP |
| Editor icon | bespoke | UKSF_Factions original | GAP |
| Vehicle stencil | bespoke | UKSF_Factions original | GAP |
| Graffiti/marker set | bespoke | UKSF_Factions original | OPTIONAL |
| Civilian regional faces | visual diversity | Vanilla/3CB/external | CANDIDATE |
| Backpacks/sacks | low-tier and logistics | RHS/3CB/CUP/Vanilla | READY |

---

## 6. Visual Priority Gaps

The audit suggests that **weapons are not the problem**.

The most important visual gaps are likely to be:

### Priority 1 — Clothing silhouette

We need enough regional clothing to prevent NTEF looking like ordinary Arma riflemen carrying AKs.

Highest-value items:

- convincing loose regional shirts;
- loose trousers;
- layered field jackets;
- muted civilian clothing;
- dark but non-uniform assault clothing.

### Priority 2 — Footwear

Sandals and appropriate civilian footwear are useful because they significantly change the silhouette of low-tier fighters.

This is a strong candidate for an external/original asset if existing dependencies do not provide good options.

### Priority 3 — Headwear

A strong selection of:

- regional caps;
- pakol-style headwear;
- scarves;
- wraps;
- simple face coverings;

will probably contribute more to the faction's identity than additional weapon models.

### Priority 4 — Technical vehicle variety

We should aim for several visual states rather than one repeated technical:

- clean civilian pickup;
- worn civilian pickup;
- cargo pickup;
- light weapon technical;
- heavier technical;
- command/leadership SUV;
- utility van/truck.

### Priority 5 — Original faction markings

The final faction needs its own:

- emblem;
- flag;
- patch;
- editor icon.

These should be `UKSF_Factions` original assets and therefore have no dependency.

---

## 7. External / Non-Workshop Asset Intake

The user expects additional assets from sources outside the normal Workshop ecosystem.

Every proposed incorporated asset should receive an entry in an asset register **before it is committed**.

### Required metadata

| Field | Requirement |
|---|---|
| Asset ID | Internal unique identifier |
| Asset type | Model / texture / material / sound / animation / other |
| Original title | Name of original work/game/mod |
| Original creator | Author/studio/rightsholder |
| Source location | Where the source was obtained |
| Source version | Version/build/date if known |
| Original licence | Exact licence or permission basis |
| Modification allowed | Yes / No / Conditional |
| Arma conversion allowed | Yes / No / Conditional |
| Redistribution allowed | Yes / No / Conditional |
| Public GitHub source allowed | Yes / No / Conditional |
| Steam Workshop distribution allowed | Yes / No / Conditional |
| Attribution required | Exact credit wording |
| Permission evidence | File/email/message/screenshot reference |
| Changes made | What UKSF modified |
| Final path | Location inside project |
| Status | Pending / Approved / Rejected |

### Approval rule

An incorporated external asset is `APPROVED` only when we can answer:

1. Who owns it?
2. What licence applies?
3. Are derivatives/conversions permitted?
4. Is redistribution permitted?
5. Is redistribution on the intended platform permitted?
6. What attribution is required?
7. Do we possess evidence of any special permission?

If those answers are unknown, the asset remains `PENDING` and should not enter a public release branch.

---

## 8. Assets From Other Games

Owning or having access to another game does **not** by itself establish permission to extract and redistribute its assets.

For `UKSF_Factions`, assets from another game should only be incorporated where:

- the developer/rightsholder has released the asset under a suitable licence;
- an official modding/source package explicitly allows the conversion/use;
- the rightsholder has granted permission;
- or another clear permission basis exists.

Bohemia's own rules similarly distinguish normal game content from material released through licensed data packages; the official Arma licensing framework defines specific licences such as APL and APL-SA for content that may be adapted under their conditions.

### Repository rule

Do **not** place questionable third-party game source files in Git history while permission is being investigated.

Use a local staging directory outside the repository until approval.

Suggested local-only structure:

```text
_external_staging/
    pending/
    approved/
    rejected/
```

Add `_external_staging/` to `.gitignore`.

Approved source assets can then be moved into the project only when their licence permits repository distribution.

---

## 9. Mod Asset Permissions

### RHS

Default assumption:

`DEPENDENCY / CLASS REFERENCE ONLY`

Do not extract and repack RHS content based solely on having the mod installed.

### 3CB

Default assumption:

`DEPENDENCY / CLASS REFERENCE ONLY`

3CB's published licence is CC BY-NC-ND 4.0 and specifically directs users to contact 3CB for permission to modify their work.

### CUP

Default assumption:

`DEPENDENCY / CLASS REFERENCE ONLY`

CUP explicitly prohibits custom "light" repacks.

Any use beyond ordinary dependency/reference use must be checked against the applicable CUP licence and asset provenance.

### Donated/private mod assets

Default assumption:

`PENDING UNTIL PERMISSION RECORDED`

A private download link or access to unbinarised source does not automatically establish redistribution rights.

---

## 10. Recommended Repository Structure

Initial documentation structure:

```text
UKSF_Factions/
├── docs/
│   ├── factions/
│   │   └── north_takistan/
│   │       ├── 01_north_takistan_extremist_research_brief.md
│   │       └── 02_ntef_asset_dependency_audit.md
│   └── assets/
│       ├── asset_register.md
│       ├── permissions/
│       └── credits.md
├── UKSF_Factions/
│   └── ...
└── .gitignore
```

The `permissions/` directory should contain **only permission records safe and appropriate to store publicly**.

Private email addresses, personal information, purchase records, private download links and similar material should not be committed.

A public permission record can instead state:

```text
Asset: Example Vehicle
Author: Example Author
Permission: Modification and redistribution in UKSF_Factions approved
Date: YYYY-MM-DD
Evidence: Maintained privately by UKSF Surplus
Required credit: Example Author
```

---

## 11. Proposed Asset Source Ranking

For each required item, use this decision order:

### 1. Existing dependency

Does a mod already required by the unit contain a good asset?

If yes, reference it.

### 2. Vanilla / official content

Can an acceptable asset be used without adding a dependency?

If yes, prefer it where visually appropriate.

### 3. Original UKSF asset

Is the missing item distinctive enough to justify making our own?

Strong candidates:

- insignia;
- flags;
- patches;
- editor icons;
- simple textures;
- faction-specific reskins of assets we have rights to modify.

### 4. Donated / permissively licensed Arma asset

Use where quality and permissions are suitable.

### 5. External game/source asset

Only where the permission chain is explicit and the asset provides enough value to justify conversion work.

### 6. New dependency

Add another large third-party dependency only when it solves several important gaps.

---

## 12. First-Pass Dependency Recommendations

### Strong candidate

**RHS weapon ecosystem**

Reason:

The NTEF weapon requirement is almost completely covered by existing RHS families.

### Strong candidate if already in unit modset

**3CB Factions**

Reason:

It contains a very large amount of immediately relevant Middle East/Takistan/Afghanistan clothing, faction, weapon and vehicle material, including technicals.

### Hold

**CUP**

Do not require it yet.

Review only if the first in-game asset survey finds important visual gaps not covered by the existing stack.

### Always available

**Vanilla Arma 3 / owned official DLC**

Use for civilian and generic equipment where the 2035 aesthetic does not conflict with the contemporary visual target.

### Planned

**Original / properly licensed external assets**

Use these primarily to give NTEF a distinctive silhouette rather than to duplicate weapons that RHS/3CB already cover well.

---

## 13. In-Game Audit Required

Web documentation is not enough to lock final equipment.

The next practical stage should inspect the actual installed modset in Arma 3 and capture **class names plus screenshots**.

For each item record:

```text
Display name:
Class name:
Source mod:
Category:
Visual tier:
Colour/camo:
Hidden selections:
Retexturable:
Clipping issues:
ACE compatibility:
Notes:
Decision:
```

### First in-game review order

1. regional uniforms;
2. civilian/traditional headwear;
3. facewear;
4. chest rigs/webbing;
5. plate carriers;
6. backpacks;
7. AK variants;
8. machine guns;
9. marksman weapons;
10. launchers;
11. pickups;
12. technicals;
13. SUVs/vans;
14. motorcycles;
15. captured utility vehicles.

The first session should focus on **appearance**, not balancing.

---

## 14. Proposed NTEF Asset Targets

These numbers are targets for variety, not mandatory minimums.

### Uniform/clothing pool

Target:

- 8–15 low-tier combinations;
- 6–10 core combinations;
- 4–8 veteran combinations.

These should be produced from a smaller number of reusable garments rather than requiring dozens of unique models.

### Headwear/facewear

Target:

- 6+ regional/civilian headwear options;
- 4+ scarf/wrap options;
- 3+ helmet options for captured/veteran use;
- several no-face-covering identities.

### Vests

Target:

- 4+ simple rig/webbing styles;
- 2–4 basic armour styles;
- 2–3 modern veteran plate-carrier styles.

### Weapons

Target weapon families:

- AKM;
- AK-74;
- AK-100/modern AK;
- PKM;
- RPK/RPD;
- SVD;
- RPG-7;
- small minority of FAL/G3/SKS/captured Western rifles.

We do **not** need a large new custom weapon pack.

### Vehicles

Target:

- 2–4 unarmed civilian pickup variants;
- 3+ technical appearances;
- 2+ SUVs;
- 1–2 vans;
- 1–2 cargo/utility trucks;
- motorcycle if a suitable asset is available;
- a small captured government vehicle pool.

---

## 15. First-Pass Decisions

### Decision 01

**Do not start `config.cpp` yet.**

The available clothing and vehicle classes should be visually reviewed first.

### Decision 02

**RHS is the preferred initial weapon source.**

It already covers the core NTEF arsenal well enough that custom weapon development is unnecessary for the first faction.

### Decision 03

**3CB Factions is the highest-value existing regional content candidate.**

However, it should become a mandatory dependency only after confirming whether it is already in the unit deployment modset and whether its specific classes meet our visual standard.

### Decision 04

**CUP remains optional.**

No dependency should be added until it fills a demonstrated gap.

### Decision 05

**External assets are expected and supported by the project workflow.**

Every incorporated external asset must have recorded provenance and redistribution permission before public release.

### Decision 06

**The first bespoke assets should be identity assets, not weapons.**

Priority original work:

1. NTEF emblem;
2. NTEF flag;
3. patch;
4. editor icon;
5. vehicle marking.

---

## 16. Open Questions / Audit Tasks

- [ ] Confirm the deployment modset's existing major content dependencies.
- [ ] Record exact installed RHS versions/classes.
- [ ] Record exact installed 3CB Factions version/classes.
- [ ] Determine whether CUP is already part of the deployment modset.
- [ ] Inspect 3CB traditional/regional clothing in Arsenal.
- [ ] Inspect 3CB Middle East/Takistan headwear.
- [ ] Inspect available simple chest rigs.
- [ ] Inspect suitable sandals/footwear.
- [ ] Inspect Hilux/Pickup/Land Rover technical variants.
- [ ] Inspect available motorcycle models.
- [ ] Create external asset register.
- [ ] Add external staging directory to `.gitignore`.
- [ ] Log all private/non-Workshop asset candidates.
- [ ] Verify permissions before importing external models/textures.
- [ ] Select the first approved uniform pool.
- [ ] Select the first approved headwear pool.
- [ ] Select the first approved vest pool.
- [ ] Select the baseline weapon families.
- [ ] Select the baseline civilian vehicle pool.
- [ ] Select the baseline technical pool.
- [ ] Begin faction emblem design after asset direction is visually established.

---

## 17. Public Research References

Research checked on 2026-08-09.

### Red Hammer Studios

**RHS Wiki — Weapons**  
Used to confirm availability of AKM, AK-74M, AK-103, PKM, PKP, RPG-family and SVD weapon families.

**RHS — End User License Agreement**  
Used to establish default handling of RHS content as external dependency/reference content rather than material to copy into the project.

### 3 Commando Brigade

**3CB Factions — current release page**  
Used to confirm current required dependencies and included Middle East, Afghan, Takistani, Ardistani and Karzeghistani faction families.

**3CB Factions — changelog**  
Used to confirm Hilux, Pickup and Land Rover weapon variants and additional weapon/equipment content.

**3CB — Released Mods / licence**  
Used to establish the current CC BY-NC-ND 4.0 licence and the need to seek permission for modifications.

### Community Upgrade Project

**CUP — Asset List**  
Used to confirm availability of searchable weapon, clothing, unit, vehicle, item and prop catalogues.

**CUP — FAQ**  
Used to confirm package dependency ordering and the prohibition on custom "light" repacks.

**CUP — CUP Licence**  
Licence reference for any later use beyond normal dependency classes.

### Bohemia Interactive

**Bohemia Interactive — Intellectual Property / Licensed Data guidance**

**Bohemia Interactive — Community Licences**

Used to establish that specifically licensed data packages can carry rights to adapt content under licences such as APL/APL-SA, while ordinary access to game data should not be treated as permission to redistribute it.

---

## 18. Current Working Conclusion

NTEF does **not** need a custom weapon ecosystem.

The current likely strengths are:

- RHS for core Eastern/regional weapons;
- 3CB Factions for high-value Middle Eastern/Takistani clothing and vehicle references;
- vanilla content for generic civilian support assets.

The current likely gaps are:

- distinctive regional clothing combinations;
- footwear;
- selected headwear/facewear;
- faction-specific identity assets;
- possibly additional contemporary civilian/technical vehicle models.

This is favourable for the project because external or original development effort can be concentrated on **visual identity** instead of recreating weapon systems that already exist at high quality.

The next development step should be a **live Arsenal/Eden class audit** of the user's actual installed content, beginning with uniforms and headwear, one category at a time.
