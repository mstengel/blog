---
layout: post
title: Gebietsverwaltung - Karten mit OSM (Teil 1)
categories: [jwtech]
tags: [Gebietsverwaltung, mapping]
description: Als ich für unsere Versammlung den Auftrag bekam mich um die technische Seite der Gebietsverwaltung zu kümmern und dabei vor allem den in die Jahre gekommenen Bestand an Gebietskarten zu erneuern, musste ein zeitgemäßer Weg gefunden werden. Dies ist eine Beschreibung dieses Weges, also Tipps aus eigener Erfahrung – aufgeschrieben, um die Schritte nachvollziehbar zu machen und so die Aktualisierung durch jedermann zu ermöglichen
comments: true
---

![header](http://stngl.net/assets/201512/thg_karten_header.jpg)

Als ich für unsere Versammlung den Auftrag bekam mich um die technische Seite der Gebietsverwaltung zu kümmern und dabei vor allem den in die Jahre gekommenen Bestand an Gebietskarten zu erneuern, musste ein zeitgemäßer Weg gefunden werden. Dies ist eine Beschreibung dieses Weges, also Tipps aus eigener Erfahrung – aufgeschrieben, um die Schritte nachvollziehbar zu machen und so die Aktualisierung durch jedermann zu ermöglichen.

Folgende Überlegungen zu Anforderungen an Gebietskarten liegen dem zugrunde:

  * Sie zeigen die **Grenzen** des Gebiets deutlich an. Es ist zum Beispiel eindeutig erkennbar, welche Seite einer begrenzenden Straße oder welche Blocks dazugehören.
  * Zusammen mit einer Liste der Straßen und Nummern ermöglichen gut lesbare Straßennamen und (wenn verfügbar) eingezeichnete Hausnummern einfach zu erkennen, **was zum Gebiet gehört**.
  * Sie zeigen die nähere **Umgebung** soweit an, dass es möglich ist schnell zu erkennen, wo dieses Gebiet liegt und wie man dorthin kommt. Handelt es sich zum Beispiel um ein Wohngebiet mit kleineren Straße wäre eine Kartenausschnitt mit der nächsten Hauptstraße sinnvoll.
  * Sie hilft die Bearbeitung des Gebietes dadurch zu planen, dass ersichtlich ist, wie sich die Häuser und Blocks verteilen. Damit ist zum Beispiel der Aufwand pro Straße abzuschätzen (Einfamilienhäuser oder Blocks) und auch abgelegene Wohneinheiten werden nicht vergessen.
  
Die Pflege der Gebietskarten ist eine der zeitraubendsten Aufgaben des Gebietsdieners, aber man leistet damit für seine Brüder und Schwestern einen Dienst, der die Freude vergrößern kann. Neben Sorgfalt verlangt das auch den Willen, diesen Auftrag mit den vorhandenen Möglichkeiten so gut wie möglich zu erfüllen. Ausdauer ist gefragt, da Karten ja nicht nur einmal erstellt werden, sondern im Verlauf von Jahren auch aktualisiert und erweitert werden müssen. Dennoch soll die technische Aufgabe der Gebietskartenpflege nicht die eigene Dienstzeit einschränken, die letztlich wichtiger ist. Wo immer möglich, sollte man andere um Hilfe bitten, zum Beispiel beim Erkunden vor Ort.

Folgende Punkte werden im Folgenden kurz aus eigener Erfahrung beschrieben:

  1. Beschaffung von geeignetem Kartenmaterial
  1. Erstellung einer flexiblen Quelldatei auf Vektorbasis
  1. Export und Erstellung von Gebietskarten auf Papier

## Beschaffung von geeignetem Kartenmaterial

Aus den oben beschriebenen Anforderungen ergeben sich einige Leitkriterien bei der Auswahl des Kartenmaterials.

  * **Problemlose Skalierbarkeit, saubere Darstellung** in verschiedenen Maßstäben. Die Fläche der Gebietskarte ist immer gleich, jedoch unterscheiden sich die Gebiete in ihrem Ausmaß. In einem Gebiet aus Einfamilienhäusern verteilt sich dieselbe Anzahl Wohneinheiten auf einer größeren Fläche, als bei einem Gebiet mit Wohnblöcken. Dennoch soll alles ohne Lupe lesbar sein. (Landgebiete, die sich unter Umständen über mehrere Quadratkilometer erstrecken stellen hier einen Sonderfall dar, auf den später eingegangen wird).
  * Vorhandensein von gut lesbaren **Beschriftungen**. Unabhängig vom gewählten Kartenausschnitt sollten alle beteiligten Straßen eine Bezeichnung aufweisen.
  
Weitere wünschenswerte Kriterien kommen hinzu:

  * Keine **ablenkenden Symbole und Beschriftungen**. Karten, die im Internet zur Verfügung stehen (z.B. Google-Maps oder Bing-Maps) warten zwar mit einer gefälligen Darstellung und Detaillierung auf, kommen aber mit zahlreichen Zusatzinformationen daher, die für eine Gebietskarte nicht unbedingt brauchbar sind, siehe Beispiel unten. ![Innenstadtdarstellung mit Zusatzinformationen, von Google-Maps](http://stngl.net/assets/201512/thg_karten_BeispielGoogleMaps.png) _Innenstadtdarstellung mit Zusatzinformationen, von Google-Maps_
  * Wünschenswert ist es, dass für die Organisation einer nicht-kommerziellen, ehrenamtlichen Tätigkeit keine zusätzlichen Kosten anfallen, das Kartenmaterial also **kostenlos** verfügbar ist.
  * Die Kartendaten müssen **aktuell** sein. Gerade in Bereichen des Gebiets, wo noch neu und umgebaut wird, erleichtern möglichst aktuelle Karten das Bearbeiten und einteilen des Gebiets sehr.
  
Das alles führt zur folgenden Empfehlung als Quelle für das Kartenmaterial: **Vektor-Daten von Openstreetmap.org**

### 1. Vorzüge Vektor-Daten

Während in einem Rastergrafikdatenformat Informationen für jeden Punkt gespeichert werden, unabhängig davon, was der Inhalt des Bilds ist, werden bei Vektorgrafikformaten einfach gesagt die Inhalte, also Linien, Flächen (die so genannten Pfade) usw. gespeichert. Im Prinzip handelt es sich um Text in einer bestimmten Auszeichnungssprache, der alle Inhalte der Grafik definiert, z.B. Kreis mit Durchmesser a und Farbe b an Position x y. Dieser „Beschreibungstext“ muss für die Darstellung als Bild gerendert werden, d.h. in eine Grafik „übersetzt“ werden, was z.B. jeder zeitgemäße Browser beherrscht.

  * Gegenüber Rastergrafik (Bild besteht aus Pixeln, z.B. Bitmap, JPEG), die beim Vergrößern pixelig wird, hat Vektorgrafik den Vorteil einer sauberen Darstellung in jeder Vergrößerung, ohne Treppenbildung oder „Pixelmatsch“. Ganz egal welche Vergrößerung ein Kartenausschnitt für ein Gebiet also erfordert, die Darstellung wird immer befriedigend sein.
  * Während bei Rastergrafiken nur eine ganzheitliche Bearbeitung über alle Bestandteile möglich ist und Veränderungen am Inhalt nicht sauber bzw. mit aufwändigeren Algorithmen möglich sind (z.B. mit Adobe Photoshop oder GIMP), kann der Inhalt von Vektorgrafiken einfach und selektiv verändert werden (z.B. mit Adobe Illustrator oder Inkscape). Möchte man z.B. aus einem Kartenausschnitt im JPEG-Format die Beschriftung eines Gebäudes entfernen, ist das nur schwer möglich, denn die Bildpunkte, die die Buchstaben der Beschriftung darstellen, müssen durch eine Fortsetzung des Hintergrunds ersetzt werden. Liegt der Kartenausschnitt in einem Vektorgrafikformat vor, kann man den Pfad der Beschriftung einfach löschen, sodass die darunter liegenden Ebenen ohne Lücke sichtbar werden, z.B. ein Gebäudegrundriss.

### 2. Vorzüge Openstreet-Map

[Openstreetmap](http://www.openstreetmap.org) ist ein gemeinnütziges Projekt, das der Gemeinschaft aktuelle und hochwertige Karten der ganzen Welt zur Verfügung stellen möchte. Dahinter steht das von Wikipedia bekannte Prinzip aus freiwilligem Mitgestalten für jedermann und gegenseitiger Selbstkontrolle derer, die etwas beitragen. Das Ergebnis sind sehr detaillierte Karten, besonders für dicht besiedelte Regionen, die man kostenlos herunterladen und verarbeiten kann. Dies sind die Vorzüge:

  * Die Karten sind sehr **aktuell**, denn denn es finden sich viele Personen, die gemäß den Entwicklungen in ihrer Umgebung freiwillig und engagiert die Daten pflegen.
  * Die Karten sind **herunterladbar**, was bei populären Diensten wie Google-Maps nicht der Fall ist.
  * Die Karten sind u.a. im Vektordatenformat verfügbar und damit lokal und nach den eigenen Vorstellungen **bearbeitbar**.
  * Die Karten sind **kostenfrei** zu haben. Das haben sich die Initiatoren vorgenommen. Natürlich entstehen für den Service laufenden Kosten. Es besteht die Möglichkeit an die Organisation zu spenden.
  
Eine Bemerkung am Rande: Hinter OpentreetMap steht eine aktive und breit aufgestellte Szene und das Thema ist komplex. Wenn man die daraus resultierenden Vorzüge nutzt, ist es nur fair, auch selbst etwas zum Datenbestand beizutragen. Dies ist zum Beispiel dadurch möglich, dass man auf Fehler hinweist (online einfach unter [http://www.openstreetmap.de/karte.html](http://www.openstreetmap.de/karte.html) machbar) oder selbst aktiv Daten pflegt. Als Nebeneffekt unseres Dienstes beschäftigen wir uns mit Hausnummern und Straßen vermutlich so intensiv wie kaum ein anderer. Was liegt da näher, als die offiziellen Daten zu aktualisieren, wenn uns ein Fehler auffällt? Dies geht ebenfalls online oder anhand von speziellen Editorprogrammen (z.B. JOSM, [https://josm.openstreetmap.de](https://josm.openstreetmap.de)) Als Vorteil für uns ergibt sich daraus wiederum sehr aktuelles und genaues Kartenmaterial. Der sinnvollen Betätigung sind also keine Grenzen gesetzt, wenn man Freude daran hat und Zeit dafür erübrigen kann.

### 3. Download von Kartendaten

Die Größe einer einzelnen von openstreetmap.org herunterladbaren Grafikdatei ist begrenzt. Die Dateigröße wird durch durch das Maß des Ausschnitts und dessen Auflösung bestimmt. Da der Maßstab für Gebietskarten erfahrungsgemäß zwischen 1:8500 und 1:11000 liegen sollte, schränkt dies die Maße der einzelnen Abschnitte ein. Es ist also nötig eine größeres Gebiet in mehrere Dateien zu unterteilen. Dies ist auch für eine flüssige Bearbeitung der Vektordateien förderlich. Die einzelnen Teile sollten so gewählt werden, dass Stadtteile nicht geteilt werden. Überlappungen sind aber kein Problem.

Die Zoomstufe / der Maßstab bestimmen auch den Umfang der dargestellten Informationen. In den Onlinekarten werden Hausnummern z.B. erst ab ca. 1:5000 dargestellt. Hier ist also abzuwägen, ob die Abdeckung einer möglichst großen Fläche oder maximale Detaillierung schwerer wiegt.

(Komplexere Maßnahmen, um die Beschränkung der Export-Dateigrößen zu umgehen werden im Abschnitt 2.3 ganz kurz angerissen.)

Neben dem erstmaligen Download von Kartendaten eines Bereichs sollte Folgendes unbedingt bedacht werden: Irgendwann wird man die Daten aktualisieren wollen oder müssen. Die im Folgenden beschriebenen Schritte berücksichtigen die sich daraus ergebene Notwendigkeit, einen einst gewählten Kartenausschnitt mit identischen Grenzen erneut herunterladen zu können.

  * Aufruf von [openstreetmap.org](http://openstreetmap.org) in einem beliebigen Browser; im Linken Bereich „Daten exportieren“ aufrufen. Dies ist die Funktion zum Export der OSM-Rohdaten, also kein Export von gebrauchsfertigen Vektordaten. Leider besteht neuerdings nur hier die Möglichkeit, eine Auswahl des zu exportierenden Kartenausschnitts mit genauen Koordinaten zu treffen. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen001.png)
  * „Einen anderen Bereich manuell auswählen“ anklicken und in der Kartendarstellung einen Rahmen aufziehen, z.B. für einen bestimmten Stadtteil (die oben beschriebene Größeneinschränkung im Sinn behalten). Die 4 Koordinaten sollte man sich unbedingt notieren. Durch die Eingabe der 4 Werte kann man den Rahmen für einen späteren Export exakt wieder aufrufen. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen002.png)
  * Danach den Dialog „Export“ geöffnet lassen (damit der Rahmen sichtbar bleibt) und aus der rechten Werkzeugleiste „Teilen“ auswählen. Es öffnet sich ein weiterer Dialog. Hier das Häkchen „Ausschnitt festlegen“ aktivieren. Es legt sich ein weiterer Rahmen über das Bild. Dieser repräsentiert den zu exportierenden Kartenausschnitt. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen003.png)
  * Die vier Ecken des neuen Rahmens müssen nun exakt auf die vier Ecken des ersten Rahmens gelegt werden. Mit Hilfe der Zoomfunktion ist dies ohne Probleme schnell gemacht. Danach bei „Format“ SVG wählen und bei „Maßstab“ z.B. 8500 eingeben. Wenn dies bei dem gewählten Ausschnitt nicht möglich sein sollte, wird der Maßstab automatisch auf die kleinst-mögliche Zahl gesetzt. Dann muss man prüfen, inwieweit der maximal mögliche Maßstab akzeptabel ist (bis 11000 in der Regel kein Problem) bzw. den Ausschnitt verkleinern. ![Screenshot](http://stngl.net/assets/201512/thg_karten_screen004.png)
  * Mit Klick auf „Herunterladen“ die SVG-Grafik des gewählten Auschnitts herunterladen.
  
Dieser Umweg über zwei Rahmen ist recht umständlich und scheint unsauber. Das ist dem Ziel zuzuschreiben, die Auswahl durch Kenntnis der genauen Koordinaten wiederherstellbar zu machen (Früher konnte man auch für das Herunterladen direkt Koordinaten eingegeben werden. Dies wurde von den Betreibern geändert). Die eigentliche Exportfunktion funktioniert natürlich auch direkt durch eine Auswahl nach Augenmaß o.ä. Jedoch wird es dann nicht gelingen den identischen Kartenausschnitt zu einem späteren Zeitpunkt erneut herunterzuladen.

Wenn aber die Koordinaten des Ausschnitts feststehen, ist möglich denselben Ausschnitt direkt über einen bestimmten Link herunterzuladen.

Schema:

    http://render.openstreetmap.org/cgi-bin/export?bbox=[West],[Süd],[Ost],[Nord]&scale=[Maßstab]&format=svg

Beispiel für den oben gezeigten Ausschnitt:

    http://render.openstreetmap.org/cgi-bin/export?bbox=13.0426,52.3907,13.0634,52.4062&scale=8500&format=svg

Diesen Link kann man in die Adress-Zeile des Browsers kopieren, was den Download der entsprechenden Daten sofort auslöst. Dies macht ein erneutes Herunterladen, zum Beispiel zum Zwecke der Aktualisierung, relativ einfach.

Auf dem Rechner liegt jetzt eine Datei map.svg vor. Es empfiehlt sich diese entsprechend dem Inhalt umzubennenen. Diese Schritte sollten für alle Teile des Versammlungsgebietes wiederholt werden, für die Gebietskarten zu erstellen sind, z.B. für alle Stadtteile nacheinander. Damit liegt nun das Ausgangsmaterial für die Erstellung der einzelnen Karten vor. Angesichts des gewissen Aufwands ist es gut zu wissen, dass diese Downloads im Folgenden nur für Aktualisierungen notwendig sind.

In Teil 2 geht es darum aus dem Kartenmaterial die Grundlage für die Erzeugung der einzelnen Kartenansichten zu erarbeiten.

Fragen oder Anregungen bitte in die Kommentare.
