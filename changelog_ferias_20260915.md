# Changelog — Exhibition-Forum_Calendar.xlsx — 2026-09-15

Investigación de ferias, congresos y seminarios de energía y almacenamiento (BESS)
en Chile, Argentina, Brasil (foco reforzado), Colombia, Perú y Uruguay. Cruzado
contra el archivo actual (26 filas previas) antes de agregar o modificar filas,
según instrucción del CLAUDE.md para este archivo.

## Filas modificadas (2)

| Fila (evento) | Cambio | Motivo | Fuente |
|---|---|---|---|
| Brazil Windpower 2026 | Description actualizada con pricing de 3er lote (BRL, delegate/visitor); Status pasa de "Not Confirmed (registration not yet open... waitlist only)" a "Registration Open (3rd batch pricing, as of 2026-09-15)" | Registro se abrió desde la última corrida (2026-08-17) | brazilwindpower.com.br/en/registration, accessed 2026-09-15 |
| FENIBAT + FENILITIO 2027 | Description y Price actualizados: evento gratuito solo para industria (sujeto a aprobación); Status aclara que la apertura de inscripciones estaba programada para 2026-09-15 pero la página seguía mostrando "Closed" al momento de la consulta | Fecha de apertura de inscripción ya alcanzada, se verificó el estado real | fenibat.com/en/inscricao, accessed 2026-09-15 |

## Filas nuevas (6)

| Evento | País | Fecha | Fuente |
|---|---|---|---|
| Energyear Argentina 2026 | Argentina | 16-17 sept 2026, Buenos Aires | energyear.com/en/argentina, energyear.com/en/eventos-2026, accessed 2026-09-15 |
| CIGRE Argentina — Seminario BESS 2026 | Argentina | 27-28 oct 2026, Buenos Aires | sites.google.com/site/cigrearg (CIGRE Argentina), accessed 2026-09-15 |
| Forum Energy Storage Brasil (6th Edition) | Brasil | 18-19 nov 2026, São Paulo | saopaulo.energystoragebrasil.com, accessed 2026-09-15 |
| The smarter E South America 2027 | Brasil | 24-26 ago 2027, São Paulo | thesmartere.com.br, accessed 2026-09-15 |
| 18° Congreso Internacional de Energía (Congreso Energía Perú) | Perú | 11-12 mar 2027, Lima | congresoenergiaperu.com, accessed 2026-09-15 |
| XVI CLAGTEE 2026 | Chile | 28-30 oct 2026, Santiago | eie.pucv.cl / clagtee2026.org, accessed 2026-09-15 |

**Corrección respecto a la primera versión de este PR:** la primera pasada de búsqueda
no encontró el circuito internacional Energyear (activo en LATAM desde 2013, con
ediciones propias por país) — quedó fuera de los términos de búsqueda usados. Al
revisarlo se detectó que Energyear Argentina 2026 se realiza el 16-17 de septiembre de
2026 (esta semana respecto a la fecha de esta corrida), por lo que se agregó. El resto
del tour Energyear LATAM 2026 ya visible en energyear.com/en/eventos-2026 (Brasil 4-5
feb, Perú 9 mar, Chile 11-12 mar, Colombia 6-7 may, Caribe 8-9 jul, Centroamérica 14-15
jul) ya había ocurrido para la fecha de esta corrida y no se agrega como fila nueva,
según la regla de eventos pasados del CLAUDE.md. No se publicó fecha 2027 para esas
ediciones al momento de la consulta.

Todas las filas nuevas siguen el formato exacto de columnas (Name | Date | Location |
Description | Price [USD] | Status) y el estilo de celda (fuente, wrap, alto de fila,
bordes) copiado de una fila de dato existente. Ningún precio en USD estaba
públicamente disponible para las filas nuevas — se marcó "Not Confirmed" en vez de
estimarlo o dejarlo vacío, y el detalle en moneda local (cuando existía) se documentó
en Description.

## Eventos evaluados y descartados (no agregados)

- **Perú Energía 2026 / Expo Energía Perú 2026** (17-18 jun 2026, Lima): mismo evento
  bajo dos nombres; fecha ya pasada respecto a esta corrida (hoy 2026-09-15) — no se
  agrega como fila nueva, según regla del CLAUDE.md.
- **XII Congreso LATAM Renovables (AUDER, Uruguay)** (28-29 jul 2026, Montevideo):
  fecha ya pasada; el presidente de AUDER adelantó que habrá una próxima edición pero
  sin fecha publicada todavía — no hay dato confirmable para anotar como próxima fecha
  estimada.
