# ¿Cómo puedo contribuir en Hack4u Community Center?

Puedes proponer contenido desde la web de GitHub sin clonar el repositorio ni instalar el proyecto. En el repositorio, crea o edita los archivos desde **Add file**. Para imágenes, usa **Upload files**. GitHub te permitirá guardar los cambios en una rama y abrir un pull request (PR) para que se revisen.

## Añadir un artículo

1. Elige una categoría existente dentro de `content/`, por ejemplo `FAQ/`, `EXTRAS/` o `SOLUCIONES-BSPWM/`.
2. Crea un archivo `.md` en esa categoría. El nombre del archivo si contiene espacios sustituyelos por `-` como por ejemplo `mi-solucion.md`.
3. Escribe el artículo en Markdown. Incluye un título claro, el contexto necesario, los pasos para reproducir el problema y una solución verificada cuando exista.

Puedes partir de la plantilla `content/_plantillas/problema.md`. El bloque inicial de metadatos es opcional; un ejemplo:

```yaml
---
title: Título del artículo
description: Resumen breve
tags: linux, bspwm
badge: Solución
order: 2
banner: assets/img/mi-banner.png
---
```

Las carpetas cuyo nombre empieza por `_` son auxiliares y no aparecen en el catálogo. No edites `content/manifest.json`, `content/search.json`, `public/` ni `dist/`, *(se generan durante el build.)*

## Sintaxis Markdown

Referencia de la sintaxis disponible para escribir artículos `.md`.

### Encabezados

Usa de uno a seis signos `#` al principio de la línea:

```md
# Título
## Sección
### Subsección
```

### Párrafos y separadores

Deja una línea en blanco entre párrafos. Para insertar una línea horizontal, escribe tres guiones en una línea aparte:

```md
Primer párrafo.

Segundo párrafo.

---
```

### Énfasis

```md
*cursiva* o _cursiva_
**negrita** o __negrita__
~~texto tachado~~
`código en línea`
```

### Listas

```md
- Elemento sin ordenar
- Otro elemento
  - Elemento anidado

1. Primer paso
2. Segundo paso

- [x] Tarea completada
- [ ] Tarea pendiente
```

### Enlaces

```md
[Enlace externo](https://example.com)
[Otro artículo](../FAQ/mi-articulo.md)
[Enlace a una sección](#nombre-de-la-seccion)
```

Los enlaces a otros artículos deben apuntar al archivo `.md` con una ruta relativa. Los encabezados se convierten en anclas en minúsculas, sin tildes y con guiones en lugar de espacios y signos; por ejemplo, `## Configuración básica` genera `#configuracion-basica`.

### Imágenes

```md
![Descripción de la imagen](imagenes/captura.png)
![Imagen externa](https://example.com/imagen.png)
```

Usa nombres de archivo claros y elimina de las imágenes y los textos cualquier dato personal, credencial, token o información privada.

Las rutas relativas parten de la carpeta del artículo. Escribe una descripción entre corchetes para que la imagen sea accesible.

### Bloques de código

Usa tres tildes invertidas. Puedes indicar el lenguaje después de las tildes:

````md
```bash
ip addr
```
````

Para código dentro de una frase, usa una sola tilde invertida: `` `ip addr` ``.

### Citas

Empieza cada línea de la cita con `>`:

```md
> Esta es una cita.
>
> Puede ocupar varios párrafos.
```

### Avisos

Para mostrar un aviso destacado, empieza la cita con `[!DANGER]`, `[!WARNING]`, `[!NOTE]` o `[!UPDATE]`:

```md
> [!NOTE]
> Información útil para el lector.

> [!WARNING]
> Revisa este comando antes de ejecutarlo.
```

### Tablas

Separa las columnas con `|` y usa guiones para separar el encabezado:

```md
| Comando | Uso |
| --- | --- |
| `ip addr` | Consultar interfaces |
| `ping host` | Comprobar conectividad |
```

Usa dos puntos para alinear columnas, por ejemplo `| :--- | ---: |`.

### Caracteres literales

Antepon una barra invertida a un carácter que Markdown interpreta:

```md
\*Este texto no estará en cursiva\*
\# Esto no será un encabezado
```

### Vídeos de YouTube

Puede emplear el siguiente shortcode:

```md
@[youtube](https://youtu.be/VIDEO_ID)
```

### Vídeos mp4

Puede emplear el siguiente shortcode:

```md
@[video](/ruta-al-video/)
```

También se aceptan enlaces habituales de `youtube.com`.

### Repositorios de GitHub

Escribe la URL directa del repositorio en una línea propia:

```md
@[github](https://github.com/usuario/repositorio)
```

## Abrir un pull request

Después de añadir o editar los archivos en GitHub, guarda los cambios en una rama nueva y crea un PR hacia `main`. Describe brevemente qué aporta el contenido y cómo se comprobaron los pasos. Al combinarse el PR, GitHub Actions genera el índice y publica el sitio.