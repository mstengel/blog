---
layout: post
title: Flashing Xiaomi
categories: [snippet]
tags: [Android, HowTo, LinkDump]
description: Heute habe ich das erste Mal ein Custom-ROM auf einem Android-Gerät installiert. Bis jetzt erschien das einfach nicht nötig in meinem Handyleben. Dem China-ROM auf dem Xiaomi MI 5S Plus ging es jetzt aber an den Kragen. Ich musste feststellen, dass es nicht _die_ Anleitung gibt, in der alles steht. Und dass es für einen unbedarften Anfänger in der Materie nach wie vor keine simple Sache ist von diesem Vorteil der Android-Welt zu profitieren. 
comments: true
---

Heute habe ich das erste Mal ein Custom-ROM auf einem Android-Gerät installiert. Bis jetzt erschien das einfach nicht nötig in meinem Handyleben. Dem China-ROM auf dem Xiaomi MI 5S Plus ging es jetzt aber an den Kragen. Ein paar Monate wurde es damit zwar verwendet (auf English), aber die vielen China-Apps nervten auf Dauer. Den übereifrigen und intransparenten Berechtigungsmanager des hauseigenen MIUI8 Launchers haben wir in manchen Punkten zwar in den Griff bekommen, aber bis zum Schluss - warum auch immer - synchronisierte der Google-Kalender nicht zuverlässig und eine Ortung für die schnelle Navigation in Google-Maps war kaum möglich.

Ich musste feststellen, dass es nicht _die_ Anleitung gibt, in der alles steht. Und dass es für einen unbedarften Anfänger in der Materie nach wie vor keine simple Sache ist von diesem Vorteil der Android-Welt zu profitieren. 

Um mich zu einem späteren Punkt noch mal daran zu erinnern, hier die wichtigsten Schritte und ein paar Links

