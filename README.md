# Sintaxis Markdown

Referencia de la sintaxis disponible para escribir artículos `.md`.

## Encabezados

Usa de uno a seis signos `#` al principio de la línea:

```md
# Título
## Sección
### Subsección
```

## Párrafos y separadores

Deja una línea en blanco entre párrafos. Para insertar una línea horizontal, escribe tres guiones en una línea aparte:

```md
Primer párrafo.

Segundo párrafo.

---
```

## Énfasis

```md
*cursiva* o _cursiva_
**negrita** o __negrita__
~~texto tachado~~
`código en línea`
```

## Listas

```md
- Elemento sin ordenar
- Otro elemento
  - Elemento anidado

1. Primer paso
2. Segundo paso

- [x] Tarea completada
- [ ] Tarea pendiente
```

## Enlaces

```md
[Enlace externo](https://example.com)
[Otro artículo](../FAQ/mi-articulo.md)
[Enlace a una sección](#nombre-de-la-seccion)
```

Los enlaces a otros artículos deben apuntar al archivo `.md` con una ruta relativa. Los encabezados se convierten en anclas en minúsculas, sin tildes y con guiones en lugar de espacios y signos; por ejemplo, `## Configuración básica` genera `#configuracion-basica`.

## Imágenes

```md
![Descripción de la imagen](imagenes/captura.png)
![Imagen externa](https://example.com/imagen.png)
```

Las rutas relativas parten de la carpeta del artículo. Escribe una descripción entre corchetes para que la imagen sea accesible.

## Bloques de código

Usa tres tildes invertidas. Puedes indicar el lenguaje después de las tildes:

````md
```bash
ip addr
```
````

Para código dentro de una frase, usa una sola tilde invertida: `` `ip addr` ``.

## Citas

Empieza cada línea de la cita con `>`:

```md
> Esta es una cita.
>
> Puede ocupar varios párrafos.
```

## Avisos

Para mostrar un aviso destacado, empieza la cita con `[!DANGER]`, `[!WARNING]`, `[!NOTE]` o `[!UPDATE]`:

```md
> [!NOTE]
> Información útil para el lector.

> [!WARNING]
> Revisa este comando antes de ejecutarlo.
```

## Tablas

Separa las columnas con `|` y usa guiones para separar el encabezado:

```md
| Comando | Uso |
| --- | --- |
| `ip addr` | Consultar interfaces |
| `ping host` | Comprobar conectividad |
```

Usa dos puntos para alinear columnas, por ejemplo `| :--- | ---: |`.

## Caracteres literales

Antepon una barra invertida a un carácter que Markdown interpreta:

```md
\*Este texto no estará en cursiva\*
\# Esto no será un encabezado
```

## Vídeos de YouTube

Escribe el shortcode en una línea propia:

```md
@[youtube](https://youtu.be/VIDEO_ID)
```

También se aceptan enlaces habituales de `youtube.com`.

## Repositorios de GitHub

Escribe la URL directa del repositorio en una línea propia:

```md
@[github](https://github.com/usuario/repositorio)
```