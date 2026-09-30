---
title: Kali Linux Auto-Resize
banner: /assets/img/banners/kali-linux-auto-resize.png
---

Un fallo que puede ocurrirte es que Kali Linux no adapte automáticamente la resolución, por ejemplo al realizar el cambio de pantalla completa. Es un fallo sencillo de resolver.

Crearemos un archivo con el nombre `50-x-resize.rules` en el directorio `/etc/udev/rules.d/`:

```bash
sudo nano /etc/udev/rules.d/50-x-resize.rules
```

Ahora meteremos el siguiente contenido:

```
ACTION=="change",KERNEL=="card0", SUBSYSTEM=="drm", RUN+="/usr/local/bin/x-resize"
```

Ahora crearemos un archivo llamado `x-resize` en el directorio `/usr/local/bin`:

```bash
sudo nano /usr/local/bin/x-resize
```

Y añadiremos el siguiente contenido:

```
#!/bin/bash
# Bash required
# Should be run as root and saved to /usr/local/bin/x-resize
# Requies udev rule: /etc/udev/rules.d/50-x-resize.rules
# udev rule content: ACTION=="change",KERNEL=="card0", SUBSYSTEM=="drm", RUN+="/usr/local/bin/x-resize" 
# Make sure auto-resize is enabled in virt-viewer/spicy
# Credit for Finding Sessions as Root: https://unix.stackexchange.com/questions/117083/how-to-get-the-list-of-all-active-x-sessions-and-owners-of-them
# Credit for Resizing via udev: https://superuser.com/questions/1183834/no-auto-resize-with-spice-and-virt-manager
## Ensure Log Directory Exists
LOG_DIR=/var/log/autores;
if [ ! -d $LOG_DIR ]; then
    mkdir $LOG_DIR;
fi
LOG_FILE=${LOG_DIR}/autores.log
## Function to find User Sessions & Resize their display
function x_resize() {
    declare -A disps usrs
    usrs=()
    disps=()
    for i in $(users);do
        [[ $i = root ]] && continue # skip root
        usrs[$i]=1
    done
    for u in "${!usrs[@]}"; do
        for i in $(sudo ps e -u "$u" | sed -rn 's/.* DISPLAY=(:[0-9]*).*/\1/p');do
            disps[$i]=$u
        done
    done
    for d in "${!disps[@]}";do
	    session_user="${disps[$d]}"
	    session_display="$d"
	    session_output=$(sudo -u "$session_user" PATH=/usr/bin DISPLAY="$session_display" xrandr | awk '/ connected/{print $1; exit; }')
	    echo "Session User: $session_user" | tee -a $LOG_FILE;
	    echo "Session Display: $session_display" | tee -a $LOG_FILE;
	    echo "Session Output: $session_output" | tee -a $LOG_FILE;
	    sudo -u "$session_user" PATH=/usr/bin DISPLAY="$session_display" xrandr --output "$session_output" --auto | tee -a $LOG_FILE;
    done
}
echo "Resize Event: $(date)" | tee -a $LOG_FILE
x_resize
```

Ahora le daremos permisos de ejecución:

```bash
chmod +x /usr/local/bin/x-resize
```

---