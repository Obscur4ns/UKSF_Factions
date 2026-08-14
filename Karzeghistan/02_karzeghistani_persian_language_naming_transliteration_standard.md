# UKSF_Factions — Karzeghistani Persian Language, Naming & Transliteration Standard

**Project:** `UKSF_Factions`  
**Author:** `UKSF Surplus`  
**Document:** Karzeghistani Persian Language, Naming & Transliteration Standard  
**Status:** Active / Research & Art Standard  
**Created:** 2026-08-09  
**Country:** Karzeghistan  
**Project language convention:** Persian  
**Working descriptive term:** Karzeghistani Persian  
**Related documents:**
- `01_karzeghistan_country_theatre_research_brief.md`
- `../sharig/01_sharig_protection_front_research_brief.md`
- `../../project/02_class_and_editor_naming_standard.md`

---

# 1. Purpose

This document establishes the language convention used for Karzeghistan throughout `UKSF_Factions`.

It defines how Persian should be handled in:

- national and government text;
- military and police terminology;
- border-service terminology;
- personal names;
- faction names;
- Sharig Protection Front terminology;
- road signs;
- government signage;
- vehicle markings;
- patches;
- fictional documents;
- intelligence briefs;
- editor display names;
- config classnames;
- texture filenames.

The central rule is:

> **New Karzeghistani native-language material is written in real Persian, while established Armaverse Latin spellings remain unchanged.**

The project should not drift into a mixture of:

```text
Persian
Pashtu
Arabic
Urdu
invented pseudo-script
```

simply because different source assets happen to contain different text.

---

# PART I — PROJECT LANGUAGE DECISION

## 2. Karzeghistani Language

**Decision:** `PERSIAN`

For `UKSF_Factions`, Persian is the standard Karzeghistani language.

Use Persian for new in-universe Karzeghistani state/national text unless a specific minority, foreign actor or historical context requires another language.

---

## 3. Project Term

In English project documentation, the convention may be described as:

```text
Karzeghistani Persian
```

This means:

- real Persian grammar;
- real Persian script;
- Persian-based naming conventions;
- fictional Karzeghistani political/geographic identity.

It does **not** mean Karzeghistan is Iran.

---

## 4. Language Name

English:

```text
Persian
```

Native:

```text
فارسی
```

The project may use `Persian` rather than `Farsi` in English-language documentation.

---

# PART II — CANON STATUS

## 5. Language Is a UKSF Extension

**Status:** `UKSF EXTENSION`

No sufficiently authoritative Bohemia source reviewed for this project explicitly establishes Persian as Karzeghistan's national language.

The decision is based on:

- established Armaverse place-name character;
- Karzeghistan's regional position;
- the need for a consistent fictional linguistic convention;
- deliberate differentiation from Pashtu-speaking Takistan.

Therefore:

```text
KARZEGHISTAN → PERSIAN
```

is a project continuity decision, not a claim of BI canon.

---

# PART III — WRITING SYSTEM

## 6. Script

Persian is written using a Persian form of the Arabic-derived script.

Project rule:

```text
RIGHT TO LEFT
```

Native artwork must be produced using software that correctly handles:

- right-to-left layout;
- contextual joining;
- Persian characters;
- Unicode text.

---

## 7. Persian-Specific Letters

The Persian alphabet contains letters not present in standard Arabic:

```text
پ
چ
ژ
گ
```

Any font intended for Karzeghistani native text must support these correctly.

---

## 8. Persian Character Forms

Where text is stored digitally, prefer proper Persian Unicode forms.

Important examples:

```text
ک
ی
```

rather than substituting Arabic-script variants purely because they look similar in one font.

This improves:

- searchability;
- consistency;
- shaping;
- future text reuse.

---

## 9. Font Test String

Before approving a font, test at minimum:

```text
فارسی
کارزغستان
پ چ ژ گ
ک ی
```

Check:

- every glyph exists;
- RTL order is correct;
- joining is correct;
- no fallback font appears;
- punctuation remains sensible;
- export to texture/PAA preserves the result.

---

# PART IV — TYPOGRAPHY

## 10. Native Text Style

For ordinary modern state signage, use a clear Persian typeface suitable for:

- roads;
- government buildings;
- vehicles;
- uniforms;
- documents.

Do not automatically use decorative calligraphy for functional signage.

---

## 11. Nasta'liq

Nasta'liq has deep importance in Persian calligraphic tradition.

