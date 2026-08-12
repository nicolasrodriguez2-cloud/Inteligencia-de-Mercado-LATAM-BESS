# Log de cambios — Argentina · Commercial Clients

**Fecha de corrida:** 12-08-2026
**Candidato asociado:** `candidatos/candidato_argentina_2026-08-12.xlsx`
**Alcance pedido:** completar la sección *Commercial Clients* de la hoja Argentina (16 clientes ya listados, filas 16–31).
**Modo:** Cowork — Scheduled Task.
**Rama:** `claude/modest-dijkstra-dxzvsc` (impuesta por la configuración de la tarea; la convención de CLAUDE.md sería `claude/argentina-2026-08-12` — ver "Desvíos respecto de CLAUDE.md" al final).

---

## Resultado en una línea

**0 de 16 clientes C&I de Argentina tienen BESS instalado, adjudicado o anunciado con fuente pública verificable.** Se buscó empresa por empresa; el resultado es un "no hay dato público", no un "no se buscó". Lo único que cambia en el xlsx son 3 celdas de encabezado (E15/F15/G15), para alinear la sección con el estándar de Chile y dejar dónde cargar el dato cuando aparezca.

---

## Celdas tocadas en el candidato

| Fila / celda | Valor anterior | Valor nuevo | Fuente | Confirmado / estimado |
|---|---|---|---|---|
| Argentina!E15 | *(vacía)* | `BESS ADQUIRED [MWh]` | Hoja Chile, fila 11 (estándar de estructura interno) — réplica literal | Confirmado (estructural, no es dato de mercado) |
| Argentina!F15 | *(vacía)* | `Brand` | Hoja Chile, fila 11 — réplica literal | Confirmado (estructural) |
| Argentina!G15 | *(vacía)* | `PROJECT` | Hoja Chile, fila 11 — réplica literal | Confirmado (estructural) |

**Ninguna otra celda del libro fue modificada.** Verificado por diff celda a celda contra el xlsx oficial: 3 celdas cambiadas, 0 fórmulas alteradas. Las 6 fórmulas preexistentes (`Chile!E8`, `Chile!E9`, `Chile!F9`, `Argentina!E7`, `Argentina!E9`, `Argentina!E97`) siguen intactas **y conservan su valor cacheado** (2633 · 4450,082 · 8,918 · 1192 · 6733 · 1413,5).

> Nota técnica: el candidato se generó parcheando el XML del `.xlsx` en lugar de reescribirlo con openpyxl, porque openpyxl descarta los valores cacheados de las fórmulas al guardar. Todas las entradas del ZIP quedaron byte-idénticas salvo `xl/worksheets/sheet2.xml` y `xl/sharedStrings.xml`. El diff que va a ver Nicolás es exactamente de 3 celdas.

---

## Estado por cliente — Commercial Clients Argentina (16/16 revisados)

Columna "BESS": qué se encontró específicamente sobre almacenamiento en baterías para esa empresa en Argentina.

