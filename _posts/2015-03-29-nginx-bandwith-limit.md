---
layout: post
title: "Trafficlimit mit nginx"
---
Will man nur ein grobes Limit für den Webservertraffic setzen, so bietet es sich an direkt die Funktionen von nginx zu nutzen.

Man kann sehr einfach in einem Sever/Location Block limitierungen setzen.

{% highlight bash %}
limit_rate_after 300m;
limit_rate 5000k;
{% endhighlight %}

Das setzt ein Limit auf etwa 50MBit wenn mehr als 300MB von einer(!) Verbindung aus geladen werden. Die Werte muss natürlich jeder für sich selbst einstellen und dienen hier nur dem Beispiel.

Möchte man nun aber unabhängig der Verbindung den Server oder die IP des Gegenüber drosseln so bieten sich die nginx Zonen an.

{% highlight bash %}
limit_conn_zone $binary_remote_addr zone=perip:300m;

server {
  limit_conn perip 5;
}
{% endhighlight %}

So lässt sich zum Beispiel ein Limit auf eine IP eines Server setzen, unabhängig davon, wieviele Verbindungen dieser öffnen - diese können auch limitiert werden.

Noch mehr dazu gibt es in den [nginx-docs]

[nginx-docs]: http://nginx.org/en/docs/http/ngx_http_limit_conn_module.html
