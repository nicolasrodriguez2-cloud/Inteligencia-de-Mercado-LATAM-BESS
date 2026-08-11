# Mapa de gaps — BESS Potential Clients (referencia: hoja Chile)

Generado: 07-08-2026. Última actualización: 11-08-2026 (auditoría de completitud por cliente en Generation/Commercial Clients, sobre el xlsx real). Actualizar manualmente cada vez que una sesión de nivelación cierre una categoría (marcar ✅ y anotar fecha).

Chile es el estándar de completitud (12 secciones). Este mapa muestra, por país, qué sección existe con datos, cuál existe pero vacía/parcial, y cuál no existe todavía.

## Leyenda
- ✅ Completa (o con nivel de detalle equivalente a Chile)
- 🟡 Existe pero incompleta / parcial
- ⬜ No existe todavía en la hoja

**Nota sobre Generation Clients y Commercial Clients específicamente:** el ✅/🟡 de estas dos secciones indica si la sección *existe con nombres*, no si cada cliente tiene sus datos numéricos (MW/MWh) completos. Ver la sección "Completitud por cliente" más abajo para el detalle real — es la referencia a usar para priorizar trabajo, no el estado a nivel de sección.

## Chile (estándar — no requiere nivelación estructural, solo mantenimiento semanal)
Overview ✅ · Generation Clients ✅ (4/4 clientes con dato completo) · Commercial Clients 🟡 (2/28 clientes con dato numérico — ver nota metodológica abajo) · Government Institutions ✅ · Regulation Involved ✅ · Public Policies ✅ · Competitors ✅ (4 registros — ampliable) · BESS capacity (serie temporal) ✅ · Incentives ✅ · Technical/grid requirements ✅ (el más detallado de las 4 hojas) · Pricing (CMg) ✅ · BESS Projects ✅

**Pendiente decisión de Nicolás:** ¿el bajo llenado de Commercial Clients en Chile (2/28) refleja el techo real de datos públicos disponibles (la mayoría de estos clientes no tiene BESS anunciado), o es un gap real a completar? Si es lo segundo, agregar Chile — Commercial Clients a la cola de trabajo igual que el resto de los países.

## Completitud por cliente — Generation Clients & Commercial Clients (auditado 11-08-2026, sobre el xlsx real)

| País | Generation Clients | Commercial Clients |
|---|---|---|
| Chile | 4/4 con MW instalado + BESS + construcción | 2/28 con dato numérico (CODELCO 175 MWh/DUNE PLUS; COPEC 3.9 MWh/TESLA/COUSIÑO) |
| Argentina | 7/8 con MW instalado (NA-SA sin ningún dato); "under construction" solo en 3/8 | 0/16 con dato numérico — solo nombre y categoría |
| Colombia | 6/6 nombres, sin ninguna columna de capacidad rellenada | 0/12 con dato numérico — solo nombre y categoría |
| Perú | 9/9 con MW instalado; BESS capacity en 3/9 (formato inconsistente); construcción en 1/9 | 0/17 con dato numérico — solo nombre y categoría |
| Uruguay | 0 registros, solo headers | 0 registros, solo headers |

**Nota metodológica — importante para no malinterpretar el gap:** Generation Clients son generadoras que publican MW instalados como práctica estándar/regulatoria — un vacío ahí es casi siempre un gap real de investigación. Commercial Clients (C&I) es distinto: la mayoría de estas empresas (retail, hospitales, puertos, telecom) no tiene BESS instalado o anunciado todavía, así que un llenado bajo puede ser el techo real de datos públicos disponibles, no falta de trabajo. Al revisar candidatos de Cowork sobre Commercial Clients, distinguir "confirmé que no hay BESS público para esta empresa" (dejar vacío, documentado) de "no busqué lo suficiente" (gap real).

---

## Argentina
| Sección | Estado | Nota |
|---|---|---|
| Overview | ✅ | |
| Generation Clients | 🟡 | 7/8 clientes con MW instalado — NA-SA sin ningún dato. Columna "BESS capacity under construction" vacía en 5/8 filas |
| Commercial Clients | 🟡 | 0/16 clientes con dato numérico — sección tiene nombre y categoría, falta todo dato de MW/MWh/BESS. Ver nota metodológica sobre disponibilidad real de dato público |
| Government Institutions | ✅ | |
| Regulation Involved | ✅ | Muy completo, incluye AlmaGBA/AlmaSADI |
| Public Policies | ✅ | |
| Incentives | ✅ | |
| Competitors | 🟡 | Revisado 07-08-2026 — **sin dato público confirmado**: adjudicatarios de AlmaGBA/AlmaSADI aún deben cerrar acuerdos tecnológicos con proveedores BESS (CATL, BYD, Fluence, Sungrow, Tesla). Scaffold con header agregado a la hoja; falta la asociación empresa-tecnología-proyecto. Volver a revisar cuando haya anuncios |
| BESS capacity (serie temporal) | ⬜ | **Prioridad alta — sigue pendiente** — no existe |
| Technical/grid requirements | ⬜ | No existe |
| Pricing | ⬜ | No existe (equivalente a CMg / precio spot) |
| BESS Projects (listado) | ✅ (07-08-2026) | Agregado: AlmaGBA (713 MW/12 proyectos — 3 con nombre propio confirmado: BESS San Fernando/Aluar 30MW, BESS Brown/Rowing 22MW, BESS Chingolo Sull/Sullair 24MW; resto 637 MW agregado sin desglose individual público) y AlmaSADI (700,5 MW/20 proyectos — Genneia 421MW/7 proy. incl. Bragado I-II 100MW, DQD Energy 149,5MW/8 proy., 360 Energy Solar 68MW/3 proy., Aluar 50MW, Intermepro 12MW). Desglose por proyecto individual incompleto para Central Puerto, Genneia (AlmaGBA), MSU Green Energy, YPF Luz, Coral Energía, Central Dock Sud, Eólica del Sur 3 — completar si aparece dato público |

