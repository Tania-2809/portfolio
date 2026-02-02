Prompt (original en español):

Teniendo en cuenta mis líneas de diseño y decisiones técnicas descritas en `project-brief.md` y `project-inspiration.md` (y respetando los tokens de `assets/css/_variables.css`), analiza estos 3 portfolios de ilustradores  -https://koto.com/projects/fitbit-ace-lte
-https://pictoric.com.ua
-https://atolldigital.com.

## Volcado de entrega (archivos destino)

- `docs/prompt-analisis-galerias.md`: pega este prompt + la respuesta completa.
- `project-inspiration.md`: añade las 3 URLs analizadas y 3 bullets de “patrones transferibles” (sin copiar).
- `project-brief.md`: incorpora 2 decisiones concretas (layout + contenido) en Key Sections / Design Direction.

Objetivo pedagógico: detectar **patrones transferibles** (no copiar estética).

Para cada uno, evalúa:

1. **Diseño Visual (Awwwards criteria)**

   - Estética general (1-10)
   - Tipografía y jerarquía
   - Uso de color y contraste
   - Composición y espaciado

2. **UX de Galería**

   - Facilidad para explorar proyectos
   - Claridad de navegación
   - Información por proyecto (título, descripción, tags)
   - Call-to-actions efectivos

3. **Técnica**

   - Tipo de layout (grid, masonry, custom)
   - Responsive behavior
   - Performance (carga de imágenes)
   - Micro-interacciones

4. **Insights Accionables (aplicables a mi brief)**
   - 3 patrones que puedo reutilizar sin copiar (con explicación)
   - 3 riesgos/antipatrones a evitar (con explicación)
   - 2 decisiones concretas para mi galería (layout + contenido), justificadas con mi `project-brief.md`

Devuelve:

- Tabla comparativa (Diseño / UX / Técnica)
- “Decisiones para mi proyecto” (bullets)
- Checklist de verificación (qué revisar al implementarlo)


---

RESPUESTA / ANÁLISIS COMPLETO

Resumen rápido

Analicé las tres referencias siguiendo tus criterios: Koto (caso de estudio de agencia con imágenes grandes y Next.js image service), Pictoric (galería/marketplace de ilustración, estructura curatorial) y Atoll Digital (web de agencia con case studies y tarjetas de proyecto). A continuación tienes el análisis por sitio, patrones transferibles, riesgos y decisiones concretas para tu galería.

