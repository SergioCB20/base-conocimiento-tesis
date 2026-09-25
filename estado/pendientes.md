# Pendientes

Documento vivo: marcar `[x]` al completar y mover detalles a la bitácora.

## Repo / base de conocimiento
- [x] Transcribir el PDF de la tesis a `capitulos/NN-nombre.md`. Hecho el 2026-09-25 desde `20202117_SergioChumbimuni_LuisVives_E2.pdf` (100 pp.): archivos `00` a `07` y figuras en `imagenes/`. Convenciones en `capitulos/README.md`.
- [ ] **Validar cada `capitulos/*.md` contra el PDF** (el autor). Hasta entonces no se genera ningún `.docx`.
- [ ] Revisar las 18 observaciones de consistencia de `capitulos/README.md` y decidir cuáles corregir en la tesis.
- [x] Verificar citas contra la bibliografía. Reporte en `estado/verificacion-citas.md`.
- [ ] Corregir en la tesis las discrepancias del reporte de citas: 3 citas sin referencia (Wagner 2024, Zafar et al. 2019, Anders et al. 2020), autor de "Li et al., 2023" (es Ji et al.), año de DispaRisk, autoría de SageMaker Model Monitor, cita truncada "(Nguyen, 20 Nguyen et al., 2025)", entre otras.
- [ ] Decidir qué hacer con los 2 PDFs sin cita en el texto: `(Un) Fairness Along the AI Pipeline…` y `Preeclampsia predictor…` (no borrar sin confirmar).
- [x] Resolver las 25 referencias sin ficha (skill `resolver-referencias`): 9 PDFs agregados y 25 fichas nuevas en `index.md`. Hardt (2016) y Bartlett (2022, working paper 2019) ya tienen PDF.
- [x] Confirmar a mano las 7 fuentes no verificadas (W10–W16): completadas con los archivos del autor; Nguyen et al. (2025) confirmada como inexistente.
- [x] Reescritura editorial de los capítulos (citas, marco legal, numeración, erratas) sin tocar el producto de software. Detalle en `capitulos/CAMBIOS.md`.
- [ ] **Revisar `capitulos/CAMBIOS.md`**, sobre todo: CI-1 (2019 → 2020), la nueva sección 2.3.4 (D.S. 115-2025-PCM) y la reescritura de 2.3.2 (CFPB/ECOA).
- [ ] Resolver los 2 PENDIENTE del Cap. 2: fuente oficial de la fórmula ECL y fechas de aplicación del Reglamento (UE) 2026/1744.
- [ ] Decidir los temas abiertos de `CAMBIOS.md` §4: German Credit vs. Davronov en el ejemplo Turtle, local vs. nube, indicadores de 4.2.4/4.3.4/4.4.4 vs. Tabla 2, cronograma 109 vs. 125 días, Lin et al. sin cita, y rehacer las Figuras 2 y 5.
- [ ] Decidir cómo tratar en la tesis la **Circular CFPB 2023-03, retirada el 12-may-2025**, y la **modificación del AI Act por el Reglamento (UE) 2026/1744** (ver `estado/verificacion-citas.md`, sección H).
- [ ] Agregar PDFs o fuentes del dataset real (Davronov, Kaggle), Fairlearn / `ThresholdOptimizer` y DVC si se van a citar en el Cap. 5.
- [x] Escribir ADRs en `decisiones/` para las decisiones ya tomadas (hecho el 2026-09-25: ADR-001, 002, 003 y 005; ver `decisiones/README.md`):
  - [x] Elección del dataset Davronov frente a German Credit, South German Credit, LendingClub y HMDA.
  - [x] Exclusión de `Marital` por ser proxy de `Sex` (resultado del QA Gate 2).
  - [x] Mitigación con `ThresholdOptimizer` (`equalized_odds`) en el QA Gate 3.
  - [x] CSV versionado en Git solo para CI por el bug de DVC 3.67.1 en clones limpios.
- [ ] Corregir en `AGENTS.md` la ruta del índice: menciona `bibliografia/docs/index.md` y también `bibliografia/index.md` (el archivo real está en `bibliografia/index.md`).
- [ ] Decidir dónde queda el PDF de la tesis (hoy está en la raíz del repo).

## Tesis
- [ ] Redactar el Capítulo 5 (Implementación): en E2 solo existen 5.1 y el inicio de 5.2.1. El README ya documenta los resultados de QA Gates 1–3 y CI/CD que pueden alimentarlo.
- [ ] Actualizar el script de la exposición (15 min) y la preparación de preguntas del jurado con el estado final de la implementación.
- [ ] Generar el `.docx` de cada capítulo **solo después** de que el usuario valide su `.md`.

## Rediseño aprobado (2026-09-25)
- [x] Aplicar `estado/propuesta-diseno.md` a los capítulos (Caps. 1, 2, 4, 5 y Anexo B).
- [ ] Revisar los capítulos reescritos, sobre todo el Cap. 4 completo y 2.1.7.
- [x] Escribir los ADRs del rediseño (ADR-003 a ADR-009).
- [ ] Redibujar las Figuras 4–9 en Lucidchart a partir de los diagramas Mermaid; reemplazar o quitar la Figura 2 del Cap. 3.
- [ ] Poner en privado los repositorios de GitHub y DagsHub; decidir si se limpia el CSV del historial (con respaldo).
- [ ] Implementar el rediseño en el código (motor de contratos, C2 por paso, C3 con remediación y bootstrap, C4, MLflow, exportador RDF) y reemplazar los valores ilustrativos del Cap. 4.
- [ ] Calibrar los umbrales del C2 (0,60 y 0,02) con el caso `Marital`.
