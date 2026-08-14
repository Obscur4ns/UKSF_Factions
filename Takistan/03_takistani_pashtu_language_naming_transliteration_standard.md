# UKSF_Factions — Takistani Pashtu Language, Naming & Transliteration Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Takistani Pashtu Language, Naming & Transliteration Standard  
**Status:** Active / Research & Art Standard  
**Created:** 2026-08-09  
**Country:** Takistan  
**Project language convention:** Pashtu  
**Native language name:** پښتو  

---

# 1. Purpose

This document establishes the language convention used for Takistan throughout `UKSF_Factions`.

It defines how Pashtu should be handled in:

- faction names;
- personal names;
- unit names;
- military and police markings;
- road signs;
- government signage;
- vehicle markings;
- patches;
- fictional documents;
- place names;
- intelligence briefs;
- editor display names;
- config classnames;
- texture filenames.

The purpose is consistency. The project should never drift into a mixture of Pashtu, Dari, Arabic, Urdu and invented pseudo-script simply because source assets contain different text.

---

# PART I — PROJECT LANGUAGE DECISION

## 2. Takistani Language

**Decision:** `PASHTU`

For `UKSF_Factions`, Pashtu is the standard Takistani language.

Use Pashtu for new in-universe Takistani text unless a specific future faction or foreign community has a reason to use another language.

## 3. English Spelling of the Language

The project-standard English label is:

```text
Pashtu
```

External linguistic sources may use:

```text
Pashto
Pushto
Pushtu
```

These are treated as alternate English spellings of the same language.

The Library of Congress currently titles its reference:

```text
Pushto Romanization Table
```

while many modern linguistic references use `Pashto`.

`UKSF_Factions` uses **Pashtu** because that is the project's chosen convention.

## 4. Native Name

Native-script language name:

```text
پښتو
```

---

# PART II — SCRIPT

## 5. Writing System

Pashtu uses a modified Perso-Arabic writing system.

Project rule:

```text
RIGHT TO LEFT
```

Native signage/art must be created using proper RTL-capable text/layout software.

Do not:

- type disconnected glyphs manually;
- reverse text by hand;
- use an Arabic font that lacks Pashtu characters;
- fake native text using decorative Arabic-looking shapes.

## 6. Pashtu-Specific Characters

Pashtu includes letters and distinctions not present in ordinary Persian or Arabic orthography.

Useful font-test characters include:

```text
ټ
څ
ځ
ډ
ړ
ږ
ښ
ګ
ڼ
```

A font being able to display Arabic does **not** prove it can correctly display Pashtu.

## 7. Font Handling

Before approving a font for Takistani assets, test:

```text
پښتو
ټ
څ
ځ
ډ
ړ
ږ
ښ
ګ
ڼ
```

Check:

- glyph exists;
- joining is correct;
- no fallback font appears;
- RTL ordering remains correct after export;
- PAA conversion does not damage rendering.

---

# PART III — WRITTEN STANDARD

## 8. Project Orthographic Convention

**UKSF PROJECT STANDARD**

Use a consistent **Afghanistan-oriented written Pashtu convention** for new native-script material when orthographic variants require a choice.

This is a project consistency rule, not a claim that Takistan is Afghanistan.

## 9. Dialect

**Decision:** `DO NOT HARD-CODE A SPOKEN DIALECT`

Do not state that all Takistanis speak a particular real-world Pashtu dialect.

Takistan is fictional.

The project defines a written-language convention, not a real-world linguistic census.

## 10. Pronunciation

If voiced Pashtu is later commissioned:

1. use a fluent/native Pashtu speaker;
2. provide native script;
3. provide intended meaning/context;
4. allow the speaker to recommend natural phrasing;
5. do not derive pronunciation mechanically from English spelling alone.

---

# PART IV — THREE TEXT LAYERS

## 11. Native Layer

Used for:

- signs;
- patches;
- police markings;
- government boards;
- official documents;
- vehicle text;
- environmental graphics.

Native script is authoritative for newly created in-world Takistani-language material.

## 12. Operational Romanisation Layer

Used for:

- UKSF intelligence reports;
- briefing text;
- map annotations;
- mission dialogue subtitles;
- English-language documentation.

This should be readable to ordinary players.

It does not need to preserve every Pashtu phonological distinction.

## 13. Config / ASCII Layer

Used for:

- Arma classnames;
- variable names;
- filenames where practical;
- function names;
- folder names.

Requirements:

```text
ASCII
no spaces
no diacritics
no native script
```

