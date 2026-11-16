# La Fabulosa · Landing page

Landing de una sola página para **La Fabulosa**, una cafetería y bar de barrio **ficticia** situada en Moratalaz (Madrid). Es un proyecto de portfolio.

- **Previsualización:** https://lafabulosa-moratalaz.netlify.app
- **Tecnología:** HTML y CSS estáticos, sin framework, sin dependencias y sin paso de compilación.
- **Hosting:** Netlify. El formulario de contacto usa Netlify Forms.

## Estructura

```
.
├── index.html            # Landing completa (estilos, logo SVG y JSON-LD incluidos)
├── gracias.html          # Página que se muestra al enviar el formulario
├── aviso-legal/          # Páginas legales de ejemplo
├── privacidad/
├── cookies/
├── img/                  # Fotografías en WebP + imagen para redes (og.jpg)
├── favicon.png
├── apple-touch-icon.png
└── netlify.toml          # Configuración de Netlify (carpeta de publicación)
```

## Cómo arrancar el proyecto

No hay nada que instalar ni compilar.

**Abrirlo en local:**

1. Clona o descarga el repositorio.
2. Sirve la carpeta con cualquier servidor estático, por ejemplo:
   ```bash
   npx serve .
   # o
   python3 -m http.server 8000
   ```
3. Abre `http://localhost:3000` (con `serve`) o `http://localhost:8000` (con Python).

También puedes abrir `index.html` directamente en el navegador, aunque el formulario solo envía cuando la web está publicada en Netlify (en local, el envío da error, y es normal).

**Publicarlo en Netlify:**

- **Arrastrando:** entra en https://app.netlify.com/drop y arrastra la carpeta del proyecto.
- **Desde GitHub:** en Netlify, *Add new project › Import an existing project*, elige este repositorio y deja vacío el comando de compilación. La carpeta de publicación ya está definida en `netlify.toml`.

Después, para que el formulario funcione:

1. En el panel del sitio, ve a **Forms › Enable form detection**.
2. Vuelve a publicar (arrastrando la carpeta otra vez o lanzando un nuevo deploy). La detección solo se aplica a partir de la siguiente publicación.
3. Opcional: en **Forms › Form notifications**, activa el aviso por email de cada mensaje.

## Qué está simulado

| Elemento | Situación |
| --- | --- |
| El negocio | La Fabulosa no existe. La historia (fundada en 1956 por Jacinto, llevada hoy por sus nietos Javier y Diego) es inventada. El footer lo indica. |
| Dirección | Calle Fuente Carrantona, 127. La calle es real; el número es inventado. El mapa usa una búsqueda aproximada de la calle. |
| Teléfono y email | 913 333 333 e info@lafabulosacafe.es son de ejemplo. |
| Instagram | @lafabulosacafe es un usuario inventado. Las tres imágenes del bloque de Instagram no son publicaciones reales. |
| Fotografías | Generadas con IA (Nano Banana Pro). No muestran ningún local real. |
| Carta | Sin precios, a propósito. |
| Páginas legales | Aviso legal, privacidad y cookies son páginas de ejemplo sin texto legal real. |
| Indexación | La web lleva `noindex, nofollow` para que los buscadores no la indexen. Quítalo en `index.html` si algún día se publica de verdad. |
| Formulario de contacto | **No está simulado:** envía de verdad a Netlify Forms y redirige a `gracias.html`. Tiene un campo trampa (honeypot) contra bots. |

## Cómo reiniciar los datos de ejemplo

El proyecto no tiene base de datos: todos los datos de ejemplo (textos, horarios, dirección, teléfono) están escritos en `index.html`, y el JSON-LD del `<head>` los repite para los buscadores. Para reiniciarlos basta con volver a la versión del repositorio:

```bash
git checkout -- index.html
```

Los únicos datos que se generan al usar la web son los **mensajes del formulario**, que se guardan en Netlify. Para borrarlos:

1. En el panel del sitio, ve a **Forms** y abre el formulario **contacto**.
2. Selecciona los mensajes (también los de la pestaña *Spam*) y bórralos.

Si cambias los datos de contacto u horarios, cámbialos en dos sitios de `index.html`: en el texto visible y en el bloque `<script type="application/ld+json">`.

## Identidad

- **Colores:** caoba `#6B2917`, rosa `#E8A48C`, negro `#1E1A17`, gris `#EBEBEB`, crema `#F4EBDD`.
- **Tipografías:** DM Sans (textos) y Danfo (monograma "LF"), desde Google Fonts. El logotipo es un SVG con el texto convertido en trazados.
