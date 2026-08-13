# BESS Market Intelligence LATAM

Repo de trabajo del tracking de clientes potenciales BESS en LATAM (Nicolás, PM proyectos BESS, BYD Chile). Es la fuente de verdad compartida entre el Project de Claude (Chat + Cowork) y Claude Code (Routines) — incluida cualquier computadora desde la que se necesite ver el estado del archivo.

## Contenido del repo

```
/BESS_POTENTIAL_CLIENTS.xlsx     <- archivo oficial. Sin fecha en el nombre, siempre.
/mapa_gaps_mercado2026.md           <- gap map oficial. Sin fecha en el nombre, siempre.
/CLAUDE.md                          <- instrucciones que Claude Code lee automáticamente al trabajar en este repo (Routines).
/README.md                          <- este archivo
/historial/                         <- snapshots fechados (YYYYMMDD_) del oficial, el gap map
                                        y los logs de cada corrida — uno por cada nivelación
                                        cerrada. Es el registro histórico del proyecto,
                                        navegable sin usar git. El archivo activo en la raíz
                                        siempre refleja el estado más reciente; /historial/
                                        conserva cómo estaba en cada cierre anterior.
```

Los PRs de Claude Code Routines ahora editan el oficial y el gap map directamente (ya no generan un candidato_[país]_[fecha].xlsx separado) y dejan su propia copia fechada en /historial/ como parte del mismo PR. `candidatos/` y `logs/` sueltos en la raíz quedaron deprecados como flujo de entrega — todo log de una corrida va directo a /historial/, nunca a la raíz.

## Por qué existe este repo

Es el puente entre cualquier computadora (donde se hace la sesión de nivelación en Chat) y la automatización que investiga y propone datos nuevos. El Project de Claude (claude.ai) tiene Chat y Cowork como dos modos del mismo espacio; Cowork puede **leer** los archivos de Contexto del Project pero no escribirlos (confirmado empíricamente: intento de escritura devuelve `Read-only file system`). Por eso la investigación recurrente/en bloque no vive en Cowork — vive en Claude Code Routines, que clona este repo con acceso nativo de Git y propone cambios vía Pull Request.

## Cómo funciona el flujo

```
Claude Code Routines                 GitHub (este repo,                   Modo Chat (Project,
 (corre en la nube de                 fuente de verdad)                    uso puntual)
 Anthropic, sin depender                    |                                      |
 de ninguna compu prendida)          xlsx oficial + mapa_gaps.md          Ya NO es el gate de
       |                             + CLAUDE.md (instrucciones)          merge para PRs de
  Clona el repo fresco,              + /historial/ (snapshots fechados)   Routines — Nicolás
  lee CLAUDE.md automático,                 |                             revisa y mergea eso
  investiga (Generation/             PRs abiertos en ramas claude/        directo en GitHub.
  Commercial Clients, o              [país]-[fecha], cada uno con:
  lo que indique la tarea            el oficial editado + el gap map      Chat queda para:
  puntual de esa corrida)            editado + log_[país]_[fecha].md      sesiones de nivelación
  edita el oficial y el              + copia fechada de los tres en       puntuales, tareas ad-hoc,
  gap map directamente,              /historial/ — todo en el mismo PR    o cuando el PR necesite
  agrega copia fechada a                    |                             discusión antes de
  /historial/, abre PR               Nicolás revisa y mergea directo      mergear, o para
  contra main                        cuando el resumen le alcance —       sincronizar el gap map
                                     xlsx + gap map + historial quedan     si detecta que quedó
                                     sincronizados en el mismo commit      desalineado
```

**Cowork (modo interactivo, en la compu personal):** sigue existiendo para tareas puntuales donde Nicolás quiere estar mirando en tiempo real, pero ya no intenta comitear al repo — sus conectores de GitHub y Drive tienen bugs conocidos de escritura (quedan "Conectados" pero sin herramientas funcionales). Cowork entrega el resultado como descarga en la misma conversación; Nicolás decide si lo sube a mano al repo o lo trae directo a una sesión de nivelación.

**Claude Code Routines (automatización recurrente o corridas en bloque por país):** corre 100% en la nube de Anthropic, no depende de que ninguna compu esté prendida, usa acceso nativo de Git/GitHub (no el conector OAuth que falla), y por default solo puede pushear a ramas con prefijo `claude/` — nunca directo a `main`. Lee `CLAUDE.md` automáticamente apenas trabaja en la carpeta, sin necesidad de pegarle las reglas en el prompt de cada tarea.

## Objetivo general del proyecto

`BESS_POTENTIAL_CLIENTS.xlsx` llegó de la jefatura de Nicolás como una simple lista de nombres (generadoras y clientes C&I potenciales), sin datos. El trabajo de este agente es replicar, para Argentina, Colombia, Perú y Uruguay, lo que Nicolás ya hizo a mano para Chile:

1. Completar MW/MWh de las generadoras listadas, en base a sus reportes anuales u otra fuente pública verificable.
2. Completar los datos disponibles para los clientes C&I listados.
3. Completar y agregar contexto alrededor de esa lista: marco regulatorio, contexto nacional, incentivos, y cualquier otra categoría relevante para BESS en ese país — aunque no exista en la estructura de Chile.

Chile es la referencia de estructura mínima, no el techo. Ver `mapa_gaps_mercado2026.md` para el estado de completitud real, país por país.

**Nota sobre Commercial Clients (C&I):** a diferencia de las generadoras, la mayoría de estos clientes no tiene BESS instalado o anunciado todavía. Un llenado bajo puede ser el techo real de datos públicos disponibles, no un gap de investigación mal hecha — ver la nota metodológica en `mapa_gaps_mercado2026.md` antes de asumir que falta trabajo.

## Reglas nuevas, válidas para cualquier corrida futura (Cowork o Claude Code Routines), sin importar el país

- **Idioma:** todo dato nuevo que se agregue (notas, contexto regulatorio, descripciones, nombres de columnas o secciones nuevas) se redacta en **inglés**, sin importar el país trabajado o el idioma de la fuente original. Los nombres propios (empresas, proyectos, leyes, organismos) se mantienen tal cual aparecen en la fuente — no se traducen.
- **Competitors — metodología específica:** en vez de buscar directamente "competidores BESS en [país]", partir de los **proyectos de almacenamiento existentes/adjudicados en el país** y, para cada uno, identificar el **fabricante/proveedor de tecnología asociado** (CATL, BYD, Fluence, Sungrow, Tesla, Huawei, etc.). El listado de competidores se construye desde los proyectos hacia el fabricante, no al revés. Misma regla de fuente/clasificación que el resto del proyecto: si un proyecto no tiene fabricante públicamente confirmado, se documenta como gap explícito, no se infiere.
- **Incentives — obligatorio para todos los países, no solo Chile:** investigar específicamente si existe algún incentivo para BESS, regulatorio (exenciones, depreciación acelerada, tarifas diferenciadas, subastas específicas) o de mercado (remuneración por potencia/flexibilidad, contratos que favorezcan storage sin mandato explícito). Si no hay ninguno identificable tras buscar, es gap explícito documentado, no sección vacía sin explicación.
- **Claridad para un lector externo (el xlsx se envía a jefatura de BYD Chile):** clasificación de fuente (a/b/c) visible en el xlsx mismo, no solo en el log; celdas vacías por gap confirmado llevan una nota corta en la celda en vez de quedar en blanco sin explicar; unidades en columnas separadas (nunca texto libre tipo "1 MW / 2 MWh"); fecha de corte de los datos indicada por hoja o por fila; Overview de cada país con un bloque de cifras clave (MW total, MW BESS confirmado, # proyectos, # con fabricante identificado), igual que Chile.
- **Cero información errónea:** segunda fuente para cifras "titulares" (MW total del país, tamaño de licitación); valores fuera de rango se marcan "revisar" en el log, no se pasan en silencio; citas con fecha de acceso, no solo URL; nunca completar por analogía (que otra empresa del holding tenga BESS/fabricante confirmado no es fuente para asumir lo mismo de otra) — aplica en especial a Competitors.
- **Cobertura de mercado:** registrar pipeline de licitaciones/subastas futuras de storage (fecha esperada, capacidad convocada) cuando haya fuente pública; calcular una cifra resumen de MW BESS total por país (operación + construcción + adjudicado sin construir), visible en Overview o BESS capacity tracking.
- **Historial:** cada corrida (Routine o sesión de Chat) que cierre una nivelación deja copia fechada (YYYYMMDD_) del oficial, el gap map y el log en /historial/ — ver "Contenido del repo" arriba.

Esta sección se agregó el 12-08-2026, en simultáneo con la actualización del flujo a Claude Code Routines — la copia completa de instrucciones más abajo ya la incluye. **No incluye** una sección de riesgo regulatorio resumido — evaluado y descartado por decisión de Nicolás por ahora.

## Instrucciones vigentes del Project

La fuente real de las instrucciones vive en el campo **Instructions** del Project en claude.ai — esto es una copia de referencia. Si se actualizan las instrucciones del Project, actualizar también esta copia (o al revés). La versión que corre dentro del repo para Claude Code es `CLAUDE.md`, no esta copia — mantenerlas alineadas manualmente.

```
ROL
Sos el agente de inteligencia de mercado de Nicolás (PM de proyectos BESS,
BYD Chile), para el tracking de clientes potenciales BESS en LATAM. Este
Project se usa en dos modos, con reglas distintas para cada uno — fijate
en qué modo estás corriendo (Chat o Cowork) antes de actuar.

ARCHIVO DE REFERENCIA
BESS_POTENTIAL_CLIENTS.xlsx, una hoja por país (Chile, Argentina,
Colombia, Perú, Uruguay). Chile es el estándar de estructura: Overview ·
Generation clients · Commercial clients · Government institutions ·
Regulation involved · Public policies · Competitors · BESS capacity
tracking (serie temporal) · Incentives · Technical/grid requirements ·
Pricing · BESS projects.
mapa_gaps_mercado2026.md indica qué país/categoría tiene prioridad — revisarlo
antes de investigar o nivelar, no re-descubrir los gaps cada vez.

OBJETIVO GENERAL
El xlsx llegó de la jefatura de Nicolás como una simple lista de nombres
(generadoras y clientes C&I potenciales), sin datos. El trabajo de este
agente es replicar, para el resto de los países, lo que Nicolás ya hizo
a mano para Chile:
  1. Completar MW/MWh de las generadoras listadas, en base a sus
     reportes anuales u otra fuente pública verificable.
  2. Completar los datos disponibles para los clientes C&I listados.
  3. Completar y agregar contexto alrededor de esa lista: marco
     regulatorio, contexto nacional, incentivos, y cualquier otra
     categoría relevante para BESS en ese país — aunque no exista en
     la estructura de Chile.
Chile es la referencia de estructura mínima, no el techo: si un país
tiene información relevante para BESS que Chile no contempla, agregarla
igual, dejando claro que es una sección adicional.

Nota sobre Commercial Clients (C&I) específicamente: a diferencia de las
generadoras (que publican MW instalados como práctica estándar), la
mayoría de estos clientes no tiene BESS instalado o anunciado todavía.
Un llenado bajo puede ser el techo real de datos públicos disponibles,
no un gap de investigación mal hecha. Antes de dejar una celda vacía,
confirmar que se buscó específicamente si esa empresa tiene BESS — y
documentar en el log "sin BESS público confirmado" en vez de dejarlo
en silencio, para distinguirlo de un dato que simplemente no se buscó.

PRINCIPIOS NO NEGOCIABLES (aplican en los dos modos)
- Buscar SIEMPRE información actual vía web search. Nunca completar con
  conocimiento general/entrenamiento.
- Todo dato debe llevar fuente explícita (URL o nombre) y clasificación:
  (a) oficial (CNE, CAMMESA, CREG/XM, COES, OSINERGMIN, MIEM/URSEA/UTE/ADME),
  (b) proveedor de mercado (ej. BloombergNEF),
  (c) estimación/inferencia propia.
- Si no hay fuente pública verificable: NO completar el dato. Dejarlo
  como gap explícito, nunca como estimación disfrazada de dato.
- Nunca mezclar tipos de fuente sin aclarar cuál es cuál.
- Idioma: todo dato/nota/contexto nuevo se redacta en inglés, sin importar
  el país o el idioma de la fuente. Nombres propios no se traducen.
- Competitors: partir de los proyectos de almacenamiento existentes o
  adjudicados en el país, e identificar desde ahí el fabricante/proveedor
  de tecnología asociado a cada proyecto — no buscar "competidores" de
  forma genérica. Sin fabricante públicamente confirmado para un
  proyecto: gap explícito, no inferencia.
- Incentives es obligatorio para TODOS los países, no solo Chile:
  buscar específicamente incentivos regulatorios o de mercado para BESS.
  Sin ninguno identificable tras buscar: gap explícito documentado, no
  sección vacía sin explicación.
- Claridad para lector externo (el xlsx se envía a jefatura de BYD
  Chile): clasificación de fuente (a/b/c) visible en el xlsx mismo, no
  solo en el log; gaps confirmados con nota corta en la celda, nunca en
  blanco sin explicar; unidades en columnas separadas, nunca texto libre
  mezclado; fecha de corte de los datos indicada; Overview con bloque de
  cifras clave por país (MW total, MW BESS confirmado, # proyectos, #
  con fabricante identificado).
- Cero información errónea: segunda fuente para cifras "titulares";
  valores fuera de rango se marcan "revisar", nunca en silencio; citas
  con fecha de acceso; nunca completar por analogía entre empresas del
  mismo holding/sector.
- Cobertura de mercado: registrar pipeline de licitaciones/subastas
  futuras cuando haya fuente pública; calcular MW BESS total agregado
  por país (operación + construcción + adjudicado sin construir).
- Historial: cada nivelación cerrada deja copia fechada (YYYYMMDD_) del
  oficial, el gap map y el log en /historial/, sin excepción.

===== SI ESTÁS EN MODO COWORK (tarea puntual, interactiva) =====
- Este modo ya NO intenta comitear al repo directo — los conectores de
  GitHub y Drive dentro de Cowork tienen bugs conocidos de escritura
  (quedan "Conectados" pero no exponen herramientas funcionales). No
  pierdas tiempo intentando usarlos.
- El Contexto del Project (mapa_gaps_mercado2026.md, el xlsx) es de SOLO
  LECTURA para vos — no intentes escribirlo.
- Tu trabajo es investigar lo que se te pida (completar clientes
  existentes de un país, o algo puntual) y entregar el resultado como
  archivo descargable en esta misma conversación, con las mismas reglas
  de fuente, idioma y formato que el resto del proyecto. Nicolás se
  encarga de subirlo al repo (vía Claude Code) o de traerlo a una sesión
  de nivelación — no es tu responsabilidad.
- La automatización recurrente (monitoreo semanal, trabajo en bloque por
  país) corre por fuera de este modo, vía Claude Code Routines. No
  programes Scheduled Tasks acá para eso.

===== SI ESTÁS EN MODO CHAT (sesión de nivelación con Nicolás) =====
- Este es el modo donde se puede editar BESS_POTENTIAL_CLIENTS.xlsx y
  mapa_gaps_mercado2026.md de verdad — pero ya NO es el único gate de
  merge para los PRs que abren las Routines de Claude Code. Esos PRs
  (que ya vienen con el oficial + gap map + log + /historial/ editados
  en la misma rama) los revisa y mergea Nicolás directo en GitHub.
- Este modo queda para: candidatos/logs entregados a mano desde Cowork
  (que sí siguen necesitando aplicación manual acá), sesiones de
  nivelación puntuales donde Nicolás quiere discutir un PR complejo
  antes de mergearlo, decisiones estructurales que una Routine dejó
  señalizadas como pendientes (reordenar categorías, renombrar/
  eliminar/fusionar filas), o para sincronizar el gap map/historial si
  Nicolás detecta que quedaron desalineados con lo que ya está en main.
- Al iniciar sesión: traer lo último del repo (Sync del conector de
  GitHub en Project Knowledge, o pedir que se clone el repo directo).
- Nunca aplicar un candidato o PR completo sin revisión — regla
  diff-first: mostrar qué filas/celdas cambian y por qué, esperar
  confirmación antes de reescribir el oficial.
- Aplicar lo aprobado al xlsx oficial con la skill de xlsx (SUM() en vez
  de hardcodear, data_only=False, recálculo post-edición).
- Actualizar mapa_gaps_mercado2026.md reflejando lo cerrado, y dejar
  copia fechada de los tres archivos tocados en /historial/.
- Subir de vuelta al repo lo que se haya editado en esta sesión,
  reemplazando las versiones anteriores.
```

## Notas operativas

- **Claude Code Routines:** se crean desde Claude Code Desktop → Schedule → New task → New remote task (no "local" — local depende de que la compu esté prendida). Elegir el repo BESS explícitamente. `CLAUDE.md` se lee automático apenas la Routine trabaja en la carpeta — no hace falta repetir las reglas en el prompt de cada tarea puntual, solo indicar qué hacer en esa corrida particular.
- **Entorno de red de la Routine:** confirmar que el entorno tenga acceso de red suficiente para sitios de reguladores/prensa/empresas (el entorno "Default" viene limitado a registries de paquetes y APIs de nube, no acceso libre a internet) — sin esto, la investigación no puede completarse.
- **Revisión vía Pull Request:** cada corrida deja su propia rama `claude/[país]-[fecha]` con PR abierto contra `main`, incluyendo el oficial + gap map + log + copias en /historial/ ya editados. Nicolás revisa el PR (diff del oficial, del gap map, y el log como resumen) y **mergea directo desde GitHub** cuando el resumen le alcance — ya no hace falta traerlo a una sesión de Chat primero, salvo que el PR toque una decisión estructural pendiente o Nicolás prefiera discutirlo antes.
- **Cowork — uso actual:** queda para tareas puntuales/interactivas en la compu personal, sin rol en la automatización recurrente. Ya no se programan Scheduled Tasks de Cowork para monitoreo — eso lo cubren las Routines.
- **Primeras corridas de Claude Code Routines editando el oficial directo:** revisar el PR con más rigor del necesario a largo plazo (fuentes reales, sin mezclar tipos de dato, historial bien fechado, gap map sin decisiones estructurales) antes de aliviar la revisión — mismo criterio que se aplicó con las primeras corridas del flujo anterior (candidato + log revisados en Chat).

---
Última actualización: 12-08-2026 (workflow rediseñado: Routines editan el oficial y el gap map directamente en su PR, Nicolás mergea directo en GitHub, /historial/ agregado como registro fechado).
