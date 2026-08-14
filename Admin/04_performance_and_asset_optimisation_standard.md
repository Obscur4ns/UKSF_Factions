# UKSF_Factions — Performance & Asset Optimisation Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Performance & Asset Optimisation Standard  
**Status:** Active / Pre-asset Integration  
**Created:** 2026-08-09  
**Related documents:**
- `01_project_scope_standards_roadmap.md`
- `02_class_and_editor_naming_standard.md`
- `03_dependency_and_pbo_architecture.md`
- `../assets/asset_register.md`

---

## 1. Purpose

This document defines the technical quality standard for assets entering `UKSF_Factions`.

It applies to:

- character clothing;
- uniforms;
- vests;
- helmets;
- headgear;
- facewear;
- backpacks;
- weapons;
- vehicles;
- static props;
- faction-specific visual assets.

The purpose is to prevent externally sourced assets from becoming permanent technical debt.

Every imported asset should be treated as:

```text
SOURCE MATERIAL
      ↓
TECHNICAL REVIEW
      ↓
OPTIMISATION
      ↓
IN-GAME VALIDATION
      ↓
INTEGRATION
```

rather than:

```text
IMPORT
  ↓
PACK
  ↓
SHIP
```

---

# PART I — STANDARD TYPES

## 2. Engine Requirement vs Project Standard

This document distinguishes two categories.

### `ENGINE / ARMA REQUIREMENT`

A requirement imposed by the engine, toolchain or model/config behaviour.

Examples:

- specific functional LODs;
- closed/convex Geometry components;
- valid memory points;
- correct selections;
- valid model/config paths.

### `UKSF PROJECT STANDARD`

A project quality target chosen to improve:

- performance;
- consistency;
- maintainability;
- visual quality.

Examples:

- preferred texture resolution;
- preferred LOD reduction ratio;
- material-section review thresholds;
- source-quality grading.

Project standards may be adjusted if testing demonstrates a better value.

Do **not** describe a UKSF project budget as an Arma hard limit.

---

# PART II — CORE PERFORMANCE PHILOSOPHY

## 3. Optimisation Priorities

Optimise in this order:

1. **Correctness**
2. **LOD structure**
3. **Material/section count**
4. **Geometry complexity**
5. **Texture memory**
6. **Runtime scripts**
7. **File size**

Do not damage:

- animation;
- collision;
- hit detection;
- visual silhouette;

solely to achieve a smaller PBO.

---

## 4. Performance Context

The largest expected costs in a faction asset pack come from combinations of:

- high-resolution visible geometry;
- poor or absent LOD reduction;
- excessive materials/sections;
- high-resolution textures;
- duplicated textures;
- complex shadow geometry;
- incorrect collision geometry;
- unnecessary runtime scripting.

A large source model is not automatically unusable.

A large source model with:

```text
no sensible LODs
+
many materials
+
4K/8K textures everywhere
+
complex shadow geometry
```

is a poor candidate without substantial rework.

---

# PART III — ASSET TRIAGE

## 5. Asset Quality Grades

Every imported 3D asset should receive an initial grade.

### Grade A — Integration Ready

Asset already has:

- usable topology;
- sensible UVs;
- appropriate material count;
- good source textures;
- usable LODs or is easy to optimise;
- correct scale;
- no major clipping problem.

Action:

```text
MINOR CLEANUP → INTEGRATE
```

---

### Grade B — Worth Reworking

Asset has strong visual value but requires:

- LOD creation;
- texture consolidation;
- material cleanup;
- topology cleanup;
- skeleton adjustment;
- minor modelling;
- retexturing.

Action:

```text
OPTIMISE → REVIEW → INTEGRATE
```

Most useful external assets are expected to fall here.

---

### Grade C — Heavy Rework

Asset has desirable shape/design but suffers from major issues:

- extremely dense topology;
- poor UV layout;
- too many materials;
- weak source textures;
- difficult skeleton;
- missing geometry LODs;
- broken normals;
- unsuitable scale;
- major clipping.

Action:

```text
ONLY REWORK IF ASSET IS DISTINCTIVE
```

Do not spend days repairing a Grade C generic baseball cap that can be replaced easily.

---

### Reject

Reject where:

- asset quality is poor;
- provenance/permission is unresolved;
- topology is impractical to repair;
- visual value is low;
- duplicate existing asset is better;
- source format is destructive/incomplete;
- cost of conversion exceeds value.

Record rejected assets in the asset register where they were formally evaluated.