1) KOTO — página de proyecto (https://koto.com/projects/fitbit-ace-lte)

Diseño Visual (Awwwards criteria)
- Estética general: 9/10 — imagen potente, composición cuidada, aire editorial.
- Tipografía y jerarquía: Muy buena — jerarquía clara, títulos grandes y jerarquía tipográfica consistente.
- Uso de color y contraste: Dependiente del proyecto (Fitbit usa colores brillantes) — contraste sólido entre textos y fondos en la mayoría de secciones.
- Composición y espaciado: Amplio uso de espacio negativo y composiciones a página completa; ritmo visual fuerte.

UX de Galería
- Facilidad para explorar: Buena; las imágenes están en una secuencia vertical con navegación clara.
- Claridad de navegación: Breadcrumbs y enlaces "View All Projects" facilitan regresar a la galería.
- Información por proyecto: Moderada — hay secciones con challenge/rol pero la información meta no siempre está en cada imagen.
- CTAs efectivos: Sí — contacto visible y CTA a ver más proyectos.

Técnica
- Tipo de layout: Custom (single case-study layout con imágenes full-bleed y bloques de contenido).
- Responsive behavior: Bien resuelto; usan procesamiento de imágenes (Next.js) para servir tamaños adecuados.
- Performance: Optimizado a nivel de imagen (servicio de imágenes), pero el alto número de imágenes grandes puede impactar carga si no se lazy-load.
- Micro-interacciones: Transiciones suaves, overlays y hover states discretos.

Insights accionables (Koto)
- Patrones reutilizables:
  1. Hero/full-bleed inicial seguido de galería ordenada — comunica impacto inmediato.
  2. Optimización de imágenes en servidor (sizes + quality) para servir distintas resoluciones.
  3. CTA persistente al final/side que facilita contacto tras ver el trabajo.
- Riesgos / antipatrones:
  1. Demasiadas imágenes pesadas sin lazy-loading visible = afectación de LCP.
  2. Exceso de imagen sobre texto puede dejar poco contexto para quien necesita entender el proyecto rápido.
  3. Dependencia de JS/servicios específicos (p. ej. Next image) que obliga a stack concreto.
- Decisiones aplicables a tu brief (ejem.)
  - Layout: usar un hero destacado + galería de 3–6 imágenes optimizadas por proyecto (coincide con tu brief).
  - Contenido: añadir sección "Contexto / objetivo" compacta para cada proyecto (mejora comprensión sin sobrecargar la tarjeta).


2) PICTORIC — plataforma de ilustración (https://pictoric.com.ua)

Diseño Visual (Awwwards criteria)
- Estética general: 7/10 — enfoque curatoral, más funcional que experimental.
- Tipografía y jerarquía: Legible y simple, menos dramatismo tipográfico.
- Uso de color y contraste: Varía según las obras (la UI es neutra, permite que las ilustraciones destaquen).
- Composición y espaciado: Rejilla y tarjetas con ritmo constante; buen balance entre miniaturas y texto.

UX de Galería
- Facilidad para explorar: Excelente para descubrimiento — secciones curatoriales, filtros/colecciones.
- Claridad de navegación: Navegación por proyectos y artistas directa; múltiples puntos para ver "más info".
- Información por proyecto: Suele mostrar título y enlace a ficha del autor; a veces la descripción es secundaria.
- CTAs efectivos: Claros para explorar y comprar/leer más, dependiendo de la sección (boutique, proyecto, más info).

Técnica
- Tipo de layout: Grid de thumbnails (aparenta un grid estándar, con algunos tamaños variables para piezas destacadas).
- Responsive behavior: Adecuado; las miniaturas se reordenan y el sitio funciona como galería indexable.
- Performance: Moderada — sirven imágenes en versiones grandes/medianas; dependerá de lazy-loading.
- Micro-interacciones: Pocas; enfoque en navegar y descubrir más.

Insights accionables (Pictoric)
- Patrones reutilizables:
  1. Organización por colecciones/temas que facilita curación y navegación por intereses.
  2. Miniaturas consistentes con opción a destacar piezas — equilibrio entre uniformidad y piezas clave.
  3. Enlaces directos a ficha de autor/proyecto para profundizar (buena separación entre descubrimiento y lectura).
- Riesgos / antipatrones:
  1. Interfaz muy neutra puede sentirse fría o impersonal si buscas mostrar personalidad.
  2. Si no hay metadatos estandarizados (roles, year) la búsqueda/filtrado pierde precisión.
  3. Pocas micro-interacciones hacen la exploración menos memorable.
- Decisiones aplicables a tu brief
  - Layout: grid modular con variantes para piezas destacadas (permite mostrar 1–2 destacados en hero y una rejilla homogénea debajo).
  - Contenido: incluir enlaces claros a la ficha detallada del proyecto y estructurar metadatos (tags, rol, año) para filtrar.


3) ATOLL DIGITAL — agencia / case studies (https://atolldigital.com)

Diseño Visual (Awwwards criteria)
- Estética general: 8/10 — profesional, sobrio, enfocado en claridad corporativa.
- Tipografía y jerarquía: Muy buena, tipografía limpia y consistente.
- Uso de color y contraste: Paleta restringida, contraste suficiente para legibilidad.
- Composición y espaciado: Rejilla moderna para case studies, cards con espacio y focos de interés.

UX de Galería
- Facilidad para explorar: Clara — tarjetas de proyecto con CTA "See more" y feed de trabajos.
- Claridad de navegación: Menú y CTA de contacto accesibles; experiencia de agencia clásica.
- Información por proyecto: Tarjetas con rol/servicio breve y enlace a case study.
- CTAs efectivos: Sí — llamadas a la acción orientadas a contactar o ver más trabajos.

Técnica
- Tipo de layout: Grid de tarjetas + páginas de case study individuales.
- Responsive behavior: Diseñado para ser responsivo; buena adaptación a móviles.
- Performance: Usan imágenes optimizadas; en general buen equilibrio entre estética y carga.
- Micro-interactions: Hover states en tarjetas y transiciones para entradas a case study.

Insights accionables (Atoll)
- Patrones reutilizables:
  1. Tarjetas de proyecto limpias con resumen y CTA, ideales para primera exploración.
  2. Estructura "feed + case study" que separa descubrimiento de lectura en profundidad.
  3. CTA orientada a conversión (contacto) colocada en flujo natural del usuario.
- Riesgos / antipatrones:
  1. Estilo muy genérico si buscas personalidad ilustrativa fuerte.
  2. Tarjetas sin suficiente previsualización visual pueden bajar el engagement.
  3. Contenido demasiado escueto en tarjetas obliga a clics excesivos para entender proyectos.
- Decisiones aplicables a tu brief
  - Layout: usar tarjetas con imagen+resumen y un enlace/CTA consistente a case study (mejora usabilidad y conversión).
  - Contenido: en la página de detalle, incluir 3–6 imágenes optimizadas y una sección de contexto y rol.


Tabla comparativa (Diseño / UX / Técnica)

- **Koto**
  - Diseño: 9/10 — alto impacto visual, editorial.
  - UX: Navegación de case study fuerte; foco en imágenes.
  - Técnica: Custom layout; buenas prácticas de imagen (Next image).

- **Pictoric**
  - Diseño: 7/10 — curatorial, funcional.
  - UX: Excelente para descubrimiento por colecciones.
  - Técnica: Grid de thumbnails; dependerá de lazy-loading y CDN.

- **Atoll Digital**
  - Diseño: 8/10 — profesional y claro.
  - UX: Tarjetas + case studies con CTA claros.
  - Técnica: Grid + páginas detalle; optimización de imágenes y transiciones.


Decisiones para mi proyecto (bullets)

- **Layout (decisión concreta):** Rejilla desktop-first de 3 columnas para la galería de proyectos con 1–2 proyectos destacados en hero ancho completo. Justificación: coincide con la estrategia desktop-first, facilita mostrar imágenes grandes y permite un flujo visual equilibrado entre impacto (hero) y descubrimiento (rejilla).

- **Contenido (decisión concreta):** Cada tarjeta mostrará `Título` (H3), `Descripción corta` (40–80 palabras), `Tags/roles` y `Año`, más un botón `Ver proyecto` que abra la página de detalle (hero + 3–6 imágenes optimizadas + sección de contexto/objetivos + CTA de contacto). Justificación: respeta tus metas de accesibilidad y carga optimizada (alt text, imágenes optimizadas) y mejora conversión y comprensión rápida.


Checklist de verificación (qué revisar al implementarlo)

- Imágenes:
  - [ ] `srcset` / `sizes` configurados y pruebas en distintos breakpoints
  - [ ] Lazy-loading para imágenes fuera de viewport (`loading="lazy"` o IntersectionObserver)
  - [ ] Imágenes optimizadas (webp/avif + fallback)
  - [ ] `alt` descriptivos para cada imagen

- Accesibilidad:
  - [ ] Estructura semántica (H1..H3), roles ARIA donde sea necesario
  - [ ] Navegación por teclado (tab order, focus styles)
  - [ ] Contraste de color comprobado (WCAG AA)

- UX / Contenido:
  - [ ] Tarjeta contiene título, 40–80 palabras descripción, tags/roles, año
  - [ ] CTA `Ver proyecto` clara y con foco visual
  - [ ] Página de detalle con hero, 3–6 imágenes, contexto/objetivos y CTA de contacto

- Performance:
  - [ ] Lighthouse: LCP y CLS dentro de límites razonables (<2.5s LCP ideal)
  - [ ] Pruebas de red lenta y CPU baja

- Micro-interacciones:
  - [ ] Hover/focus states claros y no solo dependientes de hover (accesible)
  - [ ] Animaciones con prefer-reduced-motion respetadas

- Metadata & SEO:
  - [ ] Metadatos por proyecto: title, description, og:image
  - [ ] Estructura de URL amigable para cada proyecto


Conclusión breve

Las tres referencias ofrecen patterns claros que puedes reutilizar: hero + galería (Koto), curación/colecciones y ficha de autor (Pictoric) y estructura de tarjeta + case study con CTA (Atoll). Para tu brief —desktop-first, accesibilidad y 3–6 imágenes por proyecto— recomiendo combinar las ventajas: hero destacado (Koto), rejilla curada (Pictoric) y tarjetas orientadas a conversión (Atoll). Evita imágenes sin optimizar, tarjetas sin metadatos y depender exclusivamente de micro-interactions no accesibles.

---

(Analista: revisión enfocada a tu `project-brief.md` y a la necesidad pedagógica de detectar patrones transferibles.)
