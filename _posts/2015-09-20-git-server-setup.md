---
layout: post
title: Git server setup
categories: blog
tags: Ubuntu Git
---
##Встановлення

`apt-get install git`

##Створення репозиторія

`git init --bare --shared <Repos name>.git`

##Генерація SSH ключів на Windows

Git GUI<br>
Menu Help -> Show SSH Key

##Добавлення ключа на сервері

`cat <id_rsa.pub> >> ~/.ssh/authorized_keys`

##Clone repos

`<User name>@<host>:<Repos name>.git`