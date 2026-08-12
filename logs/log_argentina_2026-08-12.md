# Log — Argentina · Commercial Clients (C&I) · 12-08-2026

**Candidato asociado:** `candidatos/candidato_argentina_2026-08-12.xlsx`
**Alcance de la corrida:** completar la sección *COMERCIAL CLIENTS* de la hoja Argentina (16 clientes ya listados, filas 16–31). No se tocó ninguna otra sección ni ninguna otra hoja.
**Estado de partida (según `mapa_gaps_mercado2026.md`, auditoría 11-08-2026):** 0/16 clientes con dato numérico — solo nombre y categoría.
**Resultado:** 1/16 con dato numérico de BESS con fuente pública verificable. 15/16 quedan vacíos, con la búsqueda documentada abajo (ver "sin BESS público confirmado").

---

## 1. Celdas modificadas

| Fila / celda | Valor anterior | Valor nuevo | Fuente | Confirmado / estimado |
|---|---|---|---|---|
| Argentina!E15 (encabezado sección) | *(vacío)* | `BESS ADQUIRED [MWh]` | Réplica literal del encabezado de Chile!E11 | Estructural — ver nota 4.1 |
| Argentina!F15 (encabezado sección) | *(vacío)* | `Brand` | Réplica literal del encabezado de Chile!F11 | Estructural — ver nota 4.1 |
| Argentina!G15 (encabezado sección) | *(vacío)* | `PROJECT` | Réplica literal del encabezado de Chile!G11 | Estructural — ver nota 4.1 |
| Argentina!E16 — BARRIK GOLD | *(vacío)* | `32` | San Juan 8, 17-04-2026 · Editorial RN, abr-2026. Cita textual en ambos: "un sistema de baterías (BESS) de 32 MWh" | **Confirmado** (prensa local sanjuanina, 2 medios independientes, misma cita textual). Ver nota 4.2 sobre titularidad |
| Argentina!G16 — BARRIK GOLD | *(vacío)* | `PARQUE SOLAR COMUNITARIO IGLESIA (San Juan) — 8,5 MWp + BESS 32 MWh. Titular y operador: EPSE (Energía Provincial Sociedad del Estado); financiado por Veladero / Minera Andina del Sol (JV Barrick–Shandong Gold) vía Fideicomiso Fase 6. En construcción (abr-2026).` | Ídem anterior | **Confirmado** |
| Argentina!F16 — BARRIK GOLD (Brand) | *(vacío)* | *(se deja vacío)* | — | **Gap explícito** — el proveedor/marca de las baterías no está publicado en ninguna de las fuentes consultadas |

**Nada más se modificó.** No se agregaron filas, no se reordenaron categorías, no se tocó ninguna fórmula.

### Detalle del único dato cargado — BARRIK GOLD

- **Proyecto:** Parque Solar Comunitario de Iglesia, departamento de Iglesia, provincia de San Juan.
- **Capacidad:** central fotovoltaica de **8,5 MWp** + **sistema de baterías (BESS) de 32 MWh**, que permite inyectar energía a la red las 24 horas.
- **Inversión:** USD 10 millones. **Plazo de obra:** 12 meses (arrancó ~abr-2026). **Vida útil proyectada:** 30 años.
- **Estructura:** diseño y operación a cargo de **EPSE** (empresa provincial, fuente tipo (a) oficial en origen, aunque la difusión consultada es de prensa); financiamiento vía **Fideicomiso Fase 6** de la mina Veladero, operada por **Minera Andina del Sol** (JV Barrick Gold – Shandong Gold). Encuadrado en el régimen de **Generación Distribuida Comunitaria**.
- **Objetivo declarado:** cubrir el 100 % de la demanda eléctrica residencial y comercial del departamento de Iglesia.
- ⚠️ **Cuidado con una cifra homónima:** una nota de 0264Noticias (01-04-2026) menciona *"un sector de 32 hectáreas dentro del Parque Industrial"*. Son 32 hectáreas de terreno, **no** los 32 MWh de BESS — coincidencia numérica, no la misma magnitud. Ambas cifras se verificaron por separado.

---

## 2. Clientes sin BESS público confirmado (15/16)

Estos 15 clientes **se buscaron específicamente** por BESS/almacenamiento en baterías y **no** se encontró fuente pública verificable. Las celdas quedan vacías de forma deliberada, no por falta de búsqueda. Se anota el contexto energético relevante encontrado (que en general es **PPA renovable vía MATER, sin almacenamiento**), útil como señal comercial aunque no vaya al xlsx.

