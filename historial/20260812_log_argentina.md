# Log — Argentina · Commercial Clients (C&I) · 2026-08-12

**Scope of this run:** complete the Commercial Clients (C&I) section of the `Argentina`
sheet for the 16 clients already listed (sheet rows 16–31, list numbers 9–24). Generation
Clients, Competitors, BESS Projects, Incentives and every other section were left untouched.

**Candidate file (superseded):** this run originally produced `candidato_argentina_2026-08-12.xlsx`
as a separate file, per the workflow in place at the time. As of the 12-08-2026 reorg, this
change is applied directly to the official `BESS_POTENTIAL_CLIENTS_v2.xlsx` on `main`, and this
log is archived here in `/historial/` instead of sitting loose in the repo root.
**Base file:** `BESS_POTENTIAL_CLIENTS_v2 1.xlsx` (as it stood before this run)
**Data cut-off:** 2026-08-12 (recorded per row in the new `As of` column)

**Headline result: 0 of 16 C&I clients have a BESS in operation with a publicly verifiable
capacity figure.** Following the methodological note in `mapa_gaps_mercado2026.md`, this is
recorded as a *confirmed* gap, not an unresearched one: each of the 16 companies was searched
individually for battery storage in Argentina, and each row now carries an explicit note in
the sheet stating what was searched and what was found instead. This appears to be the real
ceiling of public data for Argentine C&I storage as of today, not a shortfall of research.

---

## 1. Changes to the xlsx

### 1.1 New columns on the Commercial Clients block (row 15 header)

The section previously had only `#` (A), name (B), category (C) and `SCALE` (D) — no data
columns at all. Columns E, F and G mirror the Chile sheet's Commercial Clients block exactly
(`BESS ADQUIRED [MWh]` | `Brand` | `PROJECT`), so the two sheets stay comparable. Columns
H–K are new and exist to satisfy the external-reader requirements in CLAUDE.md.

| Col | Header | Purpose |
|---|---|---|
| E | `BESS ADQUIRED [MWh] (blank = no BESS confirmed; see BESS STATUS column)` | Numeric only, same unit in every row. Empty in all 16 rows — no confirmed capacity exists. |
| F | `Brand` | Manufacturer. Mirrors Chile. |
| G | `PROJECT` | Project name. Mirrors Chile. |
| H | `BESS STATUS / GAP NOTE (specifically searched 2026-08-12)` | New. Confirmed-gap note plus the relevant energy context found for that company. |
| I | `SOURCE CLASSIFICATION (a = official / b = market provider incl. specialised trade press / c = own estimate)` | New. Source class visible in the xlsx itself, with the legend written into the header so it needs no external key. |
| J | `SOURCE (name + access date)` | New. Source name with access date, per the "cite with access date" rule. |
| K | `As of` | New. Per-row data cut-off. |

**Convention used for confirmed gaps:** the numeric column (E) is left blank so the column
keeps a single format and unit, and the gap note is written into F, G and H. A blank E cell
is therefore never ambiguous — the same row states in three places that no BESS was found and
on what date it was searched.

**No structural change was made beyond adding these columns:** no rows inserted, no rows
reordered, no category moved, no formula touched. The known open question about Argentina's
category order (see `mapa_gaps_mercado2026.md`, "Nota estructural pendiente") was left exactly
as it is.

### 1.2 Row-by-row detail

`#` is the list number in column A. All 16 rows: previous value = **empty (no data columns
existed)**; new value = the note below. Status of every row: **confirmed gap — searched, no
public BESS found**, except where flagged otherwise.

