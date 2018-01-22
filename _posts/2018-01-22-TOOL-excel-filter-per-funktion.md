---
layout: post
title: ⚒ Excel | Filtern per Funktion
categories: [snippet]
tags: [technology, application, excel] 
comments: true
---

Bei GoogleTabellen gibt es die schöne [Funktion](https://support.google.com/docs/answer/3093197) `Filter`.

```
FILTER(Bereich; Bedingung1; [Bedingung2; …])
```

Damit lassen sich Werte in einen anderen Bereich schreiben, die bestimmten Kriterien entsprechen. Dazu schreibt man die Formel nur in eine Zelle, worauf das Ergebnis in die darunterliegenden geschrieben wird. Bedingung ist, dass die Zellen, in denen die Werte landen sollen (Anzahl schwankt je nach Anzahl der Werte, die die Bedingung des Filters erfüllen), auch leer sind. 

Damit kann man sich eine Liste von eindeutigen Werten / Zeilenschlüsseln aus einer Tabelle in ein neues Blatt holen. Mit dem [Funktionspaar](https://www.tabellenexperte.de/excel-dream-team-index-verweis/) `INDEX` und `VERGLEICH` lassen sich dann nach Bedarf weitere Werte aus der Tabelle holen, sodass man eine dymaische, gefilterte und hoch anpassungsfähige gefilterte Liste zur Verfügung hat.

Das gibt es so bei Excel nicht (der _Erweiterte Filter_ soll im Grunde das Gleiche leisten, ist in der Handhabung aber sehr sperrig, insbesondere, wenn man die Informationen in den weiteren Spalten anders an inder Quelle aufbereiten möchte). Hiermit lässt sich aber das aber auch erreichen: 

```
KGRÖSSTE(INDEX((B$1:B$99="x")*A$1:A$99;0);2) 
```

Nachteil ist hier, dass die Formel in jede Zeile muss und man damit den Umfang des Filterergebnisses abdecken muss, damit unten nichts abgeschnitten wird. Auch hier lassen sich die weiteren Werte nach Bedarf mit `INDEX` und `VERGLEICH` holen.

Dank geht an die großartige Ressource [excelformeln.de](http://excelformeln.de/formeln.html?welcher=28), wo das Beispiel auch umfassend verständlich gemacht wird.
