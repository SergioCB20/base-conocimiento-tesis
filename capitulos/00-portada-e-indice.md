<!-- Índice actualizado tras el rediseño del 2026-09-25; los números de página corresponden al PDF E2 y deben recalcularse en el .docx. Fuente: 20202117_SergioChumbimuni_LuisVives_E2.pdf, pp. 1–3. Transcripción del PDF con correcciones editoriales (ver capitulos/CAMBIOS.md); ver capitulos/README.md -->

# Portada

**PONTIFICIA UNIVERSIDAD CATÓLICA DEL PERÚ**
**FACULTAD DE CIENCIAS E INGENIERÍA**
**ESPECIALIDAD DE INGENIERÍA INFORMÁTICA**

**Desarrollo de una Arquitectura MLOps para la Validación Continua de Equidad (Fairness) como Prueba de Calidad (QA) en Modelos de Scoring Crediticio**

Tesis para obtener el título profesional de Ingeniero Informático

**AUTOR:** Sergio Alonso Chumbimuni Bustamante

**ASESOR:** Luis Vives Garnique

Lima, Agosto, 2026

---

# Índice

- Capítulo 1. Generalidades — 4
  - 1.1 Problemática — 4
    - 1.1.1 Descripción — 4
    - 1.1.2 Árbol de problemas — 6
    - 1.1.3 Problema seleccionado — 8
  - 1.2 Objetivos — 8
    - 1.2.1 Objetivo General — 8
    - 1.2.2 Objetivos específicos — 8
    - 1.2.3 Resultados esperados — 9
    - 1.2.4 Mapeo de objetivos, resultados y verificación — 10
  - 1.3 Métodos y Procedimientos — 14
    - 1.3.1 Herramientas — 16
    - 1.3.2 Metodologías y Procedimientos — 19
- Capítulo 2. Marco Conceptual, Teórico y Legal — 21
  - 2.1 Marco Conceptual — 21
    - 2.1.1 El Scoring Crediticio en la Gestión del Riesgo de Crédito — 21
    - 2.1.2 El sesgo algorítmico y la equidad en el Scoring Crediticio — 23
    - 2.1.3 Métricas matemáticas de Equidad de Grupo — 24
    - 2.1.4 Métricas matemáticas de Equidad Individual y Multiplicidad — 25
    - 2.1.5 Degradación del sistema: Drift de Datos, de Concepto y de Sesgo — 27
    - 2.1.6 El dilema de Precisión frente a Equidad (Accuracy-Fairness Trade-off) — 27
    - 2.1.7 Incertidumbre estadística en la evaluación de la equidad
  - 2.2 Marco Teórico — 28
    - 2.2.1 El paradigma MLOps y la automatización CI/CD — 28
    - 2.2.2 Aseguramiento de Calidad proactivo: Shift-Left Testing y Contratos de Equidad — 29
    - 2.2.3 Trazabilidad semántica mediante Grafos de Conocimiento (RDF/OWL) — 30
  - 2.3 Marco Legal — 31
    - 2.3.1 Ley de IA de la Unión Europea (EU AI Act - Reglamento UE 2024/1689) — 31
    - 2.3.2 Normativa de Equidad en Finanzas Globales (ECOA de Estados Unidos) — 32
    - 2.3.3 Estándar Internacional de Gestión de IA (ISO/IEC 42001) — 33
    - 2.3.4 Reglamento peruano de Inteligencia Artificial (D.S. N.° 115-2025-PCM)
- Capítulo 3. Estado del Arte — 34
  - 3.1 Introducción — 34
  - 3.2 Objetivos de revisión — 35
  - 3.3 Preguntas de revisión — 37
  - 3.4 Protocolo de búsqueda — 38
    - 3.4.1 Motores de búsqueda — 39
    - 3.4.2 Cadenas de búsqueda a usar — 39
  - 3.5 Criterios de inclusión y exclusión — 41
  - 3.6 Formulario de extracción de datos — 45
  - 3.7 Resultados de revisión — 48
    - 3.7.1 Respuesta a Pregunta de Revisión 1 — 48
    - 3.7.2 Respuesta a Pregunta de Revisión 2 — 49
    - 3.7.3 Respuesta a Pregunta de Revisión 3 — 50
    - 3.7.4 Respuesta a Pregunta de Revisión 4 — 51
  - 3.8 Conclusiones del Estado del Arte — 52
- Capítulo 4: Diseño de la propuesta de solución — 54
  - 4.1 Introducción — 54
  - 4.2 Esquema arquitectónico detallado (Modelo C4) y flujos CI/CD — 55
    - 4.2.1. Descripción del resultado alcanzado — 55
    - 4.2.2 Metodología de logro y reproducibilidad — 61
    - 4.2.3. Verificación de existencia — 62
    - 4.2.4 Mediciones y validación del indicador — 62
  - 4.3 Especificación de diseño de los componentes modulares de validación de equidad — 64
    - 4.3.1. Descripción del resultado alcanzado — 64
    - 4.3.2. Metodología de logro y reproducibilidad — 65
    - 4.3.3. Verificación de existencia — 66
    - 4.3.4. Mediciones y validación del indicador — 67
  - 4.4. Modelo conceptual de trazabilidad y gobernanza semántica — 70
    - 4.4.1. Descripción del resultado alcanzado — 70
    - 4.4.2. Metodología de logro y reproducibilidad
    - 4.4.3. Verificación de existencia
    - 4.4.4. Mediciones y validación de indicador
  - 4.5. Discusión — 70
    - 4.5.1. Síntesis de los resultados principales — 70
    - 4.5.2. Interpretación del significado de los resultados — 71
    - 4.5.3. Contextualización con la revisión de la literatura — 71
    - 4.5.4. Generalización de los resultados — 72
    - 4.5.5. Limitaciones de los resultados — 73
- Capítulo 5: Implementación de la propuesta de solución
  - 5.1. Introducción
  - 5.2. Infraestructura base: repositorios, versionado de datos, motor de contratos y CI/CD
  - 5.3. Programación e instrumentación de las QA Gates
  - 5.4. Integración del servicio de monitoreo, registro y trazabilidad
  - 5.5. Discusión
- Referencias bibliográficas — 74
- Anexo A: Formulario de Extracción — 79
- Anexo B: Plan de Proyecto — 80
