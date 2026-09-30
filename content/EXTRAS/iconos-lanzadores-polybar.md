---
title: Iconos lanzadores en la polybar
banner: /assets/img/banners/iconos-lanzadores-polybar.png
---

# Ejemplo

![](/assets/img/extras/iconos-lanzadores-polybar/1.png)

# Configuración

>[!WARNING] Puede ocurrir que tu configuración de la polybar sea diferente, pero puede aplicarla igualmente adaptandolo a tu configuración.

Poner iconos en la polybar es sencillo, de hecho vienen algunos preconfigurados en el archivo de configuración de la polybar, el famoso archivo `current.ini`.

Lo primero seria hacer una copia de `current.ini` para poder volver atrás si algo sale mal:

```bash
cp /home/tu_usuario/.config/polybar/current.ini  current.inibu
```

Abrimos con nano *(como root)* el archivo `current.ini`: 

```bash
sudo nano /home/tu_usuario/.config/polybar/current.ini
```

y nos dirigimos al apartado `Modules`:
![](/assets/img/extras/iconos-lanzadores-polybar/2.png)

y bajamos hasta el apartado `apps`:

![](/assets/img/extras/iconos-lanzadores-polybar/3.png)

Ahora tendríamos o bien que modificar el lanzador que por defecto trae varios como `term web files etc` o copiar la estructura del lanzador y crear el nuestro.


- `[module/blue]`: es el nombre del modulo al que hay que hacer referencia en este mismo archivo en la configuración de cada apartado de la polybar.

- `type = custom/text`: describe el tipo de modulo.

- `content = "%{T3}X %{T-}`: indica el contenido del modulo en la polybar, el icono del lanzador.

- `content-foreground = ${color.color}`: indica el color del icono.

- `content-background = $(color.color)`: indica el color del fondo.

- `content-pading= 0`: indica el relleno que en este caso es cero.

- `click-left = blueman-manager &`: indica la aplicación a lanzar, en este caso el configurador de bluetooth.

Una vez personalizado nuestro lanzador *(icono, color, y comando a lanzar)* procedemos a hacer referencia a el en la sección del archivo que configura las paletas o secciones de la polybar, en este caso he usado la que utiliza s4vitar para el settarget:

![](/assets/img/extras/iconos-lanzadores-polybar/4.png)

Ahora solo habría que hacer referencia al modulo creado en la linea que empieza por modules que este sin comentar `;` en este caso `modules-center =` que indica que los iconos se distribuirán en la polybar del centro hacia los lados, en el caso de que usemos `modules-left` o `modules-right` los iconos se distribuirán de izquierda a derecha o viceversa respectivamente.

---