---

# PART IV — RESOLUTION LODS

## 6. Resolution LOD Requirement

**UKSF PROJECT STANDARD**

Every significant visible model should have multiple Resolution LODs.

Examples:

- uniforms;
- vests;
- headgear;
- weapons;
- vehicles;
- significant props.

Bohemia's model documentation defines numerical LODs as visible resolution levels: lower-numbered LODs represent more detailed visual versions, with progressively lower-detail versions used as distance increases.

---

## 7. LOD Philosophy

The objective is:

> remove detail before the player can perceive that it has been removed.

Good LOD reduction removes:

- hidden faces;
- small bolts;
- stitching geometry;
- tiny grooves;
- internal faces;
- small accessories;
- high-frequency silhouette-neutral detail;

before removing major silhouette detail.

---

## 8. Suggested LOD Reduction Targets

These are **UKSF project targets**, not engine requirements.

Starting from the highest-detail visible LOD:

| LOD Stage | Approximate Remaining Geometry |
|---|---:|
| Highest detail | 100% |
| Medium-near | 50–70% |
| Medium | 25–40% |
| Far | 10–20% |
| Very far | 3–10% |

These percentages are guidelines.

A helmet may reduce differently from a vehicle.

Visual testing overrides the percentage target.

---

## 9. LOD Count

### Small character items

Target:

```text
3–5 visible LODs
```

Examples:

- helmet;
- pakol;
- scarf;
- small vest.

### Character clothing / large wearable equipment

Target:

```text
4–6 visible LODs
```

### Weapons

Target:

```text
4–6 visible LODs
```

### Vehicles

Target:

```text
5+ visible LODs
```

depending on complexity.

Do not create extra LODs that are effectively duplicates.

---

## 10. First-Person / View LODs

Where the item is visible prominently in first person, evaluate whether a dedicated view LOD is required.

Relevant examples:

- weapons;
- hands/arms-compatible clothing;
- vehicle interiors;
- gunner/pilot views.

Bohemia's documented special LOD set includes dedicated Pilot, Gunner and Cargo view LODs where required by the asset type.

---

# PART V — TRIANGLE / FACE COMPLEXITY

## 11. No Universal Triangle Limit

`UKSF_Factions` does **not** define one hard polygon limit for all models.

Reason:

A:

```text
15k-triangle helmet
```

and a:

```text
15k-triangle truck
```

are not comparable.

Complexity must be judged based on:

- screen size;
- silhouette;
- number of instances;
- expected viewing distance;
- LOD quality;
- material count.

---

## 12. Soft Review Thresholds

These are **review triggers**, not rejection limits.

### Small headgear

Review carefully if highest visible LOD exceeds roughly:

```text
20k triangles
```

### Vest / load-bearing equipment

Review carefully above roughly:

```text
40k triangles
```

### Full character clothing mesh

Review carefully above roughly:

```text
60k triangles
```

### Handheld weapon

Review carefully above roughly:

```text
60k triangles
```

### Light vehicle

Review carefully above roughly:

```text
150k triangles
```

These values exist only to trigger scrutiny.

A model may be accepted above them if:

- geometry is justified;
- LODs reduce strongly;
- material count is good;
- in-game performance is acceptable.

A model below them can still be badly optimised.

---

# PART VI — MATERIALS & SECTIONS

## 13. Sections Matter

Arma materials and textures are assigned to model faces, and distinct material/texture combinations create separate rendering sections.

Therefore an asset can be expensive despite moderate triangle count if it contains excessive sections.

Bohemia's material documentation explicitly describes textures/materials being assigned to faces and notes engine/card limits around material/bone usage.

---

## 14. Section Reduction Priority

When importing an external model, inspect for:

- one material per tiny accessory;
- duplicated materials;
- separate materials with identical settings;
- several tiny texture sheets;
- redundant glass materials;
- unused material slots.

Consolidate where practical.

---

## 15. Project Section Targets

These are **UKSF project soft targets**.

### Headgear

Prefer:

```text
1–3 visible sections
```

### Vest / wearable item

Prefer:

```text
1–4 visible sections
```

### Full uniform

Prefer:

```text
1–3 visible sections
```

### Weapon

Prefer:

```text
2–6 visible sections
```

### Light vehicle exterior/interior

Aim to keep the total meaningfully controlled.

Review aggressively when a vehicle reaches:

```text
20+ visible material sections
```

The exact number may be justified by:

