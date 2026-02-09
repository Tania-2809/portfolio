Personaliza el sistema de diseño del portfolio scrollytelling.

## 📎 CONTEXTO - Lee estos archivos adjuntos

1. **project-brief.md** → Sección "Identidad Visual"
   - Obtén: paleta de colores, tipografías, URLs Google Fonts

2. **assets/css/_variables.css** → Variables actuales
   - Identifica: qué variables actualizar

## INSTRUCCIÓN

Extrae de `project-brief.md` sección "Identidad Visual":
- Color primario, secundario, acentos 1-3 (hex codes)
- Fuente heading y body (nombres + URLs Google Fonts)
- Verificación de contraste (debe estar documentada)

## TAREAS

1. **Actualizar _variables.css:**
   ```css
   :root {
     /* Fuentes - usar las del brief */
     --font-family-heading: '[Fuente del brief]', var(--font-family-base);

     /* Colores - usar hex del brief */
     --color-primary: #[del brief];
     --color-primary-hover: #[generar variación oscura 10%];

     /* Gradientes - crear coherentes con la paleta */
     --gradient-hero: linear-gradient(135deg, #[primario] 0%, #[secundario] 100%);
     --gradient-chapter-1: linear-gradient(135deg, #[acento1], #[variación]);
     --gradient-chapter-2: linear-gradient(135deg, #[acento2], #[variación]);
     --gradient-chapter-3: linear-gradient(135deg, #[acento3], #[variación]);

     /* Acentos - usar del brief */
     --color-accent-blue: #[acento1 del brief];
     --color-accent-red: #[acento2 del brief];
     --color-accent-green: #[acento3 del brief];
   }
## Importante
si no hay definiciones en **project-brief.md** has una sugerencia o respeta lo que ya esta 
````

## INFORME DE IMPLEMENTACIÓN

- **Extracción desde project-brief.md (sección Identidad Visual):**
   - Color primario: #ff7348
   - Color fondo: #fffdf8
   - Color secundario: #000000
   - Fuentes (Google Fonts):
      - Heading: Montserrat — https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap
      - Body: Rubik — https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Rubik:ital,wght@0,300..900;1,300..900&display=swap

- **Verificación de contraste (resumen):**
   - Texto negro `#000000` sobre fondo `#fffdf8`: contraste ≈ 20.7 → cumple WCAG AAA.
   - Texto blanco `#ffffff` sobre color primario `#ff7348`: contraste ≈ 2.7 → NO cumple (evitar).
   - Texto negro `#000000` sobre color primario `#ff7348`: contraste ≈ 7.8 → cumple WCAG AA/AAA.

- **Cambios aplicados (fichero):** [assets/css/_variables.css](assets/css/_variables.css)
   - `--font-family-base` → 'Rubik', system fallbacks
   - `--font-family-heading` → 'Montserrat', var(--font-family-base)
   - `--color-bg` → #fffdf8
   - `--color-text-primary` → #000000
   - `--color-primary-hover` → #e56841 (variación ~10% más oscura)

- **Recomendaciones:**
   - Usar texto oscuro sobre fondos claros y evitar texto blanco sobre el color primario.
   - Añadir los enlaces de Google Fonts en `index.html` para cargar `Montserrat` y `Rubik`.

Si quieres, puedo añadir los `<link>` de Google Fonts en [index.html](index.html) y ajustar componentes que usen `--color-text-primary` incorrectamente.