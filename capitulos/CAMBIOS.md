# Cambios respecto del PDF E2

- **Fecha:** 2026-09-25
- **Base:** transcripción literal de `20202117_SergioChumbimuni_LuisVives_E2.pdf`. El PDF sigue siendo la referencia del texto original.
- **Criterio:** solo se modificaron partes que **no afectan el producto de software**: citas y referencias, marco legal, erratas, numeración y coherencia del texto. No se tocó la arquitectura (Zonas, C4), los contratos C1/C2/C3 ni sus umbrales, la ontología, el stack, el dataset ni la decisión local/nube.
- **Evidencia de cada corrección:** `bibliografia/index.md` (fichas) y `estado/verificacion-citas.md`.
- **Pendientes marcados en el texto:** comentarios HTML `<!-- PENDIENTE: ... -->` en el Cap. 2.

## 1. Citas y referencias

| # | Dónde | Antes | Después | Motivo |
|---|---|---|---|---|
| 1 | Caps. 1, 3, 4 (8 veces) | (Nguyen et al., 2025) y "(Nguyen, 20 Nguyen et al., 2025)" | (Nguyen, 2024) | La publicación de ICSE 2025 no existe (confirmado por el autor); el contenido está en el Cap. 3 de la tesis de Nguyen (2024). Se eliminó la referencia. |
| 2 | 1.1.3 y Anexo B | (Dhaenens, 2024) | (Stoyanovich et al., 2022). En 1.1.3 se precisó la frase: "…concentrando el análisis en la etapa final en lugar de extenderlo a todo el ciclo de vida de los datos y del modelo" | Dhaenens (2024) no tiene venue ni datos y su lista de referencias tiene errores (ficha W14). Stoyanovich et al. sostiene esa idea en su abstract. Se eliminó la referencia. |
| 3 | Caps. 1 y 3 | (AWS, 2022), (Amazon Web Services, 2022) | (Nigenda et al., 2022) | El documento tiene autores con nombre (arXiv:2111.13657). |
| 4 | Caps. 1 y 3 (6 veces) | (IBM, s.f.) | (Caballar & Stryker, 2024) | Autores, fecha y URL reales del artículo de IBM. |
| 5 | Cap. 1 | (IJAIDSML, 2020) | (Immaneni, 2020) | Se cita por autor, no por revista. |
| 6 | 2.1.4 (3 veces) | (Li et al., 2023; …) | (Ji et al., 2023; …) | El primer autor es Ji. Se verificó que el paper define y usa la CDS. |
| 7 | Caps. 3 y Anexo B | Vasquez et al. (2023) | Vasquez et al. (2024) | El preprint es de 2024. |
| 8 | 2.1.2 | (Adebayo & Kegal, 2016; …) | (Adebayo & Kagal, 2016; Angwin et al., 2016; …) | Corrige el apellido. Angwin se reubicó aquí como ejemplo empírico de resultados discriminatorios por subgrupo. |
| 9 | 2.1.1 | Y definida con (Angwin et al., 2016; MathWorks, s.f.) | (MathWorks, s.f.) | ProPublica no trata la definición de la etiqueta. |
| 10 | 2.1.4 | "individuos similares…" (Angwin et al., 2016; Mehrabi et al., 2021) (2 veces) | (Mehrabi et al., 2021) | ProPublica trata disparidades entre grupos, no equidad individual. |
| 11 | 2.1.1 | Proxies: (Anders et al., 2020; MathWorks, s.f.) | Se agrega "pues el modelo puede depender de los atributos protegidos de forma indirecta a través de otras variables" (Adebayo & Kagal, 2016) | Anders et al. (2020) no estaba en referencias; MathWorks no trata sesgo. |
| 12 | 2.1.1 | Imperativo legal (MathWorks, s.f.) | (Reglamento IA UE, 2024; PCM, 2025) | MathWorks no respalda esa afirmación. |
| 13 | 2.1.1 | X definido con (MathWorks, s.f.; Kästner, 2021) | (MathWorks, s.f.) | Kästner se reubicó en 2.2.1, donde sí respalda el texto (validación de datos y esquemas en CI). |
| 14 | 2.1.1 | Fórmula ECL atribuida a (MathWorks, s.f.; BCBS, 2025); "se rige de manera uniforme" | "En su forma paramétrica más difundida…", sin atribución, más un comentario PENDIENTE | MathWorks no presenta la fórmula. No se encontró una fuente oficial legible para citarla. |
| 15 | 2.1.1 | Párrafo de Basilea ("directrices… deben mantener…") y viñetas PD/LGD/EAD con (BCBS, 2025) | Se reescribió según el contenido verificado del documento consultivo d591 (cuatro áreas); las viñetas quedan con (MathWorks, s.f.) | d591 es una consulta pública; no se verificó que defina PD, LGD y EAD. |
| 16 | 2.1.2 | Datos alternativos y sesgo rural atribuidos a (Demirgüç-Kunt et al., 2022) | Findex se cita solo para el dato que respalda (1 400 millones de adultos sin cuenta y brechas de acceso); lo de los datos alternativos queda como argumento propio y en condicional ("puede perpetuarse") | El informe Findex no trata datos alternativos ni scoring. |
| 17 | 2.1.3 y 4.3 (C3, 4.3.2 C) | Regla de los cuatro quintos (EEOC) con (Russo & Vidal; Zafar et al., 2019; Biswas & Rajan) o (Bartlett et al., 2022) | (Uniform Guidelines on Employee Selection Procedures, 1978) y, en 2.1.3, (Reda et al., 2025). Se aclara que la regla nació en la selección de personal | Zafar et al. (2019) no estaba en referencias; se verificó el texto en 29 C.F.R. § 1607.4(D). **El umbral 0.80 no cambia.** |
| 18 | Cap. 3 (3 veces) | (Wagner, 2024) | (Reglamento IA UE, 2024) | Wagner (2024) no estaba en referencias; las afirmaciones son sobre la Ley de IA. |
| 19 | Referencias | Varias | Corregidas: Nigenda et al., Ji et al., Vasquez 2024, Reda (título completo), Kazmierczak (título y URL), Zhu (arXiv), Caballar & Stryker (URL), BCBS [Documento consultivo], DOI de Stoyanovich (3488716 → **3488717**), DOI de Grafberger, URL vigente de la CFPB y nota de retiro. **Agregadas:** Reglamento (UE) 2026/1744, CFPB (2025, retiro de guías) y Uniform Guidelines (1978). **Eliminadas:** Nguyen et al. (2025) y Dhaenens (2024). | Ver fichas de `bibliografia/index.md`. |