- glass;
- interior;
- exterior;
- lights;
- emissive elements;
- damage materials;
- animated parts.

Do not merge materials blindly where doing so breaks required shaders or selections.

---

# PART VII — TEXTURES

## 16. Texture Format

Final Arma texture assets should use appropriate engine formats, normally:

```text
.paa
```

through the established Arma toolchain.

Source files may remain:

```text
.psd
.tga
.png
.exr
```

where useful for editing.

Editable master files should not be discarded solely because the game uses PAA.

---

## 17. Texture Naming

Use conventional suffixes where appropriate.

Examples:

```text
_co
_nohq
_smdi
_as
_mc
```

according to the texture's actual shader role.

Do not use a suffix that misrepresents the texture type.

---

## 18. Power-of-Two Standard

**UKSF PROJECT STANDARD**

Prefer power-of-two texture dimensions:

```text
256
512
1024
2048
4096
```

and appropriate rectangular combinations such as:

```text
2048 × 1024
1024 × 512
```

where useful.

Avoid unusual arbitrary dimensions unless the toolchain/shader explicitly supports and benefits from them.

---

## 19. Default Texture Resolution Targets

These are **project defaults**, not hard limits.

### Small accessories

Default:

```text
512–1024
```

Examples:

- small patch;
- simple glasses;
- small equipment accessory.

### Headgear

Default:

```text
1024–2048
```

### Vest / chest rig

Default:

```text
2048
```

### Uniform

Default:

```text
2048
```

Consider 4096 only where:

- a genuinely large reusable atlas requires it;
- visual testing shows a clear benefit.

### Weapon

Default:

```text
2048
```

Use 4096 only for exceptional close-up/high-detail cases.

### Light vehicle

Default:

```text
2048
```

per major texture set.

Use 4096 selectively for:

- large exterior atlas;
- complex vehicle interior;
- hero vehicle.

Do not use 4K for every map simply because the source included it.

---

## 20. 8K Textures

Default decision:

```text
DO NOT SHIP
```

unless a specific exceptional case demonstrates a strong reason.

External game assets may arrive with:

```text
8K
```

or larger sources.

Treat those as **source masters**.

Downsample to sensible Arma runtime sizes.

---

## 21. Texture Set Review

For each asset, inventory:

- colour/albedo/diffuse;
- normal;
- specular/material;
- ambient/shadow;
- masks;
- emissive;
- damage textures;
- unused source maps.

Do not convert every supplied source-game map mechanically.

Only include maps required by the Arma material setup.

---

# PART VIII — UVs & TEXTURE CONSOLIDATION

## 22. UV Review

Check:

- overlapping islands;
- unintended mirrored areas;
- wasted UV space;
- extreme texel-density differences;
- tiny unused islands;
- internal hidden surfaces consuming major UV area.

Retain intentional mirroring where it improves efficiency without causing visible problems.

---

## 23. Atlas Strategy

Atlas assets where this meaningfully reduces sections and improves reuse.

Good candidates:

- multiple small pouches;
- vest accessories;
- helmet accessories;
- minor vehicle details.

Do not create a giant universal atlas that:

- wastes memory;
- complicates updates;
- forces unrelated assets to load huge textures.

---

# PART IX — RVMAT / MATERIAL STANDARD

## 24. Material Setup

Every adapted asset should receive an Arma-appropriate material review.

Do not blindly port source-game shader values.

Bohemia's RVMAT documentation defines material stages and lighting properties differently from many modern PBR engines.

Therefore conversion from another game generally requires reinterpretation rather than direct numeric copying.

---

## 25. Material Review Items

Check:

- ambient;
- diffuse;
- forcedDiffuse;
- emmisive/emissive settings;
- specular;
- specularPower;
- pixel shader;
- vertex shader;
- texture stages;
- transparency;
- glass shader behaviour.

The correct setup depends on asset type.

---

# PART X — GEOMETRY LOD

## 26. Geometry LOD

**ENGINE / ARMA REQUIREMENT where relevant**

Bohemia's modelling documentation states that Geometry components should be formed from closed convex objects.

Geometry should be:

- significantly simpler than visual geometry;
- closed;
- convex by component;
- free of unnecessary tiny details;
- correctly weighted where mass is required.

Do not copy the visible model into Geometry LOD.

---

## 27. Component Convexity

Use Object Builder tools to check for:

- non-convex components;
- open geometry;
- invalid components.

For vehicles/physical objects, treat Geometry LOD errors as blockers.

---

## 28. Mass

