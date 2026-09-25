# Verificación de citas (Tarea 2 de AGENTS.md)

- **Fecha:** 2026-09-25
- **Versión revisada:** `20202117_SergioChumbimuni_LuisVives_E2.pdf` (transcrito en `capitulos/`)
- **Método:** se extrajeron todas las citas `(Autor, año)` y `Autor (año)` de `capitulos/01` a `05` y `07`, y se compararon con (1) la lista de `capitulos/06-referencias.md` y (2) los PDFs de `bibliografia/docs/` (metadatos en `bibliografia/index.md`).
- **Criterio:** si el autor o el año no coinciden exactamente, se marca como discrepancia para revisión manual. **No se corrigió nada en los capítulos**: la transcripción refleja el PDF tal cual.

---

## A. Citas en el texto sin entrada en la lista de referencias

| Cita en el texto | Veces | Dónde | Observación |
|---|---|---|---|
| (Wagner, 2024) | 3 | Cap. 3 (3.1, 3.6.1, 3.6.4) | No hay ninguna referencia de Wagner. |
| (Zafar et al., 2019) | 1 | Cap. 2 (2.1.3, regla de los cuatro quintos) | No está en referencias. |
| (Anders et al., 2020) | 1 | Cap. 2 (2.1.1) | No está en referencias. |

## B. Citas cuyo autor o año no coincide con la referencia

| Cita en el texto | Referencia más cercana | Diferencia |
|---|---|---|
| (Adebayo & Kegal, 2016) — Cap. 2 | Adebayo, J., & **Kagal**, L. (2016) | Apellido escrito distinto. |
| (IJAIDSML, 2020) — Cap. 1 | **Immaneni, J.** (2020). *Building MLOps Pipelines in Fintech…* International Journal of Artificial Intelligence, Data Science, and Machine Learning | Se cita por la sigla de la revista y no por el autor. |
| (AWS, 2022) — Cap. 1 y (Amazon Web Services, 2022) — Cap. 3 | Amazon Web Services. (2022) | Dos formas distintas de citar la misma referencia. |
| (Reglamento IA UE, 2024) — Caps. 1 y 2 (12 veces) | Parlamento Europeo y Consejo de la Unión Europea. (2024) | La etiqueta de la cita no coincide con el autor de la referencia. En el Anexo B sí se cita como (Parlamento Europeo y Consejo de la Unión Europea, 2024). |
| (ECOA, 1974) y (Equal Credit Opportunity Act [ECOA], 1974) | Equal Credit Opportunity Act, 15 U.S.C. § 1691 et seq. (1974) | Dos formas de citar; revisar formato APA de normas. |
| (PCM, 2025), (Presidencia del Consejo de Ministros [PCM], 2025), (Presidencia del Consejo de Ministros, 2025) | Presidencia del Consejo de Ministros. (2025) | Tres variantes. APA admite introducir la sigla la primera vez; revisar consistencia. |
| (Nguyen, 20 Nguyen et al., 2025) — Cap. 1 (1.3.2 Fase 2) y Cap. 4 (4.3.2) | Nguyen (2024) y Nguyen et al. (2025) | Cita truncada/pegada; probablemente debía ser "(Nguyen, 2024; Nguyen et al., 2025)". |

## C. Referencias cuyos datos no coinciden con el PDF en `bibliografia/docs/`

| Referencia en la tesis | Lo que dice el PDF | Diferencia |
|---|---|---|
| Li, Y., et al. (2023). *Causality-Aided Trade-off Analysis*. [Manuscrito de investigación]. HKUST. — citada como (Li et al., 2023) en Cap. 2 (CDS) | Ji, Z., Ma, P., Wang, S., & Li, Y. *Causality-Aided Trade-off Analysis for Machine Learning Fairness*. arXiv:2305.13057v3 (2023) | **Primer autor distinto** (Ji, no Li); título incompleto. La cita correcta sería (Ji et al., 2023). |
| Vasquez, J., Domeniconi, C., & Rangwala, H. (**2023**). *DispaRisk…* — citada como (Vasquez et al., 2023) | arXiv:2405.12372 (mayo **2024**; v3 de mayo 2025) | **Año distinto.** |
| Amazon Web Services. (2022). *Amazon SageMaker Model Monitor* [Documento técnico]. AWS AI Team. | Nigenda, D., Karnin, Z., Zafar, M. B., Ramesha, R., Tan, A., Donini, M., & Kenthapadi, K. *Amazon SageMaker Model Monitor: A System for Real-Time Insights into Deployed Machine Learning Models*. arXiv:2111.13657v3 (2022) | **Autoría distinta**: el PDF es un paper con autores personales, no un documento de AWS. |
| Reda et al. (2025). *Hybrid MLOps framework for automated lifecycle management*. Scientific Reports, 15(1). | Título completo: *…automated lifecycle management **of adaptive phishing detection models*** | Título incompleto. Volumen/DOI no verificables desde el PDF (el PDF no los muestra). |
| Zhu et al. (2025). *Stress-Testing ML Pipelines with Adversarial Data Corruption* [Reporte Técnico]. | arXiv:2506.01230v1 (2025) | Se describe como "reporte técnico"; es un preprint de arXiv. |
| Grafberger et al. (2022). The VLDB Journal, **31(5), 1103–1126**. | DOI 10.1007/s00778-021-00726-w; el PDF no muestra volumen ni páginas | Volumen/páginas no verificables desde el PDF; sería bueno agregar el DOI. |
| Russo et al. (2024). IEEE Access, **12, 96821-96847**. | Versión aceptada del autor, DOI 10.1109/ACCESS.2024.3427388 | Volumen/páginas no verificables desde el PDF. |
| Lin et al. (**s.f.**). *Preeclampsia Predictor…* Columbia University. | medRxiv, 9-jun-2022, DOI 10.1101/2022.06.08.22276107 | El PDF sí tiene fecha y DOI. |

