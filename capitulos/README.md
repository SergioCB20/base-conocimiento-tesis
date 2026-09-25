# capitulos/

Transcripción a Markdown de la tesis. Es la fuente de verdad editable; el `.docx` final de cada capítulo se genera solo después de que el autor valide su `.md` (ver `AGENTS.md`).

- **Fuente:** `20202117_SergioChumbimuni_LuisVives_E2.pdf` (raíz del repo), 100 páginas, fechado "Lima, Agosto, 2026".
- **Transcrito:** 2026-09-25.

| Archivo | Contenido | Páginas del PDF |
|---|---|---|
| `00-portada-e-indice.md` | Portada e índice | 1–3 |
| `01-generalidades.md` | Cap. 1: problemática, objetivos, resultados esperados, métodos (Tablas 1–5, Figura 1) | 4–20 |
| `02-marco-conceptual-teorico-legal.md` | Cap. 2: scoring, sesgo, métricas SPD/EOD/DI, métricas individuales, drift, trade-off, MLOps, contratos, RDF/OWL, marco legal | 20–33 |
| `03-estado-del-arte.md` | Cap. 3: revisión sistemática PICOC/PRISMA (Tablas 6–9, Figuras 2–3) | 33–52 |
| `04-diseno.md` | Cap. 4: C4 y Zonas, contratos C1/C2/C3, ontología OWL, discusión (Tablas 10–13, Figuras 4–9) | 53–80 |
| `05-implementacion.md` | Cap. 5: solo 5.1 y el inicio de 5.2.1 tienen texto; el resto son títulos | 81–83 |
| `06-referencias.md` | Referencias bibliográficas (orden del PDF) | 83–88 |
| `07-anexos.md` | Anexo A (enlace) y Anexo B: plan de proyecto (Tablas 10–12, Figura 10) | 88–100 |

## Convenciones de la transcripción

- **Base literal, correcciones editoriales y rediseño.** Además de las correcciones, el 2026-09-25 se aplicó el rediseño del producto aprobado (`estado/propuesta-diseno.md`) a los Caps. 1, 2, 4, 5 y al Anexo B (ver `CAMBIOS.md`, sección 5). **Desde esa fecha, los `.md` ya no reflejan el PDF E2**; son la versión de trabajo de la tesis.
- **Correcciones editoriales.** El texto partió de una transcripción literal del PDF. El 2026-09-25, a pedido del autor, se corrigieron citas y referencias, el marco legal, erratas y numeración, **sin tocar el producto de software**. Cada cambio está en `CAMBIOS.md`. El PDF E2 sigue siendo la referencia del texto original.
- **Fórmulas** transcritas a LaTeX (`$...$` y `$$...$$`) desde la imagen de cada página. La notación se mantiene (p. ej. `ε` como "pertenece a", `⊤` para umbrales).
- **Tablas** convertidas a tablas Markdown. En la tabla de clases OWL (Tabla 12) se unieron los nombres que el PDF corta en dos líneas (p. ej. `fair:GateExecutio n` → `fair:GateExecution`).
- **Código** (YAML, SPARQL, Turtle) en bloques con el lenguaje correcto. En el PDF los bloques aparecen etiquetados "Java" y "SQL"; se deja un comentario HTML indicándolo.
- **Figuras** extraídas del PDF a `imagenes/figNN-*.png` y enlazadas. Cuando la figura tiene texto relevante que no está en el cuerpo, se agrega una "Nota de transcripción" en cita (`>`), que **no es texto de la tesis**.
- **Cursivas:** se marcaron los términos en inglés más visibles; no se verificó cursiva por cursiva contra el PDF.
- Cada archivo empieza con un comentario HTML que indica las páginas de origen.

## Observaciones para revisión del autor

Detectadas al transcribir. **Actualización 2026-09-25:** se corrigieron las observaciones 1–7, 10–12 y 18, y las erratas de texto. Siguen abiertas las que afectan el producto o requieren decisión: 8, 9, 13–17 y las erratas dentro de figuras. El detalle está en `CAMBIOS.md` (sección 4). Las discrepancias de citas y referencias están en `estado/verificacion-citas.md`.

