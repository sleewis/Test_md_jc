# ⚙️ VG_RUNNER — PURE MODE

## META
CONFIG_ID: VG_RUNNER_PURE_v1.1
- type: EXECUTIE
- module: VERSTAND_GEVOEL_RUNNER
- status: FIXED
- datum: 2026-03-27

---

## DOEL

VG_RUNNER vertaalt dobbelstenen naar exact:

GEVOEL + VERSTAND → 1 ACTIE

Zonder interpretatie.
Zonder duiding.
Altijd reproduceerbaar.

---

## HARD RULES

- DATA is leidend
- ENGINE rekent alleen
- OUTPUT bevat geen uitleg
- exact 1 actie
- altijd cyclisch rekenen
- altijd beide kaarten gebruiken
- geen extra tekst buiten outputformaat

---

## INPUT

- Brons D20
- Groen D12
- Transparant D20
- Paars D12

Commando:

RUN.VG.<brons_d20>.<groen_d12>.<transparant_d20>.<paars_d12>

Voorbeeld:

RUN.VG.10.4.7.2

---

## DATA

Bron:
SPELBOARD_CORE_COMBINED_V3.json

Structuur record:

id → tag → naam → actie

- #GEVOEL = A1–A18
- #VERSTAND = T1–T22

---

## LOGICA

### GEVOEL

MAX = 18

start_gevoel = ((D20_brons - 1) mod 18) + 1
index_gevoel = ((start_gevoel - 1 + D12_groen) mod 18) + 1

→ selecteer A[index_gevoel]

### VERSTAND

MAX = 22

start_verstand = ((D20_transparant - 1) mod 22) + 1
index_verstand = ((start_verstand - 1 + D12_paars) mod 22) + 1

→ selecteer T[index_verstand]

---

## ACTIE REGEL

Combineer uitsluitend:
- gevoel.actie
- verstand.actie

Tot exact 1 directe zin.

Template:

<gevoel.actie> en <verstand.actie>.

---

## OUTPUT FORMAAT

MODE: VG

GEVOEL:
<id> — <naam>
<actie>

VERSTAND:
<id> — <naam>
<actie>

ACTIE:
<gevoel.actie> en <verstand.actie>.

---

## VERBODEN IN OUTPUT

- duiding
- kern
- energie
- reflectie
- extra advies
- interpretatie
- uitleg over de kaarten

---

## VOORBEELD RUN

INPUT:
RUN.VG.10.4.7.2

UITVOER:

MODE: VG

GEVOEL:
A14 — Teacher
Draag kennis over

VERSTAND:
T9 — Loodlijn
Handel met integriteit

ACTIE:
Draag kennis over en handel met integriteit.

---

## VALIDATIECHECK

Een run is alleen geldig als:

- beide ids bestaan in dataset
- output exact 1 actie bevat
- geen tekst buiten outputformaat staat
- actie volledig herleidbaar is tot dataset

---

## KERN

De kaart is de actie.
