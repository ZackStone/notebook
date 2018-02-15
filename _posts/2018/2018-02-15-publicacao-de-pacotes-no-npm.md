---
layout: post
title:  "Publicação de pacotes no npm"
date:   2018-02-15 09:10:00 -0300
categories: npm
tags: npm
language: br
summary: Publicação de pacotes no npm.
---

* Do not remove this line (it will not be displayed)
{:toc}


- Criar o arquivo `.npmignore`, caso queira ignorar algum arquivo na publicação.
  - Se um arquivo existe no `.gitignore`, mas não existe no `.npmignore`, então ele será publicado.

- Gerar arquivo compactado (tarball) de um pacote (interessante para pré-visualizar os arquivos que serão publicados):
```shell
$ npm pack
```

- Atualizar a versão no arquivo `package.json`
- git:
  - Commitar
  - Gerar tag
  - Escrever as "Release Notes" (GitHub)


- Publicar:
```shell
$ npm publish
```


# Referências

- [npm Documentation - pack](https://docs.npmjs.com/cli/pack)
- [npm Documentation - publish](https://docs.npmjs.com/cli/publish)