## Colombia
| Sección | Estado | Nota |
|---|---|---|
| Overview | ✅ | |
| Generation Clients | 🟡 | 6/6 nombres, sin ninguna columna de capacidad rellenada (instalada ni BESS) |
| Commercial Clients | 🟡 | 0/12 clientes con dato numérico — sección tiene nombre y categoría, falta todo dato de MW/MWh/BESS |
| Government Institutions | ✅ | |
| Regulation Involved | ✅ | Muy completo, incluye Subasta LP 2026 |
| Public Policies | ✅ | *(corregido — antes fusionado con Incentives bajo "PUBLIC INCENTIVES")* |
| Incentives | ✅ | |
| Competitors | ⬜ | **Prioridad alta** — no existe |
| BESS capacity (serie temporal) | ⬜ | No existe |
| Technical/grid requirements | ⬜ | No existe |
| Pricing | ⬜ | No existe (equivalente a precio de escasez / OEF) |
| BESS Projects (listado) | ⬜ | **Prioridad alta** — no existe |
| Otros (fuera de estándar Chile) | — | Tiene "Servicios BESS" y tabla de Subasta LP que Chile no tiene — mantener, no forzar a eliminar |

## Perú
| Sección | Estado | Nota |
|---|---|---|
| Overview | ✅ | |
| Generation Clients | 🟡 | 9/9 clientes con MW instalado; BESS capacity presente en 3/9 (formato inconsistente: "1 MW / 2 MWh", "/" como valor); construcción presente solo en 1/9 |
| Commercial Clients | 🟡 | 0/17 clientes con dato numérico — sección tiene nombre y categoría, falta todo dato de MW/MWh/BESS |
| Government Institutions | 🟡 | Hay una entrada duplicada/confusa de COES (filas 39 y 40) — revisar antes de nivelar |
| Regulation Involved | ✅ | Muy completo, incluye Ley 32249 y PR20 |
| Public Policies | ⬜ | **Prioridad alta** — no existe |
| Incentives | ⬜ | **Prioridad alta** — no existe |
| Competitors | ⬜ | No existe |
| BESS capacity (serie temporal) | ⬜ | No existe |
| Technical/grid requirements | ⬜ | No existe |
| Pricing | ⬜ | No existe |
| BESS Projects (listado) | ✅ | Existe, con 4 registros |

## Uruguay (hoja nueva — scaffold agregado 07-08-2026)
| Sección | Estado | Nota |
|---|---|---|
| Overview | 🟡 | Texto de partida basado en instrucciones de Vigilancia Regulatoria LATAM — marcado como estimación, confirmar vigencia |
| Generation Clients | ⬜ | Solo headers, sin registros |
| Commercial Clients | ⬜ | Solo headers, sin registros |
| Government Institutions | 🟡 | MIEM/URSEA/UTE/ADME cargados con descripción genérica — profundizar |
| Regulation Involved | 🟡 | Solo el Decreto 2020, marcado como pendiente de confirmar vigencia/alcance |
| Public Policies | ⬜ | Solo headers |
| Competitors | ⬜ | Solo headers |
| BESS capacity (serie temporal) | ⬜ | Solo headers |
| Incentives | ⬜ | Solo headers |
| Technical/grid requirements | ⬜ | Solo headers |
| Pricing | ⬜ | Sin estructura definida — Uruguay no tiene mercado spot tipo CMg; falta decidir qué métrica usar (¿tarifa UTE?) |
| BESS Projects (listado) | ⬜ | Solo headers |

## Nota estructural pendiente — Argentina (07-08-2026)
La hoja Argentina tiene un orden de categorías distinto al estándar de Chile (Incentives aparece antes que Government Institutions, y no sigue Overview→Generation→Commercial→Government→Regulation→Public Policies→Competitors→BESS capacity→Incentives→Technical→Pricing→BESS Projects). Competitors y BESS Projects se agregaron al final de la hoja (no en la posición que tendrían si se siguiera el orden de Chile) para no reordenar sin autorización. **Pendiente decisión de Nicolás:** ¿normalizar el orden de Argentina para que coincida con Chile, o mantener el orden actual?

## Orden de prioridad sugerido para sesiones de nivelación

**Prioridad 0 — transversal, base del proyecto:** Completar MW/MWh/BESS de los clientes YA LISTADOS en Generation Clients y Commercial Clients, para los 5 países. Este es el trabajo original que Nicolás hizo a mano para Chile (el xlsx llegó como una lista de nombres sin datos) — replicarlo para Argentina, Colombia, Perú y Uruguay es el objetivo de fondo del proyecto, no una categoría más. Generation Clients primero (dato público más disponible); Commercial Clients según la nota metodológica de arriba (confirmar ausencia real de BESS antes de dejar vacío).

1. **Argentina — BESS capacity (serie temporal)** (Competitors y BESS Projects ya cerrados 07-08-2026; falta la serie temporal operacional/prueba/construcción, que es el gap de mayor prioridad restante fuera de la Prioridad 0)
2. **Colombia — Competitors, BESS Projects** (Subasta LP 2026 en curso, alta probabilidad de datos nuevos)
3. **Perú — Public Policies, Incentives** (revisar primero la duplicación de COES en Government Institutions)
4. **Uruguay — profundizar Overview y Regulation, y completar Generation/Commercial Clients desde cero** (mercado incipiente, prioridad baja salvo que surja algo nuevo)
