# Implementación vs. tesis

- **Fecha de revisión:** 2026-09-25
- **Código revisado:** `C:\Users\a2020\Documents\Tesis\Proyecto\mlops-fairness-scoring` (último commit `f3977fa`, "Comprometer dataset en Git para uso en CI…"). Solo lectura; no se modificó nada del proyecto.
- **Texto comparado:** `capitulos/04-diseno.md` y `capitulos/05-implementacion.md`.
- **Objetivo:** resolver las dudas abiertas de `capitulos/CAMBIOS.md` §4 y listar dónde el diseño escrito y el código difieren, como insumo para el Cap. 5. Este documento **no modifica la tesis**: decidir qué versión se ajusta (código o texto) le corresponde al autor.

## 1. Dudas resueltas

| Duda | Lo que muestra el código | Consecuencia para la tesis |
|---|---|---|
| **Dataset** | `zona1_ingesta/data/raw/credit-scoring.csv`: dataset Davronov, **8 707 registros**, 18 columnas. Versionado con DVC (md5 `1aa87791dbf04be9e8440f4eef1ebc54`) y además comprometido en Git para CI. | El ejemplo Turtle de 4.4.3 ("German Credit", 1000 registros, hash `9dd7e9…`) no corresponde al caso real. Con datos reales sería `recordsCount 8707` y `hasDvcHash "1aa87791dbf04be9e8440f4eef1ebc54"`. |
| **Significado de `label`** | `label=1`: 8 037 (92,3%); `label=0`: 670 (7,7%). La clase mayoritaria es 1. | Coincide con la tesis (Y=1 buen pagador, Y=0 default) y con `favorable_label: 1` del C3. |
| **Brecha del label real por sexo** | P(label=1 \| Sex=1) = 94,1% (3 092/3 287); P(label=1 \| Sex=2) = 91,2% (4 945/5 420). Diferencia ≈ 2,9 pp. | Confirma la cifra de "2,8 pp" del README (diferencia de redondeo). |
| **Local vs. nube** | CI en **GitHub Actions** (`runs-on: ubuntu-latest`, Python 3.11). Remotos DVC en **DagsHub** y **Google Drive**. | Contradice la restricción de 4.2.2 ("100% de los contenedores… en un entorno local desconectado de internet"). Coincide con el Anexo B (Viabilidad técnica y Recursos). |
| **Codificación de `Sex`** | Valores {1, 2}: 3 287 y 5 420 registros. El código no indica cuál es mujer u hombre ni cuál es el grupo no privilegiado. | La tesis usa Z ∈ {0, 1} con Z=0 como no privilegiado, y el Turtle usa `unprivilegedValue "female"`. Falta documentar el mapeo real (fuente: ficha del dataset en Kaggle). |

## 2. Contratos: diseño (Cap. 4) vs. código

### Esquema declarativo (Tabla 11 y YAML de 4.3.3)

| Tabla 11 / ejemplo de 4.3.3 | Código (`contracts/*.yaml`) |
|---|---|
| Campos comunes: `contract_id`, `gate`, `stage`, `protected_attributes`, `rules[metric, operator, threshold]`, `on_violation.action` (block/warn), `tooling` | Cada contrato tiene una estructura propia: C1 usa `schema`, `integrity` y `representativeness`; C2 usa `conditional_mutual_information`; C3 usa `fairness_metrics`, `model` y `mitigation`. Solo se usan los campos `contract_id`, `name`, `version` y `applies_to`. **No existen** `on_violation`/`block`-`warn` ni `tooling`. |
| `contract_id: "C3-fairness-modelo"`; atributos protegidos `"sexo"` y `"edad_agrupada"`; `tooling: "AIF360"` | `contract_id: C3`; solo `Sex`; las métricas se calculan con **Fairlearn** (AIF360 está en `requirements.txt` pero no se usa). |

### C1 — QA Gate 1

| Tesis (4.3.4) | Código (`tests/test_qa_gate1.py`) |
|---|---|
| Integridad: tipos permitidos y `Nulos(c) = 0` en todas las columnas | Pandera valida tipos, rangos y valores permitidos de 6 columnas (`label`, `Age`, `Sex`, `Marital`, `Number_of_credits`, `Linked_cards`) sin nulos. Además, **≤5% de nulos por columna** en todas las columnas y **≤1% de filas duplicadas** (no están en la tesis). |
| Representatividad: P(Z=0 \| D_raw) ≥ 0,05 (solo el grupo no privilegiado) | **Todos** los grupos de `Sex` deben tener proporción ≥ 0,05. Es más estricto e incluye la condición de la tesis. |
| — | `tests/test_qa_gate1_failure_cases.py`: prueba negativa con un lote sintético 99%/1% que confirma que el gate falla. Es útil como evidencia para R.E.3.2. |
| — | `ingestor.py` elimina `Score_level`, `Score_class` y `Score_point` como **fuga de la variable objetivo**. No se menciona en la tesis. |

### C2 — QA Gate 2

| Tesis (4.3.4) | Código (`tests/test_qa_gate2.py`) |
|---|---|
| I(X_trans; Z \| Y) **<** 0,10, tomando X_trans como conjunto | Estima la MI de **cada feature transformada por separado** (`mutual_info_classif`, k-NN con k=3), toma el **máximo** dentro de cada estrato de Y y promedia ponderando por el tamaño del estrato; exige **≤** 0,10. Es una aproximación por feature de la MI condicional conjunta. |
| Compara la distribución **pre y post** transformación ("impacto diferencial") para aislar al transformador responsable | Solo evalúa la salida transformada; **no hay comparación pre/post** ni evaluación por transformador. |
| El "Evaluador de impacto ético" es de Fairlearn (4.2.1, Zona 1) | Usa scikit-learn (`mutual_info_classif`). |
| — | **Resultado real:** el gate detectó que `Marital` es un proxy casi perfecto de `Sex` (6 de 7 categorías con separación del 100%) y se excluyó del pipeline (comentario en `transformers/pipeline.py`). Es un buen caso de estudio para el Cap. 5 y concreta el ejemplo de "estado civil" de 2.1.2. |

