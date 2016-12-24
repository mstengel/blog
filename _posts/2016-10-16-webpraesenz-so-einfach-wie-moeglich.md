---
layout: post
title: Webpräsenz so einfach wie möglich
categories: [article]
tags: [HowTo, Logbuch]
description: 
comments: true
---

In den letzten Jahren habe ich sicher mehr Zeit darauf verwendet an der technischen Seite meiner Webpräsenz zu basteln als an der inhaltlichen. Nun ja, _das_ Thema, für das das Netz auf meine Beiträge wartet, hat sich bisher sowieso nicht herauskristalisiert, aber ein Ort um dann doch den ein oder anderen Beitrag zu teilen, habe ich mir schon immer gewünscht. Einiges davon, weil es einen Nutzen für andere haben könnte, anderes weil ich Erlebnisse festhalten möchte und mir das Schreiben selbst Spaß macht, mit dem Effekt, dass ein paar andere mitlesen können. Dabei stand für mich immer fest, dass es eine eigene, selbst gehostete Website sein muss. Ich glaube immer noch an ein Netz und einen persönlichen Austausch abseits der großen geschlossenen Plattformen.

Der Typische Ablauf war bisher immer so:
  1. Wunsch-Features im Kopf umherwälzen
  1. Zur Verfügung stehende Lösungen sichten und vergleichen
  1. unter Kompromissen eine auswählen
  1. implementieren und nach eigenen Wünschen anpassen
  1. alte Beiträge migrieren
  1. ein paar Monate unter hinzufügung neuer Inhalte nutzen
  1. Rückkehr zu (1)

## Was liegt so alles hinter mir?

**Selbst gebasteltes HTML** - OK, das ist schon ein paar Jahre her, aber aus Spaß an der Freude habe ich doch mal ein paar Sachen aus dem Nichts gebastelt. Von großen Frameworks, Boilerplates, Responsive usw. hatte ich entweder noch nichts gehört oder es war nicht aktuell. Aber ganz klar, schon die Gestaltung einer übergreifenden Navigation ist kein Kinderspiel, wenn man von dynamischen Techniken keine Ahnung hat. Aber ein Grundverständnis von HTML und CSS ist aus dieser Zeit definitiv hängen geblieben und hat mir in meinem Leben immer wieder geholfen.