## 2. Marco legal

| # | Dónde | Cambio | Motivo |
|---|---|---|---|
| 20 | 2.3.1 | "Evaluación de impacto… (Art. 29a / 96)… entidades de servicios financieros" → "(Art. 27)… responsables del despliegue de los sistemas del Anexo III 5(b)" | Art. 27 es la numeración del texto final (verificado en el AI Act Service Desk); 29a era la del borrador. |
| 21 | 2.3.1 | Nuevo párrafo sobre el Reglamento (UE) 2026/1744 (*Digital Omnibus on AI*), más un comentario PENDIENTE sobre las fechas | La modificación está confirmada en EUR-Lex; las nuevas fechas de aplicación solo se vieron en fuentes secundarias. |
| 22 | 2.3.2 | La explicabilidad ahora se apoya en la ECOA (§1691(d)) y la Regulation B; la Circular 2023-03 se menciona como precisión de la CFPB **retirada el 12-may-2025** | La circular fue retirada; la obligación sigue en la ley. |
| 23 | 4.5.2, 4.5.3, 4.5.5 | Menciones a "la circular de la CFPB (CFPB, 2023)" → ECOA y Regulation B (ECOA, 1974) | Coherente con el punto 22. |
| 24 | 2.3.3 | Texto sobre ISO/IEC 42001 reescrito según la introducción y el alcance de la norma | Se quitaron afirmaciones no verificables en la vista previa ("exige documentar y auditar sistemáticamente los objetivos de equidad…"). |
| 25 | **2.3.4 (nueva)** | Sección sobre el Reglamento peruano de IA (D.S. N.° 115-2025-PCM): definición de sesgo (art. 6), no discriminación (art. 7.a), **scoring = riesgo alto (art. 24.1.g)**, transparencia (art. 25), registro (art. 31.1), evaluación de impacto voluntaria para privados (arts. 30 y 32) | El marco legal no tenía la norma peruana, que es la más directamente aplicable. |
| 26 | 1.1.1 | Una oración sobre el art. 24.1(g) del D.S. 115-2025-PCM junto al AI Act | Mismo motivo. |

