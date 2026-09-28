---
title: Solución paquete XCB en Kali Linux
banner: /assets/img/banners/solucion-paquete-xcb-kali.png
---

En Kali Linux podremos tener un pequeño problema al intentar instalar la dependencia xcb , para solucionarlo instalaremos las siguientes dependencias:

```bash
sudo apt-get install libxcb-randr0-dev libxcb-xtest0-dev libxcb-xinerama0-dev libxcb-shape0-dev libxcb-xkb-dev libpcre3-dev -y
```

---