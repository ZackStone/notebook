---
layout: post
title:  "Instalação do Miraclecast"
date:   2018-04-01 13:30:00 -0300
categories: linux
tags: linux miraclecast
language: br
summary: Instalação do Miraclecast no Mint 18.3.
---

* Do not remove this line (it will not be displayed)
{:toc}

Não consegui instalar.

```shell
# clonar repo do miraclecast https://github.com/albfan/miraclecast.git
$ git clone git@github.com:albfan/miraclecast.git
$ cd miraclecast

# instruções de build e install: https://github.com/albfan/miraclecast/wiki/Building

$ mkdir build
$ cd build

# instalar pacote necessários
$ sudo apt-get install libudev-dev
$ sudo apt-get install libsystemd-dev
$ sudo apt-get install check

$ cmake ..
$ make

# instala o libreadline, porém esta é a versão 6
$ sudo apt-get install libreadline-dev

# baixar e extrair o readline-7.0
$ wget https://ftp.gnu.org/gnu/readline/readline-7.0.tar.gz
$ tar -xvzf readline-7.0.tar.gz

$ cd readline-7.0
$ ./configure
make
$ sudo make install

# mesmo rodando "sudo ldconfig", o erro persiste...
```


# Referências

- [Github Miraclecast](https://github.com/albfan/miraclecast)
- [Github Miraclecast - Wiki: Building](https://github.com/albfan/miraclecast/wiki/Building)
- [Github Miraclecast - Issue #157: Cannot install](https://github.com/albfan/miraclecast/issues/157#issuecomment-266254341)