Where the engine uses model mass:

- assign sensible total mass;
- distribute mass deliberately;
- do not retain arbitrary source values.

Vehicle handling should be tested in game.

---

# PART XI — VIEW GEOMETRY

## 29. View Geometry

Bohemia documents `View Geometry` as a distinct model LOD used by engine visibility/intersection systems.

It should represent the broad visual occlusion shape.

Keep it:

- much simpler than Resolution LOD;
- closed where appropriate;
- free from small cosmetic details.

Do not use detailed visible mesh unnecessarily.

---

# PART XII — FIRE GEOMETRY

## 30. Fire Geometry

Bohemia documents `Fire Geometry` as the LOD used for weapon/projectile intersection where available.

It must represent:

- surfaces that should stop or receive fire;
- meaningful openings;
- broad cover geometry.

Do not leave major holes that allow bullets through solid visual surfaces.

Do not model:

- tiny buckles;
- stitching;
- decorative bolts;

into Fire Geometry.

---

## 31. Vehicle Fire Geometry

For technicals and vehicles, validate:

- body panels;
- doors;
- windows;
- gun shields;
- cargo compartment;
- turret protection.

Gameplay behaviour matters more than perfect geometric duplication.

---

# PART XIII — HIT POINT LOD

## 32. Hit Points

Bohemia's LOD definitions include a dedicated `Hit Points` LOD.

Where an asset uses model hit selections:

- points/selections must align with config names;
- no stale selections from donor assets;
- no unreachable or misplaced hit points.

Vehicles should undergo explicit damage testing.

---

# PART XIV — MEMORY LOD

## 33. Memory LOD

Memory LOD should contain only functional points/axes/selections.

Examples:

- weapon muzzle points;
- optic points;
- vehicle entry points;
- wheel axes;
- turret axes;
- light positions;
- cargo positions;
- gunner view positions.

Bohemia's vehicle/turret configuration references explicitly rely on named memory points for functions such as gun position, optics and entry direction.

---

## 34. Memory Cleanup

External assets often contain:

- unused helper points;
- source-game rig markers;
- abandoned animations;
- duplicate axes.

Remove anything not required by the Arma implementation.

---

# PART XV — LAND CONTACT / ROADWAY / PATHS

## 35. LandContact

For vehicles/objects where required:

- contact points must align with actual wheels/tracks/base;
- remove source-game points that no longer match geometry.

Test:

- spawning on flat ground;
- slopes;
- PhysX behaviour.

---

## 36. Roadway

Only create/use Roadway geometry where the asset actually requires walkable/drivable surfaces.

Do not add Roadway LOD to ordinary wearable gear or simple vehicles without a reason.

---

## 37. Paths

Paths LOD is primarily relevant to navigable structures.

It is unlikely to be required for initial faction gear/vehicles.

Do not copy irrelevant donor LODs into the project.

---

# PART XVI — SHADOW LODS

## 38. Shadow Geometry

Dedicated shadow LODs should be substantially simpler than the highest visible mesh.

Shadow geometry should preserve:

- silhouette;
- major holes/open areas;
- significant moving parts.

Remove:

- tiny details;
- unseen internals;
- decorative elements.

Bohemia defines dedicated Shadow Volume LOD ranges and also provides model properties to control shadow behaviour per LOD.

---

## 39. Shadow Review

A visually small item should never contain a shadow mesh almost as complex as its highest visible model without a demonstrated reason.

Review all imported:

- helmets;
- vests;
- weapons;
- vehicles;

for copied high-poly shadow meshes.

---

# PART XVII — CHARACTER ASSETS

## 40. Uniform Standard

Uniform models must be checked for:

- skeleton compatibility;
- animation deformation;
- shoulder clipping;
- elbow clipping;
- knee clipping;
- prone deformation;
- seated vehicle deformation;
- backpack interaction;
- vest interaction.

Test using multiple common Arma animations.

---

## 41. Uniform Optimisation

Prioritise topology around:

- shoulders;
- elbows;
- hips;
- knees.

Reduce geometry aggressively in:

- flat torso surfaces;
- hidden areas;
- under-vest regions where safe.

Do not remove geometry in a way that creates obvious holes when equipment combinations change.

---

## 42. Vest Standard

Test vests against:

- multiple uniform body shapes;
- rifle poses;
- prone;
- crouched;
- seated positions;
- backpacks.

Clipping is more important than tiny texture imperfections.

---

## 43. Headgear Standard

