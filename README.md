# Hack4u Community Center

Sitio comunitario de artículos en Markdown, creado con React y Vite. El contenido se guarda en `content/`; durante la preparación se generan el catálogo y el índice de búsqueda.

Usa archivos con extensión `.md`. Un prefijo numérico, como `01-`, permite ordenar las entradas. La guía para proponer cambios está en [CONTRIBUTING.md](CONTRIBUTING.md).

## Metadatos del artículo

Opcionalmente, coloca este bloque al principio del archivo. Debe empezar y terminar con una línea de tres guiones:

```yaml
---
title: Título del artículo
description: Resumen breve que aparece en el catálogo.
tags: linux, bspwm, x11
badge: Solución
order: 2
banner: assets/img/mi-banner.png
---
```

- `title`: título del artículo. Si falta, se usa el primer encabezado de nivel 1 o el nombre del archivo.
- `description`: resumen que se muestra en el catálogo.
- `tags`: etiquetas separadas por comas; también se acepta una lista JSON, por ejemplo `["linux", "bspwm"]`.
- `badge`: distintivo opcional en la tarjeta.
- `order`: número para ordenar artículos y categorías; los prefijos numéricos del nombre también establecen el orden.
- `banner`: ruta desde la raíz pública del sitio para la imagen de portada. Si no indicas ningún banner automáticament se pondrá el título.

## Sintaxis Markdown

El contenido usa Markdown con las extensiones habituales de GitHub Flavored Markdown (GFM). Los ejemplos de esta sección se escriben en archivos `.md`.

### Encabezados y párrafos

Usa de uno a seis signos `#` al principio de la línea. Deja una línea en blanco entre párrafos y bloques:

```md
# Título principal
## Sección
### Subsección

Este es un párrafo. Una línea en blanco inicia otro párrafo.
```

### Énfasis

```md
*cursiva* o _cursiva_
**negrita** o __negrita__
~~texto tachado~~
`código dentro de una frase`
```

### Listas

Las listas pueden ser sin ordenar, ordenadas o tareas. Indenta los elementos anidados con espacios:

```md
- Primer elemento
- Segundo elemento
	- Elemento anidado

1. Primer paso
2. Segundo paso

- [x] Comprobado
- [ ] Pendiente
```

### Enlaces

```md
[Sitio externo](https://example.com)
[Otro artículo](../FAQ/mi-articulo.md)
[Ir a una sección](#nombre-de-la-seccion)
```

Los enlaces a artículos del sitio deben apuntar a su archivo `.md` y usar una ruta relativa al archivo actual. Para enlazar a un encabezado, el sitio convierte el texto a minúsculas, quita tildes y reemplaza los grupos de caracteres no alfanuméricos por guiones. Por ejemplo, `## Configuración básica` tiene el ancla `#configuracion-basica`. Los enlaces HTTP y HTTPS se abren en una pestaña nueva.

### Imágenes

```md
![Descripción accesible](imagenes/captura.png)
![Logo del proyecto](https://example.com/logo.png)
```

Las rutas relativas se resuelven desde la carpeta del artículo. Añade una descripción entre corchetes, especialmente para capturas importantes. Para la imagen de portada de una tarjeta, usa `banner` en los metadatos.

### Código

Para código en línea, usa una tilde invertida. Para varias líneas, usa tres tildes invertidas y, opcionalmente, indica el lenguaje:

````md
Ejecuta `ip addr` para consultar las interfaces.

```bash
ip addr
```
````

Los bloques conservan el formato y ofrecen un botón para copiar. No incluyas credenciales, tokens ni datos personales en ejemplos o logs.

### Citas y avisos

Una cita normal comienza con `>`:

```md
> Una cita o fragmento de documentación.
```

Para mostrar un aviso destacado, la primera línea del bloque debe empezar con uno de estos marcadores: `[!DANGER]`, `[!WARNING]`, `[!NOTE]` o `[!UPDATE]`.

```md
> [!WARNING]
> Revisa el comando antes de ejecutarlo.

> [!NOTE]
> Este ajuste solo aplica a sesiones X11.
```

### Tablas

Separa las columnas con barras verticales y la fila de encabezado de las demás con guiones:

```md
| Comando | Uso |
| --- | --- |
| `ip addr` | Consultar interfaces |
| `ping host` | Comprobar conectividad |
```

Puedes alinear columnas con dos puntos en la fila separadora, por ejemplo `| :--- | ---: |`.

### Separadores y caracteres literales

Una línea con tres guiones separa secciones. Para mostrar literalmente un carácter que Markdown interpreta, escápalo con una barra invertida, como `\*no cursiva\*`.

```md
---

Escribe \# si quieres que el signo `#` no inicie un encabezado.
```

### Vídeos de YouTube

Escribe el shortcode en una línea propia. Se aceptan enlaces `youtu.be` y enlaces habituales de `youtube.com`:

```md
@[youtube](https://youtu.be/VIDEO_ID)
```

El reproductor mantiene una proporción 16:9 y solo permite vídeos de YouTube.

### Repositorios de GitHub

Este shortcode crea una tarjeta con el nombre y la descripción pública del repositorio:

```md
@[github](https://github.com/usuario/repositorio)
```

La URL debe apuntar directamente a un repositorio válido. Si no hay descripción pública, se muestra el nombre del repositorio.

## Previsualizar

Desde esta carpeta, ejecuta `npm ci` y después `npm run dev`. Para comprobar la salida de producción, ejecuta `npm run build`; Vite genera `dist/`, que publica GitHub Pages. No abras el HTML con `file://`: el navegador necesita cargar el catálogo y los artículos mediante un servidor.
