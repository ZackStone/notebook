---
layout: post
title:  "Erro ENOSPC no grunt (browserify watch)"
date:   2018-07-03 10:40:00 -0300
categories: dev front-end
tags: linux grunt browserify
language: br
summary: Erro ENOSPC no grunt (browserify watch).
---

* Do not remove this line (it will not be displayed)
{:toc}


"The system has a limit to how many files can be watched by a user. You can run out of watches pretty quickly if you have Grunt running with other programs like Dropbox. This command increases the maximum amount of watches a user can have."


Verificar configuração atual
```shell
cat /proc/sys/fs/inotify/max_user_watches
```


Aplicar alteração
```shell
# adicionar nova configuração no final arquivo sysctl.conf
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf
# carregar nova configuração
sudo sysctl -p

```


# Referências

- [Stack Overflow - Grunt watch error - Waiting...Fatal error: watch ENOSPC](https://stackoverflow.com/questions/16748737/grunt-watch-error-waiting-fatal-error-watch-enospc)
- [Increasing the amount of inotify watchers](https://github.com/guard/listen/wiki/Increasing-the-amount-of-inotify-watchers#the-technical-details)