It may be appropriate for:

- ceremonial graphics;
- cultural posters;
- decorative material;
- historical documents.

It should not be the default for:

- vehicle numbers;
- road signs;
- tactical markings;
- small patches.

Readability takes priority.

---

## 12. Half-Space / ZWNJ

Persian typography can require non-breaking internal separation between morphemes.

Where a validated spelling uses a half-space / zero-width non-joiner:

- preserve it in source text;
- test it after export;
- do not replace it blindly with a normal space or remove it.

For important permanent artwork, native text should be reviewed in its final rendered form, not only as plain Unicode text.

---

# PART V — THREE TEXT LAYERS

## 13. Native Layer

Used for:

- signs;
- patches;
- state insignia;
- police markings;
- border-service markings;
- vehicle text;
- government documents;
- environmental graphics.

Native Persian is authoritative for newly created in-world Karzeghistani text.

---

## 14. Operational Romanisation Layer

Used for:

- UKSF intelligence reports;
- mission briefings;
- subtitles;
- English-language project documentation;
- Latin map labels where new names are required.

The operational form prioritises:

```text
readability
consistency
searchability
```

over academic reversibility.

---

## 15. Config / ASCII Layer

Used for:

- Arma classnames;
- variables;
- functions;
- filenames;
- folders;
- faction IDs.

Requirements:

```text
ASCII
no native script
no diacritics
no spaces where class/file syntax forbids them
```

---

# PART VI — REFERENCE ROMANISATION

## 16. ALA-LC Reference

For precise linguistic checking, use the Library of Congress ALA-LC **Persian Romanization Table** as a reference.

The scholarly system distinguishes characters and vowels using forms including:

```text
ā
ī
ū
kh
gh
sh
zh
ch
ḥ
ṣ
ẓ
ʻ
```

and contains explicit rules for Persian grammatical structures such as:

```text
izafah / ezafe
```

---

## 17. Reference Only

ALA-LC is not the routine UKSF player-facing style.

Use it for:

- checking native spellings;
- resolving ambiguous Latin renderings;
- research notes;
- source comparison.

Do not require ordinary players or mission makers to type scholarly characters.

---

# PART VII — UKSF OPERATIONAL ROMANISATION

## 18. General Principle

Prefer:

> **stable, readable Latin spelling**

over:

> **fully reversible academic transliteration**.

Established Armaverse proper-name spellings override mechanical transliteration.

---

## 19. Basic Consonants

Preferred project digraphs:

```text
خ  → kh
ش  → sh
چ  → ch
ژ  → zh
غ  → gh
ق  → q
```

Other consonants normally use their obvious English Latin equivalent.

---

## 20. Long Vowels

Scholarly macrons are removed in normal project text:

```text
ā → a
ī → i
ū → u
```

Example principle:

```text
scholarly: Shāpur
project:   Shapur
```

Existing BI spelling always wins.

---

## 21. Ayn / Hamza

Specialist transliteration signs are normally omitted from routine player-facing text unless needed to prevent confusion.

Do not use:

```text
ʻ
ʿ
ʾ
```

inside normal classnames or filenames.

---

## 22. Qaf and Ghayn

When a new native spelling is known:

```text
ق → q
غ → gh
```

in the operational layer.

Although these may be pronounced similarly in some modern Persian varieties, retaining the spelling distinction improves consistency and research traceability.

---

# PART VIII — EZAFE

## 23. Importance

Persian frequently links nouns and modifiers through **ezafe**.

The Library of Congress scholarly system represents this using forms such as:

```text
-i
-yi
```

depending on context.

---

## 24. UKSF Operational Rule

For normal UKSF-facing Latin text, use:

```text
-e
-ye
```

This better reflects common modern pronunciation and, importantly, aligns with an existing Armaverse-style name:

```text
Shapur e-Dalanper
```

---

## 25. Formatting

Preferred for newly created names:

```text
Name-e Modifier
Name-ye Modifier
```

when the connection needs to be explicit in Latin script.

Existing Armaverse punctuation/spelling remains unchanged even if it does not exactly match the new project style.

---

# PART IX — EXISTING ARMAVERSE PLACE NAMES

## 26. Existing Latin Names Are Locked

Do not re-transliterate established names.

Examples:

```text
Karzeghistan
Mazargan
Shapur
Shapur e-Dalanper
Sharig Plateau
```