Do not place RTL native text into public config classnames.

---

# PART V — ROMANISATION POLICY

## 14. Reference Romanisation

For linguistic checking, use the Library of Congress ALA-LC **Pushto Romanization Table** as a technical reference.

The table distinguishes letters using forms such as:

```text
ṭ
ḍ
ṛ
ṇ
ṡ
ż
ṣh
ẓh
```

and differentiates long vowels and diphthongs.

This is useful for source checking and resolving ambiguous spellings.

It is **not** the normal player-facing UKSF style.

## 15. Why Not Use Scholarly Romanisation Everywhere

Full scholarly romanisation creates problems for:

- classnames;
- filenames;
- typing in Eden;
- mission scripting;
- searchability;
- ordinary player readability.

Therefore:

```text
SCHOLARLY ROMANISATION
        ↓
verification only

UKSF OPERATIONAL ROMANISATION
        ↓
player-facing Latin spelling
```

---

# PART VI — UKSF OPERATIONAL ROMANISATION

## 16. General Principle

Prefer readable, stable English transliteration over perfectly reversible academic transliteration.

Established proper-name spelling overrides mechanical transliteration.

## 17. Consonant Style

Use familiar digraphs:

```text
kh
gh
sh
zh
ch
```

where needed.

Avoid academic diacritics in ordinary project text.

## 18. Pashtu Distinctions Simplified

For operational text, some distinctions may collapse into the closest readable Latin representation.

| Scholarly distinction | UKSF operational tendency |
|---|---|
| `ṭ` | `t` |
| `ḍ` | `d` |
| `ṛ` | `r` |
| `ṇ` | `n` |
| `ṡ` | `ts` where distinction matters |
| `ż` | `dz` where distinction matters |
| `ṣh` | `sh` |
| `ẓh` | `zh` |

The native Pashtu form remains authoritative.

## 19. Long Vowels

Ordinary UKSF display spelling normally omits macrons:

```text
ā → a
ī → i
ū → u
```

unless an established proper name is commonly written another way.

## 20. Apostrophes and Ayn/Hamza

Avoid specialist transliteration symbols in routine display text.

Where a name is already established with punctuation, retain it.

Config filenames/classnames should omit punctuation unless functionally necessary.

---

# PART VII — EXISTING ARMAVERSE / TERRAIN PLACE NAMES

## 21. Existing Latin Names Are Locked

Established map and Armaverse spellings remain unchanged.

Examples:

```text
Takistan
Rasman
Bastam
Zargabad
Shapur
Karzeghistan
```

Do not "correct" them into another transliteration system.

## 22. North Takistan Terrain Names

The existing Latin settlement names remain the mission/editor standard.

Examples include:

```text
Bastam
Chahe Shrin
Chaman
Garmarund
Imarat
Jamak
Kharu
Kushkak
Laura
Mantiq
Par-e Siah
Qorghan
Raqol
Rasman
Sagram
Sar e Bolaq
Sarcasma
Sarqul
Tarchi
Tazri
Yakavlang
Zari
Zavarak
```

Retain exact map spelling in briefings, markers, mission names and documentation.

## 23. Native Place-Name Forms

Native Pashtu versions may be created later for:

- road signs;
- government maps;
- environmental graphics.

Workflow:

```text
existing map name
      ↓
research intended pronunciation/origin
      ↓
validated Pashtu spelling
      ↓
native sign
```

Do not mechanically convert every Latin name character-by-character.

Some terrain names may derive from other regional naming traditions.

---

# PART VIII — NEW PLACE NAMES

## 24. New UKSF-Created Locations

If a campaign requires a new village, compound, district, checkpoint, base, road or industrial site:

1. define intended English meaning;
2. create natural Pashtu wording;
3. record native script;
4. produce operational romanisation;
5. produce ASCII config token if required.

## 25. Do Not Build Names from Random Syllables

Do not invent "regional-looking" names by combining random fragments.

Use valid language.

---

# PART IX — PERSONAL NAMING

## 26. Flexible Naming Model

Real Afghan/Pashtun naming practice does not map neatly onto a fixed Western:

```text
First Name + Permanent Family Surname
```

model.

Sources describe personal names that may stand alone or be compound, while administrative contexts may additionally record family or paternal information.

`UKSF_Factions` should therefore not force every Takistani into one identical two-name pattern.

## 27. Project Personal Name Format

Allowed display patterns:

```text
Given Name
Compound Given Name
Given Name + Byname/Surname
```

