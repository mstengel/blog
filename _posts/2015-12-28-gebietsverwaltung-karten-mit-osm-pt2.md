---
layout: post
title: Gebietsverwaltung - Karten mit OSM (Teil 2)
categories: [jwtech]
tags: [Gebietsverwaltung, mapping]
description: Auf dem Weg zu zeigemäßen Gebietskarten ging es im ersten Teil um die Beschaffung von geeignetem Kartenmaterial mit Hilfe von OpenStreetMap. In diesem Teil geht es darum aus dem Kartenmaterial die Grundlage für die Erzeugung der einzelnen Kartenansichten zu erarbeiten. Im Rahmen der nachfolgenden Schritte werden in die Ausgangs-Datei im Vektorgrafik-Format alle Gebiete des betreffenden Stadtteils eingezeichnet. Dies gewährleistet eine Aufteilung ohne Lücken oder Überschneidungen. Dabei bleiben alle Grenzen und Einzeichnungen vollständig bearbeitbar. Danach werden die einzelnen Gebiete als Pixelgrafik-Dateien exportiert und zu Gebietskarten verarbeitet.
comments: true
---

Auf dem Weg zu zeigemäßen Gebietskarten ging es im [ersten Teil](http://blog.stngl.net/jwtech/2015/12/28/gebietsverwaltung-karten-mit-osm-pt1/) um die Beschaffung von geeignetem Kartenmaterial mit Hilfe von OpenStreetMap. In diesem Teil geht es darum aus dem Kartenmaterial die Grundlage für die Erzeugung der einzelnen Kartenansichten zu erarbeiten.

Im Rahmen der nachfolgenden Schritte werden in die Ausgangs-Datei im Vektorgrafik-Format alle Gebiete des betreffenden Stadtteils eingezeichnet. Dies gewährleistet eine Aufteilung ohne Lücken oder Überschneidungen. Dabei bleiben alle Grenzen und Einzeichnungen vollständig bearbeitbar. Danach werden die einzelnen Gebiete als Pixelgrafik-Dateien exportiert und zu Gebietskarten verarbeitet.

Alle Arbeitsschritte werden Anhand der freien und kostenfrei erhältlichen Software Inkscape ([http://inkscape.org](http://inkscape.org)) gezeigt. Eine kurze Einführung zu den wichtigsten Bedienungsprinzipien gibt es z.B. unter [http://inkscape.org/doc/basic/tutorial-basic.de.html](http://inkscape.org/doc/basic/tutorial-basic.de.html). Antworten auf spezielle Fragen lassen sich im Internet dank aktiver Community in der Regel schnell per Suche finden.

  * Datei **öffnen**. Dann mithilfe des Knoten-Werkzeugs (F2, Mehrfachmarkierung mit Shift + Linksklick) nach Gefühl **Elemente löschen**, die das „saubere“ Erscheinungsbild der späteren Gebietskarte stören könnten, z.B. Symbole für Geschäfte, Verkehrstechnische Symbole o.ä..
  * Über „Ebene > Ebenen ...“ das Ebenen-Fenster öffnen. Dort eine neue **Ebene erstellen** (Button mit grünem Plus) und ihr einen eindeutigen Namen geben, z.B. „Karte“. Diese soll das gesamte Kartenmaterial aufnehmen und sozusagen den **Hintergrund** darstellen. Mithilfe des Auswahlwerkzeugs (F1) gesamte Grafik markieren (Strg + A) und ausschneiden. Dann Im Ebenen-Fester die neu erstellte Ebene auswählen und alles aus der Zwischenablage einfügen. Fall die Grafik im Verhältnis zum grauen Rahmen verschoben sein sollte, alles so verschieben, dass die Grenzen der Grafik wieder mit dem Rahmen übereinstimmen. Zum Test mithilfe des Augen-Symbols bei der Ebene diese ausblenden. Wenn alles korrekt ist, verschwindet die Karte. Dann mit dem Klick auf das geschlossene Auge wieder einblenden. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen010.png)
  * Jetzt können die einzelnen **Gebietsgrenzen** eingezeichnet werden. Jedes Gebiet muss in einer eigenen Ebene erstellt werden.
    * Im Ebenen-Fenster neue Ebene erstellen (Button mit grünem Plus) und mit der Gebietsnummer benennen. Sichergehen, dass auch die neue Gebiets-Ebene aktiv ist.
    * Mithilfe des Freihandlinien-Werkzeugs (F6) den Gebietsumriss zeichnen. Dazu an einer Ecke des Gebiets kurz klicken, um den ersten Punkt klicken, dann den Cursor an den Endpunkt der gewünschten Linie klicken – es ergibt sich eine gerade Linie. Dann mit dem weiterhin aktiven Werkzeug über den Endpunkt der ersten Linie fahren, sodass dieser Rot hervorgehoben wird und dann mit einem einfachen Klick den Startpunkt für die nächste Linie setzen usw.. Auf diese Weise den Umriss des Gebiets zeichnen und den Endpunkt der letzten Linie auf den Startpunkt der ersten setzen. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen011.png)
    * Falls etwas an dem Umriss geändert werden muss kann dies einfach mit dem Knoten-Werkzeug bewerkstelligt werden (F2). Hier können Punkte des Umrisses markiert und verschoben, aber auch gelöscht usw. werden.
    * Als nächstes müssen die optischen Eigenschaften dieses neuen Objekts auf gute Erkennbarkeit getrimmt werden. Dazu das Umriss-Objekt mit dem Auswahl-Werkzeug (F1) markieren, dann per Rechtsklick den Dialog „Füllung und Kontur aufrufen“. Folgende Einstellungen haben sich als günstig erwiesen.
      * Über den Schieberegler unten sollte die **Deckkraft** der gesamten Ebene auf 60% gesenkt werden. Das sorgt für eine ansehnliche Integration in den Kartenhintergrund.  ![Screenshot](http://stngl.net/assets/201512/thg_karten_Auswahl_008.png)
      * Im Reiter **„Füllen“** wiederum den Reiter „RGB“ wählen. Hier mit den Farbwerten (0;0;255) ein sattes Blau einstellen. Mit Blick auf die Farben des Kartenmaterials kann hierdurch ein guter Kontrast erzielt werden. Der vierte Wert (Alpha-Wert) gibt die Deckkraft der Füllung an. Diese muss im Vergleich zur Kontur nochmals deutlich abgesenkt werden. Eine dezente Füllung des Areals, was am Ende das Gebiet darstellt, trägt zur Deutlichkeit der Darstellung bei und ist empfehlenswert. Hier den Wert 50 eingeben.
      * Im Reiter „Farbe der Kontur“ mit (0;0;255) die selbe Farbe wie für die Füllung einstellen, den Alpha-Wert aber bei 255 belassen.  ![Screenshot](http://stngl.net/assets/201512/thg_karten_Auswahl_009.png)
      * Im Reiter „Muster der Kontur“ muss eigentlich nur die Breite auf 3px erhöht werden.Damit ist ein Gebiet eingezeichnet. Auf diese Weise können nun alle weiteren Gebiete für den Stadtteil, der in dem Kartenausschnitt abgebildet wird, eingezeichnet werden. Nicht vergessen: Jedes Gebiet muss in einer gesonderten Ebene angelegt werden.  ![Screenshot](http://stngl.net/assets/201512/thg_karten_Auswahl_010.png)
      * Falls es versehentlich passiert, dass zwei Gebietsumrisse in dieselbe Ebene geraten, so kann der zu verschiebende Umriss ausgewählt und mit (Strg + X) ausgeschnitten werden. Danach kann das Einfügen in die korrekte Ebene mit (Strg + V) erfolgen. Oftmals muss die Linie dann manuell an die richtige Stelle geschoben werden.
      * Überaus hilfreich für das Einzeichnen mehrerer Gebiete ist die Funktion, die Eigenschaften eines Objekts (in diesem Fall Füllung und Kontur) auf ein anderes zu übertragen. Dazu das Vorbild mit (Strg + C) kopieren, das Objekt, auf das es die Eigenschaften zu übertragen gilt, anwählen, um die Eigenschaften dann mit (Umschalt + Strg + V) zu übertragen.
      * Beim Einzeichnen der Gebiete muss Eindeutigkeit gewährleistet sein. Dies gilt insbesondere, wenn nur einzelne Straßenseiten (statt z.B. eines ganzen Straßenblocks) zu einem Gebiet gehören sollen. Außerdem sollte es vermieden werden Umrisse über Straßennamen zu zeichnen. Im Notfall können Straßennamen verschoben werden. Unten ein Beispiel bei dem diese empfehlenswerten Regeln eingehalten worden sind.  ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen012.png)
    * Um die Übersicht nicht zu verlieren, ist es sinnvoll eine **Beschriftung** der einzelnen Gebiete einzufügen.  ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen013.png)
      * Da die Beschriftung nur für diese Gesamtdatei eine Rolle spielt (die Beschriftung für die einzelnen Karten wird anders vorgenommen, siehe unten), kann die Beschriftung für alle abgebildeten Gebiete in einer gemeinsamen Ebene „Beschriftung“ erfolgen. Diese muss über allen anderen liegen, also im Ebenen-Fenster an oberster Stelle stehen.
      * Eine solche Nummern-Beschriftung besteht aus einem Rechteck (Rechteck-Werkzeug, F4), mit den Eigenschaften: Deckkraft 85%, Unschärfe 55; Kontur: Breite 0; Füllung: weiß
      * Darüber wird ein Textfeld gelegt (Textobjekt-Werkzeug, F8), schwarz mit voller Deckkraft.
      * Dieses Beschriftungsfeld (Rechteck + Text) kann nun in jedes Gebiet kopiert werden (immer innerhalb der Ebene „Beschriftung“.
  * Auf diese Weise gelingt es recht schnell, die Einteilung eines bestimmten Stadtteils in einzelne Gebiete abzubilden. Da jedes einzelne Gebiet als eigene Ebene abgebildet wird ist es möglich, die einzelnen Gebiete auszublenden (Auge-Symbol im Ebenen-Fenster), sodass nur die gewünschten Gebiete sichtbar bleiben (Auch die gesamte Gebietsnummerierung kann ausgeblendet werden). Dies ist für den nachfolgenden Export einzelner Gebietskarten entscheidend. Ferner können aus dieser Datei heraus auch auf einfache Weise Übersichtskarten erzeugt werden, die alle Gebiete einer Gegend enthalten, z.B. für die Ablage oder den Aushang im Königreichssaal.
  
![Screenshot](http://stngl.net/assets/201512/thg_karten_screen014b.png)

Die so für die einzelnen Teile des Versammlungsgebietes erstellen Basis- oder Ausgangsdateien stellen die Grundlage für den Export der einzelnen Gebietskarten dar.

## Aktualisierung der Basisdatei

Von Zeit zu Zeit kann der erneute Download des Kartenmaterials von OpenStreetMap sinnvoll sein, um bauliche Veränderungen des Gebiets in den Karten abbilden zu können.

Dazu geht man mit den beim ursprünglichen Download notieren Koordinaten vor, wie unter 1.3 beschrieben. Wiederum erhält man eine Datei map.svg. In Maßstab und Dimension entspricht sie dem ursprünglichen Download.

Diese neue Datei wird dann im Vektorgrafik-Bearbeitungsprogramm (hier Inkscape) geöffnet, der gesamte Inhalt markiert (Strg + A) und kopiert (Strg + C). Nicht wundern, wenn das einen Augenblick dauert.

Um seine Basisdatei zu aktualisieren muss man diese öffnen und am besten alle eigenen Eintragungen ausblenden (Über den Ebenen-Dialog und das Augensysmbol), sodass man nur noch den Karten Hintergrund sehen kann. Auch der Inhalt dieser Ebene wird markiert (Strg + A) und gelöscht (Entf), sodass nur eine weiße Ebene zurückbleibt.

Jetzt können die neuen Daten aus der Zwischenablage eingefügt werden (Strg + V) sodass das Kartenmaterial in der Ebene erscheint. Nun ist zwar die Größe der eingefügten Grafik identisch mit der Größe der Ebene, aber die Position stimmt höchstwahrscheinlich nicht. Daher lässt man das Eingefügte markiert und bringt es mit dem Verschiebewerkzeug in Position, d.h. die Seiten in Deckung mit den Rändern der Ebene.

Störende Inhalte, die man aus der Karte nach dem ersten Download manuell entfernt, sind jetzt natürlich wieder da und müssen erneut gelöscht werden.

Auf diese Weise bleiben alle eingetragenen Gebietsgrenzen gültig und an der richtigen Position, sodass sie nach Belieben eingeblendet und bearbeitet werden können, wie zuvor.

## Die Grenzen des bis hier verwendeten Kartenmaterials

Die Erfahrung in Verbindung mit der Erstellung von Gebietskarten zeigt, dass die Darstellung der OpenStreetMap-Karten in höheren Maßstäben (z.B. 1:50.000), wie sie für die Darstellung von flächigen Landgebieten nützlich wären, nicht unbedingt geeignet ist. Die Art der Renderung der Daten hebt Details wie z.B. verstreute Häusersammlungen nicht gut genug hervor.

_OSM 1:50000_
![OSM](http://stngl.net/assets/201512/thg_karten_vergleich_OSM50.png)

_Ausschnitt aus den offiziellen digitalen Karten des Landesvermessungsamts (DTK50)_
![DTK50](http://stngl.net/assets/201512/thg_karten_vergleich_TOPO50.png)


Vorteilhaft an topografischen Karten ist u.a. die Beschriftungsgröße, die kontrastreiche Gesamtdarstellung und die zuverlässige Darstellung von alleinstehenden Einzelgebäuden. Hingegen sind zum Beispiel Straßennamen in diesem Maßstab nicht enthalten. Hintergrund totographische Karte (von [hier](https://opentopomap.org/about)):

> Für gute topographische Karten kommen besonders folgende Generalisierungmechanismen zum Einsatz:
> **Verdrängung**: Nah zusammenliegende Linien-Objekte (z.B. Straßen) können sich überlappen und dadurch verschwinden. Mittels Verdrängung können diese lokal verschoben werden, sodass beide Objekte nebeneinander liegen. Dadurch entsteht natürlich ein kleiner geographischer Fehler.
> **Intelligentes Setzen von Beschriftungen**: Ortsnamen sollten nicht blind über die Stadt gesetzt werden, sondern über Objekten geringerer Entropie.
> **gesperrte Beschriftungen von Flächen**: Die Beschriftung von z.B. Seen sollte in einer Hauptmittelachse in Kurven niedriger Ordnung geschehen; die Lettern von Regionsnamen (z.B. Bundesländer) sollten zusätzlich in passenden "Löchern" platziert werden.

Je nachdem, wie schwerwiegend diese Anforderungen für das eigene Versammlungsgebiet sind, kann es sich lohnen, die Gebietskarten für Gebiete außerhalb von Siedlungen auf Basis digitaler topografischer Karten zu erstellen.

### Topographische Karte für Langebiet auf Basis der OpenTopoMap

[OpenTopoMap](https://opentopomap.org/about) ist eine freie, topografische Karte, die aus den Daten der OpenStreetMap und SRTM-Höhendaten generiert wird. Der Kartenstil orientiert sich an den amtlichen Karten und setzt auf gute Lesbarkeit durch hohen Kontrast und ausgewogene Signaturen. Die Karte ist unter [https://opentopomap.org](https://opentopomap.org) zu sehen.

Um die Karten der Flächen- / Landgebiete, wie oben erklärt zu erstellen, ist es ebenfals empfehlenswert eine Basiskarte für das betroffene Areal oder sogar das gesamte Versammlungsgbiet zu erzeugen. Eine einfache Exportfunktion, wie bei openstreetmap.org gibt es jedoch nicht. Ferner werden die Daten nicht als Vektorgrafik dargestellt, sonderns muss als PNG-Pixelgrafik verwendet werden. Die Erstellung funktioniert folgendermaßen:

1. **Ermittlung der Gradnetzkoordinaten** der Grenzen des zu betrachtenden Areals. Das geht zum Beispiel innerhalb der oben beschriebenen Openstreetmap.org-Exportfunktion. Die einmal festgelegten Daten unbedingt aufschreiben!
1. **Ermittlung der Kachelnummern** - Der Download des Kartenmaterials erfolgt in kleinen Bildern á 256x256 pixel, den sog. Kacheln. Diese sind weltweit durchnummeriert. Die Errechnung des Kachelnummernbereichs ist vom Vergrößerungsfaktor (Zoom-Level abhängig) - Hintergründe gibt es [hier](https://wiki.openstreetmap.org/wiki/Slippy_map_tilenames). Durchführen kann die Umrechnung anhand der zuvor ermittelten Grenzen des Ausschnittes z.B. hier: [http://oms.wff.ch/calc.php](http://oms.wff.ch/calc.php)
1. **Erzeugen des PNGs** - Per Script (siehe unten) müssen die Kacheln heruntergeladen und zu einem einzigen, großen Bild zusammengefügt werden. Dazu werden dort der Kachelbereich in X- und Y-Richtung eingetragen, sowie die Zoom-Stufe. Für den hier betrachteten Zweck ist 14 am besten geeignet.

~~~ bash
#!/bin/bash 

#Fill in the desired tile numbers here
X1=8593
X2=8625
Y1=5242 
Y2=5261
Z=14

for x in `seq $X1 $X2`; do
    
    for y in `seq $Y1 $Y2`; do
    	
	if [ -e ${Z}_${y}_${x}.png ]
		then
    		echo "Keep ${Z}_${y}_${x}.png"
	else
		echo "Getting ${x},${y}"
        	curl -s -k https://a.tile.opentopomap.org/${Z}/${x}/${y}.png -o ${Z}_${y}_${x}.png &
		wait
	fi

    done

done

echo "Start montage"

montage -limit thread 8 -limit memory 30000MB -mode concatenate -tile "$((X2-X1+1))x" "${Z}_*.png" out_z${Z}_${X1}_${Y1}-${X2}_${Y2}.png
~~~

Die Verarbeitung und Einzeichnung der Gebietskarten doch genauso erfolgen, denn die Vektor-Grafik-Programme können in den Ebenen auch Rastergrafiken handhaben. Dazu unter 'Inkscape' in einem neuen Dokument die Größe in Pixeln auf die des zuvor erzeugten Bildes bringen (über "Datei" > "Dokumenteneinstellungen"), über das Ebenenmenenü eine neue Ebene hinzufügen (diese z.B. OpenTopo-Z14 nennen) und dann die Grafik importieren ("Datei" > "Importieren"). Ab hier können die einzelnen Gebiete genauso eingezeichnet werden, wie oben für Vektor-Grafiken beschrieben.

_Derselbe Kartenausschnitt wie oben mit dem Material von OpenTopo mit einigen Gebietsgrenzen. Diese wurden hier aufgrund des etwas anderen Farbspektrums der topografischen Karten in rot gehalten_
![OpenTopo](http://stngl.net/assets/201512/thg_karten_vergleich_Opentopo.png)

Teil 3 beschäftigt sich mit der Erstellung der einzelnen Gebietskarten.

Fragen oder Anregungen bitte in die Kommentare.