Test:

- multiple heads/faces;
- balaclavas;
- scarves;
- NVGs where applicable;
- weapon optics;
- prone/crouched poses.

Avoid headgear that floats far from the head solely because the original source used a different character scale.

---

# PART XVIII — WEAPON ASSETS

## 44. Weapon Geometry

Prioritise visible detail near:

- receiver;
- sights;
- handguard;
- magazine;
- stock.

Small mechanical detail may be baked into normal maps rather than retained as geometry.

---

## 45. Weapon View Quality

Weapons occupy substantial first-person screen space.

Therefore acceptable highest-detail geometry/texture budgets may be higher than an equally sized environmental prop.

However, third-person LOD reduction must still be aggressive.

---

## 46. Attachment Compatibility

Where supported:

- verify optic rails;
- muzzle positions;
- suppressor alignment;
- magazine alignment;
- hand animations.

Do not retain attachments the faction does not need merely because the donor weapon supports them.

---

# PART XIX — VEHICLE ASSETS

## 47. Vehicle Review Priority

Vehicles require the most thorough technical review.

Check:

- exterior;
- interior;
- visible LODs;
- Geometry;
- PhysX;
- View Geometry;
- Fire Geometry;
- Memory;
- LandContact;
- HitPoints;
- turret/gunner geometry;
- cargo proxies;
- lights;
- wheels;
- mirrors;
- animations;
- destruction behaviour.

---

## 48. Vehicle Interior Budget

Do not render unnecessary high-detail interior geometry at long external viewing distances.

Use appropriate:

- LOD reduction;
- hidden interiors;
- view LODs;

where practical.

---

## 49. Vehicle Variants

Prefer one reusable model with:

- hidden selections;
- proxies;
- modular turret variants;

over several near-identical copied P3Ds.

But do not create dozens of hidden selections that increase complexity purely to avoid a second model.

---

# PART XX — HIDDEN SELECTIONS

## 50. Hidden Selection Policy

Use hidden selections for meaningful customisation:

- faction markings;
- paint schemes;
- vehicle colour;
- removable visual components.

Do not turn every pouch/bolt into a hidden selection.

The feature should solve a real reusability problem.

---

# PART XXI — PROXIES

## 51. Proxy Use

Use proxies for repeated/separable assets where appropriate.

Potential examples:

- weapon systems;
- crew;
- wheels;
- common vehicle accessories.

Do not duplicate large repeated geometry inside the parent P3D when a proxy is technically appropriate.

---

# PART XXII — DUPLICATION

## 52. Duplicate Asset Rule

Before importing a new asset, check whether `UKSF_Factions` already contains something fulfilling the same role.

Do not retain:

```text
four near-identical AK chest rigs
```

merely because four source mods supplied them.

Select the best assets.

---

## 53. Texture Duplication

If multiple models share the same material/texture source:

- reuse where practical;
- do not create several byte-identical copies under different faction folders.

Faction-specific retextures are valid where they actually differ.

---

# PART XXIII — DAMAGE MATERIALS

## 54. Damage Textures

Vehicles should only receive damage materials/textures that:

- function;
- are visually worthwhile;
- fit the model.

Do not preserve broken source-game damage layers that never display correctly in Arma.

---

# PART XXIV — SCRIPT PERFORMANCE

## 55. Static Content First

Where functionality can be expressed in config/model data, prefer that over runtime script.

Examples:

Prefer config for:

- loadouts;
- armour;
- faction;
- hidden selections;
- editor placement.

Do not use an SQF loop to maintain something the engine already supports.

---

## 56. Per-Unit Code

Avoid automatically starting:

- loops;
- `while` threads;
- per-frame handlers;
- repeated scanning;

on every spawned faction unit.

A faction consisting of 100 AI should not create 100 permanent background loops unless absolutely necessary.

---

## 57. CBA PFH

If future functionality needs a CBA Per Frame Handler:

- centralise it where possible;
- process registered objects centrally;
- stop it when there is no work;
- use the lowest sensible update rate.

Do not attach a PFH to every fighter.

---

## 58. Event-Driven Behaviour

Prefer:

```text
event handler
interaction
state change
```

over:

```text
poll every frame forever
```

This principle will be especially important for optional ACE features.

---

# PART XXV — EXPLOSIVE VEST PERFORMANCE

## 59. Explosive Vest

The future explosive vest should remain technically lightweight.

The visual model behaves as ordinary character gear.

Functional logic should be based on:

