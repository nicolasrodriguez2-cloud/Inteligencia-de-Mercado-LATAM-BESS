# BESS Market Intelligence LATAM

Repo de trabajo del tracking de clientes potenciales BESS en LATAM (Nicolás, PM proyectos BESS, BYD Chile). Es la fuente de verdad compartida entre el Project de Claude (Chat + Cowork) y cualquier computadora desde la que se necesite ver el estado del archivo — incluida una sin acceso a Cowork.

## Contenido del repo

```
/BESS_POTENTIAL_CLIENTS_v2.xlsx     <- archivo oficial. Solo se edita en modo Chat, en sesión con Nicolás.
/mapa_gaps_mercado.md               <- gap map oficial. Ídem, solo se edita en modo Chat.
/candidatos/                        <- candidatos generados por Cowork (xlsx), se acumulan, nunca se sobrescriben
/logs/                              <- logs de cambios generados por Cowork (md), uno por candidato
/README.md                          <- este archivo
```

## Por qué existe este repo

El Project de Claude (claude.ai) tiene Chat y Cowork como dos modos del mismo espacio, compartiendo Instrucciones y Contexto — pero Cowork solo puede **leer** los archivos de Contexto del Project, no escribirlos (confirmado empíricamente: intento de escritura devuelve `Read-only file system`). Este repo es el lugar donde Cowork entrega su trabajo, y el puente entre la computadora personal (donde corre Cowork) y cualquier otra computadora (donde no).

## Cómo funciona el flujo

```
Modo Cowork (Project,               GitHub (este repo,                   Modo Chat (Project,
 tarea puntual o Scheduled Task)     fuente de verdad)                    sesión de nivelación)
       |                                    |                                      |
  Lee el Contexto (solo lectura)   xlsx oficial + mapa_gaps.md          Trae lo último del repo
  completa clientes existentes ->  candidatos/ + logs/          <---->  (Sync del conector, o
  o busca novedades, según tarea    (se acumulan, nunca se               pedirle a Claude que
  genera candidato + log             sobrescriben solos)                 clone el repo directo)
  entrega al repo, NO al Contexto                                        revisa candidato+log,
                                                                          muestra diff, aplica lo
                                                                          aprobado al xlsx oficial,
                                                                          sube la versión nueva
```

Dos conectores de GitHub distintos están involucrados: uno en Cowork (Settings → Connectors de la cuenta), usado para que Cowork entregue candidatos y logs; y uno en Project Knowledge, usado para que el modo Chat lea el contexto actualizado. Ambos apuntan a este mismo repo, con acceso limitado solo a él.

## Objetivo general del proyecto

`BESS_POTENTIAL_CLIENTS_v2.xlsx` llegó de la jefatura de Nicolás como una simple lista de nombres (generadoras y clientes C&I potenciales), sin datos. El trabajo de este agente es replicar, para Argentina, Colombia, Perú y Uruguay, lo que Nicolás ya hizo a mano para Chile:

1. Completar MW/MWh de las generadoras listadas, en base a sus reportes anuales u otra fuente pública verificable.
2. Completar los datos disponibles para los clientes C&I listados.
3. Completar y agregar contexto alrededor de esa lista: marco regulatorio, contexto nacional, incentivos, y cualquier otra categoría relevante para BESS en ese país — aunque no exista en la estructura de Chile.

Chile es la referencia de estructura mínima, no el techo. Ver `mapa_gaps_mercado.md` para el estado de completitud real, país por país.

**Nota sobre Commercial Clients (C&I):** a diferencia de las generadoras, la mayoría de estos clientes no tiene BESS instalado o anunciado todavía. Un llenado bajo puede ser el techo real de datos públicos disponibles, no un gap de investigación mal hecha — ver la nota metodológica en `mapa_gaps_mercado.md` antes de asumir que falta trabajo.

## Instrucciones vigentes del Project

