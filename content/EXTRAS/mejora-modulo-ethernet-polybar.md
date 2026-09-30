---
title:
banner: /assets/img/banners/mejora-modulo-ethernet.png
---

Os comparto un script que podéis cambiarlo por el actual que tenéis en el modulo de ethernet, este script lo que hace es mediante un simple condicional en Bash es detectar si estamos usando la VPN (por ejemplo la de HTB). Lo que hará es cambiar el icono y la IP, esto podrá ayudar para entornos que buscan tener una polybar con menos módulos.

```bash
#!/bin/bash

wlan=$(ifconfig | grep -C 1 "wlan0" | grep inet | awk '{print $2}')
vpn=$(ifconfig | grep -C 1 "tun0" | grep inet | awk '{print $2}')

if [[ "$1" = 1 ]];then
  xclip ~/.myip
elif [[ "$vpn" = "" ]];then
  echo -e "%{F#2495e7} %{F#ffffff} $wlan"
  echo "$wlan" > ~/.myip
else
  echo -e "%{F#95e105} %{F#ffffff} $vpn"
  echo "$vpn" > ~/.myip
fi
```

>[!WARNING] CAMBIAR LOS COLORES AL QUE MÁS OS GUSTE Y LA INTERFAZ DE RED SI NO ES `wlan0`

![](/assets/img/extras/mejora-modulo-ethernet/1.png)
(Interfaz wlan0)

![](/assets/img/extras/mejora-modulo-ethernet/2.png)
(Interfaz tun0)

---