| # | Row | New value (summary) | Source | Confirmed / estimated |
|---|---|---|---|---|
| 9 | BARRIK GOLD | No BESS owned or announced by Barrick in Argentina. Veladero (50/50 JV Barrick–Shandong Gold, operated by Minera Andina del Sol) is supplied via the "Libertadores" line under a 25 MW / 8-year PPA with Enel imported from Chile; site also has a 2 MW wind turbine and an on-site PV plant with no published capacity. | Editorial RN 22-Apr-2026; Barrick corporate site (Veladero); GAPP / Club Minero — accessed 2026-08-12 | Confirmed gap (b) |
| 10 | GLENCORE | No BESS announced. El Pachón (~USD 9,500 m) and MARA / Agua Rica–Alumbrera (~USD 4,000–4,500 m) are in feasibility and RIGI stage; Alumbrera restart announced for 2026, production targeted 2028. No electricity-supply or storage solution publicly disclosed. Future potential load, not a current asset. | El Economista; La Nación; Minería & Desarrollo; infoenergia.info — accessed 2026-08-12 | Confirmed gap (b) |
| 11 | YAMANA GOLD | **DATA-QUALITY FLAG.** Entity ceased to exist 31-Mar-2023 (acquired by Pan American Silver, USD 4,800 m). Cerro Moro is now 100% Pan American Silver; MARA is held by Glencore. No BESS under any owner. | Pan American Silver release 31-Mar-2023; PAAS operations page — accessed 2026-08-12 | Confirmed (a) |
| 12 | YPF | No BESS in operation. **Announced, not built — VERIFY:** hybrid park pairing 250 MW solar with a 120 MW / 5–6 h battery, seeking RIGI benefits, reported Aug-2026. No figure entered in column E (see §2.1). YPF Luz's El Quemado (305 MW, Mendoza, with EMESA) has no storage component. | BNamericas, accessed 2026-08-12 (headline/abstract only, full text paywalled); pv magazine, Strategic Energy Europe | Announced, unverified (b) |
| 13 | PANAMERICAN ENERGY | No public BESS announced. PAE publishes a renewable portfolio but discloses no battery storage project in Argentina. Naming caution recorded in the cell: PAE (oil & gas) ≠ Pan American Silver (mining). | pan-energy.com renewables page + targeted press search — accessed 2026-08-12 | Confirmed gap (b) |
| 14 | TECPETROL | No BESS announced. Techint decarbonisation is wind-based: Buena Aventura wind park (Gonzales Chaves, BA; USD 203 m; commissioned 2024) supplies ~50% of Tenaris Campana, within ~300 MW of wind for Tenaris/Ternium. TechEnergy Ventures has USD 40 m in 17 start-ups incl. lithium/battery — venture capital, not an installed asset. | Tecpetrol corporate news; LIDE Argentina — accessed 2026-08-12 | Confirmed gap (b) |
| 15 | PUERTO DE BUENOS AIRES | No BESS. Rooftop PV of ~134 kW total minimum power reported, explicitly **on-grid, without storage**. Operator: Administración General de Puertos S.A.U. (AGP). | Dynamic Energy (installer) project note — accessed 2026-08-12 **via search snippet; direct fetch returned HTTP 503**; AGP page (argentina.gob.ar) | Confirmed gap (b) — capacity figure is vendor-sourced and single-source, flagged in the cell as indicative |
| 16 | PUERTO DE ROSARIO | No public BESS announced for Terminal Puerto Rosario (TPR). Nearest comparable in the Gran Rosario node is a 1.2 MW PV self-generation plant (2,300 panels) at the ACA terminal in Timbúes, approved as "Autogenerador" under SE Res. 295/2025 — **different company and site, no storage**; recorded as context only. | estaciones.com.ar 18-Jul-2025 — accessed 2026-08-12 | Confirmed gap (b) |
| 17 | CENCOSUD | No BESS in Argentina. The AES Andes renewable supply contract extended to March 2037 (>80% of store operations) is **Chile-only and is a PPA, not Cencosud-owned storage** — not transferable to this row. | pv magazine Latinoamérica 16-Jun-2026; Guía Chile Energía — accessed 2026-08-12 | Confirmed gap (b) |
| 18 | FALABELLA | **DATA-QUALITY FLAG.** Falabella exited Argentina in 2021 — last stores closed Apr-2021, e-commerce closed 31-May-2021, definitive exit 01-Jun-2021. No operating load in the country, therefore no BESS potential as listed. | Infobae 01-Jun-2021; La Nación 06-Abr-2021; Cooperativa.cl 01-Jun-2021 — accessed 2026-08-12 | Confirmed (b) |
| 19 | EZEIZA AIRPORT BUENOS AIRES | No BESS. Aeropuertos Argentina reports 100% renewable electricity at Ezeiza and at AA Cargas (**contracted supply, not on-site storage**), ISO 50001, Airport Carbon Accreditation. The USD 110 m 2026 plan includes a ground energy supply system for five aircraft stands — no battery component disclosed. | Futuro Sustentable; Diario Río Negro; Aviación News; Ámbito — accessed 2026-08-12 | Confirmed gap (b) |
| 20 | TELECOM | No public BESS announced. USD 1,300 m capex planned for 2026 (5G, fibre), no storage component. Site/data-centre back-up batteries are standard practice but are not published as BESS capacity — no MW/MWh available. Acquired Telefónica Argentina Feb-2025 (USD 1,245 m), ANC-conditioned. | TeleSemana 24-Apr-2026; argentina.gob.ar (ANC ruling) — accessed 2026-08-12 | Confirmed gap (b) |
| 21 | MOVISTAR | No public BESS announced. **DATA-QUALITY FLAG:** acquired by Telecom in Feb-2025 (ANC-conditioned) — rows 20 and 21 may be the same corporate group. Pre-transaction mobile share: Movistar 24.4%, Telecom/Personal 33.8%, Claro 41.8%. | argentina.gob.ar (ANC ruling); TeleSemana 24-Apr-2026 — accessed 2026-08-12 | Confirmed (a) |
| 22 | CLARO | No public BESS announced. USD 500 m capex planned for 2026, no storage component; ~42% mobile share post-consolidation. | TeleSemana 24-Apr-2026 — accessed 2026-08-12 | Confirmed gap (b) |
| 23 | PUBLIC HEALTH NETWORK | No public BESS announced at Argentine public hospitals. Generic category, not a named counterparty — a specific network has to be defined before capacity can be tracked. | Targeted web search 2026-08-12 — no public BESS found | Confirmed gap (b) |
| 24 | PRIVATE CLINICS | No public BESS announced at any named private clinic in Argentina. Solar-plus-storage micro-grids are commercially offered by installers, but only as vendor marketing — not usable as project evidence. Generic category, same caveat as #23. | Targeted web search 2026-08-12 — no public BESS found | Confirmed gap (b) |

