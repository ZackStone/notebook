---
layout: post
title:  "Instalação do Spark no CentOS"
date:   2018-02-15 17:10:00 -0300
categories: spark
tags: spark centos
language: br
summary: Instalação do Spark no CentOS.
---

* Do not remove this line (it will not be displayed)
{:toc}

# Instalação do Spark no CentOS

## Instalar Java

```shell
$ yum install java-1.8.0-openjdk
$ java -version
> openjdk version "1.8.0_161"
> OpenJDK Runtime Environment (build 1.8.0_161-b14)
> OpenJDK 64-Bit Server VM (build 25.161-b14, mixed mode)
```


## Instalar Scala

```
$ wget https://downloads.lightbend.com/scala/2.12.4/scala-2.12.4.rpm
$ yum install scala-2.12.4.rpm
$ scala -version
> Scala code runner version 2.12.4 -- Copyright 2002-2017, LAMP/EPFL and Lightbend, Inc.

```


## Instalar Spark

- Baixar, extrair e mover para pasta correta
```
$ wget http://mirror.nbtelecom.com.br/apache/spark/spark-2.2.1/spark-2.2.1-bin-hadoop2.7.tgz
$ tar xvf spark-2.2.1-bin-hadoop2.7.tgz
$ mv spark-2.2.1-bin-hadoop2.7 /usr/local/spark
```

- Adicionar a linha abaixo no arquivo `~/.bashrc`
```
export PATH=$PATH:/usr/local/spark/bin
```

- Atualizar ...
```shell
$ source ~/.bashrc
```

- Verificar instalação do Spark
```shell
$ spark-shell --version
> Welcome to
>       ____              __
>      / __/__  ___ _____/ /__
>     _\ \/ _ \/ _ `/ __/  '_/
>    /___/ .__/\_,_/_/ /_/\_\   version 2.2.1
>       /_/
> 
> Using Scala version 2.11.8, OpenJDK 64-Bit Server VM, 1.8.0_161
> Branch
> Compiled by user felixcheung on 2017-11-24T23:19:45Z
> Revision
> Url
> Type --help for more information.
```


### Acesso à interface web

#### Acesso local em ambiente com proxy

- Adicionar endereço local à lista de exceções do proxy:
    - Adicionar a linha abaixo no arquivo `~/.bashrc`
```
    export no_proxy="127.0.0.1, localhost, 127.0.0.1:8080, localhost:8080"
```

#### Acesso remoto

- Abrir a portas para acesso remoto à interface web
```shell
$ firewall-cmd --zone=public --add-port=1-9999/tcp --permanent
$ firewall-cmd --reload
$ firewall-cmd --list-ports
```


# Referências

- [Apache Spark Installation](https://www.tutorialspoint.com/apache_spark/apache_spark_installation.htm)
- [Scala - Download](http://www.scala-lang.org/download/)
- [Vultr - How to install scala on centos 7](https://www.vultr.com/docs/how-to-install-scala-on-centos-7)
- [How to configure http proxy exceptions](http://xmodulo.com/how-to-configure-http-proxy-exceptions.html)
- [Open port 80 in centos 6.5](https://unix.stackexchange.com/questions/109443/open-port-80-in-centos-6-5)