## Wahl des ROMs

  * Das Gerät haben wir über [tradingshenzhen.com](https://www.chinahandys.net/uebersicht-xiaomi-smartphones-rom-uebersicht/) bezogen und es wurde mit dem "original" China-ROM ausgeliefert. D.h. System in English, Playstore nachinstallieren und zahlreiche chinesische Apps, die das System durchsetzen. 
  * Dem recht nahe sind die Xiaomi.EU Custom ROMs, das auch Deutsch unterstützt, den Play-Store usw. sowie die MIUI-Erfahrung mitbringt. Hier gibt es eine [Übersicht über die MIUI-ROMs für Xiaomi-Geräte](https://www.chinahandys.net/uebersicht-xiaomi-smartphones-rom-uebersicht/) und hier [alles zu dem infrage kommenden Xiami.EU ROM](https://xiaomi.eu/community/threads/6-10-13.35585/)
  * Da Android eigentlich solche Launcher / Aufsätze nicht braucht, habe ich mich für die Android-Distribution [Lineage OS](https://www.lineageos.org/) entschieden, was dem Gerät letztlich einen Betrieb mit einem unverbastelten und höchst aktuellem Android ermöglicht. Seit Oktober 2016 gibt es das ROM auch [für das Xiaomi Mi 5S Plus](https://wiki.lineageos.org/devices/natrium).
  * Da es dem Komfort sehr dienlich ist ein paar Google-Apps dabei zu haben, auch die [GAPPs herunterladen](http://opengapps.org/), die wie das Betriebssystem installiert werden und dann von Anfang an im System zur Verfügung stehen. "Platform" ist für das Xiaomi Mi 5S Plus `ARM64` und "Android" die aktuelleste Version, wenn LineageOS installiert werden soll. Der Umfang der einzelnen Pakete wird auf der Website des Projekts beschrieben und kann nach eigenen Vorlieben gewählt werden (zwischen "nur das nötigste" oder "die original Goolge-Erfahrung").
  * Das gewünschte ROM und die G-Apps herunterladen und als ZIP-Datei in das Grundverzeichnis des Telefons verschieben (geht auch anders, ist aber so am einfachsten)


## Vorbereitung & Bootloader entsperren

  * Das Entsperren des Bootloaders (um was anderes als das intallierte System zu laden) erfolgt bei Xiaomi per Antrag. Auf [dieser Website](http://en.miui.com/unlock/) legt man sich einen MI-Account an und darf dann mit einer textlichen Beschreibung um die Unlock-Berechtigung für seinen Account bitten. An seinem Gerät muss man zu diesem Zeitpunkt noch gar nichts tun; die Freigabe dauert 2 bis 4 Tage und man wird per SMS benachrichtigt ([hier eine ausführliche Anleitung](http://en.miui.com/unlock/) und [hier noch eine ausführlichere](http://en.miui.com/thread-199580-1-1.html)).
  * Ferner muss das zu entsperrende Gerät noch mit dem angelegten Account verbunden werden. Das erfordert 2 Schritte (meine Beschreibung ist etwas grob, weil ich kein MIUI mehr zur Verfügung habe :-) )
    * Anmeldung in der "Mi Account" App auf dem Telefon mit dem zuvor angelegten Account
    * Unter _Einstellungen_ > _Telefoninfo_ ein paar Mal auf die MIUI-Version tippen, bis die "Developer Options" aktiviert sind, dann unter _Einstellungen_ > _weitere Einstellungen_ > _Developer options_ 1. USB-Debugging aktivieren und 2. unter _Unlock Status_ auf "Associate with Account" tippen. Ab jetzt scheint die "Binding Time" zu zählen, die bis zum Unlock ein 
    * Zur Prüfung kann man sich wiederum [hier](https://i.mi.com/) einloggen und unter "find device" nachschauen, ob das Gerät dort erscheint.
  * Nach der Freischaltung kann endlich entsperrt werden und zwar mit Hilfe einer kleinen Software, die man sich jetzt nach Login [auf der Unlock-Seite](http://en.miui.com/unlock/) herunterladen kann (gibt es nur für Windows und das Entsperren hat bei mir _nicht_ auf eine virtuellen Maschine funktioniert).
  * Handy mit gleichzeitig gedrückter [Lautstärke-] und [Stanby-Taste] mit Fastboot starten und per USB an den PC anschließen.
  * Unlock-Programm ausführen, mit dem Mi-Account einloggen, den Buttons folgen und Sicherheitshinweise ignorieren.
  * Das Ergebnis kann wieder unter _Einstellungen_ > _weitere Einstellungen_ > _Developer options_ > _Unlock Status_ gesehen werden. Hier müsste jetzt stehen "This device is unlocked". 

## Alternative Recovery-Lösung installieren

  * Jetzt geht es daran das Custom-Recovery _TWRP_ aufs Gerät zu bringen, was letztlich erlaubt ein anderes Betriebssystem zu installieren. ([hier eine ausführliche Anleitung](https://www.chinahandys.net/anleitung-twrp-xiaomi/) und [ein Video](https://www.youtube.com/watch?v=G_P7Qd3kpAI) zu diesem Schritt)
  * Dazu _Minimal ADB and Fastboot_ [herunterladen](https://forum.xda-developers.com/showthread.php?t=2317790) und installieren und TWRP für die passende Board-Version [hier herunterladen](https://www.androidfilehost.com/?w=files&flid=50678) und als `twrp.img` in den Programmordner von _Minimal ADB and Fastboot_ verschieben (Zusammenhang zwischen Board-Bezeichnung und Modell lässt sich [hier](https://xiaomi.eu/community/forums/miui-weekly-rom-releases.103/) ergründen)
  * Spätestens jetzt alles auf dem Gerät sichern bzw. mit einem Cloud-Dienst synchronisieren, was man später noch verwenden möchte.
  * Handy mit gleichzeitig gedrückter [Lautstärke-] und [Stanby-Taste] mit Fastboot starten und per USB an den PC anschließen.
  * In dem Terminal mit `adb devices` die Kommunikation prüfen und dann mit `fastboot flash recovery twrp.img` gefolgt von `fastboot boot twrp.img` _TWRP_ kopieren und starten

## OS installieren

  * Der entscheidende Schritt geht eigentlich ganz schnell. Zuerst TWRP auf was anderes als Chinesisch einstellen wie in der Bilderfolge [dieser Anleitung](https://www.chinahandys.net/anleitung-twrp-xiaomi/) ersichtlich
  * Dann mit _Wipe_ das System löschen, danach auf _Zurück_ und mit _Installieren_ fortfahren. Hier zum Grundverzeichnis des Handys navigieren, zuerst das gewählte Betriebssystem-ZIP anwählen und _Image installieren_ wählen, danach genau das Gleiche mit der G-Apps-ZIP. Die Rückmeldung auf dem Bildschirm lässt einem nicht umklaren, wie es um den Fortschritt bestellt ist.
  * Dann Neustarten und das Handy mit neuem Betriebssystem einrichten und genießen.
  * Dank OTA-Updates bleibt das System aktuelle solange es von der Community gepflegt wird.