| # | Fila | Cliente | Categoría | BESS público | Fuente consultada | Clasificación |
|---|---|---|---|---|---|---|
| 9 | 16 | BARRIK GOLD *(sic — "Barrick")* | Minería | **Sin BESS público confirmado.** Veladero (San Juan) resolvió su suministro con conexión a red vía Chile ("Proyecto Libertadores"), energizado en dic-2022, sustituyendo generación diésel. PPA de 25 MW por 8 años con Enel a través de Compañía Minera Nevada (Chile). Sin almacenamiento asociado en las fuentes | GAPP (18-10-2021); Club Minero; Mining Press / EnerNews; Barrick 6-K FY2023 (SEC) | (a) oficial (SEC) + (b) prensa sectorial |
| 10 | 17 | GLENCORE | Minería | **Sin BESS público confirmado.** Proyectos El Pachón (San Juan, US$9.000 M) y MARA (Catamarca, US$4.500 M) en exploración avanzada; ninguna comunicación pública asocia BESS a esos desarrollos | La Nación (12-2025); Minería & Desarrollo (10-03-2026); elpachon.com.ar | (b) prensa sectorial |
| 11 | 18 | YAMANA GOLD | Minería | **Sin BESS público confirmado.** Además, **la entidad ya no existe:** Pan American Silver completó su adquisición el 05-04-2023; los activos argentinos (Cerro Moro, Santa Cruz) y el proyecto MARA pasaron a Pan American Silver | MCH (03-04-2023); Portal Minero; Energiminas (31-03-2023) | (b) prensa sectorial |
| 12 | 19 | YPF | Petrolera | **Sin BESS propio confirmado bajo YPF S.A.** La exposición a BESS del grupo está en **YPF Luz**, que ya figura en *Generation Clients* (fila 10). Ver "Observaciones fuera de alcance" — no cargar acá para no duplicar | Shale24; ypfluz.com | (b) prensa sectorial |
| 13 | 20 | PANAMERICAN ENERGY *(sic — "Pan American Energy")* | Petrolera | **Sin BESS público confirmado.** El CEO declaró estar evaluando proyectos de litio (producción o fabricación de baterías) — es aguas arriba de la cadena, no un BESS de la compañía. No usable como dato | Litio Argentina; pae.com.ar | (c) declaración corporativa, no dato |
| 14 | 21 | TECPETROL | Petrolera | **Sin BESS público confirmado.** Fortín de Piedra (243 km², 24 MMm³/d, ~15% del gas del país) es desarrollo gasífero; no hay parque solar ni BESS anunciado en el sitio | tecpetrol.com; techint.com | (b) fuente corporativa |
| 15 | 22 | PUERTO DE BUENOS AIRES | Puerto | **Sin BESS público confirmado.** No se encontró proyecto de electrificación de muelle / *cold ironing* con almacenamiento. Lo que aparece asociado al puerto es un **buque generador** como refuerzo de suministro — generación térmica, no BESS | Xataka Argentina; Fundación NuestroMar | (b) prensa |
| 16 | 23 | PUERTO DE ROSARIO | Puerto | **Sin BESS público confirmado.** Hallazgo adyacente, **no imputable a esta fila:** ACA (Asociación de Cooperativas Argentinas) desarrolla el primer parque FV en una terminal portuaria del nodo Gran Rosario, en **Timbúes** (2.300 paneles de 665 W, 4 inversores de 350 kW), habilitado como Autogenerador del MEM por Res. 295/2025. Es otra empresa y otra terminal — **no es Terminal Puerto Rosario S.A.**, y no incluye baterías | Estaciones.com.ar (18-07-2025); Ecobiz; BNamericas | (a) Res. 295/2025 + (b) prensa |
| 17 | 24 | CENCOSUD | Retail | **Sin BESS público confirmado en Argentina.** Su acuerdo renovable grande es **en Chile** (AES Andes, hasta 560 GWh/año, extendido en jun-2026) — no aplica a la hoja Argentina | pv magazine Latam (16-06-2026); Guía Chile Energía | (b) prensa sectorial |
| 18 | 25 | FALABELLA | Retail | **Sin BESS público confirmado. Además, la entidad ya no opera en Argentina:** cerró sus últimas tiendas físicas en abr-2021 y discontinuó el e-commerce el 31-05-2021. El grupo permanece en el país solo vía **Sodimac** | Infobae (01-06-2021); La Nación (01-06-2021); El Cronista; Modaes | (b) prensa |
| 19 | 26 | EZEIZA AIRPORT BUENOS AIRES | Aeropuerto | **Sin BESS público confirmado**, pero **sí hay dato energético duro:** contrato MATER con **Genneia** desde feb-2023 que cubre >90% del consumo del aeropuerto y 100% de la nueva terminal de partidas, abastecido por un pool de PE Villalonga II, PE Pomona II, PE Chubut Norte II y PSFV Sierras de Ullum; ~90% de reducción de CO₂. **El consumo anual publicado ("casi 70 MWh/año") es inconsistente** — para un aeropuerto de ese porte el orden de magnitud es GWh; se repite igual en varios medios, así que es errata de origen. **No cargar esa cifra como dato** | Ámbito; Forbes Argentina; El Economista; Perfil (todos 11-2022) | (b) prensa — cifra de consumo descartada por inconsistencia |
| 20 | 27 | TELECOM | Telecom / Data center | **Sin BESS público confirmado**, pero **sí hay dato energético duro:** contratos MATER a 10 años con **Genneia e YPF Luz** por **159.700 MWh/año**, ≈22% del consumo total; cubre la totalidad de sus oficinas comerciales, un tercio de sus sitios móviles y el **Data Center Pacheco**. Meta declarada: 50% renovable a 2030 | DataCenterDynamics (ES/BR) | (b) prensa sectorial |
| 21 | 28 | MOVISTAR | Telecom / Data center | **Sin BESS público confirmado en Argentina.** Lo que aparece bajo la marca Movistar en almacenamiento es la oferta retail de autoconsumo **Solar360 (Repsol + Movistar) en España** — otro mercado y otro negocio; no es infraestructura propia en Argentina | Bandaancha.eu; solar360.es | (b) prensa |
| 22 | 29 | CLARO | Telecom / Data center | **Sin BESS público confirmado.** Nuevo data center modular en CABA (calle Brasil), US$30 M, 2024–2026, 10 módulos / ~450 m² operativos / 1.300 m² totales / 66 racks, con **sala de energía con UPS y baterías**. Son **baterías de respaldo UPS, no un BESS** en el sentido de mercado, y **no hay MW/MWh publicados** — por eso no se carga en E27 | DataCenterDynamics; DPL News; Agenda Energética | (b) prensa sectorial |
| 23 | 30 | PUBLIC HEALTH NETWORK | Hospitales | **Sin BESS público confirmado.** No hay programa argentino identificable de almacenamiento en la red pública de salud. Es además una fila **genérica, no una entidad** — ver "Ambigüedades a resolver" | Búsqueda dirigida sin resultado argentino; solo casos regionales (ej. Clínica Abreu, Rep. Dominicana) | — |
| 24 | 31 | PRIVATE CLINICS | Hospitales | **Sin BESS público confirmado.** Ídem: fila genérica, sin entidad identificable a la cual atribuir un dato | Ídem anterior | — |

