---
layout: post
title: Android Custom-ROM wechseln
---
![](http://flipez.de/wp-content/uploads/2014/09/CM11-2-480x274-300x171.jpg)

Hallo Zusammen,

gestern habe ich noch berichtet wie man eine ROM Aktualisierung durchführt. Heute will ich kurz den wechsel von einer Custom-ROM zur anderen beschreiben. Der ganze Vorgang ist dem recht ähnlich da z.B das Recovery schon existent ist.

Was brauchen wir also? Nun, für die neue Installation von CM benötigen wir das CM Image und die Google Apps. Das Cyanogenmod Image findet Ihr für das Gerät eurer Wahl [hier](http://download.cyanogenmod.org/ "Cyanogenmod Download"). Dort könnt Ihr einfach euer Gerät auswählen und dann die gewünschte Version herunterladen. Meiner Erfahrung nach ist der Nightly Build schon relativ stabil. Zumindest auf dem Nexus 4. Ich lade mir also den Nightly-Build herunter.

Wichtig für ein funktionierendes System sind ausserdem die Google Apps (kurz GAPPS). Diese findet Ihr für jede CM Version [hier](http://wiki.cyanogenmod.org/w/Google_Apps "Google-Apps"). Haben wir CM und die GAPPS heruntergeladen kopieren wir beide .zip Archive in einen Ordner unserer Wahl auf dem Handy und merken ihn uns. Nun können wir das Telefon in den Recovery Modus neu starten. Je nach einstellungen geht das ganz einfach mit dem erweiterten Neustartmenü. Dies gibt es unter anderem in AOKP und Cyanogenmod. Alternativ wird einfach, je nach Telefon, z.B mit Power-Taste + Leiser der Recovery Modus gestartet.

Als erstes müssen wir das Handy bereinigen. Heißt, formatieren. In der Regel sollten die Daten auf der SD Karte erhalten bleiben, das kann aber auch mal nicht so sein. Zur Sicherheit sollte man also ein Backup der wichtigen Daten haben. In meinem Beispiel benutze ich das ClockworkMod Recovery. Der Ablauf kann also ggf. abweichen. Als ersten Wählen wir also 'wipe data/factory reset' und bestätigen mit 'Yes'.

Je nach Größe des Speichers dauert dieser Vorgang nun einige Sekunden. Danach ist das Telefon bereit für die neue ROM. Wir klicken also auf 'install zip' und je nach Bedarf auf 'choose from /sdcard' oder 'choose from last install folder' und navigieren in den Ordner in dem wir die .zip abgelegt haben. Solltet ihr vorher kein laufendes System gehabt haben, so könnt ihr das Archiv auch per adb/sideload auf das Handy bringen. Dazu aber in einem anderen Post mehr. Wir wählen also das Cyanogenmod Image aus und installieren dies. Danach installieren vor noch die Google-Apps nach dem selben Prinzip wie den Cyanogenmod.

Damit ist die Installation auch schon erledigt. Wer auf der sicheren Seite sein möchte, kann auch noch den Cache und Dalvik-Cache leeren. Das ist idR aber nicht nötigt wenn der Wipe richtig durchgelaufen ist. Wir starten nun einfach das Handy neu und dann ist es auch schon vollbracht. Willkommen in der CyanogenMod Welt :)

PS: Wie in diesem Beispiel ersichtlich wurde der CyanogenMod 11 mit der Android Version 4.4.4 installiert. Dazu aber die GAPPS für 4.4.3. Es bietet sich also in jedem Fall an alle Apps zu aktualisieren. Die sollte aber so wie so routine sein.

![CyanogenMod 11](http://flipez.de/wp-content/uploads/2014/09/Screenshot_2014-09-21-18-31-21-1024x614.png)
