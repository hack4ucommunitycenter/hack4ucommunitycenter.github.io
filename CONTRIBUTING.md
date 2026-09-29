# ¿Cómo puedo contribuir en Hack4u Community Center?

Puedes proponer contenido desde la web de GitHub sin clonar el repositorio ni instalar el proyecto. En el repositorio, crea o edita los archivos desde **Add file**. Para imágenes, usa **Upload files**. GitHub te permitirá guardar los cambios en una rama y abrir un pull request (PR) para que se revisen.

## Añadir un artículo

1. Elige una categoría existente dentro de `content/`, por ejemplo `FAQ/`, `EXTRAS/` o `SOLUCIONES-BSPWM/`.
2. Crea un archivo `.md` en esa categoría. Puedes usar un prefijo numérico en el nombre, como `02-mi-solucion.md`, para controlar su orden.
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

Las carpetas cuyo nombre empieza por `_` son auxiliares y no aparecen en el catálogo. No edites `content/manifest.json`, `content/search.json`, `public/` ni `dist/`: se generan durante el build.

## Añadir imágenes

Para usar una imagen como portada, súbela a `assets/img/` y referencia su ruta en `banner`, por ejemplo `banner: assets/img/mi-banner.png`.

Para incluir capturas dentro de un artículo, puedes subirlas a una subcarpeta junto al archivo Markdown. Por ejemplo, para `content/FAQ/mi-articulo.md`, guarda la imagen en `content/FAQ/imagenes/captura.png` y enlázala así:

```markdown
![Descripción de la captura](imagenes/captura.png)
```

Usa nombres de archivo claros y elimina de las imágenes y los textos cualquier dato personal, credencial, token o información privada.

## Abrir un pull request

Después de añadir o editar los archivos en GitHub, guarda los cambios en una rama nueva y crea un PR hacia `main`. Describe brevemente qué aporta el contenido y cómo se comprobaron los pasos. Al combinarse el PR, GitHub Actions genera el índice y publica el sitio.