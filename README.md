# Pink Case Móvil — Catálogo con venta guiada

Página estática (sin backend) del catálogo de **Pink Case Móvil**, negocio de accesorios para celulares en Ixtlahuaca, Estado de México.

## Qué hace

- **Asesor guiado**: el visitante elige marca/modelo de su celular → para quién es → estilo y color, y ve solo las fundas compatibles, con las más vendidas primero.
- **Catálogo completo con filtros** por categoría (fundas, micas, audífonos, accesorios).
- **Complementos sugeridos**: micas, audífonos y cargadores que acompañan la compra.
- **Pedido por WhatsApp**: el carrito arma un mensaje pre-llenado que se envía por WhatsApp al negocio.
- Secciones de confianza: equipo (asesoras reales), tiendas, garantía de micas con seguro y enlace a la página de Facebook.

## Objetivo general

Convertir esta página en el canal digital de Pink Case que replique la asesoría del local físico y cierre ventas por WhatsApp, sin depender de redes sociales para vender.

## Objetivos específicos

1. Guiar a la clienta paso a paso (modelo del celular → para quién es → estilo → color) mostrándole solo las fundas compatibles, con las más vendidas primero.
2. Exhibir el catálogo completo con filtros por categoría (fundas, micas, audífonos, accesorios).
3. Sugerir complementos (micas, audífonos, cargadores) para elevar el ticket promedio de cada pedido.
4. Armar el pedido y enviarlo por WhatsApp con un mensaje pre-llenado, listo para que el negocio lo confirme.
5. Generar confianza con asesoras reales, fotos de los locales, garantía de micas con seguro y enlace a la página de Facebook.
6. Mantener la página rápida, mobile-first y 100% estática: sin backend, sin base de datos y sin dependencias externas que puedan fallar.

## Limitaciones: lo que esta página no puede llevar

Reglas que se cumplen en cada publicación. Nada de esto puede aparecer en una página publicada para Pink Case:

1. **Datos personales de clientas**: ni nombres, ni teléfonos, ni capturas de conversaciones de WhatsApp.
2. **Precios inventados**: solo se publican rangos y precios reales del negocio.
3. **Inventario en tiempo real**: la página es estática y no puede prometer disponibilidad garantizada ni existencias actualizadas.
4. **Fotos ajenas**: solo imágenes del negocio o autorizadas expresamente por Axel.
5. **Formularios de datos personales**: no hay backend donde guardarlos ni aviso de privacidad que los respalde.
6. **Cambios en Facebook**: esta página no publica ni modifica nada en la página de Facebook del negocio.
7. **Rastreadores de terceros**: ningún script de analítica, píxel o publicidad sin aprobación explícita.
8. **Dependencia de internet para lo esencial**: fuentes, estilos e imágenes van autohospedados; la página debe verse bien aun con conexión lenta.
9. **Promesas incumplibles**: nada de envíos, entregas o tiempos que el negocio no pueda cumplir.
10. **Tono ajeno a la marca**: nada de faltas de ortografía ni textos que no suenen a Pink Case.

## Tecnología

- Un solo `index.html`: HTML + CSS + JavaScript vanilla, sin dependencias ni paso de compilación.
- Diseño con variables CSS (tokens), modo oscuro neón negro/rosa, mobile-first.
- Tipografías autohospedadas en `assets/fonts/`: Unbounded (titulares, precios, botones) y Archivo (texto).
- Datos de productos definidos en arreglos de JavaScript (`FUNDAS`, `MICAS`, `EXTRAS`, `MODELS`); el estado del pedido se guarda en `localStorage`.

## Publicar

Cualquier hosting de archivos estáticos sirve: GitHub Pages, Netlify, Cloudflare Pages o un cPanel. Solo hay que subir `index.html` y la carpeta `assets/`.

## Estructura

```
index.html        # todo el sitio
assets/
  funda-*.jpg     # fotos de fundas
  mica-*.jpg      # fotos de micas
  audifonos-*.jpg # fotos de audífonos
  accesorio-*.jpg # fotos de accesorios
  asesora-*.jpg   # fotos del equipo
  tienda-*.jpg    # fotos de los locales
  logo.jpg        # logo del negocio
  fonts/          # Unbounded + Archivo en woff2
```

## Editar el catálogo

Los productos viven en los arreglos de JavaScript al final de `index.html`. Para agregar o cambiar un producto basta con editar su objeto (id, nombre, precio, imagen, compatibilidad) y recargar la página.