![html1](http://stngl.net/foto/uploads/big/ae2088d7467036e1e703b3f4d0734d15.png)

![html2](http://stngl.net/foto/uploads/big/db98003ee56b9871648c819752aa3a65.png)

![html3](http://stngl.net/foto/uploads/big/1f6a54cb2b49af868dcd291bfeef7352.png)

**Nibbleblog** - Neben diversen Versuchen mit Wordpress bin ich seinerzeit auf diese Lösung für einen Blog ohne Datenbank gestoßen, kam dennoch mit einem Backend daher. Irgendwie wurde der Inhalt in XML-Dateien gespeichert, die ohne die Umgebung von [Nibbleblog](http://www.nibbleblog.com/) wiederum nicht so gut lesbar sind. Damit ergab sich eine Abhängigkeit zu einem ziemlich kleinen CMS Projekt, was inzwischen tatsächlich auch nicht weiterentwickelt wird.

**Posterous & Tumblr** - Diese Dienste für sog. Microblogging (heißt schnell, einfach, kleine Beiträge) waren sehr populär. Das ist natürlich nichts selbstgehostetes, aber es kam auch nicht daher wie eine der heutigen Plattformen. Man konnte sich zwar die Posts derer, denen man folgte in einer einheitlichen Oberfläche anschauen, die Blogs / Feeds selbst konnten aber individuell gestaltet werden und dies mit großer Freiheit. Das erschien mir ein guter Kompromiss, weil es technisch unkompliziert war und man ganz dezent Teil einer Community wurde. Die Ausrichtung auf Bilder passte ganz gut dazu, dass ich darüber auch meine Fotos veröffentlicht habe. _Posterous_ wurde von Twitter [aufgekauft](https://en.wikipedia.org/wiki/Posterous) und 2013 eingestellt (die Macher haben danach den [Bezahldienst _Postheaven_](posthaven.com) ins Leben gerufen, der sich das Versprechen auf die Fahne geschrieben hat, nie aufgekauft zu werden), _Tumblr_ habe ich dann für längere Zeit genutzt, um Bilder zu teilen, was auch wirklich Spaß gemacht hat. Da der Dienst 2013 von Yahoo aufgekauft wurde, wollte ich meine Präsenz dort nicht vertiefen und für längere Texte war dort sowieso nicht der richtige Platz.  

**Scriptogram** - Die Lösung, die Scriptogram bot, war eine gute Kombination aus Flat-File-Ansatz und Online-Pflege. Markdown-Textdateien wurden in einen Dropboxordner gelegt und dann durch den Dienst als HTML zur Verfügung gestellt, konnte auch über eine eigene Domain erfolgen. Die Inhaltspflege und Backup konnten also nach Belieben erfolgen, ein wirklilches Backend gab es nicht, viel Auswahl beim Theme usw. auch nicht. Der Dienst wurde leider ersatzlos eingestellt.

**Octopress** - Da es mir gefallen hat, Inhalte per Markdown zu verfassen und die Textdateien unabhängig von der Lösung aufheben und gebrauchen zu können, habe ich mich den statischen Blog-Generatoren zugewendet. [Octopress](http://octopress.org/) war da eine einladende Lösung (weiter entwickelt hinsichtlich themes, plugins als z.B. das sehr ähnliche [Pelican](http://blog.getpelican.com/)) - aus den Textdateien wird lokal die fertige Website generiert und dann auf den Webspace geladen, der freilich nichts anderes können muss, außer HTML. Auch die Seitenaufrufe sind entsprechend schnell. Leider ist die Arbeit am Blog dann nur an dem System möglich, wo alles installiert ist. Das wiederum ist für Octopress (was mit Ruby läuft) aber sehr schwierig - es gibt viele Abhängigkeiten und Updaten macht erst recht keinen Spaß. Der Macher wollte vieles daran ändern, aber seit der Ankündigung der nächsten Hauptversion ist anderthalb Jahre nichts passiert.

**Hugo** - [Hugo](http://gohugo.io/) ist eine junger statischer Websitgenerator, funktioniert also prinzipiell wie Octopress, macht aber so ziemlich alles besser und startet gerade richtig durch. Hier muss nur eine einzige Datei an bestimmter Stelle im System integriert werden, der Rest ist dann per Terminal bedienbar. Wenn also ein sog. 'Static Blog' die Lösung für mich wäre, dann definitiv mit Hugo. Leider bleibt die naturgemäße Einschränkung, dass die Pflege von Inhalten nicht online erfolgen kann, z.B. durch Mobilgeräte oder von anderen Rechnern (das sähe anders aus, wenn man Hugo auf einem Server betreiben würde, aber ich möchte vorerst bei Shared Hosting bleiben). Auch für die Medienverwaltung oder eine Kommentarfunktion gibt es keinerlei Komfort.

![hugo_terminal](http://stngl.net/foto/uploads/big/1d8eeb82246a3f25da27e0df991eda08.png)

_Einmal Block mit alles bitte_

![hugo](http://stngl.net/foto/uploads/big/44e5ecb39167d0569d6f05dac3abe782.png)

**Wordpress** - Wordpress als **die** Lösung für seelbstgehostete Blogs und Inhalte hat natürlich über die ganzen Jahre eine Rolle gespielt. Aber für meine Zwecke - vielleicht ein Post in 2 Wochen mit geringer Reichweite - erscheint es einfach "oversized". Mit jedem Log-In warten neue Updates, für jeden Sonderwunsch scheint es Plug-Ins zu geben, die die Installation aber unübersichtlich werden lassen, für richtig gute Lösungen (Themes wie Plugins), wird man zur Kasse gebeten, bevor man sie richtig testen kann. Darüber hinaus bin ich aber nicht wunschlos glücklich geworden, z.B. was meine Vorstellungen zur Einbindung von Bildern und Galerien angeht. Somit war ich mal wieder an dem Punkt mich mit Wordpress nicht mehr vollends wohl zu fühlen.

![wordpress](http://stngl.net/foto/uploads/big/1adc0af33d78dab21ca3ec8e02ddb82f.png)

_Mein Blog wie es zuletzt mit Wordpress und dem tollen Template [Independet Publisher](http://independentpublisher.me/) aussah_

Auf **Pico-CMS** bin ich vor nicht allzu langer Zeit gestoßen und habe damit auch ein klitzekleines Projekt umgesetzt. Und eigentlich finde ich das richtig gut:

  * Läuft mit dem sehr schlanken [Pico CMS](http://picocms.org/), braucht keine Datenbank, nur PHP
  * Das CMS ist nicht aufs Blog beschränkt, wie erforderliche Funktionen implementiert werden, ist in der Dokue beschrieben; für das Listing gibt es ein [Pagination Plugin](https://github.com/rewdy/Pico-Pagination)
  * Inhalte liegen in Textdateien vor, formatiert mit Markdown - können also lokal gesichert und unabhängig von Pico CMS verwendet werden
  * Templating erfolgt mit Twig, Theme ist somit recht einfach selbstgemacht, und zwar ausgehend von [Clean Blog von Startbootstrap](https://startbootstrap.com/template-overviews/clean-blog/)
  * Das Online-Editieren der auf dem Webspace liegenden Markdown-Datien wird durch [ein Plugin](https://github.com/blocknotes/pico_edit) möglich.
  * Der RSS-Feed wird wird den guten alten Google-Dienst _Feedburner_ gestellt (Das entsprechende Plug-In für Pico-CMS wurde leider nicht auf Version 1.0 migriert).
  * Bilder werden von Extern geliefert, aus einem eigenen Bilder-CMS, nämlich [_Lychee_](https://lychee.electerious.com/)

Das ganze ist so simpel, dass eigentlich nichts kaputtgehen kann, selbst wenn der Entwickler mal keine Lust mehr haben sollte. Die Plug-Ins sind sowieso von Dritten entwickelt (leider sind so einige, die mit Version 0.X von Pico CMS noch funktionierten nicht an die Version 1.0 angepasst), die Themes auch bzw. dank Twig auch schnell selstgemacht. Den Umfang von Version 1.0 erachte ich für zukunftssicher und ausreichend.

Diese simple Lösung setzt natürlich voraus, dass ich meine Erwartung etwas anpassen muss.

  * Gallerien - sofern sie überhaupt zum Einsatz kommen sollen, nicht über das CMS gepflegt werden. Daher wird der große Umfang von Fotos, die präsentiert werden sollen, unter einer gesonderten URL zu finden sein. Artikel, z.B. übr Reisen, könnten ein paar Highlights direkt beinhalten und für den Rest nach Extern verweisen
  * Ein Blog wird ist nach wie vor leider kein Ersatz für die kleinen Nachrichten / Fotos / Entdeckungen aus dem Alltag, die man schnell mit seinen Leuten teilen möchte, und die die "sozialen Netzwerke" so groß haben werden lassen. Zur Zeit pflege ich kein Profil, nur ein bisschen bei Google+. Um Kern-Facebook möchte ich weiter einen Bogen machen, Instagram ist immer noch schwer angesagt in meinem Umkreis, weiß mit seiner Einfachheit anzuziehen, aber der Besitzer Facebook wird sicher Umsatzmäßig auch noch mehr herausholen wollen. _Twitter_ hat etwas Reifes und Professionelles, jedoch spielt das Privat keine so große Rolle. Na ja, bis eine Entscheidung gefällt ist, könnte ich mich ja mal an Beiträgen an dieser Stelle versuchen, die nur einen Absatz umfassen

## Aktuell

Natürlich habe keine Garantie, dass die Reise an diesem Punkte zu Ende ist. Dennoch soll dieser Rückblick die Sache für mich etwas fixieren. Zur Technischen Basis dieser Website.

Diese Lösung basiert auf [GitHub Pages](https://pages.github.com/) das weiderum von [Jekyll](http://jekyllrb.com/) befeuert wird, bei dem es sich um den Urvater der statischen HTMl-Generatoren handelt. Mit [Poole](http://getpoole.com/) habe ich es mir etwas einfacher gemacht. Weiteres wird an dieser Stelle folgen.

## Noch zu tun

Eine Möglichkeit für Kommentare soll hier noch Einzug halten, nach Möglichkeit nicht _Disqus_; Ich denke eher an [_Hashover_](http://tildehash.com/?page=hashover) oder [_jskomment_](https://github.com/monperrus/jskomment).

Außerdem sollen Bilder per Klick größer werden, dabei der Alternativtext als Bildunterschrift erscheinen und die Bilder in einem Beitrag per Caroussel durchsehbar sein, na ja, wir werden sehen ... 