The final identity pool should use reviewed names rather than blind procedural combinations.

## 28. Administrative Identity

For fictional dossiers/intelligence documents, fuller identification may use:

```text
Name:
Father:
Grandfather:
Place of origin:
```

where useful.

These fields are not required for normal Arma unit identities.

## 29. Surnames

Surnames are optional, not mandatory.

Potential bynames may derive from locality, family, lineage or an established surname.

Do not automatically assign every character a tribal surname.

## 30. Tribal Labels

Do not assign real Pashtun tribal identities to fictional Takistani characters by default.

If fictional Takistani tribal/clan structures become useful, they should receive a separate research brief.

---

# PART X — PERSONAL NAME POOL

## 31. Name Pool Standard

Before config implementation, create reviewed lists for:

```text
Takistani male given names
Takistani female given names
Takistani optional surnames/bynames
```

Each entry should contain:

```text
Native:
Operational Latin:
ASCII token if needed:
Notes:
```

## 32. Initial Variety Target

Suggested first pool:

```text
40–60 male given-name forms
30–50 female given-name forms
20–30 optional surnames/bynames
```

These are project variety targets, not demographic claims.

## 33. Arabic-Origin Names

Arabic-origin personal names are normal in Pashtu-speaking contexts.

When used in a Pashtu context, keep spelling/romanisation consistent with the project's Pashtu convention instead of switching to an unrelated Arabic transliteration system.

---

# PART XI — TITLES & HONORIFICS

## 34. Use Sparingly

Do not attach titles such as:

```text
Mullah
Khan
Haji
Sheikh
```

to random characters simply to make them sound regional.

Titles should reflect an actual fictional role or background.

## 35. Military Ranks

Editor/display names should initially remain English:

```text
Private
Corporal
Sergeant
Lieutenant
Captain
```

or role-based:

```text
Rifleman
Team Leader
Section Commander
```

## 36. Native Rank Text

If rank text appears on documents, signage, name tapes or formal graphics, translate that specific rank when needed and validate it.

Do not build an unnecessary full translated rank system before the TNA structure is locked.

---

# PART XII — GOVERNMENT / MILITARY ORGANISATION NAMES

## 37. English/NATO Names

The primary English project designations remain:

```text
Takistani National Army
Takistani National Police
Takistani Border Guard
Takistani Special Operations Command
Takistani Air Corps
```

Acronyms:

```text
TNA
TNP
TBG
TSOC
TAC
```

## 38. Native Official Forms

Native Pashtu versions should be created before the associated patch, HQ sign, vehicle marking or official document is finalised.

These should be natural translations, not phonetic spellings of the English names.

## 39. NATO/UK Intelligence Designations

An English intelligence designation may differ from a group's native self-designation.

Preferred record format:

```text
Native self-designation:
Pashtu

English translation:
English

UK/NATO designation:
English/ASCII acronym
```

---

# PART XIII — NTEF LANGUAGE POLICY

## 40. NTEF Self-Designation

`Northern Takistan Emirate Front / NTEF` remains the UK/NATO/editor designation.

The organisation should eventually receive a natural fictional Pashtu self-designation.

## 41. Native NTEF Name Requirements

The native name should:

- be valid Pashtu;
- convey approximately the intended organisational meaning;
- avoid copying a real extremist group's formal title;
- avoid real extremist slogans;
- remain fictional;
- provide a practical short form if possible.

## 42. Do Not Force English Word Order

The Pashtu self-designation does not need to be a word-for-word translation of:

```text
Northern Takistan Emirate Front
```

Natural Pashtu takes priority.

The English/NATO label may remain a simplified analytical translation.

---

# PART XIV — SIGNAGE

## 43. Government Signage

Preferred hierarchy:

```text
Pashtu
English optional
```

English is appropriate at facilities with regular coalition interaction.

Do not make every village sign bilingual by default.

## 44. Military Bases

Potential layout:

```text
Pashtu facility name
TNA emblem
optional Latin/English identifier
```

## 45. Police Signage

Primary:

```text
Pashtu
```

English is optional.

Vehicle markings may combine:

- TNP symbol;
- Pashtu wordmark;
- `POLICE` where player recognition benefits.

## 46. Road Signs

For new UKSF-created road signs:

```text
Pashtu place name
+
existing Latin map spelling
```

This preserves player usability.

---

# PART XV — VEHICLE TEXT

## 47. TNA

Prefer symbols and numbers over large amounts of text:

