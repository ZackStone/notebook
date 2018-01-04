---
layout: post
title:  "Instalação de versões anteriores do R no CentOS"
date:   2018-01-04 10:00:00 -0300
categories: r centos
tags: r centos linux
language: br
summary: Instalação de versões anteriores do R no CentOS.
---

* Do not remove this line (it will not be displayed)
{:toc}


- Instalar os pacotes necessários:
```shell
$ yum groupinstall "Development Tools"
$ yum install ncurses-devel zlib-devel texinfo gtk+-devel gtk2-devel qt-devel tcl-devel tk-devel kernel-headers kernel-devel
```

- Baixar a versão desejada em https://cran.r-project.org/src/base/ (R-2, R-3, ...)
```shell
$ wget https://cran.r-project.org/src/base/R-x/R-x.x.x.tar.gz
$ tar zxvf R-x.x.x.tar.gz
$ cd R-x.x.x/
```

- Compilar e instalar o R:
```shell
$ ./configure --with-x=no
$ make
$ make install
```


# Referências

- [Stack Overflow - How to install older R version on CentOS](https://stackoverflow.com/questions/37769985/how-to-install-older-r-version-on-centos)
- [Stack Overflow](https://stackoverflow.com/questions/17473547/error-with-readline-yes-default-and-headers-libs-are-not-available)
