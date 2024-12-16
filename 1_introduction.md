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
und Beziehungen sowie Interaktionen zwischen diesen Entitäten extrahiert werden.

Computerlinguistisch gesprochen sollen die gegebenen Informationen das
maschinelle Training für die folgenden Informationsextraktions-Aufgaben
ermöglichen:

-   Entity Detection
-   Named Entity Recognition
-   Coreference Resolution
-   Relation Extraction
-   Event Extraction

Das Ziel ist hierbei sowohl Konsistenz, wie auch Vollständigkeit.
Konsistenz stellt unter anderem sicher, dass Annotator:innen keine
Schwierigkeiten haben, sich für die richtige Annotation zu entscheiden,
dies verschnellert auch den Annotationsprozess. Auch maschinengestütztes
Lernen profitiert von konsistentem Trainingsmaterial. Das Ziel von
BeNASch ist daher auch, Kompatibilität für computerlinguistische
Analysen zwischen verschiedenen Editionen herzustellen.

## 1.3. Eckpunkte

### 1.3.1. Textnahe Annotation

Eine Faustregel für die Annotation in allen folgenden Kapiteln ist, dass
wir möglichst textnah annotieren. Am leichtesten lässt sich diese Regel
im Falle von Beziehungen demonstrieren. Haben wir einen Satz wie 
"Hans ist der Bruder von Maries Ehemann." dann finden wir darin die Beziehung
"Bruder" zwischen "Hans" und "Maries Ehemann", und eine "Ehe"-Beziehung
zwischen "Marie" und "Ehemann", aber keine Beziehung "Schwager" zwischen "Hans"
und "Marie". 

### 1.3.2. Hierarchische Typologien

Das Schema ist auf eine Weise geschrieben, die es ermöglichen sollte, unendliche
Unterkategorien für jede Kategorie, z.B. zur Entitätenklassifikation, zu schreiben.
Wir zielen in diesem Dokument darauf ab, eine solche Typologie vorzulegen, 
und weitere Unterklassen, welche Projekte verwenden, dieser hinzuzufügen um
möglichst grosse Kompatibilität mit späteren Projekten zu gewährleisten.

Verdeutlichen wir das an einem Beispiel mit der Beziehung vom Typ "Familie". 
Vielen Projekten würde diese grobe Einordnung der Beziehung zwischen zwei Personen ausreichen.
Ein Projekt, für welches diese Beziehungen aber in grösserem Detail festgehalten werden müssen, würde
eventuell feinere Kategorien wie "Ehe", "Geschwister", "Kinder", etc. festlegen.
Diese würden dann alle "Familie" untergeordnet und diese Verbindung würde im Schema, oder zumindest
in der Projektspezifischen Dokumentation (siehe 1.7.) festgehalten. 
Das würde Kompatibilität mit Projekten sicherstellen, welche die detaillierteren Unterscheidungen nicht verwenden.

## 1.4. Komplexität

BeNASch mag auf den ersten Blick überwältigend wirken. Es ist weitaus
komplexer als eine flache Named Entity Annotation und beansprucht auch
mehr Zeit. Leider ist nur so das Ziel einer konsistenten, vollständigen
Annotation zu erreichen.
Um den Annotationsprozess zu beschleunigen, empfehlen wir, nicht direkt
nach dem Schema zu annotieren, sondern "Abkürzungen" zu verwenden. Im
Kapitel 5 geben wir praktische Tipps mit welchen Werkzeugen die Dokumente am
schnellsten aus gängigen Formaten (Transkribus-Export, TEI) zu
annotieren sind, und welcher "Abkürzungen" sich Annotator:innen bedienen
können. Zudem stellen wir Post-Processing-Skripte bereit, mit welchen
die "abgekürzten" Annotationen dann in das vollständige Schema
umgewandelt werden können.

