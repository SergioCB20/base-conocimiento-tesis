# Catálogo bibliográfico

Una entrada por cada PDF en `bibliografia/docs/` (fichas 1–16, más las 17–25 agregadas el 2026-09-25), y además una entrada por cada referencia de la tesis que no tiene PDF local (normas, páginas web y fuentes no resueltas; fichas W1–W16). Metadatos extraídos del propio PDF (portada, bloque "ACM/PVLDB Reference Format", cabecera de revista o sello de arXiv) o de la fuente oficial consultada. Cuando el PDF es un preprint y no indica el venue final, se marca **"venue no indicado en el PDF"** en vez de suponerlo.

**Sobre los tags:** indican a qué sección/decisión de la tesis aporta cada fuente según el contenido del paper. Dónde se cita realmente cada una (por capítulo), y las discrepancias entre cita, referencia y PDF, están en `estado/verificacion-citas.md` (sección F).

Tags usados: `#fairness-pipeline` · `#fairness-metrics` · `#mitigacion` · `#preprocesamiento` · `#contratos-equidad` · `#QA-Gate-1` (datos) · `#QA-Gate-2` (features/leakage) · `#QA-Gate-3` (modelo) · `#CI-CD` · `#mlops` · `#monitoreo-drift` · `#trazabilidad-RDF` · `#provenance` · `#robustez` · `#trade-offs` · `#credit-scoring` · `#marco-legal` · `#revision-sistematica` · `#explicabilidad` · `#equidad-individual`

---

## Resumen rápido

| # | Archivo | Autor(es) | Año | Tipo | Tags principales |
|---|---------|-----------|-----|------|------------------|
| 1 | (Un) Fairness Along the AI Pipeline Problems and Solutions.pdf | Black | 2022 | Tesis PhD (CMU) | `#fairness-pipeline` `#mitigacion` |
| 2 | Amazon SageMaker Model Monitor.pdf | Nigenda et al. | 2022 (arXiv v3) | Paper de sistema | `#monitoreo-drift` `#mlops` |
| 3 | Cascaded Debiasing.pdf | Ghai, Mishra, Mueller | 2022 | CIKM '22 | `#mitigacion` `#fairness-metrics` |
| 4 | Causality-Aided Trade-off.pdf | Ji, Ma, Wang, Li | 2023 (arXiv v3) | Paper | `#trade-offs` `#fairness-metrics` |
| 5 | Data distribution debugging in machine learning pipelines.pdf | Grafberger, Groth, Stoyanovich, Schelter | 2022 | The VLDB Journal | `#preprocesamiento` `#provenance` `#QA-Gate-1` |
| 6 | DispaRisk.pdf | Vasquez, Domeniconi, Rangwala | 2024–2025 (arXiv v3) | Paper | `#QA-Gate-1` `#QA-Gate-2` |
| 7 | Employing_Hybrid_AI_Systems_to_Trace_and_Document.pdf | Russo, Chudasama, Purohit, Sawischa, Vidal | 2024 | IEEE Access | `#trazabilidad-RDF` |
| 8 | Fair Preprocessing.pdf | Biswas, Rajan | 2021 | ESEC/FSE '21 | `#preprocesamiento` `#fairness-pipeline` |
| 9 | Fairness specification and repair for machine learning pipeline.pdf | Nguyen | 2024 | Tesis PhD (Iowa State) | `#contratos-equidad` `#QA-Gate-3` |
| 10 | Hybrid_MLOps_framework_for_automated_lifecycle_man.pdf | Reda, Taie, Shaheen | 2025 | Scientific Reports | `#mlops` `#CI-CD` `#monitoreo-drift` |
| 11 | Preeclampsia predictor with machine learning.pdf | Lin et al. | 2022 | Preprint medRxiv | `#mitigacion` `#fairness-pipeline` |
| 12 | Proactively Screening MLP with ARGUSEYES.pdf | Schelter, Grafberger, Guha, Karlas, Zhang | 2023 | SIGMOD-Companion '23 | `#CI-CD` `#provenance` `#credit-scoring` |
| 13 | Stress-Testing ML Pipelines with Adversarial Data Corruption.pdf | Zhu, Xu, Lorenzi, Glavic, Salimi | 2025 (arXiv v1) | Paper | `#robustez` `#QA-Gate-1` |
| 14 | Towards_an_Ontology-Driven_Approach_to_Document_Bi.pdf | Russo, Vidal | 2025 | JAIR 83 | `#trazabilidad-RDF` |
| 15 | Trustworthy AI in Cloud MLOps.pdf | Avuthu | 2021 | J. Sci. Eng. Research | `#mlops` `#CI-CD` |
| 16 | What If You Could Stop Re-Implementing ML Pipelines.pdf | Grafberger, Guha, Groth, Schelter | 2023 | PVLDB 16(12) | `#preprocesamiento` `#robustez` |

---

## Fichas

### 1. (Un)Fairness Along the AI Pipeline: Problems and Solutions
- **Archivo:** `docs/(Un) Fairness Along the AI Pipeline Problems and Solutions.pdf`
- **Autor(es):** Emily Black
- **Año:** 2022 (julio)
- **Publicación:** Tesis doctoral, Carnegie Mellon University, reporte técnico CMU-CS-22-121.
- **Resumen:** Estudia cómo las decisiones tomadas a lo largo de todo el pipeline de modelado (no solo el algoritmo) afectan el comportamiento de fairness. Vincula inestabilidad del modelo con injusticia (decisiones que dependen de elecciones arbitrarias de modelado), muestra en un caso de auditoría tributaria que intervenciones "no-fairness" en el pipeline pueden mejorar la equidad y reducir el trade-off con la utilidad, y discute la *model multiplicity* y sus implicancias legales. Respaldo para el argumento de que la fairness debe validarse en varias etapas del pipeline y no solo al final.
- **Tags:** `#fairness-pipeline` `#mitigacion` `#trade-offs`

### 2. Amazon SageMaker Model Monitor: A System for Real-Time Insights into Deployed Machine Learning Models
- **Archivo:** `docs/Amazon SageMaker Model Monitor.pdf`
- **Autor(es):** David Nigenda, Zohar Karnin, Muhammad Bilal Zafar, Raghu Ramesha, Alan Tan, Michele Donini, Krishnaram Kenthapadi
- **Año:** 2022 (arXiv:2111.13657v3, 5-ago-2022)
- **Publicación:** Preprint arXiv (venue final no indicado en el PDF).
- **Resumen:** Describe el servicio gestionado de AWS que monitorea modelos en producción y detecta en tiempo real drift de datos, de concepto, de **sesgo (bias drift)** y de atribución de features, con alertas para el dueño del modelo. Incluye requisitos de clientes, arquitectura, metodología de detección y lecciones de dos años en producción. Referente industrial de monitoreo continuo de fairness post-despliegue (se apoya en SageMaker Clarify).
- **Tags:** `#monitoreo-drift` `#mlops` `#fairness-metrics`