- national flag;
- TNA emblem;
- tactical number;
- small native service marking.

## 48. TNP

Police vehicles may use:

```text
Pashtu police designation
+
POLICE
+
unit number
```

after native wording is validated.

## 49. TBG

Border vehicles may use:

- TBG badge;
- native service text;
- tactical/unit number.

---

# PART XVI — PATCHES

## 50. Patch Text

Prefer:

- emblem;
- short native text;
- acronym only where natural.

Do not place an entire organisation title around a tiny patch if it becomes unreadable.

## 51. National Flag Patch

No language required.

---

# PART XVII — CONFIG / SOURCE FILE RULES

## 52. Native Script in Source

Native Pashtu text may exist in:

- PSD;
- SVG;
- design documents;
- stringtable entries where technically required.

Keep text source files UTF-8.

## 53. Native Script in Classnames

**Decision:** `NO`

Use ASCII classnames.

## 54. Texture Filenames

Use ASCII English descriptors.

Preferred:

```text
tnp_police_door_co.paa
tna_hq_sign_co.paa
takistan_road_sign_rasman_co.paa
```

---

# PART XVIII — CASE & PUNCTUATION

## 55. Operational Proper Names

Use normal English capitalisation.

## 56. Hyphens

Preserve established map spelling.

Examples:

```text
Par-e Siah
Sar e Bolaq
```

Do not standardise established names merely for punctuation consistency.

## 57. Config Tokens

Remove punctuation/spaces predictably when a class token is required.

Do not create multiple config spellings for the same location.

---

# PART XIX — NUMERALS

## 58. In-World Numerals

Native-style numerals may be used in Pashtu contexts.

Western numerals:

```text
0 1 2 3 4 5 6 7 8 9
```

are also acceptable for military vehicle numbers, coalition-facing signs and player readability.

## 59. Consistency

Use one numeral convention consistently within an asset family.

---

# PART XX — ABBREVIATIONS

## 60. English Acronyms

Retain:

```text
TNA
TNP
TBG
TSOC
TAC
NTEF
EXFOR
```

for English/editor/intelligence use.

## 61. Native Acronyms

Do not invent Pashtu-letter acronyms merely to imitate Western abbreviation style.

Use a native short form only if it reads naturally.

---

# PART XXI — FICTIONAL ORGANISATION NAMING

## 62. Workflow

For every future Takistani organisation:

```text
1. Define concept in English.
2. Decide whether a native self-name is needed.
3. Draft natural Pashtu.
4. Verify grammar and meaning.
5. Record native script.
6. Create readable operational romanisation.
7. Create English translation/intelligence name.
8. Create ASCII faction ID separately.
```

## 63. Do Not Work Backwards from an Acronym

Do not choose an acronym first and force Pashtu words to fit it.

The native name should sound natural.

---

# PART XXII — AUDIO

## 64. Spoken Pashtu

If voice content is added:

- use native/fluent speakers;
- commission natural lines rather than literal machine translations;
- preserve source text and English translation.

## 65. Captured/Third-Party Audio

Do not use voice lines from another game/mod merely because they sound regional.

Require:

- permission;
- provenance;
- understanding of what is being said.

---

# PART XXIII — SOURCE VALIDATION

## 66. Minimum Validation for Native Text

Before native text ships:

- [ ] English intended meaning recorded.
- [ ] Pashtu native script recorded.
- [ ] Operational romanisation recorded.
- [ ] Spelling checked.
- [ ] Grammar checked for phrases/sentences.
- [ ] RTL rendering checked.
- [ ] Font supports Pashtu-specific letters.
- [ ] Texture export checked.
- [ ] No unintended real organisation/slogan copied.

---

# PART XXIV — DOCUMENTATION TEMPLATE

## 67. Translation Record

Use:

```text
Asset / context:
English meaning:
Pashtu:
Operational romanisation:
Literal translation:
Natural translation:
Reviewed by/source:
Notes:
```

Keep this for important permanent terminology.

---

# PART XXV — SOURCE HIERARCHY

## 68. Preferred Sources

When researching wording, prefer:

1. native/fluent Pashtu review;
2. authoritative dictionaries and linguistic references;
3. Library of Congress romanisation guidance;
4. academic language sources;
5. reputable educational sources.

Avoid relying on:

- random translation sites;
- decorative graphics;
- machine translation alone;
- unverified AI-generated native text.

---

# PART XXVI — PROJECT SPELLING VS SOURCE SPELLING

## 69. Pashtu / Pashto / Pushto

