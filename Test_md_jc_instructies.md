# Instructies voor Claude — Project Test_md_jc

## Locatie
- **Lokale werkmap:** `C:\Users\sleew\OneDrive\Documenten\Arduino\Test_md_jc`
- **GitHub repo:** https://github.com/sleewis/Test_md_jc

## Werkwijze
- Claude bewerkt en maakt bestanden aan in de lokale werkmap
- Sjoerd publiceert de wijzigingen via GitHub Desktop naar de GitHub repo
- Claude werkt altijd lokaal — nooit direct op GitHub

---

## Wat is dit project?

Een **orakelsysteem gebaseerd op heilige geometrie**, bestaande uit fysieke dobbelstenen en inzichtkaarten. De gebruiker gooit dobbelstenen, voert de waarden in, en de engine (VG_RUNNER) geeft een GEVOEL-kaart en een VERSTAND-kaart terug met een concrete actie voor die dag.

### Fysieke dobbelstenen (Platoonse Vaste Lichamen)
| Dobbelsteen | Vorm | Element/Thema | Rol in systeem |
|-------------|------|---------------|----------------|
| Zwarte D6 | Kubus (Ruwe Steen) | Aarde | Basis |
| Bronzen D20 Icosaëder | Mercurius | Water | d20b (basis) |
| Transparante D20 Icosaëder | Mercurius | Lucht | d20t (thema) |
| Blauwe D8 Octaëder | Zuiverheid | Water | Extra |
| Groene D12 Dodecaëder | Vrouw/Aarde | Spirit | d12g → GEVOEL selectie |
| Paarse D12 Dodecaëder | Intuïtie/Dromen | Spirit | d12p → VERSTAND selectie |
| Roze D4 Tetraëder | Daadkracht | Vuur | Extra |
| Yes/No munt | — | Dag↔Nacht | Richting |

---

## Dataset: SPELBOARD_CORE_COMBINED_V3.json

Twee reeksen kaarten:

### GEVOEL-kaarten (A1–A18) — Groene D12
Selectie via groene D12 (cyclisch: waarde mod 18)
Thema's: spirituele archetypen (Atlantis, Drakenmagie, Kwantumcreatie, Spaceholder, etc.)

### VERSTAND-kaarten (T1–T22) — Paarse D12
Selectie via paarse D12 (cyclisch: waarde mod 22)
Thema's: Vrijmetselarij / heilige geometrie (Ruwe Steen, Ark van het Verbond, Alziend Oog, Tempel, etc.)

---

## Hoe werkt de engine?

### Commando
```
RUN.VG.<brons_d20>.<groen_d12>.<transparant_d20>.<paars_d12>
```

### Berekening (cyclisch)

**GEVOEL** (A1–A18, MAX=18):
```
start_gevoel  = ((D20_brons - 1) mod 18) + 1
index_gevoel  = ((start_gevoel - 1 + D12_groen) mod 18) + 1
→ selecteer A[index_gevoel]
```

**VERSTAND** (T1–T22, MAX=22):
```
start_verstand  = ((D20_transparant - 1) mod 22) + 1
index_verstand  = ((start_verstand - 1 + D12_paars) mod 22) + 1
→ selecteer T[index_verstand]
```

**Voorbeeld:** `RUN.VG.10.4.7.2`
- GEVOEL: start=10, index=14 → A14 Teacher
- VERSTAND: start=7, index=9 → T9 Loodlijn

### Output formaat
```
MODE: VG

GEVOEL:
<id> — <naam>
<actie>

VERSTAND:
<id> — <naam>
<actie>

ACTIE:
<gevoel.actie> en <verstand.actie>.
```

### Optioneel: met visuele kaart
```
RUN.VG.KAART.<brons_d20>.<groen_d12>.<transparant_d20>.<paars_d12>
```
Genereert aanvullend een symbolische afbeelding (geen tekst, geen interpretatie — alleen visualisatie).

---

## Kernregels van de engine
- 1 selectie = 1 actie
- GEEN interpretatie — DATA is leidend
- ALTIJD cyclisch rekenen bij dobbelsteenwaarden
- OUTPUT is vast formaat — niets extra's buiten het formaat
- Verboden in output: duiding, kern, energie, reflectie, extra advies, interpretatie
- De kaart voegt geen betekenis toe, alleen visualisatie

---

## Actieve modules (project/map)
| Bestand | Rol |
|---------|-----|
| `SPELBOARD_CORE_COMBINED_V3.json` | Dataset A1-A18 / T1-T22 |
| `SB_CONFIG_SPELBOARD_v1.3.md` | Configuratie en spelregels |
| `VG_RUNNER_KAART.md` | Visuele kaartgenerator (in ontwikkeling) |
| `DAGSTART-INVOER.md` | Voorbeeld dagstart-invoer |
| `VG.RUN.foto.md` | Voorbeeld van een volledige run met foto |

---

## Scrum structuur
Ontwikkeling loopt via een **maanfasen-sprint (28 dagen)**. Zie `SCRUMBORD.md` voor het actieve bord.

### Rollen
| Afkorting | Rol |
|-----------|-----|
| SM | Scrummaster — bewaakt eenvoud en proces |
| DEV | Developer — implementeert |
| TEST | Tester — kwaliteit |
| PO | Product Owner — backlog en visie |
| DOC | Documenteerder — legt alles vast |

---

## Bestandsstructuur
```
Test_md_jc/
├── README.md
├── SCRUMBORD.md
├── Test_md_jc_instructies.md   ← dit bestand
├── rollen/
│   ├── SM.md / DEV.md / TEST.md / PO.md / DOC.md
├── sprints/
└── project/
    ├── SPELBOARD_CORE_COMBINED_V3.json
    ├── SB_CONFIG_SPELBOARD_v1.3.md
    ├── VG_RUNNER_KAART.md
    ├── DAGSTART-INVOER.md
    └── VG.RUN.foto.md
```