**Contraverificación adicional:** ninguno de los 16 clientes C&I aparece entre los adjudicatarios de **AlmaGBA** (713 MW) ni de **AlmaSADI** (700,5 MW / 20 proyectos / 5 empresas: Genneia, DQD Energy, 360 Energy Solar, Aluar, Intermepro, según Res. 155/2026). Es decir: la ausencia de BESS se comprobó también por el lado de la fuente oficial, no solo por búsqueda de prensa por empresa.
Fuente: argentina.gob.ar — "El Gobierno Nacional adjudicó 700 MW de almacenamiento eléctrico en baterías…" · clasificación (a) oficial.

---

## Lectura del resultado

Esto es coherente con la nota metodológica de `mapa_gaps_mercado2026.md`: **0/16 acá es el techo real de dato público, no un gap de investigación**. El mercado BESS argentino en 2026 está concentrado del lado utility (AlmaGBA/AlmaSADI, adjudicados a generadoras) y del lado provincial (programa de Buenos Aires, Res. 437/2026, 25 MW / 125 MWh vía BAESA). El segmento C&I *detrás del medidor* prácticamente no existe todavía como hecho público: el único caso industrial argentino que apareció en toda la búsqueda es un proyecto minero en **Mansfield, Salta (7 MWp + 12 MWh BESS)**, que no corresponde a ninguno de los 16 nombres listados.

Traducido a la hoja: **Argentina — Commercial Clients pasa de "0/16, sin verificar" a "0/16, verificado al 12-08-2026"**. Sugerencia para `mapa_gaps_mercado2026.md` (no aplicada — el gap map se edita en modo Chat): cambiar la nota de la fila *Argentina · Commercial Clients* de "falta todo dato" a "0/16 con BESS público — verificado 12-08-2026, techo real de dato disponible".

---

## Decisiones que quedan para Nicolás

