---
layout: post
title: Raspberry Pi - AirPlay
---
Heute wollen wir uns einmal über die Medien-Tauglichkeit des Raspberry`s unterhalten. Die Apple-Jünger unter euch wird es gefallen - heute rüsten wir den Rasperry mit AirPlay aus.

Alles was wir dazu brauchen: Raspberry Pi, Netzwerkkabel oder USB-Wlan Stick, 3.5 Klinke Soundsystem (für mehr Qualität bieten sich USB Systeme an), ein iDevice oder iTunes.

## Schritt 1 - Vorbereiten

Für die folgenden Befehle wird von Root-Berechtigungen ausgegangen. Sollte das nicht der Fall sein, muss den Befehlen mit einem * ein "_sudo_" angeführt werden.

Als erstes aktualisieren wir die Paketlisten:

{% highlight bash %}
apt-get update *
{% endhighlight %}

Danach richten wir den Klinke Ausgang als Standard ein. In den meisten Fällen wird der Ton ja über den HDMI Port ausgegeben.

{% highlight bash %}
amixer cset numid=3 1
{% endhighlight %}

Dabei steht 0 für Automatisch, 1 für Kopfhörer - also Klinke und 2 für den HDMI Ausgang.

## Schritt 2 - Die Paketinstallation

Für unseren "AirPi" benutzen wir Shairport welches wir mit ein paar zusätzlichen Paketen direkt von Github installieren können. Dazu müssen wir erst einmal Git installieren. Das machen wir wie folgt:

{% highlight bash %}
apt-get install git libao-dev libssl-dev libcrypt-openssl-rsa-perl libio-socket-inet6-perl libwww-perl avahi-utils *
{% endhighlight %}

Jetzt laden wir Shairport mit diesem Befehl herunter:

{% highlight bash %}
git clone https://github.com/albertz/shairport.git shairport *
{% endhighlight %}

Dann wechseln wir in den Shairport Ordner und compilieren:

{% highlight bash %}
cd shairport
{% endhighlight %}

{% highlight bash %}
make *
{% endhighlight %}

## Schritt 3 - Shairport automatisch starten lassen

Wir installieren es mit

{% highlight bash %}
make install *
{% endhighlight %}

Und kopieren die Init in das Startverzeichnis

{% highlight bash %}
cp shairport.init.sample /etc/init.d/shairport *
{% endhighlight %}

Dann öffnen wir init.d und weisen Shairport die benötigten Rechte zu

{% highlight bash %}
cd /etc/init.d
chmod a+x shairport *
update-rc.d shairport defaults *
{% endhighlight %}

Jetzt bearbeiten wir die Einstellungen (in /etc/init.d)

Öffnen mit

{% highlight bash %}
nano shairport *
{% endhighlight %}

Und ändern DAEMON_ARGS von

{% highlight bash %}
NAME=shairport
DAEMON="/usr/local/bin/shairport.pl"
PIDFILE=/var/run/$NAME.pid
DAEMON_ARGS="-w $PIDFILE"
{% endhighlight %}

zu

{% highlight bash %}
NAME=shairport
DAEMON="/usr/local/bin/shairport.pl"
PIDFILE=/var/run/$NAME.pid
DAEMON_ARGS="-w $PIDFILE -a NameDesAirPi"
{% endhighlight %}

Gespeichert wird, wie üblich mit STRG+O und verlassen mit STRG+X

## Schritt 4 - Starten

So. Damit wären wir fertig und können jetzt starten. Ganz einfach per:

{% highlight bash %}
/etc/init.d/shairport start *
{% endhighlight %}

Viel Spaß mit eurem AirPi ;)
