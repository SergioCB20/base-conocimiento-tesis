# AGENTS.md

Instrucciones para cualquier agente de IA (Claude Code, Cursor, u otro) que trabaje en este repositorio. Léeme primero, antes de tocar cualquier archivo.

## Qué es este repo

Base de conocimiento y espacio de trabajo para una tesis de pregrado sobre **validación de fairness en MLOps**, con arquitectura CI/CD de QA Gates distribuidos, trazabilidad semántica (RDF/OWL) y un caso de estudio de credit scoring (dataset Davronov, Kaggle). El objetivo de este repo NO es solo almacenar documentos: es que cualquier agente pueda retomar el trabajo con contexto completo, sin depender de una conversación anterior.

## Qué leer primero, en este orden

1. `README.md` — resumen ejecutivo y estado actual.
2. `estado/` — bitácora y pendientes (qué se hizo último, qué falta).
3. `bibliografia/docs/index.md` — catálogo de fuentes citadas.
4. Solo después, entrar a `capitulos/`, `decisiones/` o `defensa/` según la tarea pedida.

## Estructura del repo

```
Base de conocimiento/
├── bibliografia/
│   ├── docs/           # PDFs originales de las fuentes citadas
│   └── index.md         # Catálogo: metadatos + resumen corto por fuente
├── capitulos/            # Transcripción .md de cada capítulo del PDF de tesis (80 pp.)
├── decisiones/           # ADRs — por qué se tomó cada decisión de diseño/metodología
├── defensa/
│   ├── expo final/       # Material para la exposición final
│   └── preguntas informante/  # Prep de preguntas del jurado/informante
├── estado/               # Bitácora cronológica + pendientes
├── imagenes/             # Diagramas, capturas, figuras usadas en la tesis
├── skills/                # Instrucciones reutilizables (ej: cómo generar un ADR, formato de citas)
├── AGENTS.md
└── README.md
```

## Tareas típicas y cómo hacerlas

### 1. Transcribir el PDF de la tesis a `capitulos/*.md`
- Fuente: PDF completo de 80 páginas (se pasa directo al agente, sin conversión previa).
- Un archivo `.md` por capítulo, nombrado `NN-nombre-capitulo.md` (ej: `03-estado-del-arte.md`, `04-diseno.md`).
- La transcripción debe preservar el contenido técnico exacto (fórmulas, nombres de métricas como SPD/EOD/DI, nombres de contratos C1/C2/C3, etc.) — no resumir, no parafrasear en esta etapa. El objetivo es tener el contenido en un formato editable.
- Una vez que el contenido de un capítulo esté validado y correcto en `.md`, ese capítulo se redacta a `.docx` como entregable final (usar la skill de docx). El `.md` sigue siendo la fuente de verdad editable; el `.docx` es el output final.

### 2. Verificar que las fuentes citadas estén en la bibliografía
- Buscar patrones de cita (ej: `(Autor, año)`, `[Autor et al., año]`) dentro de los archivos en `capitulos/*.md`.
- Comparar cada cita encontrada contra las entradas de `bibliografia/index.md`.
- Reportar: (a) citas en los capítulos sin fuente correspondiente en bibliografía, (b) PDFs en `bibliografia/docs/` que no están citados en ningún capítulo (candidatos a eliminar o marcar como lectura de contexto, no citada).
- No asumir que una cita "se parece" a una fuente — si el nombre de autor/año no calza exacto, marcarlo como discrepancia a revisar manualmente, no autocorregir.

### 3. Llenar `bibliografia/index.md`
- Por cada PDF en `bibliografia/docs/`: título, autor(es), año, y un resumen corto (2-4 líneas) que capture qué aporta esa fuente a la tesis.
- El resumen debe ser útil para búsqueda futura: pensar en la pregunta "¿qué fuente respalda la decisión X?" y que el resumen ayude a responderla sin abrir el PDF.
- Si es posible, taguear con la sección/decisión de la tesis a la que aplica cada fuente (ej: `#QA-Gate-3`, `#fairness-metrics`, `#trazabilidad-RDF`).

### 4. Actualizar `estado/bitacora.md`
- Al final de cada sesión de trabajo relevante, añadir una entrada corta con fecha: qué se hizo, qué decisiones se tomaron, qué quedó pendiente.
- No reescribir entradas pasadas — solo añadir. Es un log, no un documento vivo.

## Convenciones

- Todo el contenido técnico y de tesis está en español.
- Formato de fecha en bitácora: `YYYY-MM-DD`.
- Los ADRs en `decisiones/` siguen la plantilla `template-adr.md` (crear si no existe, con: contexto, opciones consideradas, decisión, consecuencias).
- No modificar los PDFs originales en `bibliografia/docs/` — son fuente primaria, solo lectura.
- No borrar contenido de `estado/bitacora.md` — es append-only.

## Qué NO hacer sin confirmar con el usuario

- No generar el `.docx` final de un capítulo hasta que el usuario confirme que el `.md` de ese capítulo está validado.
- No eliminar PDFs de `bibliografia/docs/` aunque parezcan no citados — solo reportarlo.
- No inventar resúmenes o metadatos de fuentes que no se puedan verificar del PDF real.