## 3. Coherencia, numeración y erratas

| # | Dónde | Cambio |
|---|---|---|
| 27 | Cap. 3 e Índice | La segunda sección "3.6 Resultados de revisión" pasa a 3.7 (subsecciones 3.7.1–3.7.4) y "3.7 Conclusiones" a 3.8 |
| 28 | 3.5 (CI-1) | "entre el año 2019 y 2026" → "entre el año 2020 y 2026", para coincidir con el cribado y la Figura 3 (se excluyó lo anterior a 2020). **Confirmar** que esto refleja el proceso real. |
| 29 | Índice | Se agregan 2.3.4, 4.4.1–4.4.4 (antes decía "4.3.1") y el Capítulo 5 |
| 30 | Anexo B | Tablas 10, 11 y 12 → 14, 15 y 16 (evita duplicar la numeración del Cap. 4) |
| 31 | 4.3.4 | "(ver Tabla 3)" → "(ver Tabla 2)" |
| 32 | 4.2.3 | Se agrega la Figura 9 (Zona 4) a la lista de diagramas de componentes |
| 33 | 4.2.1 (Zona 2) | "DPD (Demographic Parity Difference)" → "SPD (Diferencia de Paridad Estadística, también denominada Demographic Parity Difference)", para usar el mismo nombre que 2.1.3 y el C3. El YAML (`demographic_parity_difference`) no cambia. |
| 34 | 4.5.3 | "correlación condicional" → "información mutua condicional" (así está definido el C2) |
| 35 | 4.5.3 | `fno:ExecutionRun` y `fno:QAGate` → `fair:GateExecution` y `fair:FairnessContract` (clases que sí existen en la Tabla 12) |
| 36 | 4.5.3 | "la literatura de Nguyen se limita al espacio de entrenamiento aislado de AutoML" → descripción fiel: contratos y verificadores sobre el programa de ML en desarrollo y ejecución, sin CI/CD ni monitoreo en producción |
| 37 | 5.1 | R.3.1 / R.3.2 / R.3.3 → R.E.3.1 / R.E.3.2 / R.E.3.3 |
| 38 | 1.3.1 | "Contrato 1A" → "Contrato C1"; "el esquema defin." → "el esquema definido" |
| 39 | Varios | Erratas: "calificacion" → "calificación"; "sistemas ." → "sistemas."; "auditalibilidad" → "auditabilidad" (2.3.1, 4.4.2); "justabilidad" → "justificabilidad"; ". ." → "."; "),." → ")."; "sesgos ," → "sesgos,"; "Técnologico" → "Tecnológico"; "cuatroalgoritmos" → "algoritmos"; "son asumidos" → "es asumido"; se quitó el título duplicado "Viabilidad tecnica" (Anexo B) |

## 4. No modificado a propósito (afecta el software o requiere decisión del autor)