These remain the authoritative English/editor/briefing forms.

---

## 27. Why

Changing them would:

- reduce Armaverse recognisability;
- create duplicate spellings;
- make mission search harder;
- falsely imply BI's names were linguistically wrong.

The project language convention supplements existing lore; it does not overwrite it.

---

# PART X — NATIVE COUNTRY NAME

## 28. Karzeghistan

**UKSF project native spelling:**

```text
کارزغستان
```

Operational Latin:

```text
Karzeghistan
```

---

## 29. Status

`کارزغستان` is a **UKSF-created Persian-script representation** of the established fictional country name.

It is not claimed as an official Bohemia-published spelling.

Use it for new project-native material after normal review.

---

## 30. Adjectival Form

Working Persian adjectival form:

```text
کارزغستانی
```

Meaning:

```text
Karzeghistani
```

Status:

`PROJECT FORM`

---

# PART XI — NATIVE PLACE NAMES

## 31. Existing Places

Native spellings for:

- Mazargan;
- Shapur;
- Shapur e-Dalanper;
- Sharig;

should be validated individually before permanent artwork.

Do not simply convert Latin letters one-by-one.

---

## 32. Why Individual Validation Matters

Existing Armaverse Latin names may encode:

- Persian morphology;
- historical spellings;
- fictional forms;
- ambiguous vowel choices.

The Latin map name remains authoritative until a native form is approved.

---

# PART XII — NEW PLACE NAMES

## 33. Workflow

For a new Karzeghistani location:

```text
1. Define intended meaning.
2. Draft natural Persian name.
3. Record Persian script.
4. Verify grammar.
5. Create operational romanisation.
6. Create English translation if needed.
7. Create ASCII config token.
```

---

## 34. Do Not Invent Persian-Looking Noise

Avoid making fictional place names by simply combining fragments such as:

```text
-shahr
-abad
-dar
-stan
```

without checking whether the result is natural.

Regional appearance is not a substitute for language.

---

# PART XIII — PERSONAL NAMING

## 35. Project Model

For practical Arma identities, Karzeghistani formal names may use:

```text
Given Name + Family Name
```

This is a **project convention** for usability.

It does not require Karzeghistan to reproduce the exact civil-registration system of any real country.

---

## 36. Informal Use

In dialogue and local contexts, characters may naturally be referred to by:

- given name;
- surname;
- title + surname;
- role + name.

---

## 37. Name Sources

A future Karzeghistani name pool should draw primarily from authentic Persian-language naming traditions.

It may include:

- Persian-origin names;
- Arabic-origin names established in Persian;
- other Iranian-origin names.

Do not build the pool exclusively from ancient Persian royal names.

---

## 38. Avoid Direct Iran Copy

A Persian-language naming pool does not mean every fictional Karzeghistani must have a name chosen to evoke modern Iranian politics or celebrity figures.

Use ordinary, broad personal-name material.

---

# PART XIV — PERSONAL NAME POOL STANDARD

## 39. Future Pool

Create reviewed lists for:

```text
male given names
female given names
family names
```

Suggested first target:

```text
50–70 male given names
40–60 female given names
40–60 family names
```

These are variety targets only.

---

## 40. Entry Format

Each permanent entry should contain:

```text
Persian:
Operational Latin:
ASCII token if needed:
Meaning/origin notes if relevant:
Source/review:
```

---

# PART XV — TITLES

## 41. Use Sparingly

Do not add Persian honorifics or political/religious titles merely to make characters sound regional.

A title should reflect an actual fictional role.

---

## 42. Military Ranks

Editor-facing rank labels should initially remain English or role-based.

Examples:

```text
Rifleman
Sergeant
Lieutenant
Team Leader
Company Commander
```

Translate ranks into Persian only where an in-world asset actually needs the text.

---

# PART XVI — GOVERNMENT ORGANISATIONS

## 43. English Designations Remain Primary in Editor

Working English names:

```text
Karzeghistani Defence Forces
Karzeghistani National Police
Karzeghistani Border Guard
```

Acronyms:

```text
KDF
KNP
KBG
```

---

## 44. Native Forms

Native institutional names should be natural Persian translations rather than transliterations of English words.

They should be validated before being fixed into:

- patches;
- headquarters signs;
- vehicle liveries;
- formal documents.

---

## 45. Working KDF Form

Provisional:

```text
نیروهای دفاعی کارزغستان
```