- **Trinasolar TrinaDay Argentina 2026 / AHK Argentina seminario BESS**: cobertura de
  prensa solo menciona que el evento ocurrió o que "se realizará", sin fecha, lugar ni
  modalidad de registro verificables — no se pudo confirmar con fuente razonable.
- **Chile Carbon Forum 2026**: foco en mercados de carbono/acción climática, no en
  energía/BESS — fuera de alcance del archivo.

## Gap explícito — Uruguay

No se identificó ningún evento nuevo de energía/BESS en Uruguay con fecha futura
confirmable (posterior a 2026-09-15) más allá de lo ya cargado en el archivo (V
Simposio CIER, 9-11 sept 2026, ya pasado a la fecha de esta corrida). Se buscó
específicamente vía UTE, MIEM, ADME, AUDER, Expo Prado y congresos de hidrógeno
verde/renovables, sin resultado. Pendiente revisar en la próxima corrida.

## Nota sobre alcance no estructural

No se modificaron las columnas ni el formato de la plantilla (Name | Date | Location |
Description | Price [USD] | Status), tal como indica el CLAUDE.md. No se creó copia en
`/historial/` para este archivo, dado que la instrucción del repo excluye explícitamente
a Exhibition-Forum_Calendar.xlsx del patrón de historial fechado.

---

# Corrida adicional — 2026-09-22: completar Description vacías

Se pidió puntualmente completar las celdas de la columna Description que habían
quedado vacías (las 13 filas originales del archivo, cargadas antes de esta serie de
corridas, nunca tuvieron Description). Ninguna fecha, precio ni status se modificó en
esta pasada — solo se agregó texto en Description, cada uno con fuente y fecha de
acceso, siguiendo la regla de "nunca dejar vacío sin explicación" del CLAUDE.md.

| Fila (evento) | Fuente(s) citada(s) en Description |
|---|---|
| Energy Storage Latin America 5th Edition (Chile) | storagelatam.solarenergyevents.com |
| Future Energy Summit — Santiago (FES Chile) | futurenergysummit.com |
| Expo Energía (Chile) | expoenergia.cl, acera.cl |
| Encuentro energías Renovables ACERA (Chile) | acera.cl, ticketmaster.cl |
| Argentina Energy Week Summit & Exhibition | ambito.com, econojournal.com.ar |
| Expo Eficiencia Energética (Argentina) | baferial.com, cpic.org.ar |
| Intersolar Exhibition (Brasil) | intersolar.net.br |
| Future Energy Summit — São Paulo (FES Brasil) | strategicenergy.eu, futurenergysummit.com |
| Expo Solar (Colombia) | feriaexposolar.com, eltiempo.com |
| Cumbre del Petróleo, Gas y Energía (Colombia) | campetrol.org, neventum.com |
| Congreso Almacenamiento de Energía (Colombia) | congresoalmacenamiento.fise.co |
| Future Energy Summit — Bogotá (FES Colombia) | futurenergysummit.com, energiaestrategica.com |
| Future Energy Summit — Lima (FES Perú) | energiaestrategica.com |

Todas las fuentes fueron consultadas el 2026-09-22. Dos notas honestas sobre calidad de
dato:

- **FES Brasil** (fila "Future Energy Summit", São Paulo, 5 nov 2026): es una parada
  nueva del tour 2026 de Future Energy Summit; no se encontró agenda específica
  publicada para São Paulo al momento de la consulta — se indicó explícitamente en la
  Description en vez de inventar detalle.
- **FES Colombia** (fila "Future Energy Summit", Bogotá, 1 oct 2026): las notas de
  prensa más específicas encontradas (quinta edición, Hotel Hilton, 21-22 oct) no
  coinciden en fecha exacta con la fila del archivo (1 oct 2026); se optó por una
  Description genérica de la franquicia FES Colombia en vez de citar cifras/fecha de
  una edición que podría no ser la misma — no se tocó la columna Date de la fila.

---

# Reconciliación — 2026-09-22: merge con la corrida paralela (PR #7) y ajuste a CLAUDE.md

