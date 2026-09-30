---
title: Máquina virtual lenta a la hora de escribir
banner: /assets/img/banners/vm-lenta-a-la-hora-de-escribir.png
---

Para que la máquina virtual te vaya con un rendimiento adecuado se recomienda asignarle unos buenos recursos:

| CPU | RAM |
|---|---|
| 4 process | 4 GB (mínimo) |

Luego otra cosa que se recomienda si usas VMware, dale Click Derecho sobre la máquina virtual y dale a `Open VM Directory`:

![](/assets/img/extras/vm-lenta-a-la-hora-de-escribir/1.png)

Abre el archivo que termina con la extensión `.vmx` con Bloc de notas, notepad...: 

![](/assets/img/extras/vm-lenta-a-la-hora-de-escribir/2.png)

Y dentro del archivo en las ultimas líneas añadiremos:

```
keyboard.allowBothIRQs = FALSE 
keyboard.vusb.enable = TRUE
````

Guardaremos e iniciaremos la máquina. 

Otra posible solución es añadir las siguientes líneas en nuestra `.bashrc` o `.zshrc` donde puede mejorar el rendimiento de si misma:

```
export MESA_GL_VERSION_OVERRIDE=4.5 
export MESA_GLSL_VERSION_OVERRIDE=450
```

Si sigue yendo lento, otras posibles soluciones:

- Podría darle un ojo al siguiente artículo [Mal rendimiento en VMWARE Windows 11/10](https://hack4ucommunitycenter.gitbook.io/home/extras/mal-rendimiento-en-vmware-windows-11-10)

- Deshabilitar la aceleración 3D si esta habilitada (Si no sabe como puede ver el [siguiente post](https://hack4ucommunitycenter.github.io/#/SOLUCIONES-BSPWM/Triangulos-En-La-Terminal))

- Si esta usando `picom` en su BSPWM prueba a deshabilitar cosas como: Sombras, blur, animaciones.

- Usar otra terminal, yo recomiendo Qterminal tiene atajos parecidos al de la kitty.

- Si estás en Parrot OS podrías probar a usar su terminal predeterminada `Mate-terminal` con [`oh-my-tmux`](https://github.com/gpakosz/.tmux)

- Usar el entorno predeterminado de Kali Linux/Parrot OS.

>[!WARNING] La terminal Kitty normalmente tiene un poco de delay.

## Configuración de picom

Les compartiré unos valores de algunas variables del archivo `picom.conf` buscarlos y cambiarlos por el valor mostrado a continuación:

``` 
backend = "xrender";
vsync = true;
shadow = false;
fading = false;
blur-background = false;
corner-radius = 0;
round-borders = 0;
use-damage = true;
detect-rounded-corners = false;
detect-client-opacity = true;
detect-transient = true;
detect-client-leader = true;
```

---