Für Projekte, welche keinen Wert auf eine vollständig BeNASch-konforme Annotation legen, stellen wir zudem Methoden vor, wie das Schema so reduziert werden kann, dass die eigenen Daten soweit kompatibel bleiben, wie möglich. _coming soon_

## 1.5. Vorverarbeitung des Textes

Die Vorverarbeitung des Textes sollte wie die Annotation einheitlich
sein. Aus diesem Grund versuchen wir, möglichst wenig am Text zu ändern,
der einzige Schritt, der zwingend durchzuführen ist, ist die
[[Tokenisierung]](https://de.wikipedia.org/wiki/Tokenisierung).
Hierbei geht es in erster Linie darum, Satzzeichen von Wörtern zu
trennen, um eine saubere Annotation zu ermöglichen.
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
Module in den Empfehlungen (_coming soon_) genutzt wurde, kann einfach das
Modul festgehalten werden. In jedem Fall ist die Version des aktuellen
BeNASch in der Dokumentation zu verzeichnen. (Versionierung beginnt bald)

## 1.8. Annotationsbeispiel

Anhand eines kurzen Textes demonstrieren wir hier die Grundlagen von BeNASch in zusammengefasster Form. Wir unterlassen hier manche weniger wichtigen Klassifikationen wie die Ordinalität, dieses Beispiel soll nur zur Einführung dienen. Es finden sich zudem Verweise und nach jedem Schritt ein Bild, wie die Annotation im von uns empfohlenen Workflow (auf der Plattform [[INCEpTION]](https://inception-project.github.io/)) zu handhaben wäre.

### 1.8.1. Ausgangstext
"Diebolt Rüly der Küfer und seine Frau Agnes haben einander\
gewidmet ihr Haus & Hofstatt in der Aeschenvorstadt"

### 1.8.2. Entitäten
In diesem Text erkennen wir die folgenden Entitäten-Erwähnungen:

REF.NAM.PER: **Diebolt Rüly** der Küfer
- REF ist der allgemeine Marker für Entitätenerwähnungen, die keine Attribute sind.
- NAM steht für *named*, also eine Entität, die anhand ihres Eigennamens erwähnt wird.
- PER steht für *person*, da es sich hierbei um eine Person handelt.
- *Diebolt Rüly* ist der *Head*, der Kern, der Erwähnung. Alle Entitätenerwähnungen müssen genau eine *Head*-Spanne aufweisen.

ATT.NOM.PER.OCC: der **Küfer**
- ATT ist der Marker für Erwähnungen, die aber "nur" die ihr übergeordnete Erwähnung, in dem Fall die des Diebolt Rüly, beschreiben.
- NOM steht für *nominative*, also eine Entität, die anhand eines Nomens beschrieben wird.
- Es handelt sich erneut um eine Person, erhält also die PER-Klassifikation.
- OCC beschreibt die Nennungsklassifikation (NOM) näher und zwar als *occupation*.
- Wie in Kapitel 1.7. beschrieben können wir uns hier beim Annotieren der Abkürzung ATT.OCC bedienen, da die Informationen NOM durch das ATT und die Info PER durch die übergeordnete Erwähnung bereits bestehen.
- *Küfer* ist der *Head*.

REF.NAM.PER: seine Frau **Agnes**

ATT.NOM.PER.FAM: seine **Frau**
- Hier handelt es sich um ein Attribut, wie schon der Beruf bei Diebolt. In diesem Fall aber is die Erwähnungspräzisierung vom Typen FAM (family) statt OCC.

REF.PRO.PER: **seine**
- Diese Pronominalnennung (PRO) bezieht sich auf Diebolt und wird in der Beziehungsannotation wichtig.

REF.PRO.PER: **einander**

REF.NOM.LOC: ihr **Haus & Hofstatt** in der Aeschenvorstadt
- Beachte, dass wir die gesamte Spanne samt der Beschreibung, wo das Haus liegt, mit einschliessen. Alles, was syntaktisch Teil der Nominalphrase rund um *Haus & Hofstatt* ist, ist Teil der Erwähnung!
- LOC steht für *location*.
- Wir annotieren die gesamte Phrase *Haus & Hofstatt* als eine einzelne Erwähnung, da es sich bei dieser Formulierung um ein und dieselbe Entität handelt, nicht um mehrere verschiedene Entitäten.

REF.PRO.PER.GRP: **ihr**
- Auch Possessiva werden als PRO annotiert und sind erneut sehr wichtig bei der Annotation der Beziehungen.

REF.NAM.LOC: der **Aeschenvorstadt**
- Bemerke, dass auch der Artikel Teil der Erwähnung ist.

![Annotation Example with Entities](./static/images/example_entities.png)
Bemerke, dass wir Pronomina abgekürzt annotieren, weil sie ihre weiteren Klassifikationen später anhand der Koreferenzen ablesen können. Wir annotieren auch keine *Heads*, wenn sie mit der Erwähnungsspanne komplett übereinstimmen würden.

### 1.8.3. Deskriptoren
Mit Deskriptoren können wir weitere Beschreibungen von Entitäten erfassen, auch wenn diese selbst keine Erwähnungen darstellen. Fett geschrieben sind zudem die optionalen Schlüsselwörter der Deskriptoren.
In der Erwähnung "ihr Haus und Hofstatt in der Aeschenvorstadt" sind folgende Deskriptorne zu annotieren:

DESC.OWNER: ihr (in "ihr Haus & Hofstatt ...")
- DESC ist der Marker für Deskriptoren.
- OWNER steht für eine Beschreibung der Besitzverhältnisse der Entität.
- Dieser Deskriptor impliziert gleichzeit eine OWNERSHIP-Beziehung (siehe nächstes Kapitel)

DESC.LOC: **in** der Aeschenvorstadt
- LOC steht für eine Beschreibung der Lage, bei einer Personenerwähnung kann es auch die Herkunft oder den Wohnort beschreiben. Wir können das LOC präzisieren, falls wir die Lage genauer beschreiben möchten (z.B. LOC_IN).

![Annotation Example with Descriptors](./static/images/example_desc.png)

### 1.8.4. Einfache Beziehungen
Beziehungen sind in weiterem Sinne Zustände (Kapitel 4), die ein Verhältnis zwischen mehreren Entitäten beschreiben.
Wie wir genau Beziehungen annotieren, wird in der Projektdokumentation spezifiziert. Nehmen wir an, dass wir uns für
die in diesem Teil folgenden Beziehungen, FAM, OWNERSHIP und LOC, auf eine einfache Annotation festgelegt haben, in der wir
nur die jeweiligen teilnehmenden Entitäten (Rollen) annotieren.
Die Textstrings hier beziehen sich auf die in 1.8.2. definierten Erwähnungen:

REL.FAM: "seine Frau" und "seine"
- FAM steht wie bei der Erwähnungspräzision in 1.8.2. für *family* und ist die Klassifikation der Beziehung.
- Rolle 1 (Ehepartner:in) ist "seine Frau", Rolle 2 (Ehepartner:in) ist "seine".
- Wenn unsere Projektdokumentation auch die Annotation der Textspanne vorschreiben würde, wäre das "seine Frau", also die gleich Spanne wie das Attribut.
- Wenn unsere Projektdokumentation auch die Annotation des Triggers vorschreiben würde, wäre das der Head "Frau".
- Wir machen uns diese überschneidenden Informationen mit dem Attribut zu Nutze und müssen im empfohlenen Workflow nur das Attribut annotieren, die Beziehung samt Rollen, optionaler Textspanne und Trigger wird dadurch impliziert und im Postprocessing erzeugt. 
- Da wir textnah annotieren, findet die Beziehung nur zwischen dem Attribut und dem unmittelbaren Pronomen statt, die Verbindung auf "Diebolt Rüly" findet erst in einem nächsten Schritt statt.

REL.OWNERSHIP:  "ihr Haus & Hofstatt ..." und "ihr"
- Auch hier können wir uns die Überschneidung mit dem Deskriptor zu Nutze machen.
- Ansonsten funktioniert alles analog zum vorigen Beispiel.

REL.LOC: "ihr Haus & Hofstatt in der Aeschenvorstatt" und "der Aeschenvorstatt"
- Funktioniert analog zum vorigen Beispiel.

### 1.8.5. Erweiterte Ereignis-Annotation
Ereignisse werden wie Zustände (u.a. Beziehungen) annotiert. In diesem Beispiel nehmen wir an, dass unser Projekt sich darauf festgelegt hat, das Ereignis "BEQUEST" (eine Widmung zweier Eheleute einander) mit obligatorischer Annotation der Textspanne, des Triggers und der Rollen der Widmenden und Empfänger der Widmung wie auch des Objekts der Widmung zu annotieren.

EV.BEQUEST:
- Textspanne: Der ganze Satz
- Trigger: "gewidmet"
    - Der Trigger sollte möglichst kurz sein und sogleich das Ereignis möglichst gut beschreiben.
- Rolle BEQUEATHER: "Diebolt Rüly der Küfer"
- Rolle BEQUEATHER: "seine Frau Agnes"
- Rolle BENEFICIARY: "einander"
- Rolle PROPERTY: "ihr Haus & Hofstatt..."

Wir müssen in diesem Beispiel die Rollen explizit annotieren, während die Rollen bei den einfachen Beziehungen im vorherigen Kapitel automatisch ableitbar waren, weshalb wir sie nicht explizit annotieren mussten. Das ist einer der Vorteile der Verschachtelung. Würden wir die Beziehungen im letzten Kapitel ausserhalb eines Deskriptors oder eines Attributs finden, oder wären sie komplexer als nur 2 Rollen, müssten wir die Rollen explizit annotieren, um Ambiguitäten zu vermeiden. 

![Annotation Example with Event](./static/images/example_event.png)


#### 1.8.6. Koreferenzen
Koreferenzen halten die Information fest, bei welchen Erwähnungen es sich um dieselben Entitäten handelt.
In unserem Beispiel finden wir zwei Pronominalerwähnungen, die wir durch Koreferenzen mit ausführlicheren Erwähnungen verbinden. 
Koreferenzen werden immer von im Text später erscheinenden Erwähnungen zu den früheren gezogen.

COREF: "seine" &rarr; "Diebolt Rüly der Küfer"

COREF: "einander" &rarr; "Diebolt Rüly der Küfer"
COREF: "einander" &rarr; "seine Frau Agnes"

COREF: "ihr" &rarr; "Diebolt Rüly der Küfer"
COREF: "ihr" &rarr; "seine Frau Agnes"

- Da es sich bei "ihr" und "einander" um Erwähnungen mehrerer Entitäten handelt, können wir auch mehrere COREFs setzen.
- Falls Listen-Elemente verwendet werden, kann die COREF einfach auf die Liste gesetzt werden, die dann sowohl Diebolt wie auch Agnes umfassen würde. In diesem Beispiel wurde auf Listen der Einfachheit halber verzichtet.
- Sind diese Koreferenzen markiert, ist nun auch klar, wie z.B. die Familienbeziehung zwischen Agnes und Diebolt repräsentiert wird.
    - "seine Frau Agnes" *ist* "seine Frau" (Attribut)
    - "seine Frau" *hat Familienbeziehung mit* "seine" (Beziehung)
    - "seine" *ist* "Diebolt Rüly" (Koreferenz)
- Wir annotieren Beziehungen zwar textnah an den Erwähnungen, aber schlussendlich ist damit zwischen den beiden Entitäten "Diebolt Rüly" und "Agnes" eine Beziehung vom Typ "FAM" ableitbar.