| # | Fila | Cliente | Categoría | Qué se buscó y qué se encontró | Estado |
|---|---|---|---|---|---|
| 1 | 17 | GLENCORE | Minería | BESS en El Pachón (San Juan) y MARA (Catamarca); reactivación de Alumbrera. El Pachón sigue en factibilidad: las "opciones de suministro eléctrico" están en estudio, construcción recién en 2029 y primera producción en 2034. Alumbrera se reactiva hacia fines de 2026, producción 2028. Ninguna definición pública de tecnología de almacenamiento | Sin BESS público confirmado |
| 2 | 18 | YAMANA GOLD | Minería | No hay BESS. **Además: la empresa ya no existe** — Pan American Silver completó la adquisición de Yamana Gold el 31-03-2023; los activos argentinos (Cerro Moro y el proyecto MARA) pasaron a Pan American Silver. Ver nota 4.3 | Sin BESS público confirmado + entidad desactualizada |
| 3 | 19 | YPF | Petrolera | BESS propio en refinerías, yacimientos o estaciones de servicio. Lo que hay es abastecimiento renovable de su red de estaciones de servicio vía PPA, y I+D en baterías de litio — sin BESS instalado ni anunciado de la petrolera. Los proyectos BESS del grupo son de **YPF Luz**, que ya está en Generation Clients (fila 10, 90 MW en construcción) — no duplicar acá | Sin BESS público confirmado |
| 4 | 20 | PANAMERICAN ENERGY | Petrolera | BESS en Cerro Dragón. Hay parques eólicos Norte III y IV (140 MW, con Genneia) y un nuevo eólico de 150 MW en diseño para H2/amoníaco — ninguno con almacenamiento anunciado. ⚠️ Las "baterías" que aparecen en fuentes de Cerro Dragón son **baterías de producción de petróleo**, no BESS. PAE no figura entre los adjudicatarios de AlmaGBA ni AlmaSADI | Sin BESS público confirmado |
| 5 | 21 | TECPETROL | Petrolera | BESS en Fortín de Piedra u otros activos. El grupo Techint tiene el Parque Eólico de la Buena Ventura (hasta 105 MW, Gonzales Chaves) y el eólico para TenarisSiderca en Campana; Tecpetrol además vendió un parque eólico. Ningún almacenamiento asociado | Sin BESS público confirmado |
| 6 | 22 | PUERTO DE BUENOS AIRES | Puerto | BESS, *cold ironing* / electrificación de muelle en el puerto y en Terminales Río de la Plata. Nada publicado. ⚠️ Cambio institucional: el puerto figura hoy bajo la **Agencia Nacional de Puertos y Navegación** — confirmar antes de nivelar si corresponde actualizar el nombre del titular | Sin BESS público confirmado |
| 7 | 23 | PUERTO DE ROSARIO | Puerto | BESS en ENAPRO / terminales del Gran Rosario. Solo se encontró un parque fotovoltaico de 2.300 paneles de la Asociación de Cooperativas Argentinas en la zona portuaria (operativo desde mediados de 2025), sin almacenamiento y sin ser del ente portuario | Sin BESS público confirmado |
| 8 | 24 | CENCOSUD | Retail | BESS en operaciones argentinas. El único acuerdo energético grande y verificable de Cencosud es en **Chile** (AES Andes, extendido hasta marzo 2037, +200 locales) — no aplica a la hoja Argentina. Sin contrato MATER ni BESS argentino publicado | Sin BESS público confirmado |
| 9 | 25 | FALABELLA | Retail | BESS en Argentina. **La cadena Falabella cerró sus últimas tiendas argentinas en junio de 2021** y se retiró del país; el grupo conservó solo Sodimac (6 locales, AMBA y Córdoba), con la condición de que se autosustente. Ver nota 4.3 | Sin BESS público confirmado + entidad desactualizada |
| 10 | 26 | EZEIZA AIRPORT BUENOS AIRES | Aeropuerto | BESS en Ezeiza. Aeropuertos Argentina alcanzó **100 % de su consumo eléctrico con energía renovable** en Ezeiza y en Aeropuertos Argentina Cargas, abastecido por Genneia (PE Villalonga II, PE Pomona II, PE Chubut Norte II y PSFV Sierras de Ullum), con ISO 50001. Es un PPA renovable **sin almacenamiento** — buen perfil de cliente C&I, pero no hay BESS | Sin BESS público confirmado |
| 11 | 27 | TELECOM | Telco / Data Center | BESS en data centers y sitios móviles. Telecom tiene PPAs a 10 años con **Genneia** e **YPF Luz** por 159.700 MWh/año (≈22 % de su consumo) y meta de 50 % renovable a 2030; reporta **22 sitios híbridos con 140 MWh/año de producción** renovable. Ese "140 MWh/año" es **energía generada al año, no capacidad de almacenamiento** — no se cargó como BESS. UPS de respaldo en data centers ≠ BESS | Sin BESS público confirmado |
| 12 | 28 | MOVISTAR | Telco / Data Center | BESS en Argentina. **Además: Telefónica vendió su filial argentina (Movistar) a Telecom Argentina** (anuncio 24-02-2025, USD 1.245 M); tras un ida y vuelta regulatorio, la operación fue aprobada con condiciones en junio de 2026 (desinversión de 6 M de líneas móviles). Movistar y Telecom pasan a ser el mismo grupo. Ver nota 4.3 | Sin BESS público confirmado + entidad desactualizada |
| 13 | 29 | CLARO | Telco / Data Center | BESS en el data center Tier III de Claro Argentina. Solo se documenta **sala de energía con UPS y baterías de respaldo** (10 módulos, 450 m², 66 racks) — respaldo de continuidad, no un BESS de arbitraje/servicios de red. No se contabiliza como BESS | Sin BESS público confirmado |
| 14 | 30 | PUBLIC HEALTH NETWORK | Hospitales | BESS en la red hospitalaria pública. No hay ningún programa de almacenamiento hospitalario publicado. Lo más cercano es el programa BESS de la **Provincia de Buenos Aires** (25 MW / 125 MWh en Mar del Tuyú, Carmen de Areco, Arrecifes y Capitán Sarmiento; ~$31.200 M; obra 2º semestre 2026, operación ene-2027), pero es **refuerzo de nodos de red provinciales, no de hospitales** — no corresponde a esta fila. Ver nota 4.4 | Sin BESS público confirmado |
| 15 | 31 | PRIVATE CLINICS | Hospitales | BESS en clínicas privadas argentinas (Swiss Medical, Hospital Italiano y equivalentes). Nada publicado. Categoría genérica, sin razón social concreta que permita rastrear un proyecto | Sin BESS público confirmado |

