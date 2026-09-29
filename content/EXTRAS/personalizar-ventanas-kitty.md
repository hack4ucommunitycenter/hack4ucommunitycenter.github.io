---
title: Personalizar ventanas kitty
banner: /assets/img/banners/personalizar-ventanas-kitty.png
---

Veremos como personalizar el gestor de ventanas de la Kitty, por si no sabéis que es es esto:

![](/assets/img/extras/personalizar-ventanas-kitty/1.png)

Para editarlo tendremos que ir a nuestra kitty.conf y añadiremos estas dos líneas de código:

```
active_tab_background #98c379
inactive_tab_background #e06c75
inactive_tab_foreground #000000
```

En las partes de `#` podremos poner el color que más nos guste, os comparto un link donde podréis sacar los códigos de colores.

| Detalles | Enlace |
|---|---|
| Con este podréis pillar los colores de una imagen y escoger el color que más os guste | https://imagecolorpicker.com/ ↗ |
| Con este podréis escoger el color y os dará el código del color | https://htmlcolorcodes.com/ ↗ |

Luego también podremos modificar la forma de el selector de ventanas, os dejo por aquí el código que tenéis que poner.


```
tab_powerline_style round
```

*(En este caso la forma del selector de ventanas sera redondeada)*

![](/assets/img/extras/personalizar-ventanas-kitty/2.png)

---