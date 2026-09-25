---
name: resolver-referencias
description: Resuelve referencias bibliográficas faltantes en un proyecto de tesis — compara referencias.md contra bibliografia/index.md, identifica discrepancias, busca en la web el PDF o la fuente oficial de cada referencia faltante, y genera fichas nuevas para index.md. Usar siempre que el usuario pida verificar citas, completar bibliografía, buscar fuentes faltantes, o corroborar que las referencias citadas en la tesis están todas catalogadas.
---

# Resolver Referencias

Skill para cerrar el ciclo de verificación bibliográfica: no solo detectar qué referencias faltan en `index.md`, sino intentar resolverlas (encontrar PDF o fuente oficial) y dejarlas listas para catalogar, sin inventar información.

## Cuándo usar esta skill

- El usuario pide comparar `referencias.md` (o el listado de referencias de la tesis) contra `bibliografia/index.md`.
- El usuario pide "buscar" o "conseguir" las fuentes faltantes.
- El usuario pide catalogar/fichar una fuente que no tiene PDF todavía.

## Paso 1 — Diagnóstico (si no se ha hecho ya)

1. Leer `referencias.md` (o el archivo equivalente con el listado completo de citas de la tesis) y extraer cada entrada: autor(es), año, título, tipo (paper académico, libro, norma/regulación, documentación técnica/web).
2. Leer `bibliografia/index.md` y extraer las fichas existentes.
3. Comparar por autor + año + título (no solo título, para no confundir dos trabajos del mismo autor en años distintos).
4. Reportar tres listas:
   - Referencias en `referencias.md` sin ficha en `index.md` (faltantes).
   - Fichas en `index.md` sin referencia correspondiente en `referencias.md` (sobrantes / posible error).
   - Coincidencias con discrepancia menor (autor mal escrito, año distinto, etc.) — no autocorregir, solo reportar.

No avanzar al Paso 2 sin que el usuario haya visto este diagnóstico, salvo que ya lo haya confirmado en el mismo turno.

## Paso 2 — Clasificar las faltantes por estrategia de búsqueda

Antes de buscar, separar las referencias faltantes en:

- **Papers académicos / libros** → buscar en fuentes de acceso abierto: arXiv, sitio del journal/conferencia, repositorio institucional de los autores, Semantic Scholar, Google Scholar (para ubicar el DOI y de ahí el PDF legítimo). Nunca usar sitios de piratería (Sci-Hub, Library Genesis, Z-Library, etc.) ni scrapear contenido con copyright evidente de un blog/medio de pago.
- **Normas, regulaciones, estándares** (leyes, reglamentos, ISO, circulares de entidades) → normalmente no requieren PDF completo citado; buscar la fuente oficial (sitio del gobierno/organismo emisor) y confirmar los metadatos exactos (número de norma, fecha de publicación).
- **Documentación técnica / artículos web** (blogs, docs de producto, Medium, etc.) → buscar la URL oficial y verificar que siga activa; estas no necesitan PDF, solo la ficha con URL y fecha de acceso.

## Paso 3 — Buscar cada referencia faltante

Para cada una, en orden de prioridad (las que sostienen decisiones técnicas centrales de la tesis van primero si el usuario las señaló):

1. Buscar el título + autor(es) + año en la web.
2. Si se encuentra un PDF de acceso abierto legítimo (arXiv, sitio institucional, journal open-access): descargarlo a `bibliografia/docs/` con nombre consistente con los demás archivos de esa carpeta.
3. Si es una norma o URL oficial: no descargar PDF necesariamente, pero registrar la URL exacta y la fecha de la búsqueda (para trazabilidad, ya que estas páginas cambian).
4. Si no se encuentra ninguna fuente accesible: NO inventar la ficha. Marcar explícitamente como `sin PDF, no verificada` y seguir con la siguiente.
5. Nunca generar un resumen o ficha basado en el título/autor solamente sin haber accedido al contenido real (abstract, norma, o página oficial) — el resumen debe reflejar lo que la fuente dice, no lo que se infiere del título.

## Paso 4 — Generar fichas para `index.md`

Para cada fuente resuelta en el Paso 3, seguir el formato ya establecido en `AGENTS.md` / `index.md` del proyecto:
- Título, autor(es), año.
- Resumen corto (2-4 líneas) de qué aporta a la tesis — basado en el contenido real accedido, no en suposición.
- Tag de sección/decisión si aplica (ej: `#QA-Gate-3`, `#fairness-metrics`).
- Para normas/URLs sin PDF: incluir la URL y una nota `[fuente web, sin PDF local]`.
- Para las que no se pudieron resolver: incluir la entrada igual, pero marcada claramente como `[sin PDF, no verificada — pendiente confirmación manual]`, sin resumen inventado.

## Paso 5 — Reporte final al usuario

Cerrar siempre con:
- Cuántas se resolvieron y agregaron a `index.md`.
- Cuántas quedaron pendientes (`sin PDF, no verificada`) y por qué.
- Cuántas fueron normas/web (sin PDF por diseño, no por falta de búsqueda).
- Cualquier discrepancia de autor/año detectada en el Paso 1 que siga sin resolver.

## Reglas duras (no negociables)

- Nunca descargar de sitios de piratería académica.
- Nunca inventar un resumen de una fuente que no se pudo leer.
- Nunca sobrescribir una ficha existente en `index.md` sin mostrar antes/después al usuario.
- Respetar las reglas de `AGENTS.md` del proyecto (no tocar PDFs existentes en `bibliografia/docs/`, no borrar bitácora, etc.) si ese archivo está presente en el repo.