## D. Referencias en la lista que no se citan en el texto

| Referencia | Observación |
|---|---|
| Lin et al. (s.f.). *Preeclampsia Predictor with Machine Learning…* | Está en la lista de referencias pero no hay ninguna cita a "Lin" en los capítulos. |

## E. Referencias incompletas

| Referencia | Qué falta |
|---|---|
| Dhaenens, F. (2024). AI Governance in MLOps: Compliance, Fairness, and Transparency | Sin tipo de documento, editorial/revista ni URL. Tampoco hay PDF en `bibliografia/docs/`. |
| Kazmierczak, J., Salama, K., & Huerta, V. (2024)… "Recuperado de la documentación de Google Cloud." | Sin URL. |
| IBM. (s.f.)… "Recuperado de https://www.ibm.com/" | URL genérica de la página principal, no del artículo. |

## F. PDFs de `bibliografia/docs/` y dónde se citan

| PDF | Cita en la tesis | Capítulos donde aparece |
|---|---|---|
| (Un) Fairness Along the AI Pipeline (Black, 2022, tesis CMU) | **No citado.** La tesis cita *Black & Fredrikson (2021), Leave-one-out unfairness* (FAccT), que es otro trabajo y no está en `docs/`. | — |
| Amazon SageMaker Model Monitor | (AWS, 2022) / (Amazon Web Services, 2022) | 1, 3 |
| Cascaded Debiasing | (Ghai et al., 2022) | 1 |
| Causality-Aided Trade-off | (Li et al., 2023) — ver discrepancia de autor | 2 |
| Data distribution debugging… | (Grafberger et al., 2022) | 3 |
| DispaRisk | (Vasquez et al., 2023) — ver discrepancia de año | 3, Anexo B |
| Employing Hybrid AI Systems… | (Russo et al., 2024) | 1, 2, 3, 4 |
| Fair Preprocessing | (Biswas & Rajan, 2021) | 1, 2, 3, 4, Anexo B |
| Fairness specification and repair… (tesis Nguyen) | (Nguyen, 2024) | 2, 3, 4 |
| Hybrid MLOps framework… | (Reda et al., 2025) | 2, 3 |
| Preeclampsia predictor… | **En referencias pero no citado en el texto** | — |
| Proactively Screening MLP with ARGUSEYES | (Schelter et al., 2023) | 3 |
| Stress-Testing ML Pipelines… | (Zhu et al., 2025) | 1, 2, 3 |
| Towards an Ontology-Driven Approach… | (Russo & Vidal, 2025) | 1, 2, 3, 4, Anexo B |
| Trustworthy AI in Cloud MLOps | (Avuthu, 2021) | 1, 2, 3 |
| What If You Could Stop Re-Implementing… | (Grafberger et al., 2023) | 3 |

**Candidatos a revisar (no eliminar sin confirmar):** `(Un) Fairness Along the AI Pipeline…` (no citado) y `Preeclampsia predictor…` (en referencias, sin cita en el texto).

## G. Fuentes citadas sin PDF en `bibliografia/docs/`

Nguyen et al. (2025, ICSE), Hardt et al. (2016), Black & Fredrikson (2021), Mehrabi et al. (2021), Menon & Williamson (2018), Bartlett et al. (2022), Adebayo & Kagal (2016), Angwin et al. (2016), Stoyanovich et al. (2022), Ogrizović et al. (2024), Immaneni (2020), Byanjankar et al. (2015), Demirgüç-Kunt et al. (2022), Kästner (2021), Kazmierczak et al. (2024), Dhaenens (2024), Petticrew & Roberts (2006), MathWorks (s.f.), IBM (s.f.), BCBS (2025), CFPB (2023), ECOA (1974), Reglamento (UE) 2024/1689, D.S. 115-2025-PCM, ISO/IEC 42001:2023.