In project prose:

```text
Pashtu
```

In citations/source titles:

preserve the source's spelling.

Example:

```text
Library of Congress — Pushto Romanization Table
```

---

# PART XXVII — LOCKED DECISIONS

## 70. Locked

- Takistani language convention is Pashtu.
- Project English spelling is `Pashtu`.
- Native name is `پښتو`.
- Native script uses proper Pashtu Perso-Arabic orthography.
- Native text is right-to-left.
- Afghanistan-oriented written forms are used where variants require a project choice.
- No specific real-world spoken dialect is declared canonical for Takistan.
- Existing Armaverse/terrain Latin place spellings remain unchanged.
- Native place-name versions may be added later without replacing established map spelling.
- Native script is authoritative for new fictional in-world Takistani wording.
- Player-facing Latin text uses simplified operational romanisation.
- ALA-LC romanisation is a verification/reference tool, not the normal player-facing style.
- Config classnames and normal filenames remain ASCII.
- Scholarly diacritics do not appear in classnames.
- Personal naming is flexible; surnames are not mandatory.
- Real Pashtun tribal identities are not automatically assigned to fictional Takistanis.
- TNA/TNP/TBG/TSOC/TAC remain English/NATO project abbreviations.
- NTEF remains the English/NATO designation until a validated Pashtu self-designation is created.
- New native organisation names must be natural Pashtu rather than acronym-driven translations.
- Pseudo-Arabic/Persian text is prohibited.
- Native text requires spelling/RTL/font review before release.

---

# PART XXVIII — OPEN TASKS

## 71. Next Language Tasks

- [ ] Build first Takistani male personal-name pool.
- [ ] Build first Takistani female personal-name pool.
- [ ] Build optional surname/byname pool.
- [ ] Create validated Pashtu form of `Takistan` for project signage.
- [ ] Create native TNA name.
- [ ] Create native TNP name.
- [ ] Create native TBG name.
- [ ] Create native TSOC name.
- [ ] Create native TAC name.
- [ ] Create NTEF self-designation.
- [ ] Create approved government-signage glossary.
- [ ] Create approved road-sign glossary.
- [ ] Test candidate fonts for all required Pashtu glyphs.
- [ ] Identify a native/fluent reviewer if substantial text/audio is produced.

---

# PART XXIX — RESEARCH SOURCES

Research reviewed 2026-08-09.

## Library of Congress — ALA-LC Romanization Tables

The current Library of Congress index includes a dedicated:

```text
Pushto (2013)
```

romanisation table.

```text
https://www.loc.gov/catdir/cpso/roman.html
```

## Library of Congress — Pushto Romanization Table

Primary technical reference for:

- Pashtu/Pushto alphabet forms;
- Pashtu-specific consonants;
- vowels;
- diphthongs;
- compounds;
- capitalisation;
- treatment of Arabic/Persian/Urdu-origin words.

```text
https://www.loc.gov/catdir/cpso/romanization/pushto.pdf
```

## Encyclopaedia Iranica — Iranian Languages and Scripts

Used to confirm Pashto/Pashtu's use of a modified Arabo-Persian script and the existence of Afghan/Pakistani written variants.

```text
https://www.iranicaonline.org/articles/iran-vi3-writing-systems/
https://www.iranicaonline.org/articles/iran-vi2-documentation/
```

## Omniglot — Pashto Language and Alphabet

Supplementary reference for alphabet presentation and written/dialect variation.

```text
https://www.omniglot.com/writing/pashto.htm
```

## ERIC — Naming and Address in Afghan Society

Broad reference for flexible personal naming and non-universal Western-style surnames.

```text
https://eric.ed.gov/?id=ED109915
```

---

# PART XXX — CURRENT CONCLUSION

The language pipeline for `UKSF_Factions` is:

```text
MEANING / CONCEPT
       ↓
NATURAL PASHTU
       ↓
NATIVE SCRIPT
       ↓
VALIDATION
       ↓
OPERATIONAL ROMANISATION
       ↓
ENGLISH / NATO DESIGNATION
       ↓
ASCII CONFIG TOKEN
```

For established Armaverse geography:

```text
KEEP THE MAP SPELLING
```

For newly created Takistani content:

```text
PASHTU FIRST
ENGLISH/ROMANISATION SECOND
CONFIG TOKEN THIRD
```

The next useful language/admin task is to create the first reviewed Takistani personal-name pool and government terminology glossary, followed by a natural fictional Pashtu self-designation for NTEF.