- ACE explosive configuration;
- event-driven interactions;
- detonation state.

Avoid persistent per-frame proximity or inventory scanning unless ACE integration proves it unavoidable.

---

# PART XXVI — CONFIG PERFORMANCE

## 60. Inheritance

Use config inheritance to reduce:

- duplicated unit config;
- duplicated faction settings;
- repeated vehicle settings.

Do not create excessive abstraction layers that make debugging difficult.

Aim for:

```text
clear + shallow
```

rather than:

```text
clever + deep
```

---

## 61. Unit Variants

Visual variants should not require hundreds of almost-identical classes.

Use a combination of:

- sensible base classes;
- controlled randomisation;
- small number of editor-visible functional variants.

The editor catalogue must remain readable.

---

# PART XXVII — SOURCE FILE MANAGEMENT

## 62. Keep Source Masters

For integrated assets, preserve source masters where permission allows.

Examples:

```text
.blend
.fbx
.obj
.psd
.tga
```

The project should not rely only on:

```text
binarised .p3d
.paa
```

if editable source is available.

---

## 63. Runtime vs Source

Keep high-resolution/source data separate from packed runtime data.

Example conceptual layout:

```text
source/
    vehicle_master.blend
    vehicle_8k_master.psd

addons/
    vehicles/
        data/
            vehicle_co.paa
            vehicle_nohq.paa
```

Whether source files belong in public Git depends on permission and repository-size strategy.

---

# PART XXVIII — REPOSITORY SIZE

## 64. Binary File Discipline

Do not commit huge intermediate exports repeatedly.

Avoid Git history containing:

```text
model_final.fbx
model_final2.fbx
model_final3.fbx
model_final_REAL.fbx
```

Use clean source versioning practices.

---

## 65. Git LFS

Git LFS may be considered later for:

- PSD;
- FBX;
- Blender source;
- large textures;

if repository size warrants it.

Do not introduce LFS before the expected source volume is known.

---

# PART XXIX — ASSET REVIEW SHEET

## 66. Required Review Record

Each significant model candidate should eventually record:

```text
Asset ID:
Asset name:
Source:
Grade:
Highest visible triangles:
Visible LOD count:
Lowest visible triangles:
Visible sections:
Shadow sections:
Texture sets:
Largest runtime texture:
Geometry LOD:
View Geometry:
Fire Geometry:
Memory LOD:
Hit Points:
LandContact:
Animation/skeleton:
Clipping:
RPT errors:
PBOProject errors:
Performance notes:
Decision:
```

This may later become a separate Markdown template or spreadsheet if the project volume grows.

---

# PART XXX — CHARACTER ACCEPTANCE CHECKLIST

## 67. Uniform / Vest / Headgear

Before approval:

- [ ] Correct scale.
- [ ] Correct skeleton.
- [ ] No major bind-pose deformation.
- [ ] Good shoulder movement.
- [ ] Good elbow movement.
- [ ] Good knee/hip movement where applicable.
- [ ] Prone tested.
- [ ] Crouched tested.
- [ ] Seated tested.
- [ ] Backpack tested.
- [ ] Vest/uniform combination tested.
- [ ] Headgear/facewear combination tested.
- [ ] Resolution LODs present.
- [ ] Shadow LOD reasonable.
- [ ] Material count reviewed.
- [ ] Texture resolution reviewed.
- [ ] No missing textures/materials.
- [ ] Clean RPT.
- [ ] Clean PBOProject build.

---

# PART XXXI — VEHICLE ACCEPTANCE CHECKLIST

## 68. Vehicle

Before approval:

- [ ] Correct scale.
- [ ] Highest visible geometry reviewed.
- [ ] Resolution LOD chain tested.
- [ ] Interior LOD reviewed.
- [ ] Shadow geometry reviewed.
- [ ] Geometry convexity validated.
- [ ] Mass configured.
- [ ] View Geometry tested.
- [ ] Fire Geometry tested.
- [ ] Hit Points tested.
- [ ] Memory points validated.
- [ ] LandContact correct.
- [ ] Wheels/suspension correct.
- [ ] Entry/exit points work.
- [ ] Driver position works.
- [ ] Cargo positions work.
- [ ] Gunner/turret positions work where relevant.
- [ ] Weapon muzzle/optics correct.
- [ ] Lights work.
- [ ] Damage/destruction works.
- [ ] Textures/materials reviewed.
- [ ] Section count reviewed.
- [ ] Eden works.
- [ ] Zeus works.
- [ ] Multiplayer test complete.
- [ ] Clean RPT.
- [ ] Clean PBOProject build.

