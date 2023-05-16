---
permalink: LFS/
---

# LFS 11.3 AARCH64 (ARM64)

[HOME](../) --- [&#x213C;](#idxXX)<br id="idx00">
## TOC

* [Packages](#idx01)
* [5.3. GCC-12.2.0 - Pass 1](#idx02)
* [6.18. GCC-12.2.0 - Pass 2](#idx03)

[&#x213C;](#)<br id="idx01">
## Packages (16 May 2023)

Bad News: The [LFS ARM64 site](https://www.linuxfromscratch.org/~xry111/lfs/view/arm64/) always updates/changes!
Always use the ORI packages!

### LFS Chapter 3.1 Download Script (<span style="color:red; font-weight:bold;">root</span>)

```
echo "============================================"
echo "LFS should be /mnt/lfs AND MAKEFLAGS = cores"
echo "LFS=$LFS MAKEFLAGS=$MAKEFLAGS"
echo "============================================"
sleep 3
mkdir -pv $LFS/sources/
chmod -v  a+wt $LFS/sources/
cd        $LFS/sources/
wget -c   https://www.linuxfromscratch.org/lfs/view/11.3/wget-list-sysv --directory-prefix=$LFS/sources
wget -c   --input-file=$LFS/sources/wget-list-sysv --directory-prefix=$LFS/sources
wget -c   https://www.linuxfromscratch.org/lfs/view/11.3/md5sums --directory-prefix=$LFS/sources
md5sum -c md5sums
chown root:root $LFS/sources/*


```

* [**ORI** Package Link](https://www.linuxfromscratch.org/lfs/view/11.3/chapter03/introduction.html)
* [KW Package Link](https://www.linuxfromscratch.org/~xry111/lfs/view/arm64/chapter03/introduction.html)

[&#x213C;](#)<br id="idx01">
### ORI vs KW

| **ORI (amd64)**                      | **KW (arm64)**                       |
| x -------------------------------- x | x -------------------------------- x | 
| Coreutils-9.1                        | Coreutils-9.3                        |
| Gawk-5.2.1                           | Gawk-5.2.2                           |
| GCC-12.2.0                           | GCC-13.1.0                           |
| Grep-3.8                             | Grep-3.10                            |
| Iana-Etc-20230202                    | Iana-Etc-20230418                    |
| IPRoute2-6.3.0                       | IPRoute2-6.3.0                       |
| Less-608                             | Less-633                             |
| Libcap-2.67                          | Libcap-2.68                          |
| Libelf from Elfutils-0.188           | Libelf from Elfutils-0.189           |
| Linux-6.1.11                         | Linux-6.3.2                          |
| Make-4.4                             | Make-4.4.1                           |
| Man-pages-6.03                       | Man-pages-6.04                       |
| Meson-1.0.0                          | Meson-1.0.0                          |
| OpenSSL-3.0.8                        | OpenSSL-3.1.0                        |
| Perl-5.36.0                          | Perl-5.36.1                          |
| Procps-ng-4.0.2                      | Procps-ng-4.0.3                      |
| Python-3.11.2                        | Python-3.11.3                        |
| Sysvinit-3.06                        | Sysvinit-3.07                        |
| Texinfo-7.0.2                        | Texinfo-7.0.3                        |
| Vim-9.0.1273                         | Vim-9.0.1503                         |
| Wheel-0.38.4                         | Wheel-0.40.0                         |
| Xz-5.4.1                             | Xz-5.4.3                             |
| Zstd-1.5.4                           | Zstd-1.5.5                           |
| x -------------------------------- x | x -------------------------------- x | 

[&#x213C;](#)<br id="idx02">
## 5.3. GCC-12.2.0 - Pass 1

* On ARM64 hosts, set the default directory name for 64-bit libraries to “lib”

```
sed -e '/lp64=/s/lib64/lib/' \
    -i.orig gcc/config/aarch64/t-aarch64-linux

```

[&#x213C;](#)<br id="idx03">
## 6.18. GCC-12.2.0 - Pass 2

* On ARM64 hosts, set the default directory name for 64-bit libraries to “lib”

```
sed -e '/lp64=/s/lib64/lib/' \
    -i.orig gcc/config/aarch64/t-aarch64-linux

```

<hr>
[&#x213C;](#)<br id="idxXX">

