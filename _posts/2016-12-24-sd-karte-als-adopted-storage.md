---
layout: post
title: SD-Karte als Adopted Storage
categories: [snippet]
tags: [Android, HowTo, LinkDump]
description: Ein paar Links dazu, wie die Speicherkarte unter Android verwendet wird mit welchen Schwierigkeiten deren Erneuerung einhergeht.
comments: true
---

Mit den mickrigen 8GB Speicher in meinem Moto G 2nd Gen bin ich auf eine SD-Karte angewiesen. Auch wenn ich an Daten, die auf dem Mobiltelefon verweilen spare, kommen immer ein paaar GB zusammen, v.a. Offline--Musik des verwendeten Streaming-Dienstes, aufgenommene Fotos und Videos und Podcasts.

Gut, dass seit Adnroid 6.0 die Möglichkeiten zur Einbindung der SD-Karte ins System verbessert wurde. Gern nahm die Option an, die SD Karte als "internen Spceicher" (adopted storage) zu verwenden. Andererseits verblieb seitdem in einem Hinterkopf ein diffuses Gefühl - was ist auf der Karte, was im Gerät? Kann man den Inhalt irgendwie sehen? Kann ich sie entnehmen? Warum wird trotz der Integration immer noch zwischen "Internem Speicher" und SD-Karte unterschieden? Die Lust sich damit auseinanderzusetzen war - zugegebenermaßen - klein.

Jetzt war ich dazu aber gezwungen. Immer wieder verabschiedete sich die SD-Karte im Betrieb, was natürlich zu zahlreichen Problemen führte. Ein Neustart behob das zwar immer wieder, aber nie für lange. Ich habe eine neue Karte besorgt und hatte die Idee den Inhalt der alten bitgenau per [dd](https://wiki.ubuntuusers.de/dd/) auf die neue zu verfrachten und reibungslos weiterzumachen.

Das klappte so letztlich nicht. Am Ende habe ich versucht das Volumen der Daten auf der Karte zu reduzieren, den Rest über die Android-Einstellungen wieder auf den internen Speicher zu verschieben (limitiert durch Platzprobleme), die alte Karte dann ausgeworfen und gelöscht und die neue zum 'internen Speicher' gemacht.

Hier möchte nur ein paar Links speichern, die in dieser Angelegenheit hilfreich waren.

  * [Hintergrund: Wie Android M die Speicherkarte anspricht](https://www.heise.de/ct/artikel/Hintergrund-Wie-Android-M-die-Speicherkarte-anspricht-2679598.html?hg=1&hgi=7&hgf=false) - Gute Beschreibung des Features 'Adopted Storage'
  * [How can I move data from an adopted SD card to a new SD card?](http://android.stackexchange.com/questions/141319/how-can-i-move-data-from-an-adopted-sd-card-to-a-new-sd-card) - Erörterung zu genau meiner Problemstellung
  * [Decrypting Android M adopted storage](https://nelenkov.blogspot.de/2015/06/decrypting-android-m-adopted-storage.html) - Hintergründe zur Verschlüsselung der SD-Karte
  
Die Verluste hielten sich in Grenzen, aber ich empfand das Ganze viel zu hakelig, als dass ich das nochmal machen wöllte. Da heutzutage auch 128 GB interner Speicher kein teurer Luxus mehr sind, denke ich, wird das für mich mit dem nächsten Gerät kein Thema mehr sein. Allgemein dürfte das einst so wichtige (und von Android-Nutzern gern hervorgehobene) Hardware-Feature der Erwetierbarkeit druch SD-Karte mittelfristig keine Rolle mehr spielen.
