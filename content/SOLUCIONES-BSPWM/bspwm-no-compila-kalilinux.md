---
title: BSPWM no compila en Kali Linux
banner: /assets/img/banners/bspwm-no-compila-kalilinux.png
---

# Ejemplo

![](/assets/img/soluciones-bspwm/bspwm-no-compila-kalilinux/1.png)

Si tenemos este problema a la hora de compilar `bspwm` tenemos 2 métodos para solucionarlo:

# 1. Instalación del paquete BSPWM mediante apt (Recomendada)

Una solución probada es saltarse la instalación manual de bspwm e instalarlo mediante `apt`: 

```bash
sudo apt install bspwm
```

# 2. Instalación de la dependencia libxcb-xinerama0-dev

Una posible solución es instalar esta dependencia `libxcb-xinerama0-dev`: 

```bash
sudo apt install libxcb-xinerama0-dev
```

Antes de volver a compilar limpia los archivos de la anterior compilación:

```bash
make clean
```

---