**Lectura del resultado:** 15/16 vacíos es, en esta corrida, el **techo real de dato público**, no un gap de investigación — coincide con lo que anticipa la nota metodológica de `mapa_gaps_mercado2026.md` (línea 29) y con Chile, donde el mismo ejercicio manual dio 2/28. El patrón argentino es claro: los grandes C&I están resolviendo su descarbonización con **PPAs renovables vía MATER** (obligación del 20 % de la Ley 27.191), no con almacenamiento propio. El BESS argentino hoy está casi íntegramente del lado de la generación y la red (AlmaGBA 713 MW + AlmaSADI 700,5 MW), no detrás del medidor.

---

## 3. Verificación técnica del archivo

- Cargado con `openpyxl`, `data_only=False`.
- **Fórmulas preexistentes:** 6 antes / 6 después, idénticas una por una (Argentina `E7`, `E9`, `E97`; Chile `E8`, `E9`, `F9`). Ninguna sobrescrita ni convertida a valor.
- **Recálculo corrido** (LibreOffice Calc headless, solo como pasada de verificación — el archivo entregado es el guardado con openpyxl, que conserva `fullCalcOnLoad=True`): Argentina `E7`=1192, `E9`=6733, `E97`=1413,5 (=713 + 700,5 ✓); Chile `E8`=2633, `E9`=4450,082, `F9`=8,918. Todos correctos.
- No se agregaron fórmulas nuevas: la sección Commercial Clients no tiene totales.
- Formato y unidades: se copió el estilo de celda existente (encabezados desde `E5`, datos desde `E6`); valor numérico en MWh, mismo criterio que Chile.

---

## 4. Notas para Nicolás — decisiones que NO tomé

### 4.1 Encabezados agregados en la fila 15
La sección *COMERCIAL CLIENTS* de Argentina no tenía encabezados en E/F/G: sin ellos no hay dónde poner el dato. Se replicaron **textualmente** los de Chile (`Chile!E11:G11`): `BESS ADQUIRED [MWh]` · `Brand` · `PROJECT`. Es la única modificación con carácter estructural de la corrida, y es de alineación al estándar de Chile, no una columna nueva. **Si preferís otro texto o no querés encabezados ahí, se revierte sin afectar ningún dato.**