---

# PART XXXII — PERFORMANCE TEST METHOD

## 69. Test in Context

Do not performance-test a single helmet floating in VR and conclude it is optimised.

Character gear should be tested with:

- 1 unit;
- 10 units;
- 30+ units;

visible in representative combat conditions.

Vehicles should be tested with multiple instances where plausible.

---

## 70. Compare Like-for-Like

Where possible, compare:

```text
UKSF asset
vs
similar vanilla/RHS/3CB asset
```

under the same:

- location;
- view distance;
- camera;
- unit count.

The goal is not exact identical FPS.

The goal is detecting assets that are obviously disproportionate.

---

## 71. RPT Review

Every integrated asset must be checked for:

- missing texture;
- missing material;
- missing selection;
- bad skeleton;
- animation errors;
- config errors;
- model errors.

"Looks fine in game" is not enough if the RPT is filling with errors.

---

# PART XXXIII — OPTIMISATION ORDER FOR EXTERNAL ASSETS

## 72. Recommended Conversion Order

When importing an external model:

### Step 1

Verify:

- permission;
- provenance;
- source quality.

### Step 2

Fix:

- scale;
- orientation;
- topology;
- normals.

### Step 3

Inspect:

- material slots;
- UVs;
- textures.

### Step 4

Create/repair:

- highest visual Arma version.

### Step 5

Create:

- lower Resolution LODs.

### Step 6

Create/repair special LODs:

- Geometry;
- View;
- Fire;
- Memory;
- Shadow;
- other required LODs.

### Step 7

Build:

- model.cfg;
- config.

### Step 8

Test:

- Object Builder;
- Buldozer if applicable;
- Arma;
- RPT.

### Step 9

Optimise further only after actual testing.

---

# PART XXXIV — NTEF-SPECIFIC PRIORITIES

## 73. High-Instance Assets

The following NTEF assets deserve particularly strong optimisation because missions may place many of them:

- regional uniforms;
- chest rigs;
- pakols/headwear;
- scarves;
- common rifles;
- common pickups.

A 5% inefficiency multiplied across:

```text
50 fighters
```

matters more than the same inefficiency on one Senior Leader model.

---

## 74. Hero Assets

Assets likely to appear once or rarely may justify slightly higher visual budgets.

Examples:

- Senior Leader outfit;
- unique command vehicle;
- specific HVT prop.

They still require correct LODs.

"Rare" does not mean "unoptimised."

---

# PART XXXV — PROJECT DEFAULT BUDGET SUMMARY

## 75. Default Runtime Texture Targets

| Asset | Default |
|---|---:|
| Small accessory | 512–1024 |
| Headgear | 1024–2048 |
| Vest | 2048 |
| Uniform | 2048 |
| Weapon | 2048 |
| Vehicle major set | 2048 |
| Exceptional hero atlas | 4096 |
| 8K runtime texture | Avoid |

---

## 76. Default LOD Expectations

| Asset | Visible LOD Target |
|---|---:|
| Headgear | 3–5 |
| Vest | 3–5 |
| Uniform | 4–6 |
| Weapon | 4–6 |
| Vehicle | 5+ |

---

## 77. Section Soft Targets

| Asset | Preferred |
|---|---:|
| Headgear | 1–3 |
| Uniform | 1–3 |
| Vest | 1–4 |
| Weapon | 2–6 |
| Vehicle | Review aggressively above ~20 |

Again:

These are **UKSF project targets**, not Arma engine limits.

---

# PART XXXVI — AUTOMATED / SCRIPTED AUDITING

## 78. Future Audit Utilities

Later development should consider small tools to report:

- P3D LOD list;
- model section count;
- texture references;
- material references;
- missing paths;
- config class source;
- duplicate files;
- texture dimensions.

Arma's current `allLODs` scripting command can return model LOD names and resolutions, making an in-game verification utility possible for binarised models.

This should be developed only when asset integration begins.

---

# PART XXXVII — LOCKED PERFORMANCE DECISIONS

## 79. Locked

