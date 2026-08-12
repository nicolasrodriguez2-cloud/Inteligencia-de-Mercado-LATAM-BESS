# BESS Market Intelligence LATAM

Repo de trabajo del tracking de clientes potenciales BESS en LATAM (Nicolás, PM proyectos BESS, BYD Chile). Es la fuente de verdad compartida entre el Project de Claude (Chat + Cowork) y Claude Code (Routines) — incluida cualquier computadora desde la que se necesite ver el estado del archivo.

## Contenido del repo

```
/BESS_POTENTIAL_CLIENTS_v2.xlsx     <- archivo oficial. Solo se edita en modo Chat, en sesión con Nicolás.
/mapa_gaps_mercado.md               <- gap map oficial. Ídem, solo se edita en modo Chat.
/CLAUDE.md                          <- instrucciones que Claude Code lee automáticamente al trabajar en este repo (Routines).
/README.md                          <- este archivo
```

`candidatos/` y `logs/` (generados a mano por Cowork) quedaron deprecados como flujo de entrega al repo — ver nota más abajo. Las Routines de Claude Code entregan su trabajo como Pull Requests en ramas `claude/[país]-[fecha]`, no como archivos sueltos en carpetas.

## Por qué existe este repo

Es el puente entre cualquier computadora (donde se hace la sesión de nivelación en Chat) y la automatización que investiga y propone datos nuevos. El Project de Claude (claude.ai) tiene Chat y Cowork como dos modos del mismo espacio; Cowork puede **leer** los archivos de Contexto del Project pero no escribirlos (confirmado empíricamente: intento de escritura devuelve `Read-only file system`). Por eso la investigación recurrente/en bloque no vive en Cowork — vive en Claude Code Routines, que clona este repo con acceso nativo de Git y propone cambios vía Pull Request.

## Cómo funciona el flujo

```
Claude Code Routines                 GitHub (este repo,                   Modo Chat (Project,
 (corre en la nube de                 fuente de verdad)                    sesión de nivelación)
 Anthropic, sin depender                    |                                      |
 de ninguna compu prendida)          xlsx oficial + mapa_gaps.md          Trae lo último del repo
       |                             + CLAUDE.md (instrucciones)          (Sync del conector, o
  Clona el repo fresco,               |                                   pedirle a Claude que
  lee CLAUDE.md automático,    PRs abiertos en ramas claude/[país]-       clone el repo directo)
  investiga (Generation/       [fecha], candidato + log                   revisa cada PR abierto,
  Commercial Clients, o        (se acumulan, nunca se                     muestra diff, aplica lo
  lo que indique la tarea      sobrescriben)                              aprobado al xlsx oficial,
  puntual de esa corrida)                                                 sube la versión nueva,
  abre PR contra main                                                     mergea o cierra el PR
```

**Cowork (modo interactivo, en la compu personal):** sigue existiendo para tareas puntuales donde Nicolás quiere estar mirando en tiempo real, pero ya no intenta comitear al repo — sus conectores de GitHub y Drive tienen bugs conocidos de escritura (quedan "Conectados" pero sin herramientas funcionales). Cowork entrega candidato + log como descarga en la misma conversación; Nicolás decide si los sube a mano al repo o los trae directo a una sesión de nivelación.

**Claude Code Routines (automatización recurrente o corridas en bloque por país):** corre 100% en la nube de Anthropic, no depende de que ninguna compu esté prendida, usa acceso nativo de Git/GitHub (no el conector OAuth que falla), y por default solo puede pushear a ramas con prefijo `claude/` — nunca directo a `main`. Lee `CLAUDE.md` automáticamente apenas trabaja en la carpeta, sin necesidad de pegarle las reglas en el prompt de cada tarea.

## Objetivo general del proyecto

`BESS_POTENTIAL_CLIENTS_v2.xlsx` llegó de la jefatura de Nicolás como una simple lista de nombres (generadoras y clientes C&I potenciales), sin datos. El trabajo de este agente es replicar, para Argentina, Colombia, Perú y Uruguay, lo que Nicolás ya hizo a mano para Chile:

