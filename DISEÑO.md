# Escritor y creador de contenido: brief de diseño

Plantilla `escritor-creador` creada el 29/10/2026 a partir de `profesional-autonomo` con `php artisan plantillas:nueva`
y rediseñada entera a ancho completo. Este fichero se queda en el repo: es lo que lee quien (persona o agente) la rediseñe.

## Brief

- **Para quién**: escritoras y escritores, pódcast, creadores de contenido, canales de vídeo y formadores en línea
  (`sectores`: escritor, podcast, creador, youtuber, formador-online). Quien entra es lector, oyente, librero,
  periodista o alguien que quiere invitarle a un acto: quiere ver qué ha publicado, escuchar lo último, saber
  dónde va a estar y cómo escribirle.
- **Qué tiene que conseguir la web**: que se apunten a la newsletter (botón de la cabecera) y que escriban para
  presentaciones, talleres o prensa. Después, comprar un libro o escuchar un episodio.
- **Tono y estilo** (`estilo: tipografico`): literario, sobrio, con carácter. Sí: suplementos culturales, páginas de
  editoriales independientes, galeradas de imprenta. No: web de «influencer» con degradados ni blog con tarjetas.
- **Paleta de ejemplo**: primario bermellón `#b8381f`, acento ocre `#e3a83b` (solo sobre tinta), fondo papel
  `#f3ede1`, texto tinta `#17171f`. Derivados con `color-mix`: papel tostado (tinta 8 % sobre papel), líneas,
  texto suave y los cuatro tonos de las cubiertas (bermellón, tinta, ocre oscurecido, bermellón oscurecido).
- **Tipografía** (del sistema): títulos en didona («Bodoni 72», «Bodoni MT», Didot; respaldo «Sitka Banner»,
  Georgia), 400, enormes (portada hasta 7,25 rem y 2,75 rem en móvil; el nombre de la franja ocupa el ancho de la
  ventana); texto en serif de lectura (Charter, «Sitka Text», Cambria, Georgia); rótulos, botones, fechas y fichas
  en monoespaciada en mayúsculas espaciadas (letra de máquina de escribir). Antetítulos con un filete de color.
- **Motivos propios**: el calderón «¶» (marca sin logo, favicon, fondo gigante de la newsletter), las reglas gruesas
  de tinta (cabecera de periódico, titulares partidos, agenda, columnas de prensa), las cubiertas tipográficas con
  la foto en duotono, el índice de libro con puntos guía para los episodios y la capitular bermellón.

## Ritmo de bandas (todas de borde a borde)

1. Cabecera fija en papel con regla gruesa de tinta; menú en letra de máquina; botón «La carta del mes».
2. `hero`: fila 7/5 (texto sobre papel, foto a sangre tocando el borde derecho; en móvil la foto va arriba) y
   franja de tinta con el nombre en didona de borde a borde. `etiquetas` con barras bermellón. Casi pantalla completa.
3. `obras`: papel; titular partido (título enorme / texto y enlace) sobre regla gruesa; la obra destacada en fila
   50/50 a sangre sobre tinta; el resto en rejilla de cubiertas (lista con cubierta pequeña en móvil, 3 columnas a
   768, 4 a 1200).
4. `fragmento`: foto a sangre con velo de tinta y cita enorme en cursiva con comilla bermellón gigante.
5. `sobre`: fila 50/50 con la foto a sangre a la izquierda; declaración con filete, capitular, credenciales con
   icono en cuadro de tinta; franja de tres fotos de borde a borde sin márgenes.
6. `episodios`: tinta plena; nombre del pódcast a 11,5 vw; índice con números en ocre, puntos guía y botón redondo.
7. `agenda`: papel; filas de programa con el día enorme en bermellón y columnas fijas (lugar, hora, enlace).
8. `newsletter`: bermellón pleno con el calderón gigante de fondo; título enorme y formulario de alta en línea.
9. `prensa`: papel tostado; primera reseña enorme en cursiva, el resto en columnas de periódico desde 1024 px.
10. `preguntas`: papel; titular fijo a la izquierda, acordeón en didona a la derecha.
11. `contacto`: franja de foto 21:7 a sangre y fila 50/50 (datos en didona grande sobre bermellón / formulario sobre
    papel tostado).
12. Pie de tinta con cuatro columnas (marca, índice, contacto, la carta del mes) y línea legal en letra de máquina.

## Responsive

Móvil primero: 16 px de margen del texto, fotos y fondos de borde a borde, botones de 48 px, menú plegable con
`details` (hasta 1100 px, porque el menú en mayúsculas espaciadas necesita sitio). A 768 cambian la portada (foto
16:9), las cubiertas (3 columnas) y la agenda; desde 1024 las filas pasan a 50/50 con el texto alineado con el
contenedor (`--medio`) y la prensa a columnas. Sin scroll horizontal (comprobado a 375, 768 y 1440).

## Fotos

`fotos.json` (12): mesa de escribir junto a un balcón con mar (portada), cuatro libros de cubierta lisa sin letras en
escenas de Cádiz (cubiertas), hojas y pluma con luz rasante (fragmento), estudio con estantería (sobre), azotea al
atardecer, cuadernos y mesa de taller (franja), micrófono de pódcast (episodios) y calle del casco antiguo
(contacto). Sin personas, sin texto legible, sin logotipos. Las cubiertas ponen el título con CSS, nunca en la foto.

## Qué no hacer

- Nada de caja centrada estrecha con tarjetas blancas ni del hero 5/7 con retrato de `profesional-autonomo`.
- No usar la serif de `psicologia-terapia` (Iowan/Palatino) ni la serif fina de `tienda-moda`: aquí manda la didona
  con la monoespaciada.
- No inventar premios, cifras de ventas ni reseñas de medios reales: el ejemplo usa medios ficticios.
