# 🔯 PENTAGRAM_BETEKENIS

## META
CONFIG_ID: PENTAGRAM_BETEKENIS_v1.0
- type: CONTEXT_LAAG
- module: PENTAGRAM
- status: ACTIEF
- datum: 2026-03-28

---

## DOEL

Voegt elementaire context toe aan een VG-run op basis van de fysieke positie
van elke dobbelsteen op het pentagram.

De positie kleurt de kaart — zonder de actie te wijzigen.

---

## PENTAGRAM POSITIES EN BETEKENIS

| Positie | Element | Spirituele betekenis |
|---------|---------|----------------------|
| Aarde | 🜃 Aarde | Geworteld, stabiel, manifest — het gevoel is verankerd in de werkelijkheid |
| Water | 🜄 Water | Vloeiend, zuiverend, receptief — ruimte voor wat wil komen |
| Vuur | 🜂 Vuur | Daadkrachtig, transformerend, willend — energie die beweegt en verbrandt |
| Lucht | 🜁 Lucht | Helder, mentaal, vrij — het verstand ademt en ziet |
| Spirit | ✦ Spirit | Verbindend, transcendent, heel — contact met de bron |
| tussen Water en Vuur | 🜄🜂 | Transformatie door gevoel — emotie die aanzet tot actie |
| tussen Spirit en Water | ✦🜄 | Intuïtieve stroom — het hogere voedt het gevoel |
| tussen Lucht en Spirit | 🜁✦ | Verheven denken — verstand reikt naar het hogere |

---

## DOBBELSTENEN OP HET PENTAGRAM

| Dobbelsteen | Positie | Rol in engine |
|-------------|---------|---------------|
| Bronzen D20 | Aarde | Start GEVOEL — gevoel geworteld |
| Transparant D20 | Lucht | Start VERSTAND — verstand helder |
| Groene D12 | tussen Spirit en Water | Selectie GEVOEL — spiritueel-intuïtief |
| Paarse D12 | tussen Lucht en Spirit | Selectie VERSTAND — mentaal-transcendent |
| Blauwe D8 | Water | Zuivering van het veld |
| Roze D4 | Vuur | Daadkracht — actie-impuls |
| Zwarte D6 | tussen Water en Vuur | Ruwe Steen — rauwe transformatie |
| Munt | DAG → NACHT stroom | Richting van de tijd |

---

## ELEMENT CONTEXT PER KAART

### GEVOEL kaart
Wordt beïnvloed door twee posities:
- **Aarde** (Bronzen D20) → verankert het gevoel in het fysieke
- **Spirit–Water** (Groene D12) → voedt het gevoel vanuit intuïtie en het hogere

Leeswijze: *het gevoel is geworteld (Aarde) en gevoed door intuïtie (Spirit–Water)*

### VERSTAND kaart
Wordt beïnvloed door twee posities:
- **Lucht** (Transparant D20) → geeft het verstand helderheid en vrijheid
- **Lucht–Spirit** (Paarse D12) → verbindt het verstand met het transcendente

Leeswijze: *het verstand is helder (Lucht) en reikt naar het hogere (Lucht–Spirit)*

---

## COMMANDO

```
RUN.VG.PENTAGRAM.<brons_d20>.<groen_d12>.<transparant_d20>.<paars_d12>
```

---

## OUTPUT FORMAAT

```
MODE: VG.PENTAGRAM

GEVOEL:
<id> — <naam>
<actie>
ELEMENT: 🜃 Aarde + ✦🜄 Spirit–Water
<element betekenis gevoel>

VERSTAND:
<id> — <naam>
<actie>
ELEMENT: 🜁 Lucht + 🜁✦ Lucht–Spirit
<element betekenis verstand>

ACTIE:
<gevoel.actie> en <verstand.actie>.
```

---

## VOORBEELD

INPUT: `RUN.VG.PENTAGRAM.12.12.12.12`

```
MODE: VG.PENTAGRAM

GEVOEL:
A6 — Kinderen
Handel vanuit eenvoud en speelsheid
ELEMENT: 🜃 Aarde + ✦🜄 Spirit–Water
Eenvoud geworteld in het dagelijkse leven, gevoed door spirituele stroom

VERSTAND:
T2 — Perfecte Steen
Streef naar innerlijke voltooiing
ELEMENT: 🜁 Lucht + 🜁✦ Lucht–Spirit
Verfijning gedragen door helderheid, reikend naar transcendentie

ACTIE:
Handel vanuit eenvoud en speelsheid en streef naar innerlijke voltooiing.
```

---

## REGELS

- De elementaire context verklaart — wijzigt de actie NIET
- ACTIE blijft identiek aan normale VG output
- Element betekenis is vast per positie — geen interpretatie per run
- Kaart blijft leidend, element is context
