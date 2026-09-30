---
title: Kali Linux warning update
banner: /assets/img/banners/kali-linux-warning-update.png
---

# Ejemplo
![](/assets/img/extras/kali-linux-warning-update/1.png)

# Solución
Para solucionar este error ejecutaremos el siguiente comando:

```bash
sudo wget https://archive.kali.org/archive-keyring.gpg -O /usr/share/keyrings/kali-archive-keyring.gpg
```

Y ahora podremos hacer un `sudo apt update` sin problemas.

---