### C3 — QA Gate 3

| Tesis (4.3.4) | Código (`tests/test_qa_gate3*.py`) |
|---|---|
| \|SPD\| ≤ 0,10 y \|EOD\| ≤ 0,10 | `MetricFrame(...).difference()` de Fairlearn (máx − mín entre grupos) ≤ 0,10. Equivale a la tesis porque hay 2 grupos. |
| DI = P(Ŷ=1\|Z=0) / P(Ŷ=1\|Z=1) ≥ 0,80 (direccional) | `demographic_parity_ratio` = mín/máx de las tasas de selección, en el rango [0,8; 1,25]. Como mín/máx ≤ 1 siempre, **el límite 1,25 nunca se activa**. |
| Si se violan los umbrales, se interrumpe el despliegue | El modelo base (regresión logística, `class_weight="balanced"`) **falla el C3**. En CI ese paso tiene `continue-on-error: true`, y luego un segundo paso evalúa el modelo **mitigado con `ThresholdOptimizer` (Fairlearn, `equalized_odds`)**, que sí pasa. La mitigación no está descrita en el Cap. 4 (se relaciona con 2.1.6 y con Hardt et al., 2016). |

## 3. Qué partes del diseño aún no están en el código

| Componente del Cap. 4 | Estado en el código |
|---|---|
| Zona 1: ingesta, QA Gates 1 y 2, transformadores, DVC | ✅ Implementado (DVC con la salvedad del CSV en Git) |
| Zona 2: entrenamiento, QA Gate 3, CI en GitHub Actions | ✅ Implementado. Stress testing, SHAP y registro en MLflow: **no** |
| Zona 3: despliegue CD, endpoint, captura/anonimización, Evidently | ❌ No hay código (evidently está en `requirements.txt`) |
| Zona 4: InterpretME, RDFLib, ontología, GraphDB, SPARQL | ❌ No hay código (rdflib está en `requirements.txt`; InterpretME no) |
| Canal de linaje MLflow | ❌ No se usa MLflow en el código |

## 4. Observaciones técnicas para el autor (no afectan el texto)

- `requirements.txt` no fija versiones, aunque el Anexo B propone "pinned requirements" como mitigación de un riesgo, y el bug de DVC 3.67.1 muestra que las versiones importan.
- `test_qa_gate1_failure_cases.py` repite la lógica del gate en lugar de llamar a la función del gate real; si esa lógica cambia, la prueba negativa no lo detectaría.
- En `train.py`, `drop_leakage_columns` se aplica dos veces: `load_raw_batch` ya lo hace. No causa error.
- `favorable_label` del C3 no se usa en el código (Fairlearn asume que 1 es la selección, lo que aquí coincide).
- Los mensajes de commit "pipeline modified N" dificultan reconstruir el historial para el Cap. 5.

## 5. Implicaciones para la tesis (decisión del autor)

1. **Cap. 4 vs. código:** para cada diferencia de la sección 2, decidir si se ajusta el texto de diseño (Tabla 11, fórmulas de C1/C2, DI, mitigación) o el código.
2. **Ejemplo Turtle (4.4.3):** reemplazar German Credit por Davronov con el hash y el número de registros reales.
3. **Restricción "local sin internet" (4.2.2):** reformular, porque CI y los remotos DVC dependen de servicios en la nube.
4. **Cap. 5:** el código ya da material para 5.2 (DVC, workaround del CSV, CI) y 5.3 (QA Gates 1–3, prueba negativa del C1, hallazgo de `Marital`, mitigación del C3). 5.4 (monitoreo y registro) aún no tiene implementación.

## 6. Ficha verificada del dataset Davronov (Kaggle API, 2026-09-25)

- **Referencia:** `islombekdavronov/creditscoring-data` — "Credit-scoring data", Islombek Davronov, versión 2 (29-dic-2021). https://www.kaggle.com/datasets/islombekdavronov/creditscoring-data
- **Licencia:** "Data files © Original Authors" (`copyright-authors`). **No es una licencia abierta**: no concede permiso explícito de redistribución.
- **Descripción del autor:** "The data is collected from the real source and converted to numeric values…". **No menciona una fintech ni el país, y no trae diccionario de columnas.** Etiqueta de Kaggle: *banking*. La atribución "FinTech company in Central Asia" proviene de Giang Thi Thu et al. (2024, arXiv:2412.20298), no de la página del dataset.
- **Archivos:** `data_train.csv` (364 617 bytes = el CSV del proyecto, mismo tamaño que en el `.dvc`) y `data_test.csv` (2 197 bytes, ≈48 filas, con `label`). 8 707 + 48 = 8 755, el total que reporta el paper.
- **Codificación de `Sex` y `Marital`:** no documentada en el dataset ni en el notebook del autor. El cruce Marital × Sex (6 de 7 categorías separadas al 100%) sugiere que las categorías de `Marital` dependen del sexo, pero no permite saber qué valor corresponde a cada sexo.
- **Notebook del autor** (`islombekdavronov/credit-scoring`): usa `Score_*` como variables y reporta una exactitud "cercana al 100%", lo que confirma la fuga de la variable objetivo que el ingestor del proyecto elimina.
