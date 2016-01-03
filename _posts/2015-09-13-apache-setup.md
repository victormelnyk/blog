---
layout: post
title:  Apache setup
categories: blog
tags: Ubuntu Apache
---
##Встановлення

`apt-get install apache2`

##Налаштування default host

`/etc/apache2/ports.conf`

{% highlight linux-config %}
Listen 81
{% endhighlight %}

`/etc/apache2/sites-enabled/000-default.conf`

{% highlight linux-config %}
Listen 81
{% endhighlight %}

##Створення host

Копіюємо налаштування

`/etc/apache2/sites-available/default.conf -> /etc/apache2/sites-available/<New host>.conf`

Редагуємо значення

Pеєстуєм сайт

`sudo a2ensite <New host>`<br>
`sudo a2dissite default`