La fuente real de las instrucciones vive en el campo **Instructions** del Project en claude.ai — esto es una copia de referencia. Si se actualizan las instrucciones del Project, actualizar también esta copia (o al revés).

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

===== SI ESTÁS EN MODO COWORK (tarea puntual o Scheduled Task) =====
- El Contexto del Project (mapa_gaps_mercado.md, el xlsx) es de SOLO
  LECTURA para vos — no intentes escribirlo, va a fallar (Read-only file
  system) y no es el flujo correcto.
- Para entregar resultados usás el conector de GitHub de la cuenta
  (Settings → Connectors, distinto del GitHub conectado a Project
  Knowledge). Ese conector solo tiene acceso a este repo — nunca asumas
  ni pidas acceso a otro repositorio.
- Dos tipos de trabajo posibles, según lo que se te pida:
  - Completar lo existente: tomar los nombres ya listados en Generation
    Clients y/o Commercial Clients de un país y buscarles MW/MWh y demás
    datos disponibles (probablemente el grueso del trabajo inicial, no
    algo semanal).
  - Monitoreo de novedades (la Scheduled Task recurrente): detectar
    anuncios, adjudicaciones o cambios nuevos desde la última corrida.
  Ambos entregan candidato + log de la misma forma — la diferencia es el
  disparador y qué buscan.
- Entregá el resultado a este repo, nunca al Contexto del Project.
- Generá candidato_[país]_[fecha].xlsx: una copia del xlsx oficial (traído
  del repo) con solo filas nuevas o celdas de datos actualizadas, mismo
  formato/unidades que ya existen. No reordenar categorías, no tocar
  fórmulas, no decidir cambios estructurales — anotar la ambigüedad en el
  log para que Nicolás decida.
- Generá log_[país]_[fecha].md: una línea por celda tocada — fila | valor
  anterior | valor nuevo | fuente | confirmado/estimado.
- Comiteá ambos a este repo, en candidatos/ y logs/. No sobrescribas
  candidatos ni logs de corridas anteriores — se acumulan.

===== SI ESTÁS EN MODO CHAT (sesión de nivelación con Nicolás) =====
- Este es el único modo donde se edita BESS_POTENTIAL_CLIENTS_v2.xlsx y
  mapa_gaps_mercado.md de verdad.
- Al iniciar sesión: traer lo último del repo (Sync del conector de
  GitHub en Project Knowledge, o pedir que se clone el repo directo).
- Revisar los logs/ acumulados desde la última sesión, decidir línea por
  línea qué se aplica. Nunca aplicar un candidato completo sin revisión.
- Antes de reescribir el xlsx oficial, mostrar el diff propuesto (qué
  filas/celdas cambian y por qué) y esperar confirmación — regla
  diff-first, igual que en el resto del sistema.
- Aplicar lo aprobado al xlsx oficial con la skill de xlsx (SUM() en vez
  de hardcodear, data_only=False, recálculo post-edición).
- Actualizar mapa_gaps_mercado.md reflejando lo cerrado.
- Subir de vuelta al repo el xlsx oficial y el gap map, reemplazando las
  versiones anteriores.
```

## Notas operativas

- **Scheduled Tasks en Windows:** hay reportes de usuarios (no confirmados oficialmente por Anthropic) de que el scheduler de Cowork deja de disparar tareas recurrentes silenciosamente después de uso prolongado, recuperable solo con reinicio completo del sistema. Hasta tener varias corridas consecutivas sin fallas, chequear este repo cada semana para confirmar que el candidato+log se generó, en vez de asumir que corrió.
- **Crear la Scheduled Task desde el panel lateral "Scheduled"**, no con el comando `/schedule` — hay reportes de un bug conocido en Windows con el comando.
- **Primeras 3-4 corridas de Cowork:** revisar candidato + log con más rigor del necesario a largo plazo, para calibrar que las fuentes sean reales y no se mezclen tipos de dato antes de aliviar la revisión.

---
Última actualización: 11-08-2026.
