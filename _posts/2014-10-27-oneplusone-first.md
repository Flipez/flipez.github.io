---
layout: post
title: "OnePlus One: Unlock, Root, CM-Mod"
---
Hallo Zusammen,

seit einigen Tagen bin ich nun Besitzer eines OnePlus One - nun soll dort eine 'richtige' Version vom Cyanogenmod drauf. Nicht nur, weil es mich irgendwie stört, dass die ihr eigenes Süppchen kochen - sondern auch, weil die aktuelle, offizielle Version doch ein paar nervige Bugs hat. Aber wie dem auch sei, fangen wir an.

Wichtig ist, dass wir die passenden USB Treiber und adb/fastboot korrekt eingerichtet haben. Das ist je nach OS teilweise ziehmlich frickelig. Eventuell kommt dazu noch mal ein Beitrag. Beachtet, dass ihr bei diesem Vorgang alle Daten verliert! Die benötigten Daten (und ein paar weitere findet ihr [hier](http://dl.flipez.de/android/oneplusone-bacon/ "Flipez"))

Wir schauen also einmal nach ob denn unser OnePlus One auch brav mit uns spielen will.

{% highlight bash %}
adb devices
{% endhighlight %}

Das sollte dann etwa so aussehen:

```bash
List of devices attached
1ce85e50        device
```

Dann rebooten wir das Gerät ganz entspannt in den Bootloader ( Überraschung!) und ensperren diesen.

```bash
adb reboot bootloader
fastboot oem unlock
```

In den meisten Fällen müsst ihr euch nun noch einmal durch die Startup-Einstellungen durklicken und das USB-Debugging wieder aktivieren.
Dannach wird wieder in den Fastboot Modus gestartet und das recovery geflasht.

```bash
adb reboot bootloader
fastboot flash recovery openrecovery-twrp-2.8.0.1-bacon.img
```

Danach starten wir das One in den Recovery Modus. Dazu einfach Leiser + Power gedrückt halten bis ihr das Logo seht. Dann aufhören da sonst das Handy wieder neu startet.

Hier kann dann entweder per .zip, Sideload oder Push das entsprechende Image installiert werden. Wir werden das Heute einmal per Push machen.

```bash
adb devices
   #  List of devices attached
   #  1ce85e50        recovery

adb push cm-11-20141008-SNAPSHOT-M11-bacon.zip /sdcard/
   #  2799 KB/s (268409500 bytes in 93.642s)
```

Dann wählen wir das Image einfach wie gewohnt aus und installieren es. Die GAPPS dürfen natürlich nicht vergessen werden. Dannach solltet ihr das ganz 'normale' CM auf eurem OnePlus One haben. Das ganze geht natürlich auch mit AOKP oä. Einfach die entsprechenden Images flashen.
