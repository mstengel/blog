---
layout: post
title: Gebietsverwaltung - Karten mit OSM (Teil 3)
categories: [jwtech]
tags: [Gebietsverwaltung, mapping]
description: Teil 1 und Teil 2 dieser Artikelserie beschäftigten sich mit dem Weg zu einer Datenbasis, die dazu dienen soll die einzelnen Gebietsansichten zu erzeugen. Wie das geht, ist Gegenstand dieses dritten Teils..
comments: true
---

[Teil 1](http://blog.stngl.net/jwtech/2015/12/28/gebietsverwaltung-karten-mit-osm-pt1/) und [Teil 2](http://blog.stngl.net/jwtech/2015/12/28/gebietsverwaltung-karten-mit-osm-pt2/) dieser Artikelserie beschäftigten sich mit dem Weg zu einer Datenbasis, die dazu dienen soll die einzelnen Gebietsansichten zu erzeugen. Wie das geht, ist Gegenstand dieses dritten Teils.

## Export einzelner Kartenausschnitte

Einzelne Gebietskarten stellen wiederum einen Ausschnitt aus den zuvor erstellten Ausgangsdateien dar, in denen nur der Umriss eines einzelnen Gebiets zu sehen ist, sowie ein Teil der Umgebung, um beim Gebrauch eine schnelle Zuordnung zu gewährleisten.

Die exportierten Bilddateien sollten immer dasselbe Seitenverhältnis haben, um auf der gedruckten Karte immer denselben Platz einzunehmen. Wie groß dieser sein soll, hängt von der gewählten Aufteilung ab. Es ist aber durchaus empfehlenswert, die gesamte Vorderseite der Karte dem Kartenausschnitt zu widmen und alle weiteren Angaben auf der Rückseite unterzubringen. Auch wenn das Layout der alten braunen Gebietskarte (S-12-X) nicht mehr bindend ist, ist es doch empfehlenswert das Grundformat beizubehalten. Es ist handlich und passt in die vorhandenen Klarsichthüllen. Das Format ist 14,55 x 9,4 mm, das Seitenverhältnis beträgt also 1:1,55.

Hierfür braucht es in der Basisdatei eine neue Ebene namens „Export“, die in vorderster Ebene liegen muss. In diese wird mit dem Viereckwerkzeug um ein beliebiges Gebiet ein Rechteck eingezeichnet, das über den Dialog „Füllung und Kontur“ so gestaltet wird, dass es ohne Füllung und mit einer schmale, gestrichelte Linie hat.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen015.png)

Jetzt muss das Seitenverhältnis eingestellt und fixiert werden, damit später auf der Karte kein Platz verschwendet wird. (Es ist hier allerdings noch nicht nötig ein festes Maß in mm einzustellen.) Dazu das gezeichnete Rechteck mit dem Werkzeug „Objekte auswählen und verändern“ markieren, sodass im oberen Bereich eine Leiste mit den Dimensionen in px sichtbar wird. Um das angestrebte Seitenverhältnis einzustellen den Wert H (Höhe) mit in diesem Fall 1,55 multiplizieren und das Ergebnis bei B (Breite) eingeben. Das Rechteck hat nun das korrekte Seitenverhältnis. Mit Aktivierung des Schloss-Buttons neben den Größenfeldern kann man dieses fixieren.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen016.png)

Dieser Rahmen kann jetzt innerhalb der Ebene „Export“ mehrfach kopiert und eingefügt werden, sodass um jedes Gebiet herum ein geeigneter Ausschnitt markiert wird. Mit den schwarzen Pfeilen am markierten Objekt kann dabei die Größe der Gebietsmarkierung angepasst werden. Auch eine Drehung ins Hochformart kann empfehlenswert sein, wenn ein Gebietsumriss eher hoch als breit ist. Das Ergebnis mutet etwas unübersichtlich an, ist aber eine zuverlässige Basis für den eigentlichen Export.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen017.png)

Der nächste Schritt ist nun der Export einer einzelnen Gebietsansicht. Dazu muss man Anhand des Augen-Symbols in der Ebenenübersicht alle Gebiete und die Nummerierung ausblenden, sodass nur die Ebene, die zu dem zu exportierenden Gebiet gehört und die Export-Rahmen sichtbar bleiben. Dann wird der Rahmen um das sichtbare Gebiet mit dem Werkzeug „Objekte auswählen und verändern“ markiert. Danach kann auch die Ebene „Export“ ausgeblendet werden. Dabei bleibt die Markierung aber bestehen.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen018.png)

Über „Datei > Bitmap exportieren“ ist der Dialog zum Speichern des Ausschnitts als PNG-Datei und damit Pixelgrafik erreichbar. Von den Möglichkeiten muss „Auswahl“ gewählt werden. Hier kann auch eine passende Auflösung in DPI angegeben werden, die am Ende die Breite und Höhe der Bilddatei bestimmt.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen019.png)

Am gewählten Speicherort liegt jetzt eine PNG-Datei die das Gebiet abbildet. Auf diese Weise muss nun für alle Gebiete der Basisdatei verfahren werden.