---

## 2. Items flagged for review ("revisar")

### 2.1 YPF — announced hybrid, entity attribution unconfirmed
BNamericas reported (Aug-2026) that "YPF" is proceeding with a hybrid park of 250 MW solar +
120 MW / 5–6 h battery under RIGI. Two reasons this was **not** entered as a capacity figure:

1. **Single source**, and the full text is paywalled — only the headline and abstract could be
   read. No second source corroborating the figures was found.
2. **The reporting does not distinguish YPF S.A. from YPF Luz.** YPF Luz is the group's power
   arm and is a *separate row* in Generation Clients (row 10). Attributing the battery to the
   oil company row purely because they share a corporate group would be exactly the
   completion-by-analogy that CLAUDE.md prohibits.

It is recorded in the cell as an announcement with a VERIFY flag. Worth re-checking once
Spanish-language trade press picks it up and names the developing entity.

### 2.2 Rows whose subject no longer matches reality
Three of the 16 rows are not, today, trackable Argentine C&I counterparties. These are
**structural decisions and were deliberately left for Nicolás** — no row was renamed or removed:

| Row | Issue | Options |
|---|---|---|
| #11 YAMANA GOLD | Company dissolved into Pan American Silver in 2023; Argentine asset is Cerro Moro | Rename to Pan American Silver, or remove |
| #18 FALABELLA | No operations in Argentina since 2021 | Remove, or replace with a retailer that still operates locally |
| #21 MOVISTAR | Acquired by Telecom (#20) in Feb-2025 | Merge rows 20 and 21, or keep separate while the ANC conditions apply |

Rows #23 (PUBLIC HEALTH NETWORK) and #24 (PRIVATE CLINICS) are generic categories rather than
named companies, so no capacity data can ever be attached to them as written. They are usable
as market-segment placeholders, but not as client records.

### 2.3 Source-quality caveats
- **#15 Puerto de Buenos Aires** — the ~134 kW PV figure comes from the installing company's
  own website, and the page returned HTTP 503 on direct retrieval, so the number was read from
  a search snippet. It is flagged as indicative in the cell. It is *not* a BESS figure in any
  case, so it does not affect any capacity total.
- No value in this run was classified **(c) own estimate**. Nothing was inferred.

---

## 3. Findings outside this run's scope (not written to the xlsx)