| Tema | Por qué no se tocó |
|---|---|
| Ejemplo Turtle con **German Credit** (4.4.3) vs. "Fintech real" (Davronov) | Es parte del diseño de la ontología y del caso de estudio. |
| **Local vs. nube** (4.2.2 vs. Anexo B, Viabilidad técnica y Recursos) | Define dónde corre el sistema. |
| Alcance de las QA Gates "durante la fase de preprocesamiento" (Anexo B, Alcance) vs. C3 sobre el modelo | Describe el alcance del producto. |
| Riesgo con Adult Income / COMPAS (Anexo B) | Afecta el plan de validación experimental. |
| Propiedades de la ontología usadas en los ejemplos pero no definidas (Tabla 13) | Es diseño de la ontología. |
| Figura 2 vs. Figura 5 (dos versiones del diagrama de contenedores) y la Zona 3 etiquetada "DVC - Evidently AI" | Son imágenes del diseño; hay que rehacerlas en Lucidchart. |
| Erratas dentro de las figuras ("evaluén", "comparativoa", "IEE Explore", "Reentranamiento") | Están en las imágenes. |
| Textos de los indicadores citados en 4.2.4, 4.3.4 y 4.4.4 que no coinciden con la Tabla 2 | Hay que decidir cuál versión del indicador es la vigente (compromiso del proyecto). |
| Cronograma: "109 días" en el texto vs. 125 en la Tabla 15 | Depende del cronograma real (Google Sheets). |
| Lin et al. (Preeclampsia) en referencias sin cita en el texto | Decidir si es uno de los 22 estudios primarios (entonces citarlo) o si se elimina. |
| Fórmula ECL sin fuente (2.1.1) y fechas del Reglamento 2026/1744 (2.3.1) | Marcados como PENDIENTE en el texto. |

---

# 5. Rediseño del producto (2026-09-25)

Aplicación de `estado/propuesta-diseno.md`, **aprobada por el autor**. A diferencia de las secciones 1–4 (correcciones editoriales), aquí **sí cambia el diseño del producto**.

## 5.1 Resumen por capítulo

| Capítulo | Alcance del cambio |
|---|---|
| **1** | O2, O3 y O4 reformulados (contratos declarativos, motor de contratos, datasets reales). R.E.2.2, R.E.3.1–3.3 y R.E.4.1–4.2 actualizados. **Tablas 2, 3 y 4:** nuevos medios de verificación e indicadores (la Tabla 2 ahora coincide textualmente con lo que cita el Cap. 4). **Tabla 5**, **1.3.1 Herramientas** (sin InterpretME ni AIF360; se agregan PROV-O, DQV, SHACL, pySHACL, Oxigraph y Fairlearn como biblioteca única de equidad; MLflow como canal de linaje; SHAP para razones de rechazo; repositorios privados) y **1.3.2 Fases 2–5** reescritos. La sección 1.1 y el objetivo general no cambian. |
| **2** | 2.1.3: párrafo nuevo sobre varios atributos protegidos y métricas simétricas. **2.1.7 nueva:** incertidumbre estadística y *bootstrap*. 2.2.3: MLflow, PROV-O, DQV y SHACL con citas textuales; GraphDB deja de ser obligatorio. 2.3.1: "Captura y anonimización" → "Captura y seudonimización"; se quita AIF360. |
| **3** | Sin cambios (describe la literatura). Queda pendiente la Figura 2 (ver 5.3). |
| **4** | **Reescrito completo:** 4.1 (tres principios); C4 niveles 1–3 con motor de contratos y canal de linaje (**Figuras 4–9 en Mermaid**); restricción "reproducible local y en CI" en lugar de "local sin internet"; Tabla 10 con C1–C4; Tabla 11 con el esquema común; **Tabla 14 nueva** (casos de estudio); C1 (nulos ≤ 5 %, duplicados ≤ 1 %, columnas prohibidas, representatividad de todos los grupos); **C2 por paso** (AUC de Z dado X estratificado por Y, tope 0,60, incremento δ = 0,02, localización); **C3 con remediación**, métricas simétricas o direccionales y *bootstrap*; **C4 nuevo** (deriva); ontología sobre PROV-O/DQV/SHACL (Tablas 12 y 13 nuevas); SPARQL y Turtle con **Davronov** (hash `1aa87791…`, 8 707 registros; la métrica se marca como ilustrativa); forma SHACL; discusión y limitaciones nuevas (licencia, codificación de `Sex`, operación simulada, umbrales calibrados). |
| **5** | 5.1 reescrita (R.E.3.x según el nuevo diseño; entorno Windows y Ubuntu; datasets y licencia). Títulos de 5.2 y 5.4 ajustados. 5.2–5.5 siguen sin contenido. |
| **Anexo B** | Viabilidad técnica y de datos (sin "nube"; Davronov y HMDA), Alcance, **limitación nueva** (procedencia y licencia de los datos), riesgos actualizados y **riesgo nuevo** (licencia o documentación del dataset), tareas 3.2 y 3.3, recursos. Tablas renumeradas a 15, 16 y 17 (por la nueva Tabla 14 del Cap. 4). |
| **Referencias** | +10 fuentes verificadas: Albertoni & Isaac (2016), Davronov (2021), Efron & Tibshirani (1993), FFIEC (s.f.), Giang Thi Thu et al. (2024), Knublauch & Kontokostas (2017), Lebo et al. (2013), Noy & McGuinness (2001, antes citado sin referencia), Weerts et al. (2023) y Zaharia et al. (2018). |
| **Índice** | Se agregan 2.1.7 y los títulos nuevos de 5.2 y 5.4. Los números de página son del PDF E2 y deben recalcularse. |