Auch eine **Gesamtkarte** kann so sehr einfach exportiert werden, indem alle Gebiete und (wenn gewünscht) auch deren Nummern eingeblendet werden. Im „Bitmap exportieren“-Dialog kann dann „Zeichnung“ gewählt werden, sodass nicht nur ein Ausschnitt exportiert wird, sondern der gesamte sichtbare Inhalte.

## Herstellung der Vorderseiten

Als nächstes muss sichergestellt werden, dass die zukünftigen Vorderseiten der Gebietskarten im korrekten Format auf Papier gedruckt werden können. Ferner sollte auch die Gebietsnummer und – zur schnellen Orientierung – der Ortsname auf die Vorderseite gebracht werden.

Für diesen Arbeitsschritt bietet sich ein beliebiges Textverarbeitungsprogramm an. Dies sind die Arbeitsschritte in Stichpunkten:

  * Seite einrichten: Damit drei Gebietskarten auf ein A4-Bogen gedruckt werden können, müssen besonders die oberen und unteren Seitenränder sehr schmal sein. Oben/unten 0,7cm, Rechts/links 2,0 cm funktionieren gut
  * Tabelle einfügen: Jede Kartenvorderseite ist letztlich eine Zelle in einer langen, einspaltigen Tabelle. Damit die Maße stimmen über die Einstellungen der Tabelle Spaltenbreite auf 14,55 cm und Zellenhöhe auf 9,4 cm fest einstellen. Die Rahmenlinien sollten sichtbar aber dezent bleiben, da sie nach dem Druck als Vorlage für das Ausschneiden dienen.
  * Kartenausschnitte einfügen: Jetzt werden nacheinander in jede Zelle die Kartenausschnitte in Form von Bilddateien eingefügt. Falls sie zu groß oder zu klein sind, über die Bildeinstellungen die Maße auf die oben genannten einstellen, dabei das Seitenverhältnis beibehalten.
  * Gebietsnummer und Ortsname abbilden: Hierfür eignen sich Textfelder, die man vordergründig in jede Zelle einfügt, ohne allerdings wichtige Bereiche zu verdecken (z.B. die Markierung des eigentlichen Gebiets).
  
![Screenshot](http://stngl.net/assets/201512/thg_karten_screen020.png)

Auf diesem Weg entsteht eine Textdatei, die mehrere Gebietskartenvorderseiten beinhaltet. Diese kann als PDF-Datei abgelegt werden und in Ihrer Gesamtheit auch abgeheftet werden (als Ordner mit „Gebietskopien“, wie er gelegentlich empfohlen wird.) Außerdem dient die PDF-Datei als Druckvorlage für die einzelnen Karten.

Für die Erstellung der Handkarten ist es empfehlenswert, Vorder- und Rückseite getrennt zu bedrucken und getrennt in die Klarsichthülle zu stecken. Dies vereinfacht die Herstellung und Aktualisierung.

Damit sich die Gebietskarte auch hochwertig anfühlt und zur pfleglichen Behandlung einlädt empfiehlt es sich eher hochwertigen, schweren Karton (z.B. 300 g/m²) als Papier zu wählen. Hierbei muss sichergestellt werden, dass der Drucker derartig starkes Medium auch problemlos einziehen kann.

Für das Ausdrucken ist es wichtig, dass keine Verkleinerung vorgenommen wird, wie dies zum Beispiel im Rahmen der Option „in Druckbereich einpassen“ passiert. Die Skalierung muss 100% betragen, da sonst die eingestellten Abmessungen nicht 1:1 gedruckt werden. Dies wird die Warnung hervorrufen, dass der Druckbereich zu klein ist o.ä.. Dies kann ignoriert werden. Die Konsequenz ist, dass der Drucker den Rand der Vorlage nicht drucken wird, der sowieso weiß ist, dass aber der Rest der Vorlage originalgetreu zu Papier gebracht wird.

Abschließend müssen die Karten zurechtgeschnitten werden.

## Erstellung der Rückseiten

Die Rückseite sollten mindestens beinhalten: Gebietsnummer, Bezeichnung der Ortschaft, Straßen mit Nummern (wenn erforderlich), Zahl der Wohneinheiten (wenn möglich je Straße), Gesamtzahl der Wohneinheiten und den Satz „Bewahre diese Karte bitte in der Schutzhülle auf. Beschmutze, beschreibe und knicke sie nicht. Teile bitte dem Bruder, der sich um die Gebietsablage kümmert, jede Bearbeitung des Gebietes mit.“

Für die Software zur Erstellung und die Gestaltung und Anordnung gibt es verschiedene Möglichkeiten (Textverarbeitung oder Tabellenkalkulation). Es muss nur sichergestellt werden, dass auch hier das Maß 14,55 x 9,4 cm eingehalten wird.

Wenn die Vorderseite auf entsprechend starkem Karton gedruckt worden ist, kann die Rückseite auf normales Papier gedruckt und einfach dahintergesteckt werden. Für die Skalierung des Ausdrucks gilt dasselbe, wie oben für die Vorderseite beschrieben.

![Screenshot](http://stngl.net/assets/201512/thg_karten_screen021.png)

Fragen oder Anregungen bitte in die Kommentare.
