---
title: Módulo ethernet no muestra IP
banner: /assets/img/banners/modulo-ethernet-no-muestra-ip.png
---

# Ejemplo

![](/assets/img/soluciones-bspwm/modulo-ethernet-no-muestra-ip/1.png)

# Solución
Para solucionar este pequeño y simple problema solo tendremos que editar el script `ethernet_status.sh`, donde podremos ver lo siguiente:

```bash
#!/bin/sh

echo "%{F#2495e7} %{F#ffffff}$(/usr/sbin/ifconfig eth0 | grep "inet " | awk '{print $2}')%{u-}"
```

> [!NOTE]
> Este archivo se encuentra en `~/.config/bin/`

Haremos un `ifconfig` para ver que interfaz de red estamos usando:

![](/assets/img/soluciones-bspwm/modulo-ethernet-no-muestra-ip/2.png)

en mi caso estoy usando la `eth0` así que volveremos al script y buscaremos la linea donde haga el ifconfig a X interfaz:

**EJEMPLO CON LA INTERFAZ DE RED wlan0:**

```bash
#!/bin/sh
                                                   !----!
echo "%{F#2495e7} %{F#ffffff}$(/usr/sbin/ifconfig wlan0 | grep "inet " | awk '{print $2}')%{u-}"
```

---