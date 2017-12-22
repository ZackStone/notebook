---
layout: post
title:  "Miniconda no CentOS Minimal"
date:   2017-12-22 11:00:00 -0300
categories: linux
tags: centos linux anaconda miniconda virtualbox proxy
language: br
summary: Instruções para instalação do Miniconda numa máquina virtual CentOS Minimal (VirtualBox) com acesso à internet via proxy.
---

* Do not remove this line (it will not be displayed)
{:toc}


- Versão do SO utilizada: CentOS-7-x86_64-Minimal-1708.
- Configuração do adaptador de rede da máquina virtual: Modo NAT.


```
$ sudo su
```

Adicionar o usuário na lista de 'sudoers', para permitir executar comandos 'sudo'.

`/etc/sudoers`
```
user    ALL=(ALL)    ALL
```

```
$ exit
```

Setar configuração de proxy do sistema.
Arquivo `/etc/environment`:
```
http_proxy="http://host:porta"
https_proxy="http://host:porta"
```


Setar configuração de proxy do yum.
Arquivo `/etc/yum.conf`:
```
proxy=http://host:porta
```

Instalar o pacote wget.
```shell
$ sudo yum install wget
```

Setar configuração de proxy do wget.
Arquivo `/etc/wgetrc`:
```
http_proxy = http://host:porta
https_proxy = http://host:porta
```


Obter o link do arquivo de instalação da última versão do Miniconda (https://conda.io/miniconda.html).
Realizar o download do arquivo de instalação.
```shell
$ wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
```


Instalar o pacote bzip2, necessário para a instalação do Miniconda.
```shell
$ sudo wget install bzip2
```


# Referências

- [CentOS](https://www.centos.org)
- [The Sysadmin Himself - Configuring Web Proxy on CentOS](http://www.thesysadminhimself.com/2013/08/configuring-web-proxy-on-centos.html)
- [Viva o Linux - Configuração do yum com proxy no CentOS](https://www.vivaolinux.com.br/dica/Configuracao-do-yum-com-proxy-no-CentOS)
- [Stack Overflow - Setting proxy in wget](https://stackoverflow.com/questions/11211705/setting-proxy-in-wget)
- [LinuxPitStop - How to install Anaconda / Miniconda / Conda on Linux (Ubuntu, CentOS, Fedora)](http://linuxpitstop.com/install-anaconda-miniconda-conda-on-ubuntu-centos-linux/)