Operational:

```text
Niruha-ye Defa'i-ye Karzeghistan
```

English:

```text
Karzeghistani Defence Forces
```

Status:

`WORKING / REVIEW BEFORE ARTWORK`

---

## 46. Working KNP Form

Provisional:

```text
پلیس ملی کارزغستان
```

Operational:

```text
Polis-e Melli-ye Karzeghistan
```

English:

```text
Karzeghistani National Police
```

Status:

`WORKING / REVIEW BEFORE ARTWORK`

---

## 47. Working KBG Form

Provisional:

```text
مرزبانی کارزغستان
```

Operational:

```text
Marzbani-ye Karzeghistan
```

English project designation:

```text
Karzeghistani Border Guard
```

Status:

`WORKING / REVIEW BEFORE ARTWORK`

The English title does not need to be a word-for-word rendering of the short native institutional name.

---

# PART XVII — SHARIG PROTECTION FRONT

## 48. English/NATO Name

Keep:

```text
Sharig Protection Front
SPF
```

for:

- editor;
- intelligence;
- English-language documentation.

---

## 49. Native Self-Designation

Working Persian form:

```text
جبههٔ حفاظت از شاریگ
```

Operational:

```text
Jebhe-ye Hefazat az Sharig
```

Natural English:

```text
Sharig Protection Front
```

---

## 50. Status

The Persian form is:

```text
WORKING / HIGH-CONFIDENCE PROJECT TRANSLATION
```

but should still receive fluent-speaker review before permanent:

- flag;
- patch;
- propaganda-style graphic;
- vehicle stencil.

---

## 51. Why This Form

The native name is written to sound like a Persian organisational title rather than mechanically forcing the English word order.

The English acronym:

```text
SPF
```

remains independent.

Do not try to make the Persian words produce the letters `SPF`.

---

# PART XVIII — SPF TEXT POLICY

## 52. Allowed

SPF artwork may eventually use:

- faction name;
- regional wording;
- simple political slogans created specifically for fiction.

---

## 53. Review Requirement

Political slogans require stronger review than ordinary labels.

Before release:

- validate grammar;
- validate tone;
- ensure no real armed organisation's slogan is copied;
- ensure no unintended extremist/sectarian wording appears.

---

# PART XIX — SIGNAGE

## 54. Government Signage

Preferred hierarchy:

```text
Persian
English optional
```

English is plausible at:

- international facilities;
- airports;
- major border crossings;
- government ministries;
- NATO-partner sites.

---

## 55. Local Signage

Ordinary:

- shops;
- local offices;
- town signs;

should generally be Persian-first.

English should not appear everywhere solely for player convenience.

---

## 56. Road Signs

For new project-created signs:

```text
Persian place name
+
existing/approved Latin spelling
```

is preferred for major routes.

This preserves mission usability.

---

# PART XX — VEHICLE TEXT

## 57. KDF

Prefer:

- national emblem;
- tactical number;
- short Persian service marking;
- limited text.

---

## 58. KNP

Police vehicles can support more explicit text:

```text
پلیس
```

plus:

- badge;
- vehicle number;
- English `POLICE` where appropriate.

---

## 59. KBG

Use:

- border-service emblem;
- short Persian service wording;
- vehicle number.

---

## 60. SPF

Vehicle markings should remain less standardised.

Potential:

- emblem;
- small native faction text;
- tactical/local markings.

Do not make every proxy vehicle look factory-issued.

---

# PART XXI — PATCHES

## 61. Small Patch Rule

Tiny patches should prioritise:

```text
symbol
short text
readability
```

Do not force full long institutional titles onto small shoulder patches.

---

## 62. Native vs English

Government patches may be:

- symbol-only;
- Persian;
- bilingual where useful.

SPF should normally use Persian or symbol-only identity rather than English text.

---

# PART XXII — NUMERALS

## 63. Persian Digits

Persian text may use Persian digits:

```text
۰ ۱ ۲ ۳ ۴ ۵ ۶ ۷ ۸ ۹
```

---

## 64. Western Digits

Western digits remain acceptable for:

- tactical vehicle numbers;
- coalition-facing assets;
- maps;
- Arma usability.

---

## 65. Consistency

Within one asset family, choose one numeral style unless there is a clear reason to mix them.

---

# PART XXIII — ABBREVIATIONS

## 66. English Acronyms

Keep:

```text
KDF
KNP
KBG
SPF
```

