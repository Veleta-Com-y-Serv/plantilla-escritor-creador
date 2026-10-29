# Plantilla «Escritor y creador de contenido» (NoExpertise)

Web estática Astro 5 + Tailwind 4, derivada de AstroWind (MIT, ver `LICENSE-ASTROWIND.md`). Estilo: **tipográfico**
(papel + tinta + bermellón; didona de sistema enorme para los títulos, serif de lectura para el texto y letra de
máquina de escribir para rótulos, botones y fichas; bandas de borde a borde; el calderón «¶» como marca).
Todo en castellano de España, frases cortas, sin jerga.

## Dónde está cada cosa
- **Textos, contacto, menú, SEO y secciones**: `site.yaml` (raíz). Es la única fuente de contenido. `src/data/site.ts` lo carga y lo tipa; no pongas textos fijos en los componentes.
- **Colores**: `site.yaml → colores` (primario = bermellón de botones, banda de la newsletter, contacto y cubiertas; acento = ocre, solo sobre tinta: números del pódcast, etiqueta «Novedad», títulos del pie; fondo = papel; texto = tinta, también el fondo de las bandas oscuras y del pie). `src/layouts/Base.astro` los convierte en variables CSS (`--c-primario`…); los derivados (papel tostado, líneas, texto suave, tonos de las cubiertas) salen con `color-mix` en `src/styles/global.css`.
- **Tipografías y aspecto general**: `src/styles/global.css` (`--fuente-titulos` didona, `--fuente-texto` serif de lectura, `--fuente-maquina` monoespaciada; `--ancho` 90 rem; bandas `.banda-papel`, `.banda-tostado`, `.banda-tinta`, `.banda-lacre`; filas 50/50 a sangre `.fila-sangre`; botones `.btn`/`.btn-sec`/`.btn-claro`; cabecera `.cabecera--tipografico`, pie `.pie--tipografico`). Fuentes del sistema: no añadas fuentes externas.
- **Imágenes**: en `public/`. Las fotos van en `public/fotos/` (se generan con `fotos.json`); las de respaldo en `public/placeholders/` con el mismo nombre en `.svg` (`Imagen.astro` cambia a la de respaldo si la foto no existe). En `site.yaml` se referencian con ruta absoluta (`/fotos/hero.jpg`). Personas: `/placeholders/persona.svg` (**no se generan caras**).
- **Logo**: `site.yaml → logo` (ruta en `public/`); vacío = calderón «¶» + nombre en didona.
- **Pie «Web creada con NoExpertise»**: `site.yaml → marca_pie` (true en plan gratis).

## Secciones
Cada sección es un componente que solo se pinta si `site.yaml → secciones.<id>.activa` es `true`, en el orden de `site.yaml`. Un apartado nuevo puede reutilizar un diseño con `tipo: <id>`.
- `hero` → `hero.astro`: fila 7/5 (texto sobre papel + `imagen` a sangre) y franja de tinta con `nombre` enorme. `antetitulo`, `titulo`, `texto`, `etiquetas` («Novela; Relato; Pódcast»), `cta`, `cta_secundario`.
- `obras` → `obras.astro`: titular partido; la obra con `destacado: true` (o la primera) en fila 50/50 a sangre sobre tinta; el resto en rejilla de cubiertas tipográficas (foto en duotono si la hay). `cta` opcional. Sin obras, solo el titular.
- `fragmento` → `fragmento.astro`: cita enorme en cursiva sobre `imagen` a sangre con velo de tinta. `declaracion`, `autor` (de dónde sale), `antetitulo`, `cta`. Sin cita no se pinta.
- `sobre` → `sobre.astro`: fila 50/50 con `imagen` a sangre; `titulo`, `declaracion`, `texto` (párrafos, capitular), `items` (credenciales con `icono`), `cta`; `galeria` como franja de fotos de borde a borde.
- `episodios` → `episodios.astro`: banda de tinta con el nombre del pódcast o canal enorme; `texto`, `cta`, `imagen` y los episodios como índice de libro.
- `agenda` → `agenda.astro`: filas de programa con el día enorme. Sin eventos no se pinta.
- `newsletter` → `newsletter.astro`: banda bermellón; `titulo`, `texto`, `items` (qué trae cada carta), formulario de alta (mailto al email de contacto, botón `boton`), `cta` opcional (la web de la newsletter), `nota`.
- `prensa` → `prensa.astro`: `testimonios` (reseñas y lectores); la primera enorme, el resto en columnas de periódico. Sin testimonios no se pinta.
- `preguntas` → `preguntas.astro`: acordeón (`details/summary`). Sin preguntas no se pinta.
- `contacto` → `contacto.astro`: franja de foto (`imagen`) y fila 50/50: datos en bermellón + formulario con desplegable de `opciones`.
- `texto` → `texto.astro`: apartado genérico (`tipo: texto`): `titulo`, `texto`, `declaracion`, `items`, `imagen` (fila 50/50 a sangre), `cta`.