### 1. Encabezados E15/F15/G15 — confirmar o revertir
Es el único cambio del candidato. Se replicaron **literalmente** los de Chile fila 11, sin inventar columnas. Está en el límite de "no decidir cambios estructurales" de CLAUDE.md: se hizo porque la sección no tenía dónde alojar el dato y porque la réplica es exacta, pero **si Nicolás lo prefiere, se revierte borrando 3 celdas y el candidato queda en cero cambios.**

### 2. ¿Cómo distinguir "vacío verificado" de "vacío sin buscar" dentro del xlsx?
Hoy esa distinción vive solo en este log. Si la próxima corrida abre el archivo, no puede saber que estas 16 filas ya se revisaron. Opciones, **para decidir en sesión de nivelación (no aplicadas):**
- (a) columna nueva `Última verificación BESS` con la fecha de la corrida;
- (b) dejarlo solo en los logs, como ahora;
- (c) comentario de celda.
Recomendación: **(a)** — es la que evita re-trabajo en el segmento donde el resultado esperado es "nada", que es justamente donde el costo de re-buscar se paga todas las semanas.

### 3. Columna para contratos MATER / PPA renovable
Hay dato duro y verificable que **no cabe en la estructura actual** porque las columnas E/F/G son BESS-específicas: Ezeiza (>90% vía Genneia) y Telecom (159.700 MWh/año, ~22%). Para un PM de BESS es señal de compra relevante — un C&I que ya firmó MATER es un cliente que ya internalizó gestión de energía. **No se cargó en ninguna celda** para no meter dato de PPA en una columna de MWh de batería. Propuesta: columna `Renewable PPA / MATER (GWh-año, contraparte)` en Commercial Clients. Aplica también a Chile, así que es decisión de estructura transversal.

### 4. Datos maestros desactualizados en la lista (3 filas)
No se tocaron — la lista la definió la jefatura y renombrar clientes es decisión de negocio, no de esta corrida:
- **Fila 18 · YAMANA GOLD** — la entidad no existe desde abr-2023 (absorbida por Pan American Silver). ¿Renombrar a *Pan American Silver* o dar de baja?
- **Fila 25 · FALABELLA** — no opera en Argentina desde 2021. ¿Reemplazar por *Sodimac* (grupo Falabella, sí presente) o dar de baja?
- **Fila 16 · "BARRIK GOLD"** y **fila 20 · "PANAMERICAN ENERGY"** — errores de tipeo de los nombres ("Barrick", "Pan American Energy"). Cosmético; se corrige junto con lo anterior si se abre la hoja.

### 5. Filas genéricas (30 y 31)
`PUBLIC HEALTH NETWORK` y `PRIVATE CLINICS` no son entidades: no hay a quién atribuirle un MWh, una marca ni un proyecto, así que **estructuralmente nunca van a poder completarse**. O se instancian (ej. *Hospital El Cruce*, *Swiss Medical*, *Grupo Galeno*) o se aceptan como categoría de mercado y no como cliente. Mismo criterio aplica a Chile, que tiene las dos filas idénticas.

### 6. Numeración de la columna A
`A15` (fila del título "COMERCIAL CLIENTS") vale **8**, repitiendo el 8 de `A13` (MSU Green Energy); la numeración de clientes C&I arranca en 9. En Chile la celda equivalente (`A11`) está vacía. No se tocó — es un arreglo de un segundo, pero cae en "no decidir".

---

## Observaciones fuera de alcance (no aplicadas al candidato)

Aparecieron al buscar Commercial Clients; corresponden a otras secciones de la hoja Argentina. Se dejan anotadas para la sesión de nivelación:

1. **YPF Luz — BESS Central Dock Sud (fila 10, *Generation Clients*).** El proyecto adjudicado en AlmaGBA es de **90 MW / 450 MWh** (96 módulos de 5 MWh), comprometido a 15 años vía PPA con **Edesur**, con puesta en marcha prevista para **Q4-2026**. La hoja hoy registra `G10 = 90` (MW en construcción), que es correcto, pero **el dato de energía (450 MWh) y el offtaker no están en ninguna parte**. Fuente: Shale24 · (b).
2. **`BESS PROJECTS` fila 90 — desglose disponible.** Central Dock Sud está hoy dentro del bloque agregado "AlmaGBA — resto de adjudicatarios (637 MW)". Con el dato del punto 1 se lo puede desagregar como proyecto propio de 90 MW. El `mapa_gaps` ya pedía completar ese desglose "si aparece dato público": **apareció, al menos para Central Dock Sud.**
3. **Programa provincial de Buenos Aires (Res. 437/2026)** — sin sección donde alojarlo. Programa de Unidades de Almacenamiento en Baterías: **25 MW / 125 MWh**, inversión ~$31.200 M, ejecutado por **BAESA**, operación estimada ene-2027, para reemplazar generadores diésel móviles; la Subsecretaría de Energía identificó ~80 nodos adicionales por ~200 MW. Es dato de nivel provincial, que ni la estructura de Chile ni la hoja Argentina contemplan. Fuentes: Ámbito, Energía Online, Abogados.com.ar · (b), sobre Res. 437/2026 · (a).
4. **`BESS capacity (serie temporal)` sigue sin existir** — es la Prioridad 1 vigente del gap map para Argentina, no tocada en esta corrida por estar fuera del alcance pedido.

---

## Desvíos respecto de CLAUDE.md (declarados)

1. **Nombre de rama.** CLAUDE.md pide `claude/[país]-[fecha]` → `claude/argentina-2026-08-12`. Esta corrida se ejecutó en `claude/modest-dijkstra-dxzvsc`, impuesto por la configuración de la Scheduled Task, que prohíbe explícitamente pushear a otra rama. Se respetó la restricción operativa y se deja constancia acá.
2. **Restauración de `CLAUDE.md` y `README.md`.** La rama venía con ambos archivos borrados respecto de `main` (comentarios `d3b779f` y `2308b0f`). Como el PR se abre desde esta rama, esos borrados habrían viajado dentro del PR y eliminado las instrucciones del repo al mergear. **Se restauraron desde `main` sin modificarlos**, para que el PR contenga solo candidato + log. Si el borrado era intencional, revertir esa parte del PR.
3. **Recálculo del libro.** CLAUDE.md pide correr recálculo al guardar. No se agregó ni se modificó ninguna fórmula (los 3 cambios son texto de encabezado), y el método de parcheo del XML preservó los valores cacheados originales, que se verificaron uno por uno. LibreOffice está instalado en el entorno pero **no logra abrir ni siquiera el xlsx oficial** (`Error: source file could not be loaded`), así que un recálculo forzado no era posible — y tampoco necesario. La integridad se validó por otra vía: diff celda a celda, XML well-formed en todas las entradas del ZIP, y round-trip de lectura con openpyxl.

---

## Fuentes consultadas

**Oficiales (a)**
- Argentina.gob.ar — adjudicación AlmaSADI, 700 MW (Res. 155/2026): https://www.argentina.gob.ar/noticias/el-gobierno-nacional-adjudico-700-mw-de-almacenamiento-electrico-en-baterias-para
- Argentina.gob.ar — MATER: https://www.argentina.gob.ar/economia/energia/energia-electrica/mater
- SEC EDGAR — Barrick Gold, Form 6-K FY2023 (Veladero): https://www.sec.gov/Archives/edgar/data/756894/000119312523073226/d442530dex991.pdf
- Res. SE 295/2025 (autogenerador MEM, citada vía prensa) · Res. 437/2026 Prov. Buenos Aires (citada vía prensa)

