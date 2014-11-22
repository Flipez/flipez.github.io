---
layout: post
title: AOKP KitKat updaten
---
![106](https://flipez.de/wp-content/uploads/2014/09/106-300x103.png)

Heute will ich kurz zeigen, wie man ein Custom-ROM update (in diesem Fall AOKP) durchführt. Dabei bleibt zu beachten das dies natürlich nur für Aktualisierungen innerhalb einer Android Version gedacht ist. (z.B von 4.4.3 auf 4.4.4). Bei größeren Aktualiserungen (z.B 4.3.x auf 4.4.x) _sollte man_ etwas mehr Aufwand betreiben, man kann es natürlich auch so versuchen, oft klappt das auch. Ich update hier das Nexus 4 (mako) ggf. sind die Versionen bei euch neuer oder älter. Da müsst ihr dann einfach mal schauen. Wie bei so etwas üblich übernehme ich natürlich keine Haftung falls bei euch etwas schief geht.

Für die, die wie ich mit langsamem Internet gesegnet sind kommen hier schon mal die Links für die Dateien die wir brauchen:

* aktuelle AOKP Version (aktuell der nighly-build vom <small></small><span class="json-version">2014-09-11)</span>

* [Direktlink](https://s.basketbuild.com/filedl/devs?dev=aokp&amp;dl=aokp/mako/aokp_mako_kitkat_nightly_2014-09-11.zip "AOKP nightly 2014-09-11 mako")

* [Mako Übersicht](http://aokp.co/devices/mako "AOKP Nexus 4 Übersicht")

* aktuelle GAPPS ( aktluell die aokp-full_gapps-kk-20140901)

* [Direktlink](https://s.basketbuild.com/filedl/devs?dev=championswimmer&amp;dl=championswimmer/gapps/aokp-full_gapps-kk-20140901.zip "GAPPS full kk 20140901")

* [GAPPS Übersicht](http://aokp.co/devices/ "AOKP GAPPS")

Bei beiden Softwarepaketen handelt es sich um .zip Dateien, diese können direkt so bleiben. Verbindet nun euer Handy mit dem PC und kopiert die ROM und die Google-Apps in einen Ordner den ihr euch dann merkt.

Jetzt starten wir das Handy in den Recovery Modus. Je nach konfiguration kann man dies direkt auswählen wenn man das Handy neu starten, alternativ haltet ihr die Power-Taste und die leiser/lauter Taste (je nach Handy) gedrückt. In der Regel sollen man sich damit aber schon auskennen da es sich hier nur um ein update handelt.

Das aktuelle Beispiel orientiert sich am ClockworkMod Recovery (v6.0.4.7) und kann ggf abweichen.

Wir wählen _install zip_ und _choose from /sdcard_ oder _last install folder_ aus und navigieren zu unserem Ordner, in den wir die Zip-Dateien abgelegt haben. In meinem Fall wähle ich nun die _aokp_mako_kitkat_nightly_2014-09-11.zip_ aus und bestätige mit _Yes_. Je nach Leistung des Handys ist es nun Zeit für einen Kaffee oder eine kühle Mate, je nach Tageszeit.

Ist die Installation fertig leeren wir zur Sicherheit zunächst einmal den Cache sowie den Dalvik-Cache (dies ist nicht immer nötig, schadet aber auch nicht und kann Probleme minimieren).

Dafür wählen wir _go back_ und _wipe cache partition_ und bestätigen mit _Yes_. Danach navigieren wir auf _advanced_ und _wipe dalvik cache_ und bestätigen mit _Yes_. Danach gehen wir wieder auf _go back_.

Nun benötigen wir noch die aktuellen Google-Apps. Dafür wählen wir wieder _install zip_ und _choose from /sdcard_ oder _last install folder_ aus und navigieren in unseren Ordner der die Zip-Dateien enthält und wählen die GApps aus. In meinem Fall ist das die _aokp-full-gapps-kk-20140901.zip_ und bestätigen mit _Yes_

Danach klicken wir auf _go back_ und _reboot system now_. In meinem Fall kam dort noch eine Abfrage das das Recovery gelöscht wird, dort einfach _Yes - disable recovery flash_ wählen. Nach dem Neustart werdet ihr relativ lange die Boot animation sehen. Das ist normal. Danach optimiert Android die Apps (und füllt damit wieder den dalvik cache) und danach solltet ihr wieder in eurem heimischen Andoird sein. Gegebenenfalls müsst die euren Launcher noch einmal neu als Standard Start-App auswählen. Willkommen im aktualisierten AOKP ;)

[![Screenshot_2014-09-20-12-15-36](http://flipez.de/wp-content/uploads/2014/09/Screenshot_2014-09-20-12-15-36-180x300.png)](http://flipez.de/wp-content/uploads/2014/09/Screenshot_2014-09-20-12-15-36.png)
