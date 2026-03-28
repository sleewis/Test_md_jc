SB_CONFIG_SPELBOARD
#SB_CONFIG_SPELBOARD

## META
CONFIG_ID: SB_CONFIG_SPELBOARD_v1.3
- type: SPELBOARD_CONFIG
- module: VG_SANDBOX
- fase: MINIMAAL_PURE_EXTENDED
- status: ACTIEF
- datum: 2026-03-27

---

## CONTEXT
Deze configuratie beschrijft de PURE SANDBOX inclusief KAART-module.

Doel:
- deterministische VG-run
- geen interpretatie
- 1 selectie = 1 actie
- DATA is leidend
- optionele visuele laag (KAART)

---

## ACTIEVE MODULES

| CODEWOORD     | MODULE                         | STATUS | TYPE      | BESCHRIJVING                       |
|---------------|--------------------------------|--------|-----------|------------------------------------|
| SB-DATA       | SPELBOARD_CORE_COMBINED_V3.json| FINAL  | DATA      | Dataset A1-A18 / T1-T22            |
| SB-VG-RUNNER  | VG_RUNNER_PURE_v1.1.md         | FINAL  | ENGINE    | Pure selectie (geen interpretatie) |
| SB-RUN        | RUN.VG                         | FINAL  | EXECUTIE  | Actie-run                          |
| SB-KAART      | VG_RUNNER_KAART.md             | DEV    | VISUAL    | Visuele kaartgenerator             |

---

## KERNSTRUCTUUR

DATA → ENGINE → ACTIE → (OPTIE) BEELD

---

## FLOW

### BASIS

INPUT
↓
VG_RUNNER
↓
GEVOEL + VERSTAND
↓
ACTIE

### UITGEBREID

INPUT
↓
VG_RUNNER
↓
GEVOEL + VERSTAND
↓
ACTIE
↓
KAART (optioneel)

---

## COMMANDO'S

### ACTIE

RUN.VG.<d20b>.<d12g>.<d20t>.<d12p>

### ACTIE + KAART

RUN.VG.KAART.<d20b>.<d12g>.<d20t>.<d12p>

---

## REGELS (HARD)

- 1 selectie = 1 actie
- GEEN interpretatie
- ALLEEN DATA gebruiken
- ALTIJD cyclisch rekenen
- OUTPUT is vast formaat
- KAART voegt geen betekenis toe (alleen visualisatie)

---

## OUTPUT FORMAT VG

MODE: VG

GEVOEL:
<id — naam>
<actie>

VERSTAND:
<id — naam>
<actie>

ACTIE:
<gevoel.actie> en <verstand.actie>

---

## OUTPUT FORMAT VG.KAART

- eerst VG output
- daarna 1 afbeelding
- geen tekst in afbeelding
- geen extra uitleg

---

## NIET ACTIEF

- SPEL_BOARD.MD
- SB-ARCANA
- SB-SELECTOR
- SB-DICE-RUNNER
- RUN.FULL
- HELP.RUN
- LOG.RUN

---

## ROLLEN

- SM = bewaakt eenvoud
- DEV = implementeert
- RUN = voert uit

---

## SM-LOCK

Deze configuratie is PURE + VISUAL EXTENSION.

De engine:
- voegt niets toe
- legt niets uit
- voert alleen uit

De kaart:
- visualiseert alleen
- voegt geen betekenis toe

