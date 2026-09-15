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
