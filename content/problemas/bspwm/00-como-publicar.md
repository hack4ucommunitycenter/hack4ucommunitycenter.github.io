---
title: Cómo documentar un problema
description: Guía breve para que otras personas puedan reproducir y resolver una incidencia.
tags: BSPWM, Linux, soporte
badge: Guía
order: 1
---
# Cómo documentar un problema

Una buena entrada permite entender el contexto, reproducir el fallo y comprobar la solución. Copia la plantilla de `content/_plantillas/problema.md` al directorio de este entorno y completa las secciones relevantes.

## Incluye el entorno

- Distribución y versión.
- Versión de BSPWM, sxhkd y componentes relacionados.
- Método de instalación o configuración relevante.

## Describe el comportamiento

Indica qué esperabas, qué ocurrió y los pasos mínimos para reproducirlo. Añade mensajes de error o fragmentos de configuración dentro de bloques de código.

## Documenta la solución

Explica qué cambio resolvió el problema y cómo verificarlo. Si no hay una solución confirmada, deja claro qué hipótesis se probaron.

## Protege la información personal

Revisa logs y configuraciones antes de publicarlos. Elimina nombres de usuario, rutas personales, direcciones IP públicas, tokens, claves y cualquier otro dato privado.