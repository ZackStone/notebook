---
layout: post
title:  "Configurar repositório NPM privado"
date:   2018-07-03 10:40:00 -0300
categories: dev npm
tags: npm nexus
language: br
summary: Como configurar um repositório NPM privado (usando o Nexus).
---

* Do not remove this line (it will not be displayed)
{:toc}

# Configurar o repositório no Nexus

O que deve ser feito (no Nexus):
* criação de um repositório privado (hosted)
* criação de um proxy apontando para o repositório oficial (NPM Registry)
* criação de um grupo de repositórios para disponibilizar as opções acima através de uma única URL

Esta configuração permite instalar todas as dependências de um projeto usando apenas um comando (`npm install`), pois o projeto fará referência ao grupo de repositórios do Nexus, que buscará o pacote primeiramente no repositório privado, e se não conseguir encontrar, buscará no repositório oficial. Caso contrário, cada comando `npm install` deve ser usado com a opção registry:
```
npm install --registry=http://your-host:8081/nexus/content/repositories/npm-private/
```

Consultar o link https://blog.sonatype.com/using-nexus-3-as-your-repository-part-2-npm-packages para obter os detalhes das configurações.


# Consumir os pacotes do repositório NPM privado

Na pasta raíz dos projetos que consumirão pacotes do repositório NPM privado, criar/editar o arquivo `.npmrc` (ou o arquivo de contexto do usuário, que fica na raíz da pasta do usuário), adicionando a linha abaixo:
```
registry=http://your-host:8081/nexus/content/groups/npm-group/
```

Pronto, você já será capaz de consumir os pacotes tanto do repositório privado quanto do oficial.

# Publicar um pacote no repositório NPM privado

Se você tem um projeto que queira publicar no Nexus, adicione a chave abaixo no arquivo `package.json`:
```json
{
  ...
  "publishConfig": {
    "registry": "http://your-host:8081/repository/npm-private/"
  }
}
```

As informações de autenticação no Nexus devem ser inseridas no arquivo `.npmrc` do contexto do usuário (`~/.npmrc` ou `/home/<your-user>` no Ubuntu, ou `C:\Users\<your-user>\.npmrc` no Windows >> eu acho):
```
_auth=YWRtaW46YWRtaW4xMjM=
```

Você pode gerar esse hash com o comando:
```
echo -n 'myuser:mypassword' | openssl base64
```

Pronto, agora você já pode dar o comando `npm publish` na pasta do seu projeto.


# Referências

- [Using Nexus 3 as Your Repository – Part 2: npm Packages](https://blog.sonatype.com/using-nexus-3-as-your-repository-part-2-npm-packages)

