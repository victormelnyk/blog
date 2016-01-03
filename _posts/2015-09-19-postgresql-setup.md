---
layout: post
title: PostgreSQL setup
categories: blog
tags: Ubuntu PostgreSQL
---
##Встановлення

`apt-get install postgresql`

##Налаштування

`/etc/postgresql/9.1/main/postgresql.conf`

{% highlight linux-config %}
listen_addresses = '0.0.0.0'
{% endhighlight %}

`/etc/postgresql/9.1/main/pg_hba.conf`

{% highlight linux-config %}
local     all     all    md5
host     all     all     0.0.0.0/0     md5
{% endhighlight %}

##Перезавантаження

`service postgresql restart`

##Administration tool (psql)

`sudo -i -u postgres`<br>
`psql`

##Встановлення пароля для користувача postgres

`\password postgrespg_h`

##Команди для роботи з базою

`CREATE USER <User name>;`<br>
`ALTER USER <User name> WITH ENCRYPTED PASSWORD '<Password>';`<br>
`ALTER ROLE <User name> WITH CREATEDB;`<br>
`CREATE DATABASE <Db name> OWNER <User name>;`

##Переміщення кластера

`sudo pg_dropcluster --stop 9.4 main`<br>
`sudo pg_createcluster -d /path/to/new/location 9.4 main`

##Backup

`sudo su - postgres`<br>
`pg_dump <Db name> > <Backup file name>`

##Restore

`psql <Empty db name> < <Backup file name>`