### 3. Cascaded Debiasing: Studying the Cumulative Effect of Multiple Fairness-Enhancing Interventions
- **Archivo:** `docs/Cascaded Debiasing.pdf`
- **Autor(es):** Bhavya Ghai, Mihir Mishra, Klaus Mueller
- **Año:** 2022
- **Publicación:** Proceedings of the 31st ACM International Conference on Information and Knowledge Management (CIKM '22), Atlanta. DOI: 10.1145/3511808.3557155
- **Resumen:** Estudio empírico de 60 combinaciones de intervenciones de fairness (pre-, in- y post-procesamiento) con 9 métricas de fairness y 2 de utilidad sobre 4 datasets benchmark (usa AIF360). Encuentra que aplicar varias intervenciones mejora la fairness agregada a costa de utilidad, pero no de forma monótona, y que pueden perjudicar a grupos concretos (incluido el privilegiado). Útil para justificar la elección de una sola intervención de mitigación en un punto concreto del pipeline y para discutir limitaciones de métricas de disparidad entre grupos.
- **Tags:** `#mitigacion` `#fairness-metrics` `#trade-offs` `#QA-Gate-3`

### 4. Causality-Aided Trade-off Analysis for Machine Learning Fairness
- **Archivo:** `docs/Causality-Aided Trade-off.pdf`
- **Autor(es):** Zhenlan Ji, Pingchuan Ma, Shuai Wang, Yanhui Li
- **Año:** 2023 (arXiv:2305.13057v3, 3-oct-2023)
- **Publicación:** Preprint arXiv (venue final no indicado en el PDF).
- **Resumen:** Propone usar análisis causal (descubrimiento causal + inferencia) para entender los trade-offs entre métricas de fairness, desempeño y robustez cuando se aplican métodos de mejora de fairness en el pipeline. Evalúa 12 métodos sobre Adult, COMPAS y **German Credit**. Hallazgos: la elección de métrica cambia el patrón de trade-offs; AOD y Theil Index son causas frecuentes de trade-off; fairness vs. robustez es un trade-off inevitable. Sirve para justificar la selección de métricas y umbrales en los contratos.
- **Tags:** `#trade-offs` `#fairness-metrics` `#mitigacion` `#credit-scoring`

### 5. Data distribution debugging in machine learning pipelines
- **Archivo:** `docs/Data distribution debugging in machine learning pipelines.pdf`
- **Autor(es):** Stefan Grafberger, Paul Groth, Julia Stoyanovich, Sebastian Schelter
- **Año:** 2022 (recibido feb-2021, aceptado dic-2021)
- **Publicación:** The VLDB Journal (Special Issue). DOI: 10.1007/s00778-021-00726-w
- **Resumen:** Presenta **mlinspect**, librería que extrae un DAG del flujo de datos de un pipeline de preprocesamiento (pandas/sklearn) y lo instrumenta automáticamente con inspecciones predefinidas, propagando metadatos (p. ej. lineage) de operador a operador. Detecta "data distribution bugs": sesgo técnico introducido por filtros, joins o imputaciones que alteran la representación de grupos. Base para validar fairness en la etapa de datos/preprocesamiento sin instrumentar código manualmente.
- **Tags:** `#preprocesamiento` `#provenance` `#QA-Gate-1` `#fairness-pipeline`

### 6. DispaRisk: Assessing Fairness Through Usable Information
- **Archivo:** `docs/DispaRisk.pdf`
- **Autor(es):** Jonathan Vasquez, Carlotta Domeniconi, Huzefa Rangwala
- **Año:** 2024 (arXiv:2405.12372; versión v3 del 29-may-2025)
- **Publicación:** Preprint arXiv (venue final no indicado en el PDF).
- **Resumen:** Framework basado en teoría de *usable information* (V-information) para estimar, en las etapas iniciales del pipeline y antes de entrenar el modelo final, el riesgo de disparidad de un dataset y qué familias de modelos tienden a reproducir sesgo. Evaluado en KDD Census-Income, FACET y Hate Speech. Respaldo para detección temprana de sesgo en datos y de atributos que "filtran" información del atributo protegido.
- **Tags:** `#QA-Gate-1` `#QA-Gate-2` `#fairness-metrics`

### 7. Employing Hybrid AI Systems to Trace and Document Bias in ML Pipelines
- **Archivo:** `docs/Employing_Hybrid_AI_Systems_to_Trace_and_Document.pdf`
- **Autor(es):** Mayra Russo, Yasharajsinh Chudasama, Disha Purohit, Sammy Sawischa, Maria-Esther Vidal
- **Año:** 2024
- **Publicación:** IEEE Access (versión aceptada del autor). DOI: 10.1109/ACCESS.2024.3427388
- **Resumen:** Propone, a partir de patrones de diseño composicionales, un sistema de IA híbrido (ML + grafos de conocimiento) para trazar y documentar sesgos en datasets y modelos. Dos implementaciones: una de trazado fino del modelo y otra que compara sesgo en datos de entrada vs. predicciones. Usa grafos de conocimiento RDF y consultas SPARQL; caso de uso de detección de Fake News. Referente directo para la trazabilidad semántica de resultados de fairness del pipeline.
- **Tags:** `#trazabilidad-RDF` `#provenance` `#fairness-pipeline`

### 8. Fair Preprocessing: Towards Understanding Compositional Fairness of Data Transformers in Machine Learning Pipeline
- **Archivo:** `docs/Fair Preprocessing.pdf`
- **Autor(es):** Sumon Biswas, Hridesh Rajan
- **Año:** 2021
- **Publicación:** ESEC/FSE '21 (29th ACM Joint European Software Engineering Conference and Symposium on the Foundations of Software Engineering), Atenas. DOI: 10.1145/3468264.3468536
- **Resumen:** Introduce un método causal para medir el impacto en fairness de cada etapa de preprocesamiento (escalado, encoding, muestreo, imputación, PCA, etc.) en 37 pipelines reales y 5 datasets (incluye German Credit). Muestra que ciertos transformadores introducen injusticia, identifica patrones por categoría y cómo la fairness local de una etapa se compone en la global. Respaldo para validar fairness por etapa (QA Gates distribuidos) y no solo sobre el modelo final.
- **Tags:** `#preprocesamiento` `#fairness-pipeline` `#QA-Gate-1` `#QA-Gate-2` `#credit-scoring`

### 9. Fairness specification and repair for machine learning pipeline
- **Archivo:** `docs/Fairness specification and repair for machine learning pipeline.pdf`
- **Autor(es):** Giang Nguyen
- **Año:** 2024
- **Publicación:** Tesis doctoral, Iowa State University (co-advisors: Hridesh Rajan, Wei Le).
- **Resumen:** Tres aportes: (1) **Fair-AutoML**, reparación de modelos injustos con búsqueda bayesiana consciente de fairness; (2) **Fairness Contract**, aplicación de *design-by-contract* para detectar violaciones de fairness en tiempo de ejecución y localizarlas en módulos del pipeline (contratos globales descompuestos en módulos, aserciones en runtime); (3) **Fairness Checker**, detección modular de sesgo con desigualdades de concentración y un anotador para especificar fairness modular. Antecedente más cercano a los Contratos de Equidad C1/C2/C3 como QA Gates.
- **Tags:** `#contratos-equidad` `#QA-Gate-1` `#QA-Gate-2` `#QA-Gate-3` `#mitigacion` `#credit-scoring`

### 10. Hybrid MLOps framework for automated lifecycle management of adaptive phishing detection models
- **Archivo:** `docs/Hybrid_MLOps_framework_for_automated_lifecycle_man.pdf`
- **Autor(es):** Asmaa Reda, Shereen A. Taie, Masoud E. Shaheen
- **Año:** 2025 (recibido jul-2025, aceptado oct-2025)
- **Publicación:** Scientific Reports (Nature).
- **Resumen:** Presenta HAMF, framework MLOps que integra como disparadores de primera clase: reemplazo de features guiado por SHAP, reentrenamiento por eventos, **auditorías de fairness disparadas automáticamente** (usa AIF360) y feedback humano. Caso de detección de phishing; reporta detección de drift en 18 s y reducción >60% de disparidades entre subgrupos. Ejemplo reciente de fairness integrada como control automático dentro del ciclo CI/CD de MLOps.
- **Tags:** `#mlops` `#CI-CD` `#monitoreo-drift` `#fairness-pipeline`

### 11. Preeclampsia Predictor with Machine Learning: A Comprehensive and Bias-Free Machine Learning Pipeline
- **Archivo:** `docs/Preeclampsia predictor with machine learning.pdf`
- **Autor(es):** Yun C. Lin, Daniel Mallia, Andrea O. Clark-Sevilla, Adam Catto, Alisa Leshchenko, David M. Haas, Ronald Wapner, Itsik Pe'er, Anita Raja, Ansaf Salleb-Aouissi
- **Año:** 2022 (publicado 9-jun-2022)
- **Publicación:** Preprint medRxiv, sin revisión por pares. DOI: 10.1101/2022.06.08.22276107
- **Resumen:** Pipeline de ML para predecir preeclampsia severa en una cohorte de nulíparas, en cuatro momentos del embarazo. Además de desempeño (Random Forest, AUC 0.68–0.83), identifica un sesgo racial (ratio de *predictive equality* de 1.31 contra participantes negras no hispanas) y lo mitiga hasta 1.14. Ejemplo aplicado, fuera de finanzas, de detección y mitigación de sesgo dentro de un pipeline end-to-end.
- **Tags:** `#mitigacion` `#fairness-pipeline` `#fairness-metrics`

### 12. Proactively Screening Machine Learning Pipelines with ArgusEyes
- **Archivo:** `docs/Proactively Screening MLP with ARGUSEYES.pdf`
- **Autor(es):** Sebastian Schelter, Stefan Grafberger, Shubha Guha, Bojan Karlas, Ce Zhang
- **Año:** 2023 (junio)
- **Publicación:** Companion of the 2023 International Conference on Management of Data (SIGMOD-Companion '23), Seattle. DOI: 10.1145/3555041.3589682
- **Resumen:** Demo de ArgusEyes, sistema que instrumenta, ejecuta y "screenea" pipelines de ML **como parte de la integración continua** para problemas de datos especificados declarativamente (data leakage, errores de etiqueta, violaciones de fairness), usando provenance de los artefactos para detectarlos antes del despliegue. Uno de sus escenarios es un pipeline de **credit scoring** con violaciones de fairness. Referente muy directo para QA Gates de fairness en CI.
- **Tags:** `#CI-CD` `#provenance` `#QA-Gate-1` `#QA-Gate-2` `#credit-scoring`

### 13. Stress-Testing ML Pipelines with Adversarial Data Corruption
- **Archivo:** `docs/Stress-Testing ML Pipelines with Adversarial Data Corruption.pdf`
- **Autor(es):** Jiongli Zhu, Geyang Xu, Felipe Lorenzi, Boris Glavic, Babak Salimi
- **Año:** 2025 (arXiv:2506.01230v1, 2-jun-2025)
- **Publicación:** Preprint arXiv (venue final no indicado en el PDF).
- **Resumen:** Presenta **Savage**, framework de inspiración causal que modela problemas de calidad de datos realistas (valores faltantes correlacionados con demografía, etiquetas sesgadas, sesgo de selección) y busca con optimización bi-nivel las corrupciones que más degradan una métrica objetivo, tratando el pipeline como caja negra. Con ~5% de corrupciones estructuradas degrada fuertemente modelos, incluidos métodos fairness-aware. Menciona el Art. 15 del EU AI Act y el NIST AI RMF. Útil para argumentar la validación de calidad de datos y la robustez de los gates.
- **Tags:** `#robustez` `#QA-Gate-1` `#fairness-pipeline`

### 14. Towards an Ontology-Driven Approach to Document Bias
- **Archivo:** `docs/Towards_an_Ontology-Driven_Approach_to_Document_Bi.pdf`
- **Autor(es):** Mayra Russo, Maria-Esther Vidal
- **Año:** 2025 (agosto)
- **Publicación:** Journal of Artificial Intelligence Research 83, Article 38 (JAIR Track: Fairness and Bias in AI). DOI: 10.1613/jair.1.19388
- **Resumen:** Presenta la ontología **Doc-BiasO**, vocabulario integrado de tipos de sesgo de la literatura de Trustworthy AI y sus medidas, que reutiliza vocabularios existentes de ML/IA (OWL/RDF) siguiendo buenas prácticas de ingeniería ontológica. Se demuestra en un benchmark y dentro de un sistema neuro-simbólico. Fuente principal para diseñar/justificar la Ontología OWL de Fairness y la documentación semántica de sesgos (clases, propiedades, SPARQL).
- **Tags:** `#trazabilidad-RDF` `#fairness-metrics`

### 15. Trustworthy AI in Cloud MLOps: Ensuring Explainability, Fairness, and Security in AI-Driven Applications
- **Archivo:** `docs/Trustworthy AI in Cloud MLOps.pdf`
- **Autor(es):** Yogeswara Reddy Avuthu
- **Año:** 2021
- **Publicación:** Journal of Scientific and Engineering Research, 8(1):246-255.
- **Resumen:** Propone un framework para integrar explicabilidad (SHAP, LIME), monitoreo/mitigación de fairness y seguridad (entrenamiento adversarial, detección de amenazas) en flujos MLOps cloud con CI/CD y monitoreo continuo; se evalúa en riesgo financiero, salud y mantenimiento predictivo. Referencia general de fairness como requisito dentro de MLOps; revista de menor impacto, conviene usarla como apoyo y no como fuente principal.
- **Tags:** `#mlops` `#CI-CD` `#fairness-pipeline`

### 16. mlwhatif: What If You Could Stop Re-Implementing Your Machine Learning Pipeline Analyses Over and Over?
- **Archivo:** `docs/What If You Could Stop Re-Implementing ML Pipelines.pdf`
- **Autor(es):** Stefan Grafberger, Shubha Guha, Paul Groth, Sebastian Schelter
- **Año:** 2023
- **Publicación:** PVLDB 16(12): 4002-4005 (demo). DOI: 10.14778/3611540.3611606
- **Resumen:** Demo de **mlwhatif**, librería para especificar declarativamente análisis *what-if* sobre un pipeline (robustez ante errores de datos, efecto de limpieza de datos, impacto de operadores de preprocesamiento en la fairness) y generar, optimizar y ejecutar automáticamente las variantes del pipeline. Código en github.com/stefan-grafberger/mlwhatif. Apoyo para análisis de sensibilidad de fairness ante cambios de preprocesamiento.
- **Tags:** `#preprocesamiento` `#robustez` `#fairness-pipeline`

---

## Observaciones

- Los trabajos de **Schelter/Grafberger** (5, 12, 16) forman una línea coherente (mlinspect → mlwhatif → ArgusEyes) sobre inspección de pipelines basada en provenance.
- Los trabajos de **Russo/Vidal** (7, 14) son la línea de trazabilidad semántica (grafos de conocimiento y ontología de sesgos).
- Los de **Rajan** (8 y la tesis de Nguyen, 9) son la línea de ingeniería de software para fairness (composición por etapas, contratos).
- Ninguna fuente del catálogo menciona el dataset Davronov ni `ThresholdOptimizer`; la versión E2 de la tesis tampoco los nombra. La tesis sí cita Hardt et al. (2016), Nguyen et al. (2025) y Bartlett et al. (2022), cuyos PDFs no están en `docs/` (ver `estado/verificacion-citas.md`, sección G).
- Dos PDFs no tienen cita en el texto de la tesis: (1) la tesis de Black (la tesis cita otro trabajo, Black & Fredrikson 2021) y (11) Preeclampsia, que está en la lista de referencias pero sin cita.
- Dos PDFs se citan con datos que no coinciden: (4) se cita como "Li et al., 2023" pero el primer autor es Ji; (6) se cita con año 2023 pero el preprint es de 2024.

---

# Fuentes agregadas el 2026-09-25 (skill `resolver-referencias`)

Estas son las 25 referencias de `capitulos/06-referencias.md` que no tenían ficha. Cada una se buscó en fuentes legítimas: arXiv, sitio de la revista o conferencia, repositorio institucional o sitio oficial del organismo emisor. Los resúmenes se basan en el contenido realmente leído (PDF, abstract o página oficial), no en el título.

| Estado | Cantidad | Fichas |
|---|---|---|
| PDF descargado y verificado | 9 | 17–25 |
| Sin PDF local, contenido verificado en fuente oficial o abstract | 9 | W1–W9 |
| Completadas con archivos o enlace del autor (2.ª pasada) | 6 | W10–W12, W14–W16 |
| Confirmada como inexistente | 1 | W13 |

## Resumen rápido (fichas nuevas)

| # | Referencia (como en la tesis) | Estado | Tags |
|---|---|---|---|
| 17 | Hardt, Price & Srebro (2016) | PDF (arXiv) | `#fairness-metrics` `#QA-Gate-3` |
| 18 | Mehrabi et al. (2021) | PDF (arXiv v3) | `#fairness-metrics` `#equidad-individual` |
| 19 | Adebayo & Kagal (2016) | PDF (arXiv) | `#fairness-metrics` `#QA-Gate-2` |
| 20 | Black & Fredrikson (2021) | PDF (arXiv) | `#equidad-individual` |
| 21 | Menon & Williamson (2018) | PDF (PMLR) | `#trade-offs` |
| 22 | Bartlett et al. (2022) | PDF (working paper 2019, no la versión JFE) | `#credit-scoring` `#marco-legal` `#QA-Gate-3` |
| 23 | Ogrizović et al. (2024) | PDF (open access) | `#mlops` `#CI-CD` |
| 24 | Immaneni (2020) | PDF (open access) | `#mlops` `#credit-scoring` |
| 25 | Demirgüç-Kunt et al. (2022) | PDF (CC BY 3.0 IGO) | `#credit-scoring` |
| W1 | Stoyanovich et al. (2022) | Abstract verificado; PDF bloqueado | `#preprocesamiento` `#provenance` |
| W2 | Byanjankar et al. (2015) | Abstract verificado; sin PDF abierto | `#credit-scoring` |
| W3 | Kazmierczak, Salama & Huerta (2024) | Página oficial verificada | `#mlops` `#CI-CD` |
| W4 | Angwin et al. (2016) | Página oficial verificada | `#fairness-metrics` |
| W5 | MathWorks (s.f.) | Página oficial verificada | `#credit-scoring` |
| W6 | BCBS (2025) | Página oficial verificada | `#credit-scoring` `#marco-legal` |
| W7 | Reglamento (UE) 2024/1689 | Fuente oficial verificada | `#marco-legal` |
| W8 | ECOA, 15 U.S.C. § 1691 | Fuente oficial verificada | `#marco-legal` |
| W9 | CFPB Circular 2023-03 | Fuente oficial verificada (**retirada**) | `#marco-legal` `#explicabilidad` |
| W10 | ISO/IEC 42001:2023 | PDF (solo vista previa oficial) | `#marco-legal` |
| W11 | D.S. N° 115-2025-PCM | PDF oficial (El Peruano) | `#marco-legal` `#credit-scoring` |
| W12 | Petticrew & Roberts (2006) | PDF (revisado solo PICOC) | `#revision-sistematica` |
| W13 | Nguyen, Ahmed, Biswas & Rajan (2025) | **No existe** (confirmado) | `#contratos-equidad` |
| W14 | Dhaenens (2024) | PDF; **calidad dudosa** | `#mlops` |
| W15 | Kästner (2021) | HTML guardado (versión actualizada en 2023) | `#QA-Gate-1` `#monitoreo-drift` |
| W16 | Caballar & Stryker / IBM (2024) | Página oficial verificada | `#monitoreo-drift` |

## Fichas con PDF local

### 17. Equality of Opportunity in Supervised Learning
- **Archivo:** `docs/Equality of Opportunity in Supervised Learning.pdf`
- **Autor(es):** Moritz Hardt, Eric Price, Nathan Srebro
- **Año:** 2016
- **Publicación:** arXiv:1610.02413v1 (7-oct-2016). La tesis la cita como NeurIPS 2016, pp. 3323–3331; el PDF descargado es la versión de arXiv y no muestra esos datos.
- **Fuente:** https://arxiv.org/abs/1610.02413
- **Resumen:** Propone un criterio de no discriminación respecto de un atributo sensible (igualdad de oportunidades / *equalized odds*) que depende solo de la distribución conjunta de predictor, objetivo y atributo protegido. Muestra cómo ajustar de forma óptima cualquier predictor ya entrenado para cumplir el criterio, que es el post-procesamiento que implementa `ThresholdOptimizer` de Fairlearn. Incluye un caso de estudio con puntajes de crédito FICO. Es el respaldo de la métrica EOD del Contrato C3 y de la mitigación del QA Gate 3.
- **Tags:** `#fairness-metrics` `#QA-Gate-3` `#mitigacion` `#credit-scoring`

### 18. A Survey on Bias and Fairness in Machine Learning
- **Archivo:** `docs/A Survey on Bias and Fairness in Machine Learning.pdf`
- **Autor(es):** Ninareh Mehrabi, Fred Morstatter, Nripsuta Saxena, Kristina Lerman, Aram Galstyan
- **Año:** 2021 (publicado en ACM Computing Surveys 54(6), según la tesis). PDF: arXiv:1908.09635v3, 25-ene-2022.
- **Fuente:** https://arxiv.org/abs/1908.09635
- **Resumen:** Survey que recopila casos reales de sesgo en IA, enumera las fuentes de sesgo que afectan a las aplicaciones y propone una taxonomía de definiciones de fairness (de grupo e individuales). Es el respaldo de la división equidad de grupo / equidad individual y de la métrica de consistencia del Cap. 2.
- **Tags:** `#fairness-metrics` `#equidad-individual`

### 19. Iterative Orthogonal Feature Projection for Diagnosing Bias in Black-Box Models
- **Archivo:** `docs/Iterative Orthogonal Feature Projection for Diagnosing Bias.pdf`
- **Autor(es):** Julius Adebayo, Lalana Kagal (MIT CSAIL)
- **Año:** 2016 (arXiv:1611.04967v1, 15-nov-2016)
- **Fuente:** https://arxiv.org/abs/1611.04967
- **Resumen:** Procedimiento iterativo basado en proyección ortogonal de los atributos de entrada para cuantificar cuánto depende un modelo de caja negra de cada atributo, y con eso evaluar su grado de discriminación. Menciona crédito, seguros y empleo como dominios de uso. Sirve para argumentar que un modelo puede depender de atributos protegidos a través de otras variables (sesgo por proxy).
- **Nota:** en la tesis se cita como "Adebayo & **Kegal**"; el apellido correcto es Kagal.
- **Tags:** `#fairness-metrics` `#QA-Gate-2`

### 20. Leave-one-out Unfairness
- **Archivo:** `docs/Leave-one-out Unfairness.pdf`
- **Autor(es):** Emily Black, Matt Fredrikson (Carnegie Mellon University)
- **Año:** 2021 (arXiv:2107.10171v1, 21-jul-2021; la tesis la cita en FAccT 2021, pp. 285–295)
- **Fuente:** https://arxiv.org/abs/2107.10171
- **Resumen:** Define la *leave-one-out unfairness*: qué tan probable es que la predicción para un individuo cambie al agregar o quitar a una sola persona del conjunto de entrenamiento. Mide en datos reales cuánto la presentan los modelos profundos y muestra que el entrenamiento adversarial y el *randomized smoothing* tienen efectos opuestos sobre ella. Es el respaldo de la métrica LUF del Cap. 2.
- **Tags:** `#equidad-individual`

### 21. The Cost of Fairness in Binary Classification
- **Archivo:** `docs/The Cost of Fairness in Binary Classification.pdf`
- **Autor(es):** Aditya Krishna Menon, Robert C. Williamson (ANU / DATA61)
- **Año:** 2018
- **Publicación:** Proceedings of Machine Learning Research 81 (Conference on Fairness, Accountability, and Transparency). El PDF de PMLR está paginado 1–12; la tesis indica 107–118 (no verificable desde este PDF).
- **Fuente:** https://proceedings.mlr.press/v81/menon18a.html
- **Resumen:** Estudia el trade-off entre exactitud y fairness: relaciona dos medidas de fairness con riesgos sensibles al costo, muestra que el clasificador óptimo con restricción de fairness es un umbral dependiente de la instancia sobre la probabilidad de clase, y vincula el tamaño del trade-off con la alineación entre el objetivo y el atributo sensible. Es el respaldo de la sección 2.1.6 (Accuracy-Fairness Trade-off) y, de forma indirecta, de la mitigación por umbrales.
- **Tags:** `#trade-offs` `#mitigacion`

### 22. Consumer-Lending Discrimination in the FinTech Era
- **Archivo:** `docs/Consumer-Lending Discrimination in the FinTech Era.pdf`
- **Autor(es):** Robert Bartlett, Adair Morse, Richard Stanton, Nancy Wallace (UC Berkeley)
- **Año:** el PDF es la versión *working paper* de **noviembre de 2019** (sitio de la Haas School). La tesis cita la versión publicada en *Journal of Financial Economics* 143(1), 30–56 (2022), que no se descargó porque no es de acceso abierto; el texto puede diferir.
- **Fuente:** https://faculty.haas.berkeley.edu/morse/research/papers/discrim.pdf · versión publicada: https://doi.org/10.1016/j.jfineco.2021.05.047
- **Resumen:** Estima la discriminación en el mercado hipotecario de EE. UU., para prestamistas tradicionales y FinTech, usando la fijación de precios del riesgo de crédito de las GSE como identificación bajo la doctrina legal de "necesidad legítima de negocio". Encuentra que los prestatarios latinos y afroamericanos pagan 7.9 pb más en hipotecas de compra (3.6 pb en refinanciamiento), unos USD 765M al año. Los algoritmos FinTech reducen las disparidades de tasa en más de un tercio y no muestran discriminación en rechazos, pero no la eliminan. Es el respaldo de la cifra de "~40%" y de la doctrina de impacto dispar citadas en los Caps. 1 y 2.
- **Nota:** revisar que las cifras citadas en la tesis coincidan con la versión JFE 2022.
- **Tags:** `#credit-scoring` `#marco-legal` `#QA-Gate-3`

### 23. Quality assurance strategies for machine learning applications in big data analytics: an overview
- **Archivo:** `docs/Quality Assurance Strategies for ML Applications in Big Data.pdf`
- **Autor(es):** Mihajlo Ogrizović, Dražen Drašković, Dragan Bojić (Universidad de Belgrado)
- **Año:** 2024
- **Publicación:** Journal of Big Data 11:156 (survey, open access). DOI: 10.1186/s40537-024-01028-y
- **Resumen:** Survey de estrategias de aseguramiento de calidad para aplicaciones de ML sobre big data. Propone una clasificación que sigue la estructura del pipeline de ML, define el rol de cada miembro del equipo y revisa requisitos de calidad como latencia, escalabilidad, explicabilidad, fairness, privacidad, robustez y seguridad. Es el respaldo de la idea de QA a lo largo del pipeline (2.2.3).
- **Tags:** `#mlops` `#CI-CD` `#fairness-pipeline`

### 24. Building MLOps Pipelines in Fintech: Keeping Up with Continuous Machine Learning
- **Archivo:** `docs/Building MLOps Pipelines in Fintech.pdf`
- **Autor(es):** Jayaram Immaneni (JP Morgan Chase)
- **Año:** 2020
- **Publicación:** International Journal of Artificial Intelligence, Data Science, and Machine Learning 1(2), 22–32 (según el PDF). DOI según el PDF: 10.63282/30509262/IJAIDSML-V1I2P103 (igual que en la tesis). La página web de la revista muestra otras páginas (22-23) y otro formato de DOI (`10.63282/3050-9262.IJAIDSML-V1I2P103`). Licencia CC BY-NC 4.0.
- **Fuente:** https://ijaidsml.org/index.php/ijaidsml/article/view/76
- **Resumen:** Artículo de divulgación sobre los componentes de un pipeline MLOps para fintech (CI/CD, automatización, orquestación, desde la preparación de datos hasta la evaluación), los retos regulatorios y de privacidad del sector y ejemplos de adopción. No presenta evaluación experimental. Es el respaldo del uso generalizado de ML en crédito (Cap. 1).
- **Nota:** en la tesis se cita como "(IJAIDSML, 2020)" en vez de "(Immaneni, 2020)".
- **Tags:** `#mlops` `#credit-scoring`

### 25. The Global Findex Database 2021: Financial Inclusion, Digital Payments, and Resilience in the Age of COVID-19
- **Archivo:** `docs/The Global Findex Database 2021.pdf` (31 MB)
- **Autor(es):** Asli Demirgüç-Kunt, Leora Klapper, Dorothe Singer, Saniya Ansar
- **Año:** 2022
- **Publicación:** Banco Mundial, Washington DC. DOI: 10.1596/978-1-4648-1897-4. Licencia CC BY 3.0 IGO.
- **Fuente:** https://documents1.worldbank.org/curated/en/099818107072234182/pdf/IDU06a834fe908933040670a6560f44e3f4d35b7.pdf
- **Resumen:** Informe sobre inclusión financiera basado en encuestas a unos 128 000 adultos de 123 economías. La tenencia de cuentas subió de 51% (2011) a 76% (2021), y a 71% en economías en desarrollo. Hay 1 400 millones de adultos sin cuenta, y persisten brechas por género, ingreso, edad, educación y zona rural/urbana. Respalda la existencia de poblaciones excluidas del sistema financiero.
- **Nota:** la tesis lo cita (2.1.2) para afirmar que usar "datos alternativos" en scoring perpetúa el sesgo de representación contra sectores rurales. **El informe no trata datos alternativos, scoring crediticio ni algoritmos** (0 menciones); solo documenta las brechas de acceso. Conviene revisar esa cita.
- **Tags:** `#credit-scoring`

## Fichas sin PDF local

### W1. Responsible data management `[sin PDF local; abstract verificado]`
- **Autor(es):** Julia Stoyanovich, Serge Abiteboul, Bill Howe, H. V. Jagadish, Sebastian Schelter
- **Año:** 2022
- **Publicación:** Communications of the ACM 65(6), 64–74 (verificado en Crossref). **DOI correcto: 10.1145/3488717.** La tesis pone `10.1145/3488716`, que en Crossref corresponde a otro artículo ("The Go programming language and environment").
- **Fuente:** https://doi.org/10.1145/3488717 · ficha del autor: https://ssc.io/publication/responsible-data-management-cacm/ (el PDF de ACM y la copia de NSF PAR no se pudieron descargar).
- **Resumen (según el abstract):** Sostiene que las decisiones tomadas durante la recolección y preparación de datos afectan de forma profunda la robustez, la fairness y la interpretabilidad de los sistemas algorítmicos. Propone extender las consideraciones éticas y legales a todo el ciclo de vida de los datos, incluida la operación después del despliegue. Respalda el enfoque de validar desde la ingesta.
- **Tags:** `#preprocesamiento` `#provenance` `#QA-Gate-1`

### W2. Predicting Credit Risk in Peer-to-Peer Lending: A Neural Network Approach `[sin PDF local; abstract verificado]`
- **Autor(es):** Ajay Byanjankar, Markku Heikkilä, Jozsef Mezei (Åbo Akademi)
- **Año:** 2015
- **Publicación:** 2015 IEEE Symposium Series on Computational Intelligence (IEEE CIFEr). DOI: 10.1109/SSCI.2015.109
- **Fuente:** https://research.abo.fi/en/publications/predicting-credit-risk-in-peer-to-peer-lending-a-neural-network-a/ (el repositorio institucional no tiene texto completo abierto; no se usó una copia de terceros).
- **Resumen (según el abstract):** Propone un modelo de scoring con redes neuronales para clasificar solicitudes de préstamos P2P en *default* y *no default*, y reporta que filtra de forma efectiva las solicitudes que caen en *default*. Respalda la afirmación del Cap. 1 sobre el uso de ML para el otorgamiento de crédito.
- **Tags:** `#credit-scoring`

### W3. MLOps: flujos de procesamiento de entrega continua y automatización en el aprendizaje automático `[fuente web, sin PDF local]`
- **Autor(es):** Jarek Kazmierczak, Khalid Salama, Valentín Huerta (la página lista además a Sunil Kumar Jang Bahadur como colaborador)
- **Año:** página actualizada el 2024-08-28
- **Fuente:** https://docs.cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning?hl=es (consultada el 2026-09-25)
- **Resumen:** Documento de arquitectura de Google Cloud que define niveles de madurez de MLOps. Nivel 0: todo es manual, con despliegues poco frecuentes. Nivel 1: se automatiza el pipeline de entrenamiento con validación de datos y de modelos (entrenamiento continuo). Nivel 2: CI/CD automatizado del propio pipeline (compilación, pruebas y despliegue en desarrollo, staging y producción). Es el respaldo de "MLOps Nivel 2" en toda la tesis.
- **Nota:** el título en español de la página no coincide exactamente con el de la referencia ("…Canalizaciones de automatización y entrega continua…"), y la referencia no tiene URL.
- **Tags:** `#mlops` `#CI-CD`

### W4. Machine Bias `[fuente web, sin PDF local]`
- **Autor(es):** Julia Angwin, Jeff Larson, Surya Mattu, Lauren Kirchner (ProPublica)
- **Año:** 23-may-2016
- **Fuente:** https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing (consultada el 2026-09-25)
- **Resumen:** Investigación periodística sobre COMPAS (Northpointe). Aunque el algoritmo tiene tasas de error globales similares entre acusados negros y blancos, los errores difieren por raza: los acusados negros tenían casi el doble de probabilidad de ser marcados erróneamente como futuros reincidentes, y los blancos de ser clasificados erróneamente como de bajo riesgo. Ilustra la diferencia entre métricas de error por grupo.
- **Nota:** la tesis lo cita (2.1.4) para la premisa de equidad individual "individuos similares deben recibir resultados similares"; el artículo trata disparidades de error entre grupos, no equidad individual. Revisar esa cita.
- **Tags:** `#fairness-metrics`

### W5. Credit Risk Modeling: Importance and Key Components `[fuente web, sin PDF local]`
- **Autor(es):** MathWorks
- **Año:** s.f.
- **Fuente:** https://www.mathworks.com/discovery/credit-risk-modeling.html (consultada el 2026-09-25)
- **Resumen:** Página divulgativa que define PD (probabilidad de que el deudor incumpla), LGD (porcentaje de la exposición que se pierde si hay default) y EAD (exposición pendiente al momento del default), y menciona modelos estadísticos como regresión logística, árboles de decisión y redes neuronales.
- **Nota:** la tesis atribuye a esta página la fórmula $ECL = PD \times LGD \times EAD$, **pero la página no la presenta**, y tampoco trata fairness ni sesgo. Para la fórmula conviene citar una fuente regulatoria.
- **Tags:** `#credit-scoring`

### W6. Principles for the Management of Credit Risk `[fuente web, sin PDF local]`
- **Autor(es):** Basel Committee on Banking Supervision (BIS)
- **Año:** 5-feb-2025
- **Fuente:** https://www.bis.org/bcbs/publ/d591.htm (consultada el 2026-09-25)
- **Resumen:** Documento de **consulta pública** (ya cerrada) que propone actualizaciones técnicas limitadas a los principios de riesgo de crédito del año 2000 para alinearlos con el Marco de Basilea vigente. Mantiene cuatro áreas: entorno adecuado de riesgo de crédito, proceso sólido de otorgamiento, administración, medición y monitoreo del crédito, y controles adecuados.
- **Nota:** d591 es una **consulta**, no la versión final de los principios; revisar si existe versión final antes de citarla como norma.
- **Tags:** `#credit-scoring` `#marco-legal`

### W7. Reglamento (UE) 2024/1689 (Reglamento de Inteligencia Artificial) `[norma, sin PDF local]`
- **Emisor:** Parlamento Europeo y Consejo de la Unión Europea
- **Fechas:** adoptado el 13-jun-2024; publicado en el DO L 2024/1689 el 12-jul-2024; en vigor desde el 1-ago-2024.
- **Fuente:** https://eur-lex.europa.eu/eli/reg/2024/1689/oj · texto del Anexo III consultado en https://ai-act-service-desk.ec.europa.eu/en/ai-act/annex-3 (2026-09-25)
- **Contenido verificado:** el Anexo III, punto 5(b), clasifica como de alto riesgo los sistemas de IA "intended to be used to evaluate the creditworthiness of natural persons or establish their credit score, with the exception of AI systems used for the purpose of detecting financial fraud".
- **Nota importante:** EUR-Lex registra el **Reglamento (UE) 2026/1744 del 8-jul-2026 ("Digital Omnibus on AI")**, que modifica el 2024/1689 (publicado el 24-jul-2026; hay versión consolidada al 27-jul-2026). Según fuentes secundarias (despachos jurídicos), aplaza las obligaciones de alto riesgo del Anexo III al **2-dic-2027**; esa fecha no se verificó en el texto oficial. La tesis (agosto 2026) no menciona esta modificación.
- **Tags:** `#marco-legal`

### W8. Equal Credit Opportunity Act, 15 U.S.C. § 1691 et seq. `[norma, sin PDF local]`
- **Emisor:** Congreso de EE. UU. (Pub. L. 93-495, 1974)
- **Fuente:** https://www.govinfo.gov/link/uscode/15/1691 (consultada el 2026-09-25)
- **Contenido verificado:** §1691(a) prohíbe discriminar a un solicitante "on the basis of race, color, religion, national origin, sex or marital status, or age", por recibir asistencia pública o por ejercer derechos de la ley. §1691(d) exige dar al solicitante rechazado una declaración de las razones (*adverse action*).
- **Tags:** `#marco-legal` `#explicabilidad`

### W9. Consumer Financial Protection Circular 2023-03 `[norma/guía, sin PDF local — RETIRADA]`
- **Emisor:** Consumer Financial Protection Bureau (CFPB)
- **Fechas:** publicada el 19-sep-2023 (89 FR 27361, 17-abr-2024). **Retirada el 12-may-2025** (Federal Register Vol. 90, n.º 90, ítem 7 de la lista de guías retiradas). La CFPB la lista como "[withdrawn on May 12, 2025]". La Circular 2022-03, sobre algoritmos complejos, también fue retirada.
- **Fuente:** https://www.consumerfinance.gov/compliance/circulars/circular-2023-03-adverse-action-notification-requirements-and-the-proper-use-of-the-cfpbs-sample-forms-provided-in-regulation-b/ · retiro: https://www.govinfo.gov/content/pkg/FR-2025-05-12/pdf/2025-08286.pdf · lista de guías retiradas: https://www.consumerfinance.gov/compliance/guidance/withdrawn-guidance/
- **Contenido verificado:** establecía que los acreedores no cumplen con la Regulation B si dan razones de rechazo demasiado amplias o vagas, y que no pueden limitarse a la lista de razones de los formularios modelo si esas no reflejan la razón principal del rechazo.
- **Notas:** (1) la URL de la tesis (`…/circular-2023-03/`) **devuelve 404**. (2) La tesis la presenta como vigente para justificar SHAP; la obligación de dar razones específicas sigue existiendo en la propia ECOA (§1691(d), ver W8) y en la Regulation B, que puede ser mejor sustento. (3) Hay reportes no confirmados de una "Circular 2026-03"; no se encontró en el sitio oficial.
- **Tags:** `#marco-legal` `#explicabilidad`

## Fichas W10–W16 (actualizadas el 2026-09-25 con archivos aportados por el autor)

Estas siete fuentes quedaron pendientes en la primera pasada. El autor aportó los PDF o HTML de cinco, el enlace de una y confirmó que una no existe. Mantienen su ID W para no romper las referencias desde `estado/verificacion-citas.md`.

### W10. ISO/IEC 42001:2023 — Information technology — Artificial intelligence — Management system `[vista previa oficial; no es la norma completa]`
- **Archivo:** `docs/ISO-IEC-42001-2023.pdf` (14 pp.)
- **Emisor:** ISO / IEC
- **Fechas:** primera edición, 2023-12. Referencia: ISO/IEC 42001:2023(E).
- **Qué contiene el archivo:** es la **vista previa pública de iTeh Standards** ("Document Preview"): portada, índice, prólogo, introducción, alcance, referencias normativas, términos y el inicio de la cláusula 4. Las cláusulas 5–10 y los anexos (controles) no están incluidos; la norma completa es de pago.
- **Resumen (según la introducción y el alcance):** Especifica requisitos y da orientación para establecer, implementar, mantener y mejorar continuamente un **sistema de gestión de IA (AIMS)** en organizaciones que proveen o usan sistemas de IA. La introducción señala retos propios de la IA: decisiones automáticas poco transparentes o explicables, sistemas diseñados a partir de datos y no de lógica codificada, y sistemas con aprendizaje continuo que cambian de comportamiento en uso. Pide integrar en los procesos la gestión de riesgos y de aspectos de confiabilidad como seguridad, **fairness**, transparencia y calidad de datos a lo largo del ciclo de vida, y permite generar evidencia de responsabilidad y rendición de cuentas.
- **Relación con la tesis (2.3.3):** respalda la idea general de gestionar objetivos de equidad y riesgos de la IA. Lo que la tesis afirma sobre "documentar y auditar sistemáticamente los objetivos de equidad" y "registros de trazabilidad reproducibles" corresponde a cláusulas que **no están en la vista previa**, así que no se pudo verificar al detalle.
- **Nota:** la tesis enlaza https://www.iso.org/standard/81230.html; la página actual del estándar es https://www.iso.org/standard/42001.
- **Tags:** `#marco-legal`

### W11. Decreto Supremo N° 115-2025-PCM — Reglamento de la Ley N° 31814 `[norma, PDF oficial de El Peruano]`
- **Archivo:** `docs/7133522-decreto-supremo-n-115-2025-pcm.pdf` (separata de Normas Legales, El Peruano)
- **Emisor:** Presidencia del Consejo de Ministros (Perú)
- **Fechas:** dado el 8-sep-2025; publicado en El Peruano el martes **9-sep-2025**. Vigencia: 90 días hábiles después de la publicación, salvo la Primera, Segunda, Cuarta y Quinta Disposiciones Complementarias Finales, que rigen desde el día siguiente.
- **Resumen:** Reglamenta la ley peruana que promueve el uso de la IA. Define el **sesgo algorítmico** (Art. 6.e) y fija principios rectores, entre ellos la **no discriminación** (Art. 7.a: medidas para prevenir, mitigar y corregir resultados discriminatorios o sesgados) y la transparencia (Art. 7.i). Clasifica los usos por riesgo (Art. 22) y define obligaciones para los sistemas de riesgo alto: transparencia algorítmica ante el usuario (Art. 25), registro actualizado (Art. 31.1), evaluación de impacto (Arts. 30 y 32) y supervisión humana.
- **Artículos clave para la tesis:**
  - **Art. 24.1(g):** se considera de **riesgo alto** el uso de IA para "determinar la evaluación crediticia de personas; salvo si el uso de la IA, es para la detección de fraude financiero". Es el equivalente peruano del Anexo III 5(b) del AI Act, y **la tesis no lo cita**: sería el argumento más directo para el caso peruano.
  - **Art. 31.1** (obligaciones de las organizaciones): en sistemas de riesgo alto, "mantener un registro actualizado y accesible, con enfoque preventivo, sobre los principios del funcionamiento del sistema, las fuentes de datos utilizadas y la lógica del algoritmo, los impactos sociales y éticos esperados". Coincide con lo que la tesis afirma en el Anexo B y en 3.6.4.
  - **Evaluación de impacto:** es **obligatoria** para entidades de la Administración Pública (Art. 30, Título VI Cap. I) pero **voluntaria** para organizaciones privadas (Art. 32.1, Título VI Cap. II). Para una Fintech privada aplica el Art. 32.
- **Tags:** `#marco-legal` `#credit-scoring` `#trazabilidad-RDF`

### W12. Systematic Reviews in the Social Sciences: A Practical Guide `[libro, PDF aportado por el autor; revisión parcial]`
- **Archivo:** `docs/guide-of-systematic-reviews-in-social-sciences.pdf` (351 pp.)
- **Autor(es):** Mark Petticrew, Helen Roberts
- **Año:** 2006
- **Publicación:** Blackwell Publishing (Malden, MA / Oxford). ISBN-13 978-1-4051-2110-1; DOI de la edición electrónica 10.1002/9780470754887.
- **Revisión:** por indicación del autor, solo se revisó la portada y el pasaje de PICOC.
- **Resumen (del pasaje revisado):** En el Cap. 2 ("Starting the review", sección sobre cómo formular la pregunta de revisión), el libro presenta el modelo PICO y lo extiende con el Contexto: **Figura 2.2, "PICOC: Five components of a clear systematic review question"** (Population, Intervention, Comparison, Outcomes, Context), pp. 44–45. Respalda el uso de PICOC en 3.3 y 3.4 de la tesis.
- **Tags:** `#revision-sistematica`

### W13. Design by Fairness Contract for Machine Learning Pipeline (Nguyen, Ahmed, Biswas & Rajan, 2025, ICSE) `[NO EXISTE — confirmado por el autor]`
- **Búsqueda:** no aparece en la lista de artículos aceptados de ICSE 2025, ni en la página del laboratorio de los autores, ni en arXiv. El autor confirmó el 2026-09-25 que la publicación no existe.
- **Recomendación:** citar en su lugar el **Capítulo 3 de la tesis doctoral de Nguyen (2024)**, que se titula exactamente "Design by Fairness Contract for Machine Learning Pipeline" y está en `docs/` (ficha 9). Hay que corregir en la tesis las 8 apariciones de "Nguyen et al., 2025" en los Caps. 1, 3 y 4 (incluidas las 2 citas truncadas "(Nguyen, 20 Nguyen et al., 2025)") y la entrada de la lista de referencias.
- **Tags:** `#contratos-equidad`

### W14. AI Governance in MLOps: Compliance, Fairness, and Transparency `[PDF aportado por el autor; calidad dudosa]`
- **Archivo:** `docs/AI Governance in MLOps Compliance, Fairness, and Transparency.pdf` (4 pp.)
- **Autor(es):** "Dhaenens F." (solo inicial; sin afiliación)
- **Fecha:** "Date: 11/10/2024" según el PDF. No indica revista, conferencia, editorial ni DOI.
- **Resumen:** Texto breve que plantea integrar la gobernanza de IA en MLOps en tres ejes: cumplimiento regulatorio (menciona GDPR y la Algorithmic Accountability Act), fairness (repesado, *adversarial debiasing*, monitoreo continuo de sesgo por subgrupos) y transparencia (SHAP, LIME, contrafactuales, registro y versionado de modelos). Dice evaluar MLflow, TFX y Kubeflow, y concluye que la gobernanza es un requisito de un MLOps responsable.
- **Advertencias de calidad (importantes antes de citarlo):**
  - Afirma usar un método mixto con "evaluación cuantitativa" y comparación experimental, pero **no reporta ningún dato, tabla, métrica ni resultado numérico**.
  - La lista de referencias tiene 14 entradas con **duplicados** (la misma obra repetida 2–3 veces) y **dos referencias ajenas al tema** (un estudio odontológico sobre microfiltración en restauraciones dentales).
  - No tiene venue, DOI ni afiliación del autor.
  - Estos rasgos son típicos de documentos no revisados por pares o de baja calidad. **Se recomienda no usarlo como sustento** (la tesis lo cita en 1.1.3 y en el Anexo B) o reemplazarlo por una fuente revisada, por ejemplo Stoyanovich et al. (2022) (W1) u Ogrizović et al. (2024) (ficha 23).
- **Tags:** `#mlops`

### W15. Data Quality for Building Production ML Systems `[página web guardada como HTML por el autor]`
- **Archivo:** `docs/Data Quality for Building Production ML Systems _ by Christian Kästner _ Medium.html` (y su carpeta `_files/` con imágenes)
- **Autor(es):** Christian Kästner (Carnegie Mellon University)
- **Fecha:** publicado el **22-feb-2021** en Medium. El texto indica "[This chapter has been substantially updated October 2023]": la versión guardada es la actualizada, no la de 2021.
- **Fuente:** https://ckaestne.medium.com/data-quality-for-building-production-ml-systems-2e0cc7e6113f
- **Resumen:** Capítulo del libro/curso *Machine Learning in Production* (CMU) sobre calidad de datos en sistemas de ML en producción, con un caso de estudio de gestión de inventario. Cubre criterios de calidad (exactitud, completitud, consistencia, actualidad; cita ISO/IEC 25012), la diferencia entre datos imprecisos (ruido) e inexactos (error sistemático), el análisis exploratorio, la validación con **esquemas de datos**, el *data linting*, el monitoreo de **drift**, y la calidad de datos como tema de todo el sistema (documentación, procedencia, gestión).
- **Relación con la tesis:** la tesis lo cita en 2.1.1 solo para definir el vector de características X. El texto respalda mejor la **QA Gate 1** (validación de esquema e integridad con Pandera) y el monitoreo de drift de la Zona 3.
- **Nota:** el HTML es suficiente para verificar el contenido; no hace falta PDF.
- **Tags:** `#QA-Gate-1` `#monitoreo-drift` `#preprocesamiento`

### W16. ¿Qué es la gestión de riesgos de modelos? `[fuente web, sin PDF local]`
- **Autor(es):** Rina Diane Caballar, Cole Stryker (IBM)
- **Fecha:** 15-ago-2024
- **Fuente:** https://www.ibm.com/mx-es/think/topics/model-risk-management (enlace aportado por el autor; consultada el 2026-09-25). La tesis solo pone https://www.ibm.com/.
- **Resumen:** Define la gestión de riesgos de modelos (MRM) como el proceso de identificar, medir y controlar el riesgo de los modelos a lo largo de su ciclo de vida. Identifica cinco fuentes de riesgo: datos (errores, incompletitud y **sesgo**), supuestos y variables, metodología, implementación y uso o interpretación. Advierte que, si no se evalúa el sesgo de los datos de entrenamiento, los modelos de IA pueden reproducirlo y perpetuarlo. Toma como referencia la guía SR 11-7 de la Reserva Federal y la OCC, y describe pasos como validación, monitoreo continuo y gobernanza.
- **Nota:** en la referencia de la tesis conviene poner los autores (Caballar & Stryker, 2024) en lugar de "IBM (s.f.)", además de la URL exacta.
- **Tags:** `#monitoreo-drift` `#credit-scoring`