1. Completar MW/MWh de las generadoras listadas, en base a sus reportes anuales u otra fuente pública verificable.
2. Completar los datos disponibles para los clientes C&I listados.
3. Completar y agregar contexto alrededor de esa lista: marco regulatorio, contexto nacional, incentivos, y cualquier otra categoría relevante para BESS en ese país — aunque no exista en la estructura de Chile.

Chile es la referencia de estructura mínima, no el techo. Ver `mapa_gaps_mercado.md` para el estado de completitud real, país por país.

**Nota sobre Commercial Clients (C&I):** a diferencia de las generadoras, la mayoría de estos clientes no tiene BESS instalado o anunciado todavía. Un llenado bajo puede ser el techo real de datos públicos disponibles, no un gap de investigación mal hecha — ver la nota metodológica en `mapa_gaps_mercado.md` antes de asumir que falta trabajo.

## Reglas nuevas, válidas para cualquier corrida futura (Cowork o Claude Code Routines), sin importar el país

- **Idioma:** todo dato nuevo que se agregue (notas, contexto regulatorio, descripciones, nombres de columnas o secciones nuevas) se redacta en **inglés**, sin importar el país trabajado o el idioma de la fuente original. Los nombres propios (empresas, proyectos, leyes, organismos) se mantienen tal cual aparecen en la fuente — no se traducen.
- **Competitors — metodología específica:** en vez de buscar directamente "competidores BESS en [país]", partir de los **proyectos de almacenamiento existentes/adjudicados en el país** y, para cada uno, identificar el **fabricante/proveedor de tecnología asociado** (CATL, BYD, Fluence, Sungrow, Tesla, Huawei, etc.). El listado de competidores se construye desde los proyectos hacia el fabricante, no al revés. Misma regla de fuente/clasificación que el resto del proyecto: si un proyecto no tiene fabricante públicamente confirmado, se documenta como gap explícito, no se infiere.
- **Incentives — obligatorio para todos los países, no solo Chile:** investigar específicamente si existe algún incentivo para BESS, regulatorio (exenciones, depreciación acelerada, tarifas diferenciadas, subastas específicas) o de mercado (remuneración por potencia/flexibilidad, contratos que favorezcan storage sin mandato explícito). Si no hay ninguno identificable tras buscar, es gap explícito documentado, no sección vacía sin explicación.
- **Claridad para un lector externo (el xlsx se envía a jefatura de BYD Chile):** clasificación de fuente (a/b/c) visible en el xlsx mismo, no solo en el log; celdas vacías por gap confirmado llevan una nota corta en la celda en vez de quedar en blanco sin explicar; unidades en columnas separadas (nunca texto libre tipo "1 MW / 2 MWh"); fecha de corte de los datos indicada por hoja o por fila; Overview de cada país con un bloque de cifras clave (MW total, MW BESS confirmado, # proyectos, # con fabricante identificado), igual que Chile.
- **Cero información errónea:** segunda fuente para cifras "titulares" (MW total del país, tamaño de licitación); valores fuera de rango se marcan "revisar" en el log, no se pasan en silencio; citas con fecha de acceso, no solo URL; nunca completar por analogía (que otra empresa del holding tenga BESS/fabricante confirmado no es fuente para asumir lo mismo de otra) — aplica en especial a Competitors.
- **Cobertura de mercado:** registrar pipeline de licitaciones/subastas futuras de storage (fecha esperada, capacidad convocada) cuando haya fuente pública; calcular una cifra resumen de MW BESS total por país (operación + construcción + adjudicado sin construir), visible en Overview o BESS capacity tracking.

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
BESS_POTENTIAL_CLIENTS_v2.xlsx, una hoja por país (Chile, Argentina,
Colombia, Perú, Uruguay). Chile es el estándar de estructura: Overview ·
Generation clients · Commercial clients · Government institutions ·
Regulation involved · Public policies · Competitors · BESS capacity
tracking (serie temporal) · Incentives · Technical/grid requirements ·
Pricing · BESS projects.
mapa_gaps_mercado.md indica qué país/categoría tiene prioridad — revisarlo
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

===== SI ESTÁS EN MODO COWORK (tarea puntual, interactiva) =====
- Este modo ya NO intenta comitear al repo directo — los conectores de
  GitHub y Drive dentro de Cowork tienen bugs conocidos de escritura
  (quedan "Conectados" pero no exponen herramientas funcionales). No
  pierdas tiempo intentando usarlos.
- El Contexto del Project (mapa_gaps_mercado.md, el xlsx) es de SOLO
  LECTURA para vos — no intentes escribirlo.
- Tu trabajo es investigar lo que se te pida (completar clientes
  existentes de un país, o algo puntual) y entregar el resultado como
  archivo descargable en esta misma conversación: candidato_[país]_[fecha].xlsx
  + log_[país]_[fecha].md, con las mismas reglas de fuente, idioma y
  formato que el resto del proyecto. Nicolás se encarga de subirlos al
  repo o traerlos a una sesión de nivelación — no es tu responsabilidad.
- La automatización recurrente (monitoreo semanal, trabajo en bloque por
  país) corre por fuera de este modo, vía Claude Code Routines. No
  programes Scheduled Tasks acá para eso.

===== SI ESTÁS EN MODO CHAT (sesión de nivelación con Nicolás) =====
- Este es el único modo donde se edita BESS_POTENTIAL_CLIENTS_v2.xlsx y
  mapa_gaps_mercado.md de verdad.
- Al iniciar sesión: traer lo último del repo (Sync del conector de
  GitHub en Project Knowledge, o pedir que se clone el repo directo).
- Revisar lo pendiente de DOS fuentes posibles: los Pull Requests abiertos
  por las Routines de Claude Code (rama claude/[país]-[fecha]), y
  cualquier candidato/log entregado a mano desde Cowork — tratar cada uno
  igual, línea por línea, antes de aplicar.
- Nunca aplicar un candidato o PR completo sin revisión.
- Antes de reescribir el xlsx oficial, mostrar el diff propuesto (qué
  filas/celdas cambian y por qué) y esperar confirmación — regla
  diff-first, igual que en el resto del sistema.
- Aplicar lo aprobado al xlsx oficial con la skill de xlsx (SUM() en vez
  de hardcodear, data_only=False, recálculo post-edición).
- Actualizar mapa_gaps_mercado.md reflejando lo cerrado.
- Subir de vuelta al repo el xlsx oficial y el gap map, reemplazando las
  versiones anteriores. Mergear o cerrar en GitHub el/los PR(s) ya
  incorporados — el merge ahí es solo registro histórico, el oficial ya
  se actualizó a mano en este paso.
```

## Notas operativas

- **Claude Code Routines:** se crean desde Claude Code Desktop → Schedule → New task → New remote task (no "local" — local depende de que la compu esté prendida). Elegir el repo BESS explícitamente. `CLAUDE.md` se lee automático apenas la Routine trabaja en la carpeta — no hace falta repetir las reglas en el prompt de cada tarea puntual, solo indicar qué hacer en esa corrida particular.
- **Entorno de red de la Routine:** confirmar que el entorno tenga acceso de red suficiente para sitios de reguladores/prensa/empresas (el entorno "Default" viene limitado a registries de paquetes y APIs de nube, no acceso libre a internet) — sin esto, la investigación no puede completarse.
- **Revisión vía Pull Request:** cada corrida deja su propia rama `claude/[país]-[fecha]` con PR abierto contra `main`. Revisar el diff igual que se revisaba antes el log de Cowork — fuentes reales, sin mezclar tipos, nada de estructura tocada sin avisar. No mergear directo desde GitHub — traer a sesión de nivelación en Chat primero.
- **Cowork — uso actual:** queda para tareas puntuales/interactivas en la compu personal, sin rol en la automatización recurrente. Ya no se programan Scheduled Tasks de Cowork para monitoreo — eso lo cubren las Routines.
- **Primeras corridas de Claude Code Routines:** revisar PR + log con más rigor del necesario a largo plazo, para calibrar que las fuentes sean reales y no se mezclen tipos de dato antes de aliviar la revisión — mismo criterio que se aplicó con las primeras corridas de Cowork.

---
Última actualización: 12-08-2026.
