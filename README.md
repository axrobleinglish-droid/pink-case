# Pink Case Móvil — Catálogo con venta guiada

Página estática (sin backend) del catálogo de **Pink Case Móvil**, negocio de accesorios para celulares en Ixtlahuaca, Estado de México.

## Qué hace

- **Asesor guiado**: el visitante elige marca/modelo de su celular → para quién es → estilo y color, y ve solo las fundas compatibles, con las más vendidas primero.
- **Catálogo completo con filtros** por categoría (fundas, micas, audífonos, accesorios).
- **Complementos sugeridos**: micas, audífonos y cargadores que acompañan la compra.
- **Pedido por WhatsApp**: el carrito arma un mensaje pre-llenado que se envía por WhatsApp al negocio.
- Secciones de confianza: equipo (asesoras reales), tiendas, garantía de micas con seguro y enlace a la página de Facebook.

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
