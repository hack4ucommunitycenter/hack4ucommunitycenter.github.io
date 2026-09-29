---
title: Recopilación Auto-BSPWM
---

# xJackxS (Kali Linux y Parrot)

@[github](https://github.com/xJackSx/BSPWMkali)
@[github](https://github.com/xJackSx/BSPWMparrot)

>[!WARNING]
> Este repositorio esta desactualizado, si intentas instalarlo puedes tener algunos problemas de compatibilidad de algunos paquetes.

>[!DANGER] **EN EL REPOSITORIO BSPWMkali SE HA ENCONTRADO FALLAS EN LA INSTALACIÓN, LOS PROBLEMAS SON:**
> - En el `install.s`h intenta instalar el paquete `xcb`, pero tiene problemas con Kali Linux. Para solucionar este problema instalaremos las dependencias de [Solución al paquete xcb](https://hack4ucommunitycenter.github.io/#/SOLUCIONES-BSPWM/Solucion-paquetes-xcb-kali) y modificaremos el script de `install.sh` borrando el `xcb` de la línea 11. 
> - Problemas con la resolución de BupSuite, para solucionarlo acuda a Fallo de escalado en BurpSuite con BSPWM.
> - **AVISO:** Ocurre que en este repositorio a la hora de instalar BSPWM falla, para instalarlo tendréis que hacer `sudo apt install bspwm`.  Tampoco os instalará `rofi` correctamente, así que tendréis que instalarlo `sudo apt install rofi`.

# TheGoodHackerTV (Kali Linux)

@[github](https://github.com/thegoodhackertv/hackerpwm)
>[!WARNING] Este repositorio esta desactualizado, si intentas instalarlo puedes tener algunos problemas de compatibilidad de algunos paquetes.

# KyttyCrazy (Probado solo en Kali Linux)

@[github](https://github.com/kyttycrazy/auto-bspwm)

En el repo hay un pequeño error en las indicaciones de instalación, comenta que hagamos un `git clone` a un repositorio de AILL, lo que tendremos que hacer es clonar el mismo repositorio de kyttycrazy.

```bash
git clone https://github.com/kyttycrazy/auto-bspwm
```

Cuando intentes instalar este BSPWM te encontrarás con un leve problema, te dará error un paquete llamado `pywal`, para solucionar el error de instalación de este paquete es borrando o comentando la linea donde lo instala. Se ha probado a realizar eso y el BSPWM funciona perfectamente sin requerir de esa dependencia.

![](/assets/img/extras/recopilatorio-autobspwm/1.png)

# ZlCube (Kali Linux)
@[github](https://github.com/ZLCube/AutoBspwm)

# Sammy-ulfh (Kali Linux y Parrot OS)
@[github](https://github.com/sammy-ulfh/AutoBspwm)

# Justice-Reaper (Kali Linux)
@[github](https://github.com/Justice-Reaper/AutoBspwmKali)

---