---
layout: post
title: "Moar speed! moar! <br />Geschwindigkeit mit netcat testen"
---

Wenn man mal wissen möchte wie schnell das Netzwerk eigentlich ist oder ob ein Anbieter drosselt - und wann - wird meist eine Datei heruntergeladen. Nun war aber das Problem, dass diese Datei irgendwann einmal zuende ist - möchte man nun 'unendlich' viel Daten versenden um die Belastung lange aufrecht zu erhalten gibt es da sicherlich viele Möglichkeiten. Der erste Gedanke war, /dev/zero zum Symlinken und per http zur Verfügung zu stellen - das klappte nicht so ganz. Die Lösung liegt aber näher als man denkt: netcat!

Man stellt über netcat einfach /dev/zero zur verfügung (ggf. mehrfach wenn auf mehrere Clients geladen werden soll) und schließt so auch die Plattengeschwindigkeit als Problem nahezu aus. Dazu auf dem Server einfach:


{% highlight bash %}
cat /dev/zero | nc -l -p <port>
{% endhighlight %}

Auf dem Client greift man so auf die Daten zu:

{% highlight bash %}
nc <ip> <port> > /dev/null
{% endhighlight %}

So prügelt man nun viele Daten über das Netzwerk. Man kann mit 'pv' noch etwas mehr Informationen abrufen. Das sähe dann so aus:
{% highlight bash %}
nc <ip> <port> | pv > /dev/null
{% endhighlight %}