for English/editor use.

---

## 67. Native Acronyms

Do not invent Persian-letter acronyms simply because Western institutions use abbreviations.

Use a native abbreviation only if it reads naturally and is actually useful.

---

# PART XXIV — CONFIG RULES

## 68. Native Script in Classnames

**Decision:** `NO`

Do not use Persian script in public Arma classnames.

---

## 69. Public Class Pattern

Future examples:

```cpp
UKSF_Factions_KDF_Rifleman
UKSF_Factions_KNP_Officer
UKSF_Factions_KBG_Guard
UKSF_Factions_SPF_Fighter
```

---

## 70. Filenames

Use ASCII English descriptors.

Examples:

```text
kdf_patch_co.paa
knp_police_door_co.paa
kbg_border_sign_co.paa
spf_flag_co.paa
```

---

# PART XXV — SOURCE TEXT FILES

## 71. Encoding

Any source file containing Persian text must use:

```text
UTF-8
```

---

## 72. Preserve Master Text

Do not rely only on rasterised texture text.

Keep the validated native wording in a project text record so it can be reused or corrected later.

---

# PART XXVI — TRANSLATION RECORD

## 73. Template

For important native terminology:

```text
Asset / context:
English meaning:
Persian:
Operational romanisation:
Literal translation:
Natural translation:
Reviewed by/source:
Status:
Notes:
```

---

# PART XXVII — VALIDATION

## 74. Minimum Native-Text Checklist

Before permanent native text ships:

- [ ] Intended English meaning recorded.
- [ ] Persian native text recorded.
- [ ] Operational romanisation recorded.
- [ ] Grammar checked.
- [ ] Spelling checked.
- [ ] Ezafe checked.
- [ ] RTL rendering checked.
- [ ] Font supports Persian-specific characters.
- [ ] Persian `ک` / `ی` forms preserved.
- [ ] Half-spaces/ZWNJ checked where relevant.
- [ ] Texture export checked.
- [ ] No accidental real organisation slogan copied.

---

# PART XXVIII — SOURCE HIERARCHY

## 75. Preferred Sources

For Persian wording:

1. fluent/native Persian review;
2. authoritative Persian dictionaries/orthographic references;
3. Library of Congress Persian romanisation guidance;
4. Encyclopaedia Iranica / academic linguistic sources;
5. reputable educational references.

---

## 76. Machine Translation

Machine translation may be used to generate a first draft only.

It is not sufficient approval for:

- permanent insignia;
- political slogans;
- long official signs;
- lore documents presented as native text.

---

# PART XXIX — LANGUAGE VARIETY

## 77. Do Not Call It Iranian Persian In-Universe

The project language is Persian.

Karzeghistani characters do not need to describe their speech as:

```text
Iranian Persian
```

because Iran is not the fictional country being modelled.

---

## 78. Karzeghistani Persian

`Karzeghistani Persian` is a project descriptor.

It allows the fictional country eventually to develop:

- local vocabulary;
- accent;
- naming preferences;

without inventing a separate language.

---

## 79. Dialect

Do not hard-code a specific real-world Persian dialect as Karzeghistan's canonical spoken dialect.

Use broadly standard written Persian for project text.

---

# PART XXX — TAKISTAN / KARZEGHISTAN LANGUAGE BOUNDARY

## 80. Project Split

Locked:

```text
Takistan      → Pashtu
Karzeghistan  → Persian
```

---

## 81. Border Multilingualism

The political border does not require perfect linguistic separation.

Plausible:

- bilingual border residents;
- Pashtu speakers in Karzeghistan;
- Persian speakers in Takistan;
- Karzeghi families spanning the border.

Do not use this to erase the primary project-language distinction.

---

## 82. SPF Multilingualism

SPF may contain:

- Persian-speaking Karzeghistanis;
- bilingual Sharig residents;
- Pashtu-speaking Takistani recruits.

Its primary organisational native text should nevertheless use Persian.

---

# PART XXXI — EXISTING `E` PLACE-NAME PATTERN

## 83. Shapur e-Dalanper

The established Latin name:

```text
Shapur e-Dalanper
```

is useful evidence for how Persian-style linking already appears in Armaverse naming.

Do not rename it:

```text
Shapur-i-Dalanper
```

merely to match a scholarly system.

---

## 84. Future Style

For new operational Latin names, prefer:

```text
-e
-ye
```

