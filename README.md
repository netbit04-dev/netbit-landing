# Handoff: Landing page NetBit

## Resumen
Landing de una sola página para **NetBit Ingeniería Informática** (Santa Elena, Ecuador). Objetivo: presentar tres productos ya desarrollados (Mi Bolsillo, Mi Negocio, SCRUTA) y generar contacto por WhatsApp / teléfono. Idioma: español. Público: emprendedores y PYMES.

## Sobre los archivos de este paquete
Los archivos HTML incluidos son **referencias de diseño**, no código de producción para copiar tal cual:

- `reference.html` — la landing completa en HTML/CSS plano, autocontenida (solo depende de Google Fonts). Ábrela en el navegador para ver el diseño final. Úsala como fuente de verdad visual.
- `Landing NetBit v2.dc.html` — el archivo original del entorno de diseño. Sirve solo de referencia; no se ejecuta fuera de ese entorno.

La tarea es **recrear este diseño en el entorno del proyecto destino** (Next.js/React, Astro, Vue, WordPress, HTML estático, etc.) usando sus patrones y librerías existentes. Si no existe proyecto aún, elegir el stack más adecuado — para una landing estática, Astro o Next.js con Tailwind es suficiente — e implementarlo ahí.

## Fidelidad
**Alta fidelidad (hi-fi).** Colores, tipografía, espaciados y jerarquía son definitivos. Reprodúcelos con precisión. Lo único pendiente son las **imágenes reales**: en el diseño hay tres marcos vacíos (placeholders grises) donde van ilustraciones o capturas de producto.

## Estructura de la página (de arriba a abajo)

### 1. Nav (sticky opcional, hoy no sticky)
- Fila flex, ancho máximo 1200px, padding horizontal `clamp(20px, 5vw, 72px)`, padding vertical 18px, borde inferior 1px `#201e1d` al 12%.
- Izquierda: marca **NetBit** (Poppins 700, 20px). Centro/izquierda: enlaces `Productos`, `Cómo trabajamos`, `Nosotros` (15px, color texto, hover acento). Derecha (`margin-left:auto`): botón primario **Escríbenos** → WhatsApp.

