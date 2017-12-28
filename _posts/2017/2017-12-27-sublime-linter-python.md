---
layout: post
title:  "Sublime Linter - Python"
date:   2017-12-27 15:00:00 -0300
categories: sublime python
tags: sublime python linter
language: br
summary: Instalação de linters para python no SublimeText.
---

* Do not remove this line (it will not be displayed)
{:toc}


Como exemplo, usarei os linters pyflakes e pycodestyle, porém há vários outros disponíveis.


- Instalar os linters via `pip` ou `conda`:
```shell
$ pip install pyflakes pycodestyle
```

- Instalar os pacotes no Sublime via PackagerControl (`CTRL + SHIFT + P`, digitar 'Install Package'):
  - 'SublimeLinter'
  - 'SublimeLinter-pyflakes'
  - 'SublimeLinter-pycodestyle'

- Caso o python não esteja na variável PATH de ambiente:
  - No menu do Sublime: 'Preferences > Package Settings > SublimeLinter > Settings'
    - Na aba de configurações do usuário (SublimeLinter.sublime-settings - User, painel da direita)
    - Adicionar na configuração "user > paths" e "user > python_paths" os caminhos para o diretório de instalação do python de acordo com o seu sistema operacional
      - Exemplo no janelas para uma instalação do python usando Anaconda:
        ```
        "windows": [
            "C:\\Users\\yitzhak.andrade\\AppData\\Local\\Continuum\\anaconda3"
        ]
        ```

# Referências

- [...](...)