Algunas son normas o páginas web y no necesitan PDF. Las que más convendría tener, porque sostienen decisiones de diseño, son **Nguyen et al. (2025)** (contratos de equidad), **Hardt et al. (2016)** (EOD) y **Bartlett et al. (2022)** (regla de los cuatro quintos en crédito).

---

## H. Hallazgos al resolver las referencias faltantes (2026-09-25, skill `resolver-referencias`)

Detalle y fuentes en `bibliografia/index.md` (fichas 17–25 y W1–W16). No se corrigió nada en los capítulos.

| Referencia | Hallazgo | Gravedad |
|---|---|---|
| CFPB Circular 2023-03 (Caps. 2 y 4) | **Retirada por la CFPB el 12-may-2025** (Federal Register Vol. 90 n.º 90). La tesis la presenta como vigente para justificar SHAP. Además, la URL citada devuelve 404. | Alta |
| Nguyen, Ahmed, Biswas & Rajan (2025), ICSE | No se encontró en ICSE 2025 ni en la web de los autores. Posiblemente se refiere al Cap. 3 de la tesis de Nguyen (2024). | Alta (sostiene los contratos de equidad) |
| Reglamento (UE) 2024/1689 | Modificado por el Reglamento (UE) 2026/1744 (8-jul-2026, Digital Omnibus). Según fuentes secundarias, las obligaciones de alto riesgo del Anexo III pasan al 2-dic-2027. La tesis no lo menciona. | Media |
| Stoyanovich et al. (2022) | DOI incorrecto: la tesis pone 10.1145/3488716 (otro artículo); el correcto es 10.1145/3488717. | Media |
| MathWorks (s.f.) | La página no presenta la fórmula ECL = PD × LGD × EAD que la tesis le atribuye. | Media |
| Demirgüç-Kunt et al. (2022) | El informe Findex no trata datos alternativos ni scoring; la tesis lo usa para esa afirmación en 2.1.2. | Media |
| Angwin et al. (2016) | Se cita para la equidad individual; el artículo trata disparidades de error entre grupos. | Baja |
| BCBS (2025) | El documento d591 es una consulta pública, no la versión final de los principios. | Baja |
| Bartlett et al. (2022) | Solo se consiguió el working paper de 2019; verificar las cifras contra la versión JFE 2022. | Baja |
| Kazmierczak et al. (2024) | La referencia no tiene URL; el título en español de la página oficial difiere. | Baja |
| IBM (s.f.) | La URL es solo la página principal; no se identificó el artículo. | Baja |
| Dhaenens (2024), Kästner (2021), D.S. 115-2025-PCM, ISO/IEC 42001, Petticrew & Roberts (2006) | No se pudo verificar el contenido (acceso bloqueado, norma o libro de pago); solo metadatos o fuentes secundarias. | Pendiente manual |

## I. Segunda pasada con archivos aportados por el autor (2026-09-25)

| Referencia | Hallazgo | Gravedad |
|---|---|---|
| Nguyen et al. (2025), ICSE | **El autor confirmó que no existe.** Reemplazar por Nguyen (2024), Cap. 3 (mismo título). Hay que corregir 8 apariciones en los Caps. 1, 3 y 4 y la referencia. | Alta |
| Dhaenens (2024) | El PDF no tiene venue, DOI ni afiliación; dice presentar resultados cuantitativos pero no muestra ninguno; sus referencias tienen duplicados y dos citas de odontología. Se recomienda no usarlo como sustento (se cita en 1.1.3 y en el Anexo B). | Media |
| D.S. 115-2025-PCM | El **Art. 24.1(g)** clasifica como de riesgo alto la evaluación crediticia de personas; la tesis no lo cita y es su mejor argumento local. El Art. 31.1 respalda el registro que la tesis menciona. La evaluación de impacto es voluntaria para privados (Art. 32), no obligatoria. | Media (oportunidad) |
| ISO/IEC 42001 | Solo se tiene la vista previa (hasta la cláusula 4). Las afirmaciones de 2.3.3 sobre documentar objetivos de equidad y la trazabilidad no se pudieron verificar en el texto. | Baja |
| Kästner (2021) | La versión disponible fue actualizada en octubre de 2023. Se cita para definir X (2.1.1), pero respalda mejor la QA Gate 1 (esquemas) y el monitoreo de drift. | Baja |
| IBM (s.f.) | La página existe: Caballar & Stryker (15-ago-2024), https://www.ibm.com/mx-es/think/topics/model-risk-management. Corregir autoría, fecha y URL en la referencia. | Baja |
| Petticrew & Roberts (2006) | Verificado: PICOC está en la Figura 2.2, pp. 44–45. | — |