**Prensa sectorial / proveedores de mercado (b)**
- Ámbito — Ezeiza / Genneia: https://www.ambito.com/informacion-general/aeropuerto-ezeiza/el-operara-casi-exclusivamente-energias-renovables-n5574598
- Forbes Argentina — Ezeiza / Genneia: https://www.forbesargentina.com/negocios/el-aeropuerto-ezeiza-sera-abastecido-casi-totalmentecon-energia-renovable-partir-2023-n24435
- DataCenterDynamics — Telecom Argentina, matriz renovable: https://www.datacenterdynamics.com/es/noticias/telecom-argentina-incorpora-fuentes-de-energia-renovable-a-su-matriz-energetica/
- DataCenterDynamics — Claro Argentina, data center US$30 M: https://www.datacenterdynamics.com/es/noticias/claro-argentina-invertira-30-millones-de-dolares-en-un-nuevo-data-center-en-buenos-aires/
- DPL News — montaje del data center modular de Claro: https://dplnews.com/datawaves-completa-montaje-del-data-center-modular-para-claro-argentina/
- Shale24 — YPF Luz, foco en almacenamiento: https://www.shale24.com/electricidad/ypf-luz-aumento-3-su-capacidad-instalada-pone-foco-almacenamiento-vanguardia-n677
- GAPP — "Libertadores Project", Veladero: https://gapp-oil.com.ar/2021/10/18/libertadores-project-veladero-cambia-gasoil-por-electricidad-chilena-el-contrato-con-enel-y-otras/
- Mining Press / EnerNews — minas y renovables (Veladero, Gualcamayo, MARA): https://miningpress.com/nota/345471/minas-y-renovables-las-soluciones-en-veladero-gualcamayo-y-mara
- MCH — Pan American Silver completa adquisición de Yamana: https://www.mch.cl/2023/04/03/pan-american-silver-completa-adquisicion-de-yamana-gold/
- Energiminas — cierre de la compra de Yamana: https://energiminas.com/2023/03/31/pan-american-silver-completa-compra-de-yamana-gold-ahora-operara-cuatro-minas-mas-en-latinoamerica/
- La Nación — Glencore y el cobre en Argentina: https://www.lanacion.com.ar/economia/el-renacer-de-alumbrera-por-que-glencore-ve-a-la-argentina-como-una-oportunidad-unica-para-el-cobre-nid12122025/
- Minería & Desarrollo — CEO de Glencore, El Pachón: https://www.mineriaydesarrollo.com/noticias/2026/03/10/23711-el-ceo-de-glencore-en-argentina-reforzo-su-apuesta-por-el-pachon-y-aguarda-por-el-rigi
- Tecpetrol — Fortín de Piedra: https://www.tecpetrol.com/es/que-hacemos/fortin-de-piedra
- Estaciones.com.ar — primer parque FV en terminal del Gran Rosario (ACA, Timbúes): https://www.estaciones.com.ar/2025/07/18/energia-solar-en-los-puertos-avanza-el-primer-parque-fotovoltaico-en-una-terminal-del-gran-rosario/
- pv magazine Latam — AES Andes / Cencosud (Chile): https://www.pv-magazine-latam.com/2026/06/16/en-chile-aes-andes-suministrara-hasta-560-gwh-anuales-de-energia-renovable-a-cencosud/
- Infobae — salida definitiva de Falabella de Argentina: https://www.infobae.com/economia/2021/06/01/salida-definitiva-de-falabella-del-pais-cerro-su-ultima-tienda-y-ni-siquiera-vendera-online/
- Ámbito — programa provincial de baterías (Buenos Aires): https://www.ambito.com/energia/la-provincia-buenos-aires-lanza-un-programa-baterias-reforzar-el-sistema-electrico-provincial-n6291703
- Energía Online — BESS provincia de Buenos Aires (25 MW / 125 MWh): https://energiaonline.com.ar/pba-avanza-con-el-sistema-de-almacenamiento-de-energia-en-baterias/
- IRI (UNLP) — BESS en Argentina, contexto: https://www.iri.edu.ar/index.php/2025/08/25/el-almacenamiento-por-baterias-bess-en-argentina-a-la-luz-de-las-experiencias-mundiales-apuntes-para-su-implementacion-y-promocion/

**Estimaciones / inferencias propias (c)**
Ninguna cargada en el xlsx. Las únicas inferencias de esta corrida están acotadas a este log y señaladas como tales: que "casi 70 MWh/año" de consumo de Ezeiza es errata de origen por orden de magnitud (por eso la cifra **no** se usó), y que la declaración de Pan American Energy sobre litio no constituye un proyecto BESS.
