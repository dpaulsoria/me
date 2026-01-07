Tengo un proyecto “new-portfolio” hecho con Astro + Tailwind. Los proyectos se cargan desde Astro Content Collections (`src/content/projects/*.md`) y se renderizan en:
- `src/pages/index.astro` (home: solo featured ordenado por `order`)
- `src/pages/projects/index.astro` (listado)
- `src/pages/projects/[...slug].astro` (detalle: `const { Content } = await project.render();` y `<Content />`)

Quiero que revises un problema específico en mi portfolio y me digas exactamente qué cambiar.

Aquí está mi README (contexto):
[PEGO README AQUÍ]

Para depurar, usarás estos archivos (pégame la corrección con código final):
1) `src/content/config.ts`
2) `src/pages/index.astro`
3) `src/pages/projects/index.astro`
4) `src/pages/projects/[...slug].astro`
5) Un ejemplo de `src/content/projects/<proyecto>.md` (frontmatter + contenido)

Mi objetivo:
- Home: mostrar SOLO `featured: true`, ordenados por `order` (sin filtrar por fecha)
- Projects page: mostrar todos, ordenados por `order` y luego por `date` si existe
- Detail: que el Markdown se vea con estilo (Tailwind Typography / prose) y enlaces/stack funcionen

Problema actual:
[DESCRIBE AQUÍ QUÉ FALLA + PEGA EL ERROR EXACTO DE CONSOLA]

Entrega esperada:
- Diagnóstico corto
- Código corregido completo de los archivos que haga falta
- Checklist final para verificar que quedó OK
