---
permalink: LFS/
---

# LFS AARCH64 (ARM64)

## 5.3. GCC-12.2.0 - Pass 1

* On ARM64 hosts, set the default directory name for 64-bit libraries to “lib”

```
sed -e '/lp64=/s/lib64/lib/' \
    -i.orig gcc/config/aarch64/t-aarch64-linux

```

## 6.18. GCC-12.2.0 - Pass 2

* On ARM64 hosts, set the default directory name for 64-bit libraries to “lib”

```
sed -e '/lp64=/s/lib64/lib/' \
    -i.orig gcc/config/aarch64/t-aarch64-linux

```

<br>
<hr>

