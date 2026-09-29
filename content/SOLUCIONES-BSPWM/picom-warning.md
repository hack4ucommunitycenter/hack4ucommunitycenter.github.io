---
title: Picom Warning
banner: /assets/img/banners/picom-warning.png
---

# Ejemplo

![](/assets/img/soluciones-bspwm/picom-warning/1.png)

Este warning suele ocurrir porque en nuestro archivo de configuración `picom.conf` tenemos algo obsoleto o mal configurado. Una posible causa de este warning sea que tenemos el `refresh-rate` sin comentar:

![](/assets/img/soluciones-bspwm/picom-warning/2.png)

Comentaremos la linea `refresh-rate = 0` y el warning podría ya solucionarse.

>[!WARNING]
> Si no se ha solucionado el warning, ejecuta en tu terminal `picom` y podrás ver con más detalle lo que está fallando.

---