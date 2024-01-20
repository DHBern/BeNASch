---
title: 1. Einführung
layout: default
nav_order: 2
---

# 1. Einführung

## 1.1. Grundlage

BeNASch basiert auf den Automatic Content Extraction 2005 - Guidelines,
ein Standard, der im Bereich der Informationsextraktion von modernem
Englisch üblich ist. BeNASch hat viele Anpassungen erfahren, wo aber
etwas unklar sein sollte, können die Anweisungen in
[[ACE2005]](https://www.ldc.upenn.edu/sites/www.ldc.upenn.edu/files/english-entities-guidelines-v5.6.6.pdf)
aushelfen.

## 1.2. Motivation

Diese Richtlinien sollen eine einheitliche Annotation von Texten in
vormodernem Deutsch ermöglichen, wobei semantische Informationen
bezüglich relevanter Entitäten (Personen, Orte, Organisationen, etc.)
und Beziehungen zwischen diesen Entitäten extrahiert werden.

Computerlinguistisch gesprochen sollen die gegebenen Informationen das
maschinelle Training für die folgenden Informationsextraktions-Aufgaben
ermöglichen:

-   Entity Detection

-   Named Entity Recognition

-   Relation Extraction

-   Coreference Resolution

-   Event Extraction

Das Ziel ist hierbei sowohl Konsistenz, wie auch Vollständigkeit.
Konsistenz stellt unter anderem sicher, dass Annotator:innen keine
Schwierigkeiten haben, sich für die richtige Annotation zu entscheiden,
dies verschnellert auch den Annotationsprozess. Auch maschinengestütztes
Lernen profitiert von konsistenten Trainingsmaterial. Das Ziel von
BeNASch ist daher auch, Kompatibilität für computerlinguistische
Analysen zwischen verschiedenen Editionen herzustellen.

## 1.3. Eckpunkte

## 1.4. Komplexität

BeNASch mag auf den ersten Blick überwältigend wirken. Es ist weitaus
komplexer als eine flache Named Entity Annotation und beansprucht auch
mehr Zeit. Leider ist nur so das Ziel einer konsistenten, vollständigen
Annotation zu erreichen.\
Um den Annotationsprozess zu beschleunigen, empfehlen wir, nicht direkt
nach dem Schema zu annotieren, sondern "Abkürzungen" zu verwenden. Im
Dokument
[[Annotationsanleitung]](https://docs.google.com/document/u/0/d/1EL__O2yvNSZROLAoKgpeucuP032SEG1BDlfEx_mS_Sc/edit)
geben wir praktische Tipps mit welchen Werkzeugen die Dokumente am
schnellsten aus gängigen Formaten (Transkribus-Export, TEI) zu
annotieren sind, und welcher "Abkürzungen" sich Annotator:innen bedienen
können. Zudem stellen wir Post-Processing-Skripte bereit, mit welchen
die "abgekürzten" Annotationen dann in das vollständige Schema
umgewandelt werden können.

Für Projekte, welche keinen Wert auf eine vollständige Annotation legen,
stellen wir zudem BeNASch-lite vor, eine reduzierte Version dieses
Schemas, welches aber kompatibel ist.

## 1.5. Vorverarbeitung des Textes

Die Vorverarbeitung des Textes sollte wie die Annotation einheitlich
sein. Aus diesem Grund versuchen wir, möglichst wenig am Text zu ändern,
der einzige Schritt, der zwingend durchzuführen ist, ist die
[[Tokenisierung]](https://de.wikipedia.org/wiki/Tokenisierung).
Hierbei geht es in erster Linie darum, Satzzeichen von Wörtern zu
trennen, um eine saubere Annotation zu ermöglichen.\
Verwenden Sie das empfohlene Verfahren in der Anleitung, können Sie sich
der dort vorgeschlagenen Tokenisierung bedienen.

Abkürzungen sollten möglichst aufgelöst und ohne weitere Markierungen
(z.B. eckige Klammern) dargestellt werden.

## 1.6. Wörter als Basis-Einheit

In BeNASch wird auf Token-Basis annotiert. Dies deshalb, weil nur wenige
maschinelle Annotationsalgorithmen zeichenbasierte Annotationen
akzeptieren und die Annotation dadurch schneller möglich ist (Es ist
schneller auf ein Wort zu klicken, also jedes mal die genauen Zeichen zu
markieren).

## 1.7. Dokumentation

Wie schon erwähnt, empfehlen wir in diesem Schema neben den
"Basis-Typen" auch optionale Typen. Um maximale Kompatibilität zu
gewährleisten ist es wichtig, dass sich ein Projekt darauf einigt,
welche optionale Typen es nutzen möchte (siehe Kapitel 6 für
Empfehlungen). Die gewählten Typen müssen konsequent annotiert werden um
Konsistenz in den Daten zu gewährleisten!\
Die Annotationsdokumentation des Projekts muss klar und verständlich
festhalten, welche optionalen Typen annotiert wurden. Falls eines der
Module in den Empfehlungen (Kapitel 6) genutzt wurde, kann einfach das
Modul festgehalten werden. In jedem Fall ist die Version des aktuellen
BeNASch in der Dokumentation zu verzeichnen.