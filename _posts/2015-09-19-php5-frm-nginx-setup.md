---
layout: post
title: php5-fpm nginx setup
categories: blog
tags: Ubuntu Nginx php5-fpm
---
##Встановлення

`apt-get install php5-fpm`<br>
`apt-get install php5-pgsql` - для роботи з PostgreSQL

##Налаштування

`/etc/php5/fpm/php.ini`

{% highlight apacheconf %}
cgi.fix_pathinfo = 0
short_open_tag = On # зустрічається в двох місцях
{% endhighlight %}

##Перезавантаження

`service php5-fpm restart`

##Налаштування host

`nano /etc/nginx/sites-enabled/defaul`

{% highlight nginx %}
location ~ \.php$ {
  try_files $uri =404;
  fastcgi_pass unix:/var/run/php5-fpm.sock;
  fastcgi_index index.php;
  fastcgi_param SCRIPT_FILENAME
  $document_root$fastcgi_script_name;
  include fastcgi_params;
}
{% endhighlight %}