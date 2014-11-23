---
layout: post
title: Raspberry Pi - Fernsteuern
---
Im ersten Beitrag ([hier](http://flipez.de/?p=54 "Raspberry Pi - Die ersten Schritte")) haben wir uns bereits ein Raspbian installiert. Da man nun auch die Größe des Raspberry nutzen möchte und ihn nicht immer  an einem Monitor mit Maus und Tastatur betreiben möchte richten wir im folgendem Beitrag den Fernzugriff ein.

Als ersten suchen wir für die Pakete nach neuen Versionen und installieren diese falls vorhanden ganz einfach per

{% highlight bash %}
apt-get update
apt-get upgrade
{% endhighlight %}

Die Willkommens Nachricht (motd - Message of the Day) können wir mit einem Texteditor einfach abändern. Gespeichert wird mit STRG + O und mit STRG + X geht es raus.

{% highlight bash %}
nano /etc/motd
{% endhighlight %}

Jetzt ändern wir noch den Port für den Fernzugriff:

{% highlight bash %}
nano /etc/ssh/sshd_config
{% endhighlight %}

Den könnt ihr euch frei heraussuchen und an der entsprechenden Stelle einfach abändern. Änderung abspeichern und Datei schließen. Zum übernehmen der Änderung starten wir SSH neu:

{% highlight bash %}
/etc/init.d/ssh restart
{% endhighlight %}

Ab jetzt können wir von einem anderem PC auf den Raspberry zugreifen. Damit wir die IP wissen können wir entweder im Router nachschauen oder per

{% highlight bash %}
ifconfig
{% endhighlight %}

die Netzwerkeigenschafen anzeigen. Ferngesteuert kann z.B mit dem Tool [PuTTY](http://www.putty.org/ "PuTTY").

Damit währe der Fernzugriff auch schon eingerichtet.

### Frohes Remoten !