for ezafe where explicitly represented.

This helps keep new Karzeghistani names visually compatible with established Armaverse naming.

---

# PART XXXII — ART DIRECTION

## 85. Persian Text Should Look Functional

For government/security material, prioritise:

- clean type;
- strong contrast;
- readable size;
- proper RTL composition.

Do not use decorative script simply as an exotic visual texture.

---

## 86. No Pseudo-Persian

Prohibited:

- random Arabic letters;
- mirrored text;
- disconnected glyph strings;
- nonsense copied from unrelated assets;
- Arabic text assumed to be Persian.

---

# PART XXXIII — FIRST TERMINOLOGY SET

## 87. Approved Project-Level Forms

### Persian language

```text
فارسی
Farsi
Persian
```

### Karzeghistan

```text
کارزغستان
Karzeghistan
```

### Karzeghistani

```text
کارزغستانی
Karzeghistani
```

### Sharig Protection Front

```text
جبههٔ حفاظت از شاریگ
Jebhe-ye Hefazat az Sharig
Sharig Protection Front
```

The Karzeghistan and SPF forms remain UKSF-created native forms, not BI-published text.

---

# PART XXXIV — WORKING GOVERNMENT TERMINOLOGY

## 88. KDF

```text
نیروهای دفاعی کارزغستان
Niruha-ye Defa'i-ye Karzeghistan
Karzeghistani Defence Forces
```

Status:

`PROVISIONAL / VALIDATE BEFORE ARTWORK`

---

## 89. KNP

```text
پلیس ملی کارزغستان
Polis-e Melli-ye Karzeghistan
Karzeghistani National Police
```

Status:

`PROVISIONAL / VALIDATE BEFORE ARTWORK`

---

## 90. KBG

```text
مرزبانی کارزغستان
Marzbani-ye Karzeghistan
Karzeghistani Border Guard
```

Status:

`PROVISIONAL / VALIDATE BEFORE ARTWORK`

---

# PART XXXV — PERSONAL-NAME IMPLEMENTATION

## 91. Arma Identity Pool

When implemented, create separate:

```text
male given names
female given names
family names
```

rather than generating random syllables.

---

## 92. Name Display

Normal game format:

```text
Given Family
```

Example structure only:

```text
[Given Name] [Family Name]
```

Do not lock example individuals in this standard.

---

## 93. Transliteration

Personal names should receive one stable operational spelling.

Do not allow multiple variants of the same person's name across:

- briefing;
- map;
- dialogue;
- class/config;
- intel documents.

---

# PART XXXVI — NATIVE SPEAKER REVIEW GATES

## 94. Can Be Used Before Fluent Review

Generally safe after dictionary/grammar verification:

- country name project spelling;
- simple labels;
- common nouns;
- short service names;
- personal-name pool entries from reliable sources.

---

## 95. Must Be Reviewed Before Permanent Release Artwork

- mottos;
- political slogans;
- complex organisational titles;
- long signs;
- formal proclamations;
- narrative documents;
- voiced dialogue.

---

# PART XXXVII — LOCKED DECISIONS

## 96. Locked

- Karzeghistan's project language is Persian.
- Project English language label is `Persian`.
- `Karzeghistani Persian` is the internal descriptive term.
- Persian is a UKSF continuity decision, not claimed BI canon.
- Native text uses Persian Perso-Arabic script.
- Native text is right-to-left.
- Persian-specific letters must be supported correctly.
- Source text uses UTF-8.
- Proper Persian Unicode forms such as `ک` and `ی` are preferred.
- Existing Armaverse Latin place-name spellings remain unchanged.
- Existing names take priority over mechanical transliteration.
- ALA-LC Persian romanisation is a research/verification reference.
- Normal player-facing text does not use scholarly diacritics.
- UKSF operational romanisation uses readable digraphs such as `kh`, `gh`, `sh`, `zh`, `ch`.
- Long-vowel macrons are removed in normal player-facing spelling.
- Operational ezafe is written `-e / -ye`.
- This deliberately aligns with `Shapur e-Dalanper`.
- Native country spelling is project-standard `کارزغستان`.
- Native adjectival form is project-standard `کارزغستانی`.
- Existing native forms of established places are validated individually before artwork.
- New place names are created in natural Persian first.
- Config classnames and filenames remain ASCII.
- Personal names use a practical Given Name + Family Name project model.
- A reviewed personal-name pool will be created separately.
- KDF/KNP/KBG remain the English/editor acronyms.
- SPF remains the English/NATO/editor designation.
- Working native SPF self-designation is `جبههٔ حفاظت از شاریگ`.
- Operational SPF romanisation is `Jebhe-ye Hefazat az Sharig`.
- Persian is SPF's primary organisational native-text language.
- SPF may still include Pashtu-speaking/bilingual members.
- No pseudo-Persian is permitted.
- Complex/political native text requires fluent-speaker review before permanent release artwork.

