---
layout: post
title: Користувачі Ubuntu
categories: blog
tags: Ubuntu Users
---
##Cписок користувачів системи

`vipw`

##Створити корисувача

`adduser <User name>`

##Надати права адміністратора користувачу

`visudo`

{% highlight linux-config %}
<User name> ALL=(ALL:ALL) ALL
{% endhighlight %}