Two findings turned up during the C&I searches that belong to other sections of the Argentina
sheet. They were **not** applied, because this run's scope is Commercial Clients — flagging
them here so they are not lost. As of the 12-08-2026 reorg, the Competitors finding below has
been reflected in `mapa_gaps_mercado2026.md` as a documented status update (not yet applied to
the Argentina sheet's Competitors section itself — that still needs its own dedicated run).

### 3.1 Competitors — first publicly confirmed manufacturer–project pair in Argentina
The Competitors section currently reads "PENDIENTE — sin datos públicos confirmados" (reviewed
07-08-2026), on the basis that AlmaGBA/AlmaSADI awardees had not yet closed technology
agreements. **That has now changed:**

> **Trina Storage → Central Dock Sud (controlled and operated by YPF Luz) → "Alma Sur" BESS,
> 90 MW / 481 MWh, 96 Elementa 2 containers, part of the AlmaGBA programme.** Announced
> Jan-2026 as part of a 1,203 MWh LATAM package (722 MWh in Chile with T-Power/Toesca,
> 481 MWh in Argentina with YPF Luz).
>
> Sources: Trina Solar LAC newsroom (14-Jan-2026); pv magazine Latinoamérica (09-Jan-2026);
> ess-news.com (12-Jan-2026); BNamericas; Reporte Minero. All accessed 2026-08-12.
> Classification: (b) market provider / manufacturer announcement, multi-source.

This follows the Competitors methodology in CLAUDE.md (project first → manufacturer second)
and is corroborated by several independent outlets. It would also give a project name and a
capacity split to part of the aggregated "AlmaGBA — resto de adjudicatarios (637 MW)" row in
BESS Projects, which currently lists Central Dock Sud without a breakdown.

**Recommendation:** open a follow-up run for Argentina — Competitors, rather than folding it
into this PR.

### 3.2 Barrick / Iglesia Community Solar Park — a trap worth recording
Several outlets report the Iglesia Community Solar Park (8.5 MWp PV + **32 MWh BESS**,
announced Apr-2026, San Juan) in the same breath as Barrick's Veladero mine, and one headline
frames it as Barrick betting on renewables. The primary reporting is clear that the park is
**owned and executed by EPSE / Province of San Juan**, funded through the "Fideicomiso Fase 6"
mining trust, and will be operated by EPSE over a projected 30-year life; Barrick accompanies
it as a community-development commitment. It is therefore **not** Barrick BESS capacity and was
not recorded as such. If a future run picks up Argentine BESS projects by province, this is a
real 32 MWh project — it just belongs to EPSE, not to a C&I client.

---

## 4. Compliance notes

- **Language:** all new xlsx content and this log are in English; proper names (companies,
  projects, laws, regulators) are kept as they appear in the source.
- **Every figure carries a source with an access date**; source class (a/b/c) is visible in
  the xlsx itself, not only here.
- **No value was completed from general knowledge.** Every row was searched on 2026-08-12.
- **No completion by analogy:** the YPF/YPF Luz, Yamana/Pan American Silver, PAE/Pan American
  Silver and Cencosud Chile/Argentina cases were each handled by *not* transferring the
  related entity's data.
- **File handling (original run):** the candidate was produced by editing the Argentina
  worksheet XML inside the workbook package, rather than through a full openpyxl re-save. A
  round-trip through openpyxl was tested first and **silently dropped all five embedded
  images** (the logos in `xl/media/`) along with the shared-string table. The method used
  changed only `xl/worksheets/sheet2.xml` and `xl/styles.xml`; the other 30 parts of the
  package were byte-identical to the official file at the time. Verified after the build:
  identical part list, all XML well-formed, every pre-existing formula intact
  (`Argentina!E7`, `E9`, `E97=SUM(E87:E96)`; `Chile!E8`, `E9`) together with its cached value,
  and **zero new formulas introduced**.
- **Recalculation (original run):** not applicable and not run at the time — that change
  added no formulas and touched no existing one, so all cached values remained those of the
  official file. For the record, LibreOffice could not be used to verify anyway: `soffice` in
  that Routine environment timed out (>8 min) even on a two-cell test workbook.
- **Applied to the official file (12-08-2026, Chat session):** this candidate was subsequently
  applied cell-by-cell to `BESS_POTENTIAL_CLIENTS_v2.xlsx` via openpyxl (`data_only=False`),
  verified 0 diffs against the original on the other four sheets, and recalculated with 0
  formula errors (6 formulas evaluated). This log and the resulting xlsx/gap-map snapshots
  were archived to `/historial/20260812_*` as part of the same reorg that introduced this
  folder.
- **Branch (original run):** this run was pushed to `claude/modest-dijkstra-rpxwbq`, the
  branch assigned by the scheduler, instead of the `claude/[país]-[fecha]` convention in
  CLAUDE.md (`claude/argentina-2026-08-12`). The branch name was imposed by the Routine
  harness and could not be chosen at the time.

---

## 5. Update applied to `mapa_gaps_mercado2026.md` (12-08-2026)

- **Argentina → Commercial Clients:** 🟡 → ✅ (12-08-2026) — "16/16 clients specifically
  searched 2026-08-12; 0/16 with a confirmed BESS. Documented confirmed gap, with source
  class, source and access date per row. This is the real public-data ceiling, not pending
  work. 4 rows flagged for identity review (Yamana Gold, Falabella, Telecom/Movistar, YPF),
  unresolved — pending Nicolás's decision."
- **Completeness-per-client table, Argentina → Commercial Clients:** updated to "0/16 with a
  numeric figure, but now 16/16 with a documented, sourced status."
- **Argentina → Competitors:** updated with the manufacturer–project pair found 2026-08-12
  (Trina Storage → Central Dock Sud / YPF Luz, Alma Sur 90 MW / 481 MWh) — pending its own
  dedicated run to apply it to the Argentina sheet itself.