### Estructura y numeración
1. El **Índice** no incluye el Capítulo 5 y, bajo 4.4, lista "4.3.1. Descripción del resultado alcanzado" (en el cuerpo es 4.4.1).
2. Hay **dos secciones 3.6** ("Formulario de extracción de datos" y "Resultados de revisión").
3. Las tablas del **Anexo B** se numeran 10, 11 y 12, igual que las Tablas 10–12 del Capítulo 4.
4. En 4.3.4 dice "(ver Tabla 3)" para el indicador de R.E.2.2, pero ese indicador está en la **Tabla 2**.
5. En 4.2.3 se citan las Figuras 6, 7 y 8 como diagramas de componentes; la **Figura 9** (Zona 4) no se menciona.
6. En el Cap. 5 los resultados se nombran "R.3.1, R.3.2, R.3.3" en vez de "R.E.3.1…".

### Consistencia entre capítulos
7. **Rango temporal de la revisión:** CI-1 dice "entre el año 2019 y 2026", pero en el cribado y en la Figura 3 se excluyen los publicados "antes de 2020".
8. **Indicadores citados vs. Tabla 2:** los textos entre comillas atribuidos a los indicadores de R.E.2.1 (4.2.4), R.E.2.2 (4.3.4) y R.E.2.3 (4.4.4) no coinciden con lo que dice la Tabla 2 del Cap. 1.
9. **Diagrama de contenedores:** la Figura 2 (Cap. 3) y la Figura 5 (Cap. 4) son versiones distintas; la Figura 2 no tiene el "Canal de Linaje — MLflow". En la Figura 5 la Zona 3 dice "DVC - Evidently AI", mientras el texto de 4.2.1 dice "GitHub Actions, MLflow y Evidently AI".
10. **Nombre de la métrica:** la Zona 2 (4.2.1) habla de "DPD (Demographic Parity Difference)"; los contratos (2.1.3 y C3) usan "SPD"; el YAML usa `demographic_parity_difference`.
11. **Métrica del C2:** el contrato se define con información mutua condicional $I(X_{trans}; Z \mid Y)$, pero 4.5.3 habla de "correlación condicional".
12. **Clases de la ontología:** 4.5.3 menciona `fno:ExecutionRun` y `fno:QAGate`, que no aparecen en la Tabla 12 (que usa el prefijo `fair:` y la clase `fair:GateExecution`).
13. **Propiedades usadas pero no definidas:** el SPARQL y el Turtle usan `fair:hasDvcHash`, `fair:recordsCount`, `fair:contractId`, `fair:attributeName`, `fair:unprivilegedValue`, `fair:hasGateResult` y `fair:metricName`, que no están en la Tabla 13 ni en la lista de propiedades de datos. La Tabla 13 define `fair:hasOutcome`, que los ejemplos no usan.
14. **Dataset:** el ejemplo Turtle (4.4.3) usa un lote de **German Credit** (1000 registros). El Cap. 1 (O4), el Cap. 5 y el Anexo B hablan de datos de "una Fintech real", y el riesgo de convergencia del Anexo B menciona Adult Income y COMPAS. En todo el PDF no se nombra el dataset Davronov que menciona el README del repo.
15. **Local vs. nube:** 4.2.2 fija como restricción que "el 100% de los contenedores lógicos debían operar en un entorno local desconectado de internet", pero en el Anexo B la Viabilidad técnica dice que "el procesamiento principal se delegará a herramientas nativas de la nube" y los Recursos dicen que internet es "esencial para orquestar la canalización en la nube (GitHub Actions)".
16. **Alcance de las QA Gates:** el Anexo B (Alcance) dice que actúan "durante la fase de preprocesamiento de datos", pero C3 evalúa el modelo entrenado en la Zona 2.
17. **Cronograma:** la Tabla 11 del Anexo B suma **125 días**; el texto del cronograma dice "109 días de ejecución previstos".
18. En 1.3.1 (Pandera) se habla del "Contrato 1A"; en el resto de la tesis es "C1".

### Errores de tipeo que se dejaron como en el PDF
"auditalibilidad" (2.3.1, 4.4.2), "justabilidad" (2.1.4), "evaluén" y "comparativoa" (Figura 1), "el esquema defin." (1.3.1, Pandera), "cuatroalgoritmos" (Anexo B, Tabla 10), "IEE Explore" (Figura 3), "Reentranamiento" (Figura 5), "Stack Técnologico" (Tabla 9), "( la estructura" (5.1), ". ." al final del primer párrafo de 2.1.6, y "(Nguyen et al., 2025),." con coma y punto seguidos (3.6.3).
