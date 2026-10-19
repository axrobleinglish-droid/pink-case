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

## Limitaciones técnicas: lo que una página pública estática no puede hacer

Reglas técnicas que se cumplen en cada publicación. Esta página es 100% estática (sin servidor ni base de datos), y eso impone lo siguiente:

1. **Sin backend, sin base de datos**: nada se guarda en un servidor. No hay registro de pedidos, usuarios ni inventario centralizado.
2. **Sin inventario en tiempo real**: la página no puede prometer existencias. La disponibilidad siempre se confirma por WhatsApp.
3. **Sin pagos en línea**: no hay pasarela de pago ni cobro automático. El cierre de la venta es por WhatsApp.
4. **Sin cuentas de usuario**: todo lo que la página "recuerda" (el pedido en curso) vive en el navegador del visitante (`localStorage`) y se pierde si cambia de dispositivo o borra sus datos.
5. **Todo el código es público**: cualquiera puede ver el HTML y el JavaScript. Nunca se ponen claves, tokens, números privados ni datos sensibles en el código.
6. **Sin envíos automáticos**: la página no manda correos, SMS ni mensajes de WhatsApp por sí sola; solo abre el chat con el mensaje pre-llenado y la clienta presiona enviar.
7. **Formularios limitados**: sin servidor no hay a dónde mandar los datos de un formulario; solo sirven para armar el mensaje del pedido.
8. **Fotos optimizadas**: el hosting estático sirve los archivos tal cual; cada imagen debe pesar poco para que la página cargue rápido en celulares con datos limitados.
9. **Cambios manuales**: precios, productos y textos solo se actualizan editando el código y volviendo a publicar. No hay panel de administración.
10. **Una sola vista previa para compartir**: sin servidor no se generan vistas previas distintas por producto; toda la página comparte el mismo título, descripción e imagen al compartirse en redes.

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