## Campos propios de esta plantilla (además del esquema común)
- `hero.etiquetas`: cadena separada por «;» («Novela; Relato; Pódcast; Talleres»).
- `obras.obras`: `[{titulo, texto, anio, editorial, categoria, estado, imagen, url, destacado}]`. `anio` como cadena; `estado` («Novedad», «Agotado» o vacío); `url` de compra (vacía = sin botón); `destacado: true` en una sola.
- `fragmento.declaracion` (la cita) y `fragmento.autor` («De «Título» (2025)»).
- `episodios.episodios`: `[{numero, titulo, texto, duracion, fecha, url}]`, todo cadenas; `url` = dónde se escucha (vacía = sin botón).
- `agenda.eventos`: `[{fecha, hora, titulo, lugar, texto, url}]`. `fecha` libre («14 de noviembre»): si empieza por el día, el día sale en grande.
- `newsletter.boton` (texto del botón de alta), `newsletter.nota` (aviso pequeño), `newsletter.cta` (enlace opcional).
- `testimonios[].nota`: sobre qué obra («Sobre «La hora del levante»»).
- `contacto.opciones`: asuntos del desplegable separados por «;». `contacto.boton`: texto del botón.
- `redes.youtube` además de `instagram`, `facebook` y `linkedin`.
- `boton_cabecera`: botón de la cabecera (por defecto, a la newsletter).

## Reglas para órdenes
1. **Activar o quitar una sección**: cambia `activa: true|false` en `site.yaml`. No borres componentes.
2. **Reordenar secciones**: mueve el bloque dentro de `secciones:` en `site.yaml`.
3. **Cambiar textos, teléfonos, fechas, libros, episodios, fotos**: solo en `site.yaml`. Si un texto contiene comas o «: » dentro de `{ … }`, ponlo entre comillas. Años, números de episodio y precios siempre entre comillas.
4. **Listas planas**: nunca una lista dentro de un elemento de lista. Para varios valores, una cadena separada por «;».
5. **No inventes** libros, premios, fechas, reseñas ni cifras: si el cliente no los da, deja el campo vacío o la lista vacía (`eventos: []`, `testimonios: []`); el componente lo oculta.
6. **Página nueva**: crea `src/pages/<slug>.astro` con `import Base from '../layouts/Base.astro'` y `<Base titulo="…" descripcion="…">…</Base>`; enlázala en `site.yaml → menu`. Ejemplo: `src/pages/aviso-legal.astro`.
7. **Sección nueva**: mejor un id nuevo con `tipo:` (`texto`, `obras`, `agenda`…). Si hace falta un diseño nuevo, crea `src/components/secciones/<id>.astro` con `seccion(Astro.props.id)` y una banda (`banda-papel`, `banda-tostado`, `banda-tinta` o `banda-lacre`) a todo el ancho. `src/pages/index.astro` la recoge sola.
8. **No tocar** `src/pages/index.astro`, `src/layouts/Base.astro`, `tailwind.config.mjs` ni `src/styles/comun.css` salvo orden explícita de diseño. Tampoco `src/lib/seo.ts` ni `src/pages/robots.txt.ts`, `sitemap.xml.ts` y `llms.txt.ts`: son el SEO de base (canónica, og:image, `noindex` si `seo.indexable: false`, JSON-LD del negocio y de las preguntas, robots, sitemap y llms.txt) y salen solos de `site.yaml`. `seo.url` y `seo.indexable` los pone la plataforma: no los cambies.
9. Mantén: `lang="es-ES"`, imágenes con `Imagen.astro` (carga diferida y respaldo), sin JavaScript nuevo salvo necesidad real, 16 px de margen lateral del texto (`.contenedor`) con fotos y fondos de borde a borde, sin scroll horizontal en móvil, ids `hero` y `contacto`. Imágenes de contenido con `alt` sacado del contenido (`altHero`, `altFicha`, `altGaleria`, `altSeccion` de `src/lib/seo.ts`); las decorativas, `alt=""`.
10. Los formularios no tienen servidor: abren el correo (`mailto`) con el email de `site.yaml`. Para envío real, cambia `action` en `src/components/ui/FormularioContacto.astro` y en `newsletter.astro`.

## Construir
```
npm ci && npm run build      # resultado en dist/
npx astro preview            # ver dist/ en http://localhost:4321
```
Antes de dar una orden por buena: `npm run build` sin errores.