---

# PART XXXVIII — OPEN TASKS

## 97. Next Language Tasks

- [ ] Build Karzeghistani male personal-name pool.
- [ ] Build Karzeghistani female personal-name pool.
- [ ] Build Karzeghistani family-name pool.
- [ ] Validate native spelling of Mazargan.
- [ ] Validate native spelling of Shapur.
- [ ] Validate native spelling of Shapur e-Dalanper.
- [ ] Validate native spelling of Sharig.
- [ ] Fluent-review KDF native title.
- [ ] Fluent-review KNP native title.
- [ ] Fluent-review KBG native title.
- [ ] Fluent-review SPF native self-designation.
- [ ] Create government/signage glossary.
- [ ] Create military/police terminology glossary.
- [ ] Test candidate fonts.
- [ ] Identify fluent/native Persian reviewer before substantial dialogue or propaganda-style artwork.

---

# PART XXXIX — RESEARCH SOURCES

Research reviewed 2026-08-09.

## Library of Congress — ALA-LC Romanization Tables

The Library of Congress maintains an approved Persian romanisation table.

It is used as the project's technical reference for precise Latin-script checking.

```text
https://www.loc.gov/catdir/cpso/roman.html
```

---

## Library of Congress — Persian Romanization Table

The table documents:

- Persian alphabet romanisation;
- long vowels;
- consonant distinctions;
- Persian grammatical structures affecting romanisation;
- izafah;
- compounds and affixes.

```text
https://www.loc.gov/catdir/cpso/romanization/persian.pdf
```

An older accessible scan is also available:

```text
https://www.loc.gov/catdir/cpso/romanization/persian-1997.pdf
```

The UKSF operational system deliberately simplifies this scholarly layer.

---

## Encyclopaedia Iranica — Iranian Languages and Scripts

Used to verify Persian's place among modern Iranian literary languages and the use of Arabic-derived script for Persian.

```text
https://www.iranicaonline.org/articles/iran-vi2-documentation/
https://www.iranicaonline.org/articles/iran-vi3-writing-systems/
```

---

## Encyclopaedia Iranica — Arabic Elements in Persian

Used as supporting orthographic background for Persian spelling and the relationship between Arabic-origin letters and Persian pronunciation.

```text
https://www.iranicaonline.org/articles/arabic-v/
```

---

## Encyclopaedia Iranica — Calligraphy

Used for contextual background on Persian nasta'liq and related calligraphic traditions.

```text
https://www.iranicaonline.org/articles/calligraphy/
```

---

## Encyclopaedia Iranica — Personal Names

Used as broad background for the long and varied Iranian/Persian naming tradition.

```text
https://www.iranicaonline.org/articles/personal-names-iranian/
```

This is not treated as a modern Karzeghistani civil-registration rule.

---

# PART XL — CURRENT CONCLUSION

The Karzeghistani language pipeline is now:

```text
MEANING / CONCEPT
       ↓
NATURAL PERSIAN
       ↓
PERSIAN SCRIPT
       ↓
VALIDATION
       ↓
UKSF OPERATIONAL ROMANISATION
       ↓
ENGLISH / NATO DESIGNATION
       ↓
ASCII CONFIG TOKEN
```

The key regional language split is:

```text
TAKISTAN
Pashtu
پښتو

KARZEGHISTAN
Persian
فارسی
```

For established geography:

```text
KEEP BI / TERRAIN LATIN SPELLING
```

For new Karzeghistani material:

```text
PERSIAN FIRST
OPERATIONAL LATIN SECOND
CONFIG TOKEN THIRD
```

The next useful language/admin task is a **Karzeghistani Persian terminology and personal-name pool**, which should finalise:

- KDF/KNP/KBG wording;
- SPF wording;
- government/security vocabulary;
- male names;
- female names;
- family names;

before Karzeghistani insignia, vehicle markings or character identities are produced.
