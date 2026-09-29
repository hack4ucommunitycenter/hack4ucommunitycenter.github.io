---
title: Esquinas triangulares Polybar
banner: /assets/img/banners/esquinas-triangulares-polybar.png
---

# Ejemplo

![](/assets/img/soluciones-bspwm/esquinas-triangulares-polybar/1.png)

# Solución

Este "error" se soluciona de una manera sencilla, instalando picom : 

```bash
wget http://ftp.de.debian.org/debian/pool/main/p/picom/picom_9.1-1_amd64.deb
```

```bash
sudo dpkg -i picom_9.1-1_amd64.deb
```

y debería de solucionarse. 

Otra manera es empleando `apt`:

```bash
sudo apt install picom
```

>[!WARNING]
> RECUERDA: Para que picom se inicialice con BSPWM tendrás que añadir la siguiente línea en el archivo `bspwmrc`:
> 
> ![](/assets/img/soluciones-bspwm/esquinas-triangulares-polybar/2.png)

---