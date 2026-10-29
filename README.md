# Plantilla NoExpertise · Escritor y creador de contenido

Web tipográfica a ancho completo para escritores, pódcast, creadores, canales de vídeo y formadores en línea:
libros con cubiertas tipográficas, un fragmento en grande, el pódcast como índice de libro, agenda de
presentaciones, carta mensual, prensa y lectores, preguntas y contacto.

- Sectores: escritor, podcast, creador, youtuber, formador-online. Estilo: tipografico. Plan mínimo: gratis.
- Secciones: hero, obras, fragmento, sobre, episodios, agenda, newsletter, prensa, preguntas, contacto (+ `texto` genérico).
- Campos propios: `hero.etiquetas`, `obras.obras[]` (titulo, texto, anio, editorial, categoria, estado, imagen, url,
  destacado), `fragmento.declaracion/autor`, `episodios.episodios[]` (numero, titulo, texto, duracion, fecha, url),
  `agenda.eventos[]` (fecha, hora, titulo, lugar, texto, url), `newsletter.boton/nota/cta`, `testimonios[].nota`,
  `contacto.opciones/boton`, `redes.youtube`.
- Diseño: papel + tinta + bermellón; didona de sistema enorme, serif de lectura y letra de máquina de escribir;
  bandas de borde a borde (papel, papel tostado, tinta, bermellón), portada 7/5 con foto a sangre y el nombre de
  borde a borde, filas 50/50 a sangre, cabecera de periódico con regla gruesa y pie de tinta con columnas.
  Detalle en `DISEÑO.md`.
- SEO de base incluido (`src/lib/seo.ts`): canónica, og:image, JSON-LD del negocio y de las preguntas frecuentes,
  `robots.txt`, `sitemap.xml` y `llms.txt`; `noindex` si `seo.indexable: false`.
- Contenido editable en `site.yaml` (ejemplo: una escritora ficticia de Cádiz); metadatos y guion del asistente en
  `template.yaml`; reglas para el agente en `CLAUDE.md`; fotos a generar en `fotos.json`.

```
npm ci
npm run dev      # desarrollo
npm run build    # web estática en dist/
```

Basada en [AstroWind](https://github.com/onwidget/astrowind) © onWidget, licencia MIT (`LICENSE-ASTROWIND.md`).
Imágenes de relleno (`public/placeholders/`) dibujadas para esta plantilla, sin licencias de terceros.
