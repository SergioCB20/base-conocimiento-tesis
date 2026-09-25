# Bitácora

Log append-only. No reescribir entradas pasadas; solo añadir al final.

---

## 2026-09-25

**Qué se hizo**
- Revisión del estado del repo: `capitulos/`, `estado/` y `decisiones/` estaban vacíos; `bibliografia/index.md` vacío.
- Se llenó `bibliografia/index.md` con las 16 fuentes de `bibliografia/docs/`: título, autores, año, venue/DOI, resumen de 2 a 4 líneas y tags propuestos. Metadatos extraídos del texto de cada PDF (pdftotext).
- Se creó `estado/pendientes.md` y `decisiones/template-adr.md`.

**Decisiones**
- Para los preprints (SageMaker Model Monitor, Causality-Aided Trade-off, DispaRisk, Stress-Testing/Savage) se registra solo la versión arXiv, porque el PDF no indica el venue final. No se supuso el venue.
- Los tags de cada fuente son una propuesta; se confirmarán al cruzar con los capítulos.

**Pendiente**
- Falta el PDF de la tesis (80 pp.) para transcribir `capitulos/` y, después, verificar las citas (Tareas 1 y 2 de `AGENTS.md`).
- Durante la sesión se agregó a la raíz del repo el PDF de la tesis (`20202117_SergioChumbimuni_LuisVives_E2.pdf`, 80 pp.), así que la transcripción ya no está bloqueada. Aún no se transcribe.

---

## 2026-09-25 (continuación)

**Qué se hizo**
- Se transcribió el PDF de la tesis (E2, 100 pp.) a `capitulos/00` a `07`: portada/índice, Caps. 1–5, referencias y anexos. Texto literal; fórmulas en LaTeX revisadas contra la imagen de cada página; tablas en Markdown; YAML/SPARQL/Turtle en bloques de código.
- Se extrajeron las 10 figuras del PDF a `imagenes/figNN-*.png` y se enlazaron desde los capítulos.
- Chequeo automático de cobertura: cada fragmento de 5 palabras del PDF aparece en los `.md`, salvo cortes de celdas de tabla y fórmulas (estas se revisaron visualmente).
- Se hizo la verificación de citas (Tarea 2): `estado/verificacion-citas.md`.
- `capitulos/README.md` documenta convenciones y 18 inconsistencias internas del PDF (no corregidas).

**Decisiones**
- No se corrigió ningún error del PDF en los `.md` (tipeos, citas truncadas, numeración repetida): se listan para que el autor decida.
- El Cap. 5 se transcribió aunque no está en el índice del PDF; casi todo son títulos vacíos.
- Para renderizar páginas y extraer figuras se usó PyMuPDF en un entorno virtual temporal fuera del repo.

**Pendiente**
- Validación de los `.md` por el autor antes de generar cualquier `.docx`.
- Correcciones de citas y de consistencia en la tesis (ver `estado/pendientes.md`).

---

## 2026-09-25 (skill resolver-referencias)

**Qué se hizo**
- Se aplicó `skills/resolver-referencias/SKILL.md` a las 25 referencias sin ficha en `bibliografia/index.md`.
- Se descargaron 9 PDFs de fuentes abiertas legítimas (arXiv, PMLR, SpringerOpen, IJAIDSML, Berkeley Haas, Banco Mundial) a `bibliografia/docs/` y se verificó el contenido de cada uno.
- Se agregaron 25 fichas a `index.md`: 17–25 con PDF, W1–W9 verificadas en fuente oficial o abstract, y W10–W16 sin verificar o verificadas solo en parte. No se modificaron las 16 fichas existentes.
- Nuevos hallazgos agregados a `estado/verificacion-citas.md` (sección H).

**Decisiones**
- No se usaron copias de terceros de dudosa licencia (IEEE en un servidor ajeno, libro en Internet Archive).
- Ante bloqueos (Cloudflare, 403) no se intentó esquivarlos; esas fuentes quedan como pendientes manuales.

**Pendiente**
- Confirmación manual de W10–W16, en especial Nguyen et al. (2025).
- Decidir cómo tratar en la tesis la Circular CFPB retirada y la modificación del AI Act.

---

## 2026-09-25 (fuentes aportadas por el autor)

**Qué se hizo**
- El autor agregó a `bibliografia/docs/` los PDF de ISO/IEC 42001 (vista previa), D.S. 115-2025-PCM, Petticrew & Roberts y Dhaenens, más el HTML de Kästner, y el enlace de IBM. Se leyeron y se actualizaron las fichas W10–W16 de `index.md`.
- El autor confirmó que Nguyen et al. (2025, ICSE) no existe.
- Hallazgos agregados a `estado/verificacion-citas.md` (sección I).

**Pendiente**
- Corregir en la tesis la cita de Nguyen et al. (2025) y decidir si se mantiene Dhaenens (2024).
- Considerar citar el Art. 24.1(g) del D.S. 115-2025-PCM en el marco legal.

---

## 2026-09-25 (reescritura editorial de capítulos)

**Qué se hizo**
- A pedido del autor, se corrigieron los `capitulos/*.md` en todo lo que no afecta el producto de software: citas y referencias (Nguyen 2025 → Nguyen 2024; Dhaenens → Stoyanovich; IBM, AWS, Li, Vasquez, Kagal, Wagner, Zafar, Anders), marco legal (CFPB retirada → ECOA/Reg B; AI Act Art. 27 y Reglamento 2026/1744; ISO 42001 según su texto; nueva sección 2.3.4 sobre el D.S. 115-2025-PCM), numeración (3.6 → 3.7/3.8, tablas del Anexo B, índice) y erratas.
- Se verificaron fuentes nuevas antes de usarlas: 29 C.F.R. § 1607.4(D) (regla de los cuatro quintos), AI Act Art. 27, Ji et al. (CDS) y Reda et al. (umbral de 0.1).
- Registro completo en `capitulos/CAMBIOS.md`. Chequeo automático: todas las citas tienen referencia; solo Lin et al. queda en referencias sin cita.

**Decisiones**
- No se modificaron la arquitectura, los contratos C1–C3 y sus umbrales, la ontología, el stack, el dataset ni la decisión local/nube.
- La fórmula ECL y las fechas del Reglamento 2026/1744 quedaron como PENDIENTE en el texto por falta de una fuente oficial legible.

**Pendiente**
- Revisión del autor de `CAMBIOS.md`, en especial el cambio de CI-1 (2019 → 2020) y la sección 2.3.4 nueva.
- Temas abiertos de `CAMBIOS.md`, sección 4.

---

## 2026-09-25 (revisión de la implementación)

**Qué se hizo**
- Se revisó en modo solo lectura el proyecto `Tesis/Proyecto/mlops-fairness-scoring` (commit f3977fa) y se contrastó con los Caps. 4 y 5. Resultado en `estado/implementacion-vs-tesis.md`.
- Dudas resueltas: el dataset es Davronov (8 707 registros); label=1 es buen pagador (92,3%); CI en GitHub Actions y remotos DVC en DagsHub/Drive, es decir, no es 100% local.

**Pendiente**
- Decidir si se ajusta el texto del Cap. 4 o el código en las diferencias de los contratos (esquema YAML, C2 sin comparación pre/post, DI mín/máx, mitigación con ThresholdOptimizer).
- Documentar la codificación de Sex (1/2) y cuál es el grupo no privilegiado.

---

## 2026-09-25 (propuesta de rediseño)

- Se redactó `estado/propuesta-diseno.md`: motor de contratos genérico, C2 por paso, C3 con remediación y bootstrap, C4 de deriva, Zona 4 con MLflow → RDFLib (sin InterpretME), Davronov + HMDA, `Age_group` como segundo atributo protegido (<25: 7,5%, brecha de 9 pp en la etiqueta) y evaluación de O4 con escenarios E0–E6.
- El autor confirmó que los repositorios de GitHub y DagsHub son públicos y que los puede hacer privados (la licencia del dataset es `copyright-authors`).
- Pendiente: aprobación del autor (sección 13 de la propuesta); luego ADRs y cambios en los capítulos.

---

## 2026-09-25 (rediseño aplicado a los capítulos)

- El autor aprobó `estado/propuesta-diseno.md`. Se reescribieron el Cap. 4 (completo), el Cap. 1 (1.2.2 en adelante), el Cap. 2 (2.1.3, 2.1.7 nueva, 2.2.3, 2.3.1), el Cap. 5 (5.1 y títulos) y el Anexo B. Se agregaron 10 referencias verificadas (W3C PROV-O/DQV/SHACL, Fairlearn, MLflow, bootstrap, Noy & McGuinness, dataset Davronov, Giang Thi Thu et al., FFIEC).
- Chequeos: todas las citas tienen referencia; las citas textuales del O2 y de los indicadores coinciden con el Cap. 1; las citas textuales externas se verificaron contra la fuente.
- Detalle y pendientes en `capitulos/CAMBIOS.md`, sección 5.

---

## 2026-09-25 (ADRs)

- Se escribieron 9 ADRs en `decisiones/` (índice en `decisiones/README.md`): 001 exclusión de Marital, 002 CSV en Git (reemplazada por 009), 003 datasets, 004 motor de contratos, 005 remediación en C3, 006 C2 por transformador con AUC, 007 trazabilidad sin InterpretME, 008 bootstrap y 009 repositorios privados. Las fechas de 001 y 002 provienen de los commits del proyecto.

---

## 2026-09-25 (v2 en Word)

- A pedido del autor, se generó `informes/Entrega 2/20202117_SergioChumbimuni_LuisVives_E2_v2.docx` a partir de `capitulos/*.md` (pandoc + post-proceso con python-docx). Es un borrador de revisión: excepción explícita a la regla de AGENTS.md de generar el .docx solo tras validar los .md.
- Formato replicado de la v1 (A4, Times New Roman 14, márgenes de 1"). Fórmulas como ecuaciones nativas de Word; índice como campo automático; PENDIENTES visibles en rojo; notas de transcripción omitidas; Figuras 4–9 provisionales desde Mermaid. Pasa la validación de esquema OOXML.
- Script y recursos para regenerarlo: `informes/Entrega 2/fuente/`. Los diagramas Mermaid de las Figuras 6–9 se pasaron a orientación vertical (TB) también en `capitulos/04-diseno.md`.