### 4.2 Titularidad del BESS de BARRIK GOLD
El BESS de 32 MWh del Parque Solar Comunitario de Iglesia **no es propiedad de Barrick**: es de EPSE, empresa provincial, que además lo opera. Barrick (vía Veladero / Minera Andina del Sol) lo **financia** con el Fideicomiso Fase 6. La columna se llama "BESS ADQUIRED" — decidí cargar el dato con la aclaración completa en la celda `PROJECT` en vez de dejarlo afuera, porque es información comercialmente relevante (una minera argentina financiando 32 MWh de almacenamiento), pero **es tu decisión** si corresponde en esta fila o si debería ir a *BESS Projects* con titular EPSE. No lo moví por mi cuenta.

### 4.3 Tres entidades de la lista están desactualizadas
No las toqué — la lista de nombres vino de la jefatura y renombrar/eliminar filas es cambio estructural. Quedan anotadas para que decidas:
- **YAMANA GOLD** (fila 18): dejó de existir el 31-03-2023. Sus activos argentinos son hoy de **Pan American Silver** (Cerro Moro + proyecto MARA). ¿Renombrar la fila, o mantener el nombre histórico?
- **FALABELLA** (fila 25): salió de Argentina en junio de 2021. El grupo solo opera **Sodimac** (6 locales). ¿Reemplazar por Sodimac, o dar la fila de baja?
- **MOVISTAR** (fila 28): adquirida por **Telecom Argentina** (aprobada con condiciones en junio de 2026). Las filas 27 (TELECOM) y 28 (MOVISTAR) pasan a ser el mismo grupo. ¿Fusionar, o mantenerlas separadas mientras dure la desinversión de 6 M de líneas?

### 4.4 Oportunidad detectada fuera del alcance de esta corrida
El programa BESS de la **Provincia de Buenos Aires** (25 MW / 125 MWh, 4 nodos, obra 2º semestre 2026, operación ene-2027, ~$31.200 M) **no está en la hoja Argentina** — ni en *BESS Projects* ni en la serie temporal (que sigue sin existir, y es la prioridad 1 del gap map). Es un tercer canal de demanda además de AlmaGBA/AlmaSADI: licitación provincial, no nacional. Lo dejo señalado; no lo cargué porque excede el alcance de esta tarea (Commercial Clients).

### 4.5 Rama de trabajo
`CLAUDE.md` pide la convención `claude/[país]-[fecha]` (sería `claude/argentina-2026-08-12`). Esta corrida fue lanzada con una rama ya asignada por el entorno: **`claude/modest-dijkstra-0d13us`**, y las instrucciones del entorno prohíben pushear a otra rama sin permiso explícito. Trabajé sobre la rama asignada. Si querés, en la próxima corrida se renombra.

---

## 5. Fuentes consultadas

**Dato cargado (BARRIK GOLD / Parque Solar Comunitario Iglesia):**
- San Juan 8 — "Veladero acompaña la construcción del Parque Solar Comunitario de Iglesia", 17-04-2026 — https://www.sanjuan8.com/veladero-acompana-la-construccion-del-parque-solar-comunitario-iglesia-n1549564
- Editorial RN — "Veladero acompaña la construcción del Parque Solar Comunitario de Iglesia…", abr-2026 — https://editorialrn.com.ar/veladero-acompana-la-construccion-del-parque-solar-comunitario-de-iglesia-una-obra-clave-de-energia-limpia-y-ahorro-electrico/
- Eco del Viento — "Iglesia se convertirá en el primer departamento abastecido al 100 % con energía solar", 21-04-2026 — https://www.ecodelviento.com.ar/energia/2026/04/21/iglesia-se-convertira-en-el-primer-departamento-abastecido-al-100-con-energia-solar/ *(confirma 8,5 MWp; no menciona los MWh)*
- 0264Noticias — costo USD 10 M y 32 hectáreas en el Parque Industrial, 01-04-2026 — https://www.0264noticias.com.ar/noticias/2026/04/01/89682-el-parque-solar-comunitario-tendra-un-costo-de-unos-usd-10-millones-y-apunta-a-que-casi-la-mitad-de-los-iglesianos-no-paguen-la-luz

