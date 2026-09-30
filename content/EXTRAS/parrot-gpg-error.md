---
title: Parrot GPG error
banner: /assets/img/banners/parrot-gpg-error.png
---

# Ejemplo

![](/assets/img/extras/parrot-gpg-error/1.png)

# Solución

Para solucionar este error ejecutaremos en nuestra terminal los siguientes comandos:

```bash
wget https://deb.parrot.sh/parrot/pool/main/p/parrot-archive-keyring/parrot-archive-keyring_2024.12_all.deb
```

```bash
sudo dpkg -i parrot-archive-keyring_2024.12_all.deb 
```

Y listo! El error de las claves GPG al actualizar debe haberse solucionado.

![](/assets/img/extras/parrot-gpg-error/2.png)

---

# Referencias
@[url](https://parrotsec.org/blog/2025-01-11-parrot-gpg-keys/)

---