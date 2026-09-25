<!-- Fuente: 20202117_SergioChumbimuni_LuisVives_E2.pdf, pp. 81–83, REESCRITO el 2026-09-25 según estado/propuesta-diseno.md (aprobada). Ver capitulos/CAMBIOS.md, sección 5. -->
<!-- Estado: 5.1 redactado; 5.2–5.5 son títulos pendientes de redactar a partir de la implementación. Este capítulo no aparecía en el Índice del PDF E2. -->

# Capítulo 5: Implementación de la propuesta de solución

## 5.1. Introducción

El presente capítulo documenta la implementación del prototipo funcional de la arquitectura MLOps diseñada en el Capítulo 4, correspondiente al Objetivo Específico 3 (O3) del proyecto. Mientras que el capítulo anterior estableció el *qué* (la estructura de cuatro zonas modelada con C4, el esquema declarativo común de los Contratos de Equidad C1 a C4 y la Ontología de Fairness), este capítulo aborda el *cómo*: la materialización de ese diseño en un sistema ejecutable, verificable y reproducible.

La implementación se organiza en torno a los tres resultados esperados del Objetivo 3. El resultado R.E.3.1 comprende la infraestructura base: los repositorios privados de código y datos, el versionado de datos mediante DVC, el motor de contratos y la automatización del *pipeline* de integración continua mediante GitHub Actions. El resultado R.E.3.2 corresponde a la programación de las compuertas de calidad (*QA Gates*) que materializan los Contratos C1, C2 y C3 como pruebas automatizadas generadas por el motor de contratos, incluida la remediación del Contrato C3. Finalmente, el resultado R.E.3.3 aborda el servicio de monitoreo y registro: el canal de linaje en MLflow, el Contrato C4 sobre lotes de producción, la generación de razones de rechazo y la exportación del linaje al grafo de conocimiento.

Cada sección sigue una estructura uniforme de cuatro apartados. El primero describe el resultado alcanzado en términos de los artefactos producidos. El segundo detalla la metodología seguida y las condiciones necesarias para reproducir el resultado en otro entorno. El tercero aporta la verificación de existencia: la evidencia concreta y localizable de que el artefacto existe y opera. El cuarto presenta las mediciones obtenidas y valida el indicador definido para ese resultado esperado.

Conviene señalar una desviación deliberada respecto del orden nominal establecido en el cronograma del proyecto. El cronograma agrupa en R.E.3.1 la configuración de DVC y la de CI/CD, situando ambas antes de la programación de las *QA Gates* (R.E.3.2). Sin embargo, la ejecución real siguió la secuencia DVC → *QA Gates* → CI/CD, por una razón de dependencia técnica: un *pipeline* de integración continua requiere, para ser configurado y verificado, que existan previamente las pruebas que habrá de ejecutar. Configurar GitHub Actions sobre un repositorio sin lógica de validación produciría un *workflow* vacío, imposible de validar contra un indicador. Esta reordenación no altera el alcance ni los entregables comprometidos, y la trazabilidad entre tarea planificada y artefacto producido se mantiene íntegra.

El entorno de desarrollo es una estación de trabajo con sistema operativo Windows y Python 3.11. El mismo conjunto de pruebas se ejecuta en los ejecutores de GitHub Actions (Ubuntu, Python 3.11), con versiones de dependencias fijadas, de acuerdo con el principio de reproducibilidad local y en integración continua establecido en el Capítulo 4. El caso de estudio principal es el conjunto de datos "Credit-scoring data" publicado en Kaggle, reportado como proveniente de una fintech de Asia Central (Davronov, 2021; Giang Thi Thu et al., 2024). Dado que su licencia reserva los derechos a sus autores, los repositorios del proyecto se mantienen privados y el conjunto de datos no se redistribuye; el procedimiento para obtenerlo se documenta en el repositorio. Como caso secundario se emplean datos públicos del registro de solicitudes hipotecarias de Estados Unidos (FFIEC, s.f.).

## 5.2. Infraestructura base: repositorios, versionado de datos, motor de contratos y CI/CD

### 5.2.1. Descripción del resultado alcanzado

Este resultado comprende los componentes de infraestructura que sostienen la operación reproducible y automatizada del resto del sistema: los repositorios privados, el versionado de datos, el motor de contratos y la automatización del *pipeline* de integración continua.

### 5.2.2. Metodología de logro y reproducibilidad

### 5.2.3. Verificación de existencia

### 5.2.4. Mediciones y validación de indicador

## 5.3. Programación e instrumentación de las QA Gates

### 5.3.1. Descripción del resultado alcanzado

### 5.3.2. Metodología de logro y reproducibilidad

### 5.3.3. Verificación de existencia

### 5.3.4. Mediciones y validación de indicador

## 5.4. Integración del servicio de monitoreo, registro y trazabilidad

### 5.4.1. Descripción del resultado alcanzado

### 5.4.2. Metodología de logro y reproducibilidad

### 5.4.3. Verificación de existencia

### 5.4.4. Mediciones y validación de indicador

## 5.5. Discusión

### 5.5.1. Síntesis de resultados principales

### 5.5.2. Interpretación del significado de los resultados

### 5.5.3. Contextualización de la revisión de la literatura

### 5.5.4. Generalización de los resultados

### 5.5.5. Limitaciones de los resultados