Mientras esta rama (`claude/trusting-lamport-uz2qbg`) estaba en curso, Nicolás mergeó a
`main` otra corrida paralela (branch `claude/amazing-ride-8yfohn`, PR #7: "12 eventos
nuevos + 5 actualizaciones") y luego actualizó `CLAUDE.md` con una corrección
importante: **la columna Status es el estado de asistencia de BYD frente al evento
(Inscrito, Solicitado, No asistiremos, etc.), la mantiene Nicolás a mano, y la rutina
nunca debe escribir ni inferir un valor ahí.** Eso generó conflicto binario al intentar
subir esta rama. Resolución aplicada:

1. Se tomó la versión de `main` (38 filas, con Description ya completa en filas 15-38 y
   Status/Price actualizados con más detalle que mi propia corrida) como base.
2. Se le sumaron las 13 Description que esta corrida investigó para las filas
   originales (2-14), que `main` seguía teniendo vacías.
3. Se agregaron 5 de mis 6 filas nuevas exclusivas (CIGRE Argentina BESS 2026, Forum
   Energy Storage Brasil, The smarter E South America 2027, XVI CLAGTEE 2026, Energyear
   Argentina 2026) — ninguna se solapaba con las filas nuevas de la otra corrida.
4. **Se descartó mi fila "18 Congreso Internacional de Energía (Congreso Energía
   Perú)"**: comparte fecha y lugar exactos (11-12 marzo 2027, Country Club Lima Hotel)
   con la fila "CIIT Perú 2027 (CIIT Latam Congress)" que ya trajo la otra corrida.
   Verifiqué CIIT Latam Congress por separado (ciitlatamcongress.com: 9ª edición,
   organizador propio, foco en innovación tecnológica para minería/energía/industria) y
   es un evento real y distinto en el papel — pero dos congresos no relacionados en el
   mismo hotel, mismos dos días, es muy poco probable. Es más probable que mi búsqueda
   original haya mezclado resultados de "congresoenergiaperu.com" con los de
   "ciitlatamcongress.com" en la misma consulta. Ante la duda, se prefirió no duplicar
   información potencialmente errónea (principio de cero información errónea del
   CLAUDE.md) y se dejó solo la versión ya verificada por la otra corrida.
5. **Se vació la columna Status de las 5 filas nuevas agregadas en esta reconciliación**
   (antes tenían texto tipo "Registration Open" / "Not Confirmed (...)"), para cumplir
   la nueva regla de CLAUDE.md. Ese texto de estado de registro del evento (no de
   asistencia de BYD) quedó conservado en la columna Description de cada fila.
6. No se tocó el Status de ninguna fila preexistente (2-38) — se conservaron tal cual
   estaban en `main`.

## Consultas usadas por país (esta corrida, 2026-09-15 / 2026-09-22)

- **Chile**: "feria congreso energía almacenamiento baterías BESS Chile 2027",
  "Future Energy Summit Chile FES Chile 2026", "Expo Energía Santiago Chile noviembre
  2026", "ACERA Encuentro energías renovables diciembre 2026", "CLAGTEE 2026 Santiago
  Chile fecha precio inscripción".
- **Argentina**: "congreso energía renovable almacenamiento Argentina 2026 2027 feria",
  "CIGRE Argentina BESS 2026 seminario", "AHK Argentina seminario almacenamiento
  energético BESS 2026", "Argentina Energy Week 2026 Buenos Aires", "Expo Eficiencia
  Energética Argentina 2026", "Energyear Argentina 2026 septiembre fecha".
- **Brasil** (foco reforzado): "feira congresso energia armazenamento baterias Brasil
  2026", "feira storage summit Brasil 2027", "Brazil Windpower 2026 registration",
  "Fórum Energy Storage Brasil 2026", "smarter E South America 2027 São Paulo",
  "Intersolar South America São Paulo 2026", "FENIBAT FENILITIO 2027 inscripción".
- **Colombia**: "feria congreso energía almacenamiento Colombia 2026 2027", "Congreso
  Almacenamiento de Energía FISE Medellín", "Expo Solar Colombia Bogotá 2026",
  "Cumbre del Petróleo, Gas y Energía Cartagena 2026", "Future Energy Summit Colombia
  FES Bogotá 2026".
- **Perú**: "feria congreso energía almacenamiento Perú 2026 2027", "Congreso Energía
  Perú 2027 precio", "Future Energy Summit Perú FES Lima 2026" (nota: la fila que esta
  búsqueda generó para Perú terminó descartada por posible duplicado, ver arriba).
- **Uruguay**: "Uruguay feria congreso energía renovable 2026 2027 UTE MIEM ADME",
  "Uruguay energy storage BESS seminario congreso baterías", "Semana de la Energía
  Uruguay / Expo Prado / CADE", "Latam Renovables Uruguay AUDER próxima edición" — sin
  resultado nuevo verificable; gap explícito documentado arriba.

