# Badge Women Community Fest III — Warmi Ventures

Generador de badge personalizado para que las participantes del Women Community Fest III suban su foto, escriban su nombre, descarguen su badge en PNG y compartan su participación.

Es un sitio **100% estático**: un único archivo `index.html` con HTML, CSS y JavaScript (sin frameworks, sin build step, sin backend). Las imágenes de fondo están incrustadas en base64 dentro del propio HTML.

## Requisitos

- Ninguno. No hay dependencias de Node, npm, ni librerías externas.
- Solo un navegador moderno (Chrome, Safari, Edge, Firefox) para verlo o editarlo.

## Ejecutar en local

No hace falta instalar nada. Dos opciones:

1. Doble clic en `index.html` y ábrelo directamente en el navegador.
2. O sirve la carpeta con cualquier servidor estático, por ejemplo:
   ```bash
   npx serve .
   ```
   y abre la URL que te indique en consola (normalmente `http://localhost:3000`).

## Build

No aplica. No hay paso de compilación: `index.html` ya es el artefacto final que se despliega tal cual.

## Importar a GitHub

1. Crea un repositorio nuevo (vacío) en GitHub.
2. Copia `index.html` y este `README.md` dentro del repositorio.
3. `git add . && git commit -m "Badge Women Community Fest III" && git push`.

## Importar a v0 de Vercel

1. Abre v0 (https://v0.app).
2. Crea un proyecto nuevo y sube/pega el contenido de `index.html`.
3. v0 lo reconocerá como una página estática; no se necesita configuración adicional.

## Desplegar en Vercel

**Opción A — desde GitHub (recomendada):**
1. Entra a https://vercel.com → "Add New…" → "Project".
2. Importa el repositorio de GitHub donde subiste `index.html`.
3. Vercel detecta automáticamente que es un sitio estático (sin framework). No cambies ningún ajuste de build — déjalo vacío/"Other".
4. Pulsa "Deploy".

**Opción B — subida directa:**
1. Entra a https://vercel.com/new.
2. Arrastra la carpeta del proyecto (con `index.html`) al área de carga.
3. Pulsa "Deploy".

No se requieren variables de entorno, claves ni credenciales — el proyecto no usa ninguna API externa.

## Privacidad

La fotografía y el nombre se procesan **enteramente en el navegador de la participante** (vía `<canvas>`). Nada se sube a ningún servidor, no hay base de datos, no hay analítica que capture datos personales.

## Recursos pendientes / limitaciones conocidas

- El enlace de LinkedIn de **Mujeres en Expansión** no estaba confirmado en el material provisto, así que la tarjeta de esa comunidad solo muestra su Instagram (no se inventó ningún enlace).
- El botón "Compartir" (compartir nativo del dispositivo) solo aparece en navegadores/dispositivos que soportan la Web Share API (la mayoría de móviles; no todos los navegadores de escritorio). Donde no está disponible, el flujo recomendado sigue siendo "Copiar mi mensaje" + pegarlo manualmente.
- La descarga del badge usa la función de descarga del entorno de Claude.ai en la vista previa de este artifact. Una vez desplegado en Vercel, ese mismo botón usa `canvas.toBlob()` + descarga de archivo nativa del navegador — funciona igual, sin depender de Claude.ai.