## 5.2 Citas textuales incluidas (verificadas contra la fuente)

| Dónde | Cita | Fuente |
|---|---|---|
| 2.2.3 y 4.4.1 | "expresses the PROV Data Model using the OWL2 Web Ontology Language" | Lebo et al. (2013), Resumen |
| 2.2.3 y 4.4.1 | "represents the evaluation of a given dataset (or dataset distribution) against a specific quality metric" | Albertoni & Isaac (2016), sección 4.1 |
| 2.2.3 y 4.4.1 | "a language for validating RDF graphs against a set of conditions" | Knublauch & Kontokostas (2017), Resumen |
| 4.3.4 (C3) | "less than four-fifths (4/5) (or eighty percent) of the rate for the group with the highest rate will generally be regarded by the Federal enforcement agencies as evidence of adverse impact" | Uniform Guidelines… (1978), § 1607.4(D) |
| 4.4.1 | "mantener un registro actualizado y accesible, con enfoque preventivo, sobre los principios del funcionamiento del sistema, las fuentes de datos utilizadas y la lógica del algoritmo" | PCM (2025), art. 31.1 |
| 4.1, 4.2.4, 4.3.4 y 4.4.4 | Texto del O2 y de los indicadores de R.E.2.1, R.E.2.2 y R.E.2.3 | Cap. 1 (verificado que coinciden palabra por palabra) |

## 5.3 Pendientes derivados del rediseño

- **Figuras 4–9:** redibujar en Lucidchart a partir de los diagramas Mermaid del Cap. 4. Las imágenes antiguas (`imagenes/fig04…fig09`) representan el diseño anterior y ya no se enlazan.
- **Figura 2 (Cap. 3):** muestra la arquitectura anterior (con InterpretME); reemplazarla por la nueva Figura 5 o eliminarla del estado del arte.
- **Valores ilustrativos** del Turtle de 4.4.3 (SPD 0,18 e IC 0,14–0,22): reemplazarlos por los reales cuando exista la implementación.
- **Umbrales del C2** (0,60 y 0,02): calibrarlos con `Marital` y documentar el resultado en el Cap. 5.
- **Formato del autor** de Giang Thi Thu et al. (2024): confirmar el orden de apellidos (nombre vietnamita) antes de la versión final.
- Siguen vigentes los pendientes de la sección 4 que no se resolvieron (cronograma 109 vs. 125 días, Lin et al. sin cita, fórmula ECL y fechas del Reglamento 2026/1744).