### 2. Hero — banda de color
- Fondo `--color-accent-100` (#e6ecfd), sin bordes.
- Grid 2 columnas `minmax(0,6fr) minmax(0,5fr)`, gap `48px clamp(32px,5vw,80px)`, padding vertical 84px, `align-items:center`.
- Columna izquierda:
  - Kicker: `INGENIERÍA INFORMÁTICA — SANTA ELENA, ECUADOR` — 13px, uppercase, weight 600, letter-spacing .1em, color `--color-accent-700`, margen inferior 18px.
  - H1: “Tres sistemas listos para tu negocio.” — Poppins 700, `clamp(38px,5vw,64px)`, line-height 1.08, letter-spacing -0.02em.
  - Párrafo: 17px / 28px, `max-width:52ch`, margen superior 28px. Texto: “Software ya construido y en funcionamiento: finanzas personales, control de ventas y control electoral. Se instalan, se configuran y empiezan a trabajar.”
  - Botones (flex, gap 12px, margen superior 32px): primario **Ver los productos** (ancla `#productos`), ghost **Llamar 0939216689** (`tel:+593939216689`).
- Columna derecha: marco de imagen 4:3, `border-radius:14px`, `overflow:hidden`, `box-shadow: var(--shadow-md)`. Contenido: ilustración o captura del sistema.

### 3. Productos
- Sección de ancho 1200px, padding 84px arriba / 70px abajo.
- Kicker `PRODUCTOS` + H2 “Sistemas que ya están funcionando” (Poppins 700, `clamp(28px,3.2vw,40px)`, `max-width:24ch`).
- Grid de 3 tarjetas (`repeat(3, minmax(0,1fr))`, gap 24px, margen superior 48px). Cada tarjeta: fondo `--color-bg`, padding 32px, `border-radius:16px`, `box-shadow: var(--shadow-sm)`.
  - Icono: cuadro 52×52, fondo `--color-accent`, radius 14px, icono Lucide 24px trazo 2px en `#f3f2f2` (wallet / shopping-cart / triángulo-actas).
  - H3 24px Poppins 700 (margen superior 24px), etiqueta uppercase 12px en `--color-accent-700`, párrafo 15.5px / 27px.
- Contenido exacto:
  1. **Mi Bolsillo** — GESTIÓN FINANCIERA — “Ingresos y gastos, presupuestos por categoría y reportes de cierre de mes. Para saber dónde está el dinero antes de decidir.”
  2. **Mi Negocio** — CONTROL DE VENTAS — “Ventas del día, inventario, clientes y cierre de caja en un solo lugar. Para negocios que hoy llevan las cuentas en cuaderno.”
  3. **SCRUTA** — CONTROL ELECTORAL — “Registro de actas, conteo por junta y consolidado en tiempo real. Resultados propios y verificables la misma noche.”

### 4. Cómo trabajamos — banda de color
- Fondo `--color-accent-100`. Grid `minmax(0,5fr) minmax(0,6fr)`, gap igual al hero, padding vertical 84px.
- Izquierda: marco de imagen 1:1 (radius 14px, shadow-md) — ilustración del proceso.
- Derecha: kicker `CÓMO TRABAJAMOS`, H2 “De la llamada al sistema andando”, y 4 pasos. Cada paso: grid `44px 1fr`, gap 20px, padding vertical 22px, borde superior 1px `--color-accent-200`; número (01–04) 15px en `--color-accent-700`; título 17px Poppins 600; descripción 15px / 26px.
  - 01 **Contacto** — “Nos cuentas cómo trabajas hoy y qué necesitas resolver.”
  - 02 **Demostración** — “Te mostramos el sistema funcionando con datos reales de ejemplo.”
  - 03 **Configuración** — “Cargamos tus categorías, productos o juntas y dejamos todo listo.”
  - 04 **Puesta en marcha** — “Capacitación corta al equipo y acompañamiento las primeras semanas.”

### 5. Nosotros
- Grid `minmax(0,6fr) minmax(0,5fr)`, padding vertical 84px, fondo base.
- Izquierda: kicker `SOBRE NETBIT`, H2 “Desarrollo propio, soporte cercano” (`max-width:26ch`), párrafo 16px / 28px (`max-width:52ch`): “NetBit Ingeniería Informática desarrolla y mantiene sus propios sistemas desde Santa Elena, Ecuador. Cada producto se entrega instalado, configurado y con soporte directo — sin intermediarios ni licencias de terceros.” Botón ghost **Escribir por WhatsApp**.
- Derecha: foto del equipo/trabajo en **blanco y negro** (`filter: grayscale(1)`), radius 14px, shadow-md, 4:3.

### 6. Banner CTA
- Fondo `--color-accent` (#2258e6), texto `--color-bg`. Flex con `justify-content:space-between`, `flex-wrap:wrap`, gap 32px, padding vertical 72px.
- H3 “¿Listo para empezar? Los sistemas ya existen.” — `clamp(26px,3vw,38px)`, `max-width:22ch`.
- Botón blanco: fondo `--color-bg`, texto `--color-accent-700`, borde 2px blanco → WhatsApp “Escribir al 0939216689”.

### 7. Footer
- Fondo `--color-text` (#201e1d), texto `--color-bg`. Grid `2fr 1fr 1fr 1fr`, gap `40px clamp(24px,4vw,64px)`, padding 64px arriba / 40px abajo.
- Columna 1: marca NetBit 22px + “Ingeniería Informática / Santa Elena, Ecuador” (14px, opacidad .8).
- Columnas 2–4 con encabezados uppercase 12px (opacidad .7): **Productos** (Mi Bolsillo, Mi Negocio, SCRUTA), **Página** (anclas a las secciones), **Contacto** (WhatsApp 0939216689, contacto@netbitec.app).
- Línea final: “© 2026 NetBit Ingeniería Informática” 12px, opacidad .65.

## Interacciones y comportamiento
- Navegación interna por anclas (`#productos`, `#proceso`, `#nosotros`) con `scroll-behavior: smooth`.
- Botón primario: hover → `--color-accent-600`; ghost: hover → fondo `--color-accent-100`.
- Foco de teclado: `outline: 2px solid var(--color-accent); outline-offset: 2px` en todos los interactivos (no dejar el azul del navegador).
- Enlaces externos: WhatsApp `https://wa.me/593939216689`, teléfono `tel:+593939216689`, correo `mailto:contacto@netbitec.app`.
- Sin estado de aplicación, sin formularios, sin fetch. El teléfono es el único dato parametrizable (en el diseño es una prop `telefono`; el prefijo internacional se calcula reemplazando el 0 inicial por 593).
- Responsive: ≤900px las secciones a dos columnas pasan a una (la imagen queda arriba en el hero y en “Cómo trabajamos”), las tarjetas a 2 columnas y el footer a 2; ≤560px las tarjetas a 1 columna. Todo fluido, sin anchos fijos.

## Design tokens

Colores
- Fondo: `#f3f2f2` · Superficie: `#eae9e9` · Texto: `#201e1d`
- Acento (azul): `#2258e6`. Rampa: 100 `#e6ecfd`, 200 `#c3d2fa`, 300 `#9db4f6`, 400 `#6287ef`, 500 `#2258e6`, 600 `#1c48bd`, 700 `#163893`, 800 `#102969`, 900 `#0a1b45`.
- Texto en acento a tamaño pequeño: usar 700 (`#163893`), no el 500.

Tipografía
- Títulos: **Poppins** 700 (subtítulos de paso en 600).
- Cuerpo, botones, nav y kickers: **Hanken Grotesk** 400/500/600.
- Kickers: 12–13px, uppercase, weight 600, letter-spacing .1em.
- Escala: H1 `clamp(38px,5vw,64px)`/1.08 · H2 `clamp(28px,3.2vw,40px)`/1.12 · H3 24px/1.2 · cuerpo 15–17px con line-height 26–28px.

Espaciado y forma
- Escala: 4 / 8 / 12 / 16 / 24 px. Padding de sección: 84px vertical. Ancho máximo de contenido: 1200px. Gutter: `clamp(20px,5vw,72px)`.
- Radios: botones 10px, marcos de imagen 14px, cuadros de icono 14px, tarjetas 16px.
- Sombras: `sm 0 1px 2px #2d2b2b/14%` · `md 0 3px 10px #2d2b2b/16%` · `lg 0 12px 32px #2d2b2b/22%`.

## Assets
- **Iconos**: Lucide (https://lucide.dev), trazo 2px, extremos redondeados. Los tres SVG están inline en `reference.html`.
- **Fuentes**: Google Fonts (Poppins, Hanken Grotesk).
- **Imágenes**: pendientes. Tres huecos — hero (4:3), proceso (1:1), equipo (4:3, en blanco y negro). Hoy son placeholders grises; hay que reemplazarlos por ilustraciones o capturas reales de Mi Bolsillo / Mi Negocio / SCRUTA.
- No hay logotipo en archivo: la marca se compone como texto “NetBit”. Si existe un logo, sustituir el texto del nav y del footer.

## Archivos
- `reference.html` — diseño final en HTML/CSS plano (abrir en navegador).
- `Landing NetBit v2.dc.html` — archivo original del entorno de diseño (solo referencia).