- Every significant visual asset requires meaningful Resolution LODs.
- Geometry LOD must not be copied directly from visible geometry.
- Geometry components must be valid/convex where required.
- View and Fire Geometry must be intentionally simplified.
- Shadow geometry must be reviewed and simplified.
- Material/section count is treated as a first-class optimisation concern.
- 2048 is the normal runtime texture target for major character gear.
- 4096 is selective, not default.
- 8K textures are source masters, not normal runtime assets.
- Imported source-game shader settings are not copied blindly into RVMAT.
- Runtime scripts should be event-driven where practical.
- No permanent per-unit loops without strong justification.
- High-instance NTEF gear receives stricter optimisation priority.
- Asset quality is graded before conversion effort is committed.
- RPT cleanliness is part of asset acceptance.
- PBOProject cleanliness is part of asset acceptance.
- Soft budgets are project review thresholds, not claimed engine hard limits.

---

# PART XXXVIII — OPEN DECISIONS

## 80. Resolve During Real Asset Work

- [ ] Determine whether character source masters live in Git or separate archival storage.
- [ ] Decide whether Git LFS is worthwhile.
- [ ] Create standard Blender/Object Builder export workflow.
- [ ] Create asset technical-review template as a standalone file if needed.
- [ ] Establish exact model.cfg templates for character and vehicle assets.
- [ ] Establish texture conversion presets.
- [ ] Establish standard RVMAT templates by material type.
- [ ] Establish common character skeleton source.
- [ ] Establish vehicle PhysX conversion/testing workflow.
- [ ] Create automated duplicate-texture audit if asset volume becomes large.
- [ ] Create in-game `allLODs` audit utility if useful.
- [ ] Establish representative multiplayer performance benchmark mission.

---

# PART XXXIX — RESEARCH REFERENCES

Research reviewed 2026-08-09.

## Bohemia Interactive Community — Oxygen 2 Manual

Current Bohemia documentation describes Resolution LOD behaviour, special model LODs and geometry requirements. It states that Geometry components must be closed convex objects.

```text
https://community.bohemia.net/wiki/Oxygen_2_-_Manual
```

---

## Bohemia Interactive Community — LOD Resolutions

Current Bohemia reference lists Arma 3 special LOD identifiers including:

- Geometry;
- Memory;
- Land Contact;
- Hit Points;
- View Geometry;
- Fire Geometry;
- View Pilot;
- View Gunner;
- View Cargo;
- Shadow Volume.

```text
https://community.bohemia.net/wiki/LOD_resolutions
```

---

## Bohemia Interactive Community — `allLODs`

Current Arma 3 scripting documentation provides the `allLODs` command, which returns model LOD information including index, name and resolution.

This may support a future automated audit tool.

```text
https://community.bohemia.net/wiki/allLODs
```

---

## Bohemia Interactive Community — RVMAT

Bohemia's material documentation explains texture/material assignment to individual model faces and Arma material/shader configuration.

It is used here to support the project's emphasis on material-section control and Arma-specific material conversion.

```text
https://community.bohemia.net/wiki/RVMAT
```

---

## Bohemia Interactive Community — Arma 3 Named Properties

Current Arma 3 model-property documentation includes LOD/shadow-related properties and demonstrates that shadow handling is tied to model LOD setup.

```text
https://community.bohemia.net/wiki/Arma_3:_Named_Properties
```

---

## Bohemia Interactive Community — CfgVehicles Config Reference

Current vehicle configuration documentation describes model selections and Memory LOD points used for vehicle/turret features such as:

- weapon fire points;
- optics points;
- entry positions;
- direction points.

```text
https://community.bohemia.net/wiki/CfgVehicles_Config_Reference
```

---

## Bohemia Interactive Community — lineIntersectsSurfaces

Current engine documentation identifies collision/intersection checks against:

- Fire Geometry;
- View Geometry;
- Geometry;
- PhysX;
- Roadway.

This reinforces the requirement that special geometry LODs be intentional and correct.

```text
https://community.bohemia.net/wiki/lineIntersectsSurfaces
```

---

# PART XL — CURRENT CONCLUSION

`UKSF_Factions` should treat external assets as **raw source**, not finished Arma content.

The project's standard is:

```text
GOOD SOURCE
     +
ARMA-CORRECT LODS
     +
CONTROLLED MATERIALS
     +
SENSIBLE TEXTURE MEMORY
     +
MINIMAL RUNTIME CODE
     =
RELEASE ASSET
```

The most important principle is that optimisation should happen **before asset families multiply**.

Fixing one chest-rig model before producing twelve textures is easy.

Fixing the same structural problem after twelve variants, faction configs and missions depend on it is expensive.

With this standard locked, future model work can begin from a consistent technical baseline rather than retrofitting performance standards after the mod is already large.
