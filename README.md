# Tesis: Validación de Fairness en MLOps

## Objetivo

Diseño e implementación de un sistema de validación de fairness integrado al ciclo CI/CD de un pipeline de Machine Learning, con QA Gates distribuidos y trazabilidad semántica (RDF/OWL), validado sobre un caso de estudio de credit scoring.

## Alcance

La validación está delimitada al contexto de **credit scoring**, usando el dataset Davronov (Kaggle, fintech Asia Central, 2021) como caso de estudio, tras comparar alternativas como German Credit, South German Credit, LendingClub y HMDA.

## Arquitectura (resumen)

- Modelo C4 (contexto / contenedores / componentes), organizado en **4 Zonas**.
- **Contratos de Equidad** (C1, C2, C3) especificados en YAML, cada uno como QA Gate del pipeline.
- **Ontología OWL de Fairness** para trazabilidad semántica: clases, propiedades, ejemplos en Turtle y consultas SPARQL.
- 12+ herramientas integradas a lo largo del pipeline.

## Estado actual

- **QA Gate 1 (Contrato C1)** — ✅ implementado, todos los tests pasan.
- **QA Gate 2 (Contrato C2)** — ✅ implementado. Detectó leakage indirecto real: `Marital` era proxy casi perfecto de `Sex` (6/7 categorías con separación 100%). Resuelto excluyendo `Marital` del pipeline de features.
- **QA Gate 3 (Contrato C3)** — ✅ implementado. El modelo base (regresión logística) amplificaba ~6-7x la disparidad presente en el label real (2.8pp → 18pp en predicciones). Mitigado con `ThresholdOptimizer` de Fairlearn (`equalized_odds`); los 3 tests pasan tras la corrección.
- **CI/CD (GitHub Actions)** — ✅ pipeline corriendo en verde (QA Gates 1, 2, 3 base y 3 mitigado). Se documentó un bug reproducible de DVC 3.67.1 en clones limpios; solución pragmática: CSV comprometido directo en Git solo para CI, manteniendo DVC en el flujo local.
- **Redacción** — Capítulo 4 (Diseño, O2) ya redactado. En proceso: migración de capítulos del PDF original a este repo (`capitulos/`) para facilitar edición asistida por IA.
- **Defensa** — Script de exposición (15 min) y prep de preguntas del jurado ya trabajados; pendiente actualizar con el estado final de implementación.

Ver `estado/bitacora.md` para el detalle cronológico y `estado/pendientes.md` para próximos pasos.

## Estructura del repo

Ver `AGENTS.md` para la estructura completa de carpetas y las instrucciones detalladas de cómo trabajar en cada una.

## Cómo retomar el trabajo (para humanos o agentes)

1. Leer este README.
2. Leer `estado/bitacora.md` (últimas entradas) y `estado/pendientes.md`.
3. Revisar `bibliografia/index.md` si la tarea involucra fuentes o citas.
4. Consultar `decisiones/` si hay dudas sobre por qué se tomó determinado camino de diseño.