**Verificación de ausencia de BESS y contexto por cliente:**
- Pan American Silver — cierre de la adquisición de Yamana Gold, 31-03-2023 — https://panamericansilver.com/news/pan-american-silver-completes-acquisition-of-yamana-gold/
- Diario Río Negro — El Pachón, cierre de campaña 2025-2026 (Glencore) — https://www.rionegro.com.ar/energia/el-pachon-avanza-en-san-juan-glencore-cerro-su-campana-2025-2026-destacando-las-inversiones-en-infraestructura-y-el-empleo-generado-4642153/
- Mejor Energía — "Glencore reactivará Alumbrera en 2026…", 03-12-2025 — https://www.mejorenergia.com.ar/noticias/2025/12/03/4886-glencore-reactivara-alumbrera-en-2026-y-preve-retomar-la-produccion-para-2028
- Energía Estratégica — nuevo parque eólico de PAE (150 MW, H2/amoníaco) — https://www.energiaestrategica.com/pae-disena-un-nuevo-parque-eolico-de-gran-escala-que-producira-hidrogeno-o-amoniaco-verde/
- Tecpetrol — parque eólico para Tenaris (Campana) — https://www.tecpetrol.com/es/noticias/2023/parque-eolico-tenaris-argentina
- ENAPRO — terminales del Puerto de Rosario — https://enapro.com.ar/terminales-comerciales/ ; parque FV de ACA en zona portuaria — https://ecobiz.com.ar/nota/291-El-puerto-del-Gran-Rosario-que-pica-en-punta-con-la-energia-solar
- Argentina.gob.ar — terminales del Puerto de Buenos Aires (Agencia Nacional de Puertos y Navegación) — https://www.argentina.gob.ar/economia/agencia-nacional-de-puertos-y-navegacion/el-puerto-buenos-aires/terminales-portuarias
- Futuro Sustentable — Aeropuertos Argentina, 100 % renovable en Ezeiza — https://futurosustentable.com.ar/aeropuertos-argentina-alcanza-el-100-de-energia-renovable-en-ezeiza-y-refuerza-su-estrategia-de-descarbonizacion/
- Aviacionline — Ezeiza 100 % consumo eléctrico renovable — https://www.aviacionline.com/espanol/aviacion-sostenible/aeropuertos/el-aeropuerto-de-ezeiza-alcanza-100-de-su-consumo-electrico-con-energia-renovable_a6a28794803d1047930c20f52
- DatacenterDynamics — Telecom Argentina incorpora renovables (PPAs con Genneia e YPF Luz) — https://www.datacenterdynamics.com/es/noticias/telecom-argentina-incorpora-fuentes-de-energia-renovable-a-su-matriz-energetica/
- Chequeado — aprobación con condiciones de la compra de Telefónica por Telecom, jun-2026 — https://chequeado.com/el-explicador/el-gobierno-aprobo-la-venta-de-telefonica-a-telecom-con-condiciones-4-claves-para-entender-la-operacion/
- Infobae — salida definitiva de Falabella de Argentina, 01-06-2021 — https://www.infobae.com/economia/2021/06/01/salida-definitiva-de-falabella-del-pais-cerro-su-ultima-tienda-y-ni-siquiera-vendera-online/
- La Nación — Falabella conserva Sodimac en Argentina, 29-03-2021 — https://www.lanacion.com.ar/propiedades/inmuebles-comerciales/falabella-la-empresa-conservara-las-operaciones-de-sodimac-en-el-pais-nid29032021/
- Portal de Arquitectos — data center de Claro Argentina (sala de UPS y baterías) — https://portaldearquitectos.com/claro-amplia-su-datacenter/
- Revista Electricidad — acuerdo AES Andes–Cencosud (Chile, no Argentina), jun-2026 — https://www.revistaei.cl/aes-andes-y-cencosud-extienden-uno-de-los-mayores-acuerdos-de-energia-renovable-para-suministro-del-retail-en-chile/
- Energía Online — programa BESS de la Provincia de Buenos Aires (25 MW / 125 MWh) — https://energiaonline.com.ar/pba-avanza-con-el-sistema-de-almacenamiento-de-energia-en-baterias/
- Econojournal — AlmaSADI, licitación de 700 MW, mar-2026 — https://econojournal.com.ar/2026/03/almacenamiento-lanzan-una-licitacion-para-instalar-baterias-por-700-mw-con-cammesa-a-cargo-de-los-contrato/
- Primera Edición — adjudicación AlmaSADI 700,5 MW (Res. 155/2026, 08-07-2026) — https://www.primeraedicion.com.ar/nota/101121050/adjudican-700-mw-almacenamiento-electrico-baterias-almasadi/

**Clasificación de fuentes:** ninguna de las cifras cargadas proviene de conocimiento de entrenamiento. El dato numérico único (32 MWh) es **(b) prensa especializada/local**, citando textualmente y de forma coincidente a dos medios independientes, sobre un proyecto de EPSE y el Gobierno de San Juan — **no** se localizó publicación oficial de EPSE que lo confirme, así que queda pendiente ese último chequeo antes de aplicarlo al xlsx oficial. No hay ninguna estimación propia (c) en esta corrida.
