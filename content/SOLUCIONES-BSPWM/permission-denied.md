---
title: Solución paquete XCB en Kali Linux
banner: /assets/img/banners/permission-denied-settarget.png
---

# Ejemplo

![](/assets/img/soluciones-bspwm/permission-denied-settarget/1.png)


# Solución
Para solucionar este `permission denied` veremos los permisos que tiene el archivo target:

![](/assets/img/soluciones-bspwm/permission-denied-settarget/2.png)

Podremos ver que le falta permisos de lectura para el grupo y otros, asi que se los daremos:

```bash
chmod +w target
```

Ahora podremos probar `settarget`:

![](/assets/img/soluciones-bspwm/permission-denied-settarget/3.png)

# ➕ Extra

@[youtube](https://youtu.be/vqqFZSmi7Nk)

---