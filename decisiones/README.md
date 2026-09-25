# Decisiones (ADRs)

Registro de decisiones de arquitectura y metodología. Cada ADR sigue `template-adr.md`: contexto, opciones consideradas, decisión y consecuencias.

| ADR | Decisión | Estado | Fecha |
|---|---|---|---|
| [001](ADR-001-exclusion-marital-proxy-sex.md) | Excluir `Marital` por ser proxy de `Sex` | aceptada | 2026-09-16 |
| [002](ADR-002-csv-en-git-para-ci.md) | CSV en Git para el CI (workaround de DVC 3.67.1) | reemplazada por 009 (publicación del dataset) | 2026-09-19 |
| [003](ADR-003-datasets-davronov-principal-hmda-secundario.md) | Davronov como principal, HMDA como secundario; `Age_group` como segundo atributo protegido | aceptada | 2026-09-25 |
| [004](ADR-004-motor-de-contratos-generico.md) | Motor de contratos genérico con esquema declarativo común | aceptada | 2026-09-25 |
| [005](ADR-005-remediacion-explicita-en-c3.md) | Remediación explícita en el C3 (`ThresholdOptimizer`); DI direccional o simétrico | aceptada | 2026-09-25 |
| [006](ADR-006-c2-por-transformador-con-auc.md) | C2 por transformador con AUC de un clasificador auxiliar | aceptada (umbrales por calibrar) | 2026-09-25 |
| [007](ADR-007-trazabilidad-sin-interpretme.md) | Trazabilidad MLflow → RDFLib con PROV-O/DQV/SHACL, sin InterpretME | aceptada | 2026-09-25 |
| [008](ADR-008-bootstrap-en-las-compuertas.md) | Decisión de las compuertas con IC bootstrap | aceptada | 2026-09-25 |
| [009](ADR-009-repositorios-privados-por-licencia.md) | Repositorios privados y ejecución "reproducible local y en CI" | aceptada | 2026-09-25 |

Contexto completo del rediseño: `estado/propuesta-diseno.md` y `estado/implementacion-vs-tesis.md`.
