---
title: 2.1. Entitäten
layout: default
nav_order: 1
parent: 2. Entitäten
---

# 2.1. Entitäten

## 2.1.1. Identifikation von Entitäten
Eine Entitäten-Erwähnung wird dann annotiert, wenn die Entität unter eine der festgelegten Entitäten-Klassen (Kapitel 2.9.) fällt. 
In der Bestimmung der Abgrenzung der Erwähnung, d.h. welche Wörter mit zur Erwähnung gehören, folgen wir soweit möglich der syntaktischen Struktur des Satzes.
Eine Erwähnung besteht dementsprechend sowohl aus dem Kern (*Head*) sowie die diesen umgebende [[Nominalphrase]](https://de.wikipedia.org/wiki/Nominalphrase). Ein paar Beispiele um zu beschreiben, was Teil der Erwähnung ist:

Beispiel: "\[Der alte <u>Schmied</u>\]"[^1]\
Beispiel: "\[Die <u>Witwe</u> des Schmied\]"\
Beispiel: "\[Des Schmieds <u>Witwe</u>\]"\
Beispiel: "\[Das <u>Haus</u> in der Vorstadt\]"\
Beispiel: "\[Das <u>Haus</u>, das in der Vorstadt liegt\]"

Diese Erwähnungen können teils grosse Längen annehmen, gewisse Dokumententypen neigen dazu ihre Informationen stark zu verschachteln. Hier ein fiktives Beispiel, das aber z.B. im *Historischen Grundbuch der Stadt Basel* nicht unüblich wäre (die eckigen Klammern markieren die relevante Erwähnung):

"Der Schaffner zu den Barfüssen hat \[Johannes Schmidlin des Gerbers <u>Behausung</u> samt der Schüren, genannt zum Roten Stern, gelegen in der Steinenvorstadt zwischen der Gerbern Zunfthaus und des Ulrich Zofingers des Schmieds Erben, zinst dem Kloster der Barfüsser 2 sh. alle Fronfasten, sonst frei\] um versessenen Zins wegen gefrönt."


## 2.1.2. Identifikation des *Heads*
Der *Head* markiert das syntaktisch zentrale Element der Erwähnung. Welcher Teil der Erwähnung der *Head* ist,
ist von der Erwähnungs-Klassifikation (Kapitel 2.3.) abhängig und wird in den dortigen Unterkapiteln erläutert.
Die Klassifikation einer Erwähnung wiederum bezieht sich exakt auf den *Head*. Informationen ausserhalb des *Head* können wiederum selbst als Erwähnungen, Werte oder Deskriptoren erfasst werden. *Head*-Elemente können keine weiteren Annotationen enthalten.

Jede Erwähnung muss genau einen *Head* aufweisen, der aber mehrere Wörtern umfassen kann.

## 2.1.3. Erwähnungs-Klassifikation (Mention Type)

Die Erwähnungsklassifikation hält fest, auf welche Weise eine Entität
im Text genannt wird.

Wir unterscheiden nach ACE-Vorbild unter den Erwähnungsarten:

### 2.1.3.1. Eigennamen-Erwähnung (NAM)

Hierbei handelt es sich um eine Erwähnung der Entität anhand ihres
Eigennamens.

Beispiel: "\[<u>Hans Schneider</u>, der Karrer in Neuenburg
gesessen\]"

Achtung, in einem solchen Fall handelt es sich nicht um eine
Eigennamennennung:

Beispiel: "\[Der <u>Hügel</u>, Büttenberg genannt, liegt 3 Meilen
nördlich\]"

Hier ist "Hügel" das syntaktisch zentrale Wort (*head*), während die
Eigennamenerwähnung in diesem Fall als Attributivnennung zu verzeichnen
wäre (Kapitel 2.7.). Die Erwähnung wäre in diesem Fall eine nominative
Erwähnung (Nächstes Kapitel).

### 2.1.3.2. Nominative Erwähnung (NOM)

Hierbei handelt es sich um eine Erwähnung anhand eines Nomens, welches kein Eigenname ist.

Beispiel: "\[Der <u>Schaffner</u> des Spitals\]"

Nominative Erwähnungen zeichnen sich oft dadurch aus, dass sie
Informationen zur Entität enthalten, wie den Beruf oder eine Beziehung
zu einer anderen Entität. Sie sollten in dem Fall mit einem passenden
Subtypen gekennzeichnet werden (Kapitel 2.9.).

### 2.1.3.3. Pronominale Erwähnung (PRO)

Hierbei handelt es sich um eine Erwähnung anhand eines Pronomens, häufig
ergänzt mit einer Beschreibung.

Beispiel: "\[<u>Der</u>, dem der Heinzi zinst\]"

Pronominalerwähnungen finden sich aber auch oft innerhalb anderer Erwähnungen
als Possessivpronomen.

Beispiel: "\[\[<u>seine</u>\] <u>Frau</u>\]"

#### 2.1.3.3.1. Spezialfall: Selbstreferenzierung (SELF)

Wenn ein Pronomen die verfassende Instanz selbst referenziert, wird
statt PRO SELF verwendet.

Beispiel: "\[<u>Wir</u>, \[<u>Burgermeister und Rat</u>
\[der Stadt <u>Basel</u> /NAM.GPE_ORG\] /NOM.ORG_GOV\]
/SELF.ORG_GOV\]"

Die Entitätsklassifikation wird wie üblich ermittelt, was bedeutet, dass
im Text kein Hinweis auf die Klassifikation des Verfassers gegeben ist,
dieser als SELF.UNK annotiert werden sollte.

Beispiel "\... \[die <u>Helblings</u> /NAM.PER..GRP\]
\[<u>uns</u> /SELF.UNK..GRP\] gegeben haben"

### 2.1.3.4. Unbekannte Erwähnung (UNK)

Aufgrund unleserlicher Schrift kann es vorkommen, dass die Erwähnung
nicht mehr zu entziffern ist, obwohl klar ist, dass es sich dabei um
eine Erwähnung handelt. Die Stelle kann dann als UNK gekennzeichnet
werden.

### 2.1.3.5. Präzisierung der Erwähnung

Im Falle von Nominalerwähnungen können wir zusätzliche Informationen
festhalten, indem wir die Erwähnungsart weiter präzisieren. Wir
versuchen dabei möglichst dieselben Klassen zu verwenden wie für
Zustände (Kapitel 4) und Deskriptoren (Kapitel 2.7.3), wobei wir noch
weitere Präzisierungen speziell zu diesem Zweck definieren.

Wenn z.B. eine Person anhand einer Verwandschaftsbeziehung erwähnt wird
("seine <u>Frau</u>"), dann beinhaltet diese Nennung zugleich
einen Zustand. Indem wir dieselben Klassennamen verwenden, vereinfachen
wir den Annotationsprozess (siehe Annotationsanleitung).

Die passenden Präzisierungen sind abhängig von der
Entitätsklassifikation und werden aus diesem Grund in den entsprechenden
Kapiteln aufgelistet (Kapitel 2.5.).

## 2.1.4. Ordinalität

### 2.1.4.1. Einzelne Entität (SGL)

Die Erwähnung betrifft eine einzelne Entität.

Beispiel: "\[<u>Heinzi Schneider</u>\]"

### 2.1.4.2. Mehrere Entitäten (GRP)

Die Erwähnung betrifft eine Gruppe von Entitäten.

Beispiel: "\[Die <u>Nachbarn</u> an der Gerbergassen wohnend\]"

Wichtig ist bei GRP, sich der Abgrenzung zu den ORG-Entitäten bewusst zu
sein. Bei GRP handelt es sich normalerweise um Erwähnungen im Plural.
Bei ORG handelt es sich um "feste" Gruppierungen mit klaren Grenzen, die
auch meist langfristig definiert sind. Bei Familien zum Beispiel handelt
es sich nicht um GRP vom Typus PER, sondern um ORGs.

### 2.1.4.3. Negierende Erwähnung (NEG)

Die Erwähnung nennt die Entitäten auf negierende Weise. Oft unspezifisch
erwähnt.

Beispiel: "\[Kein <u>Kohlestürzer</u>\] soll hier wohnen"

## 2.1.5. Entitäts-Klassifikation

Die Aufzählung aller Klassen, Basis und Optional, findet sich in Kapitel 2.2.

Eine Klasse kann durch weitere Unterklassen genauer definiert werden, im Falle
von Geopolitischen Entitäten ist eine solche sogar Pflicht.

## 2.1.6. Spezifität

### 2.1.6.1. Spezifische Entität (SPC)

Die Erwähnung bezieht sich auf eine spezifische "existierende" Entität.

Beispiel: "\[Das <u>Haus zum Wind</u>\]"

### 2.1.6.1. Unspezifische Entitäten (USPC)

Die Erwähnung bezieht sich auf keine spezifische Entität. Beispiele
wären eine undefinierte Masse von Entitäten:

Beispiel: "\[Viele <u>Leute</u>\] sagen..."

Oder die Verwendung von "man" auf unspezifische Weise:

Beispiel "Wenn \[<u>man</u>\] die Strasse Richtung Gerbergassen
geht"

## 2.1.7. Referenzen / Attribute / Listen

In BeNASch verwenden wir zur vollständigen Informationserfassung
verschachtelte Annotationen. Zudem halten wir neben den eigentlichen
Entitätserwähnungen auch weitere Informationen zu den Entitäten fest.
Wir unterscheiden hierbei zwischen Listen, Referenzen, Attributen und
Deskriptoren (Kapitel 2.9.). Attribute und Deskriptoren können nur innerhalb von
Listen, Referenzen und Attributen vorkommen.

### 2.1.7.1. Referenzen (REF)

Eine Referenz ist eine Erwähnung, die sich nicht auf dieselbe Entität
wie die darüberliegende Erwähnung bezieht.

Beispiel: "\[der <u>Schreiner</u> /REF\]"[^2]

Beispiel: "\[der <u>Schaffner</u> \[des <u>Spitals</u>
/REF\] /REF\]"

### 2.1.7.2. Attribute (ATT)

Bei einem Attribut handelt es sich um eine Erwähnung, die sich auf
dieselbe Entität bezieht wie die darüberliegende Erwähnung.

Beispiel: "\[<u>Heinzi Müller</u>, \[der <u>Schreiner</u>
/ATT\] /REF\]"

### 2.1.7.3. Listen (LST)

Listen-Elemente dienen dem Zweck, Aufzählungen von Entitäten miteinander
zu verbinden und sie einfacher in Beziehung zu setzen, z.B. mit
Attributen, die sämtliche aufgezählte Entitäten betreffen. Ein Beispiel
verdeutlicht die Nutzung:

Beispiel: "\[\[<u>Heintzi Schneider</u>\] und \[<u>Johann
Ammann</u>\], \[<u>Nachbarn</u> an \[der
<u>Eisengasse</u>\]\] /LST\]"

Eine Liste enthält Verweise auf alle Erwähnungen, die Teil von ihr sind
(im obigen Beispiel also "Heintzi Schneider" und "Johann Ammann"). Ein
Attribut oder ein Deskriptor kann zudem eine Liste beschreiben, so wie sie sonst zu einer
anderen Erwähnung gehören können.

Listen ähneln in ihrer Funktionsweise GRP-Erwähnungen, haben aber keinen
*Head*, dieser wird durch die Aufzählung der Entitäten ersetzt. List
können Erwähnungen von verschiedenen Klassifikationen enthalten.

Beispiel: "\... zinst \[\[dem Predigerkloster /ORG\] und \[<u>Johann von
Arx</u> /PER\] /LST\] ..."

Als Aufzählungen anzusehen sind Entitätenerwähnungen, welche durch
Konjunktionen (auch Kommas falls zutreffend) verbunden werden und damit
eine gemeinsame Rolle im Dokument einnehmen, z.B. als Verkäufer,
Zinsempfänger oder Ziel einer Beziehung.

#### 2.1.7.3.1. Optionale Spezialtypen

Für manche Projekte ist es praktisch, wenn neben
Konjunktivkonstruktionen weitere Listen-artige Konstruktionen als
LST-Spezialtypen klassifiziert werden können. Ein solcher Untertyp wäre
zum Beispiel LST.CONTRA, welcher bei manchen Gerichtsdokumenten zum
Einsatz kommt.

Beispiel: "\[\[<u>Heintzi Schneider</u>\] contra \[<u>Johann
Ammann</u>\], \[<u>Nachbarn</u> an \[der
<u>Eisengasse</u>\]\] /LST\], betreffend ..."

**LST.CONTRA**

Verbindung von Entitäten über "contra", "gegen" oder ähnliches.

## 2.1.8. Deskriptoren (DESC)
Text innerhalb von Entitätenerwähnungen, welche die Entität näher beschreiben, selbst aber keine Erwähnungen darstellt, wird als Deskriptor annotiert. Deskriptoren dienen in der Praxis auch dazu, Zustände und Ereignisse im Text zu verankern (Siehe die Anleitung in Kapitel 7 für Details).

### 2.1.8.1. Deskriptor identifizieren
Deskriptoren können alle Klassifizierungen nutzen, welche für Erwähnungs-Präzisierungen, Zustände und Ereignisse zulässig sind. Auch weitere beschreibende Spannen können als UNK-Typ verzeichnet werden, falls notwendig.
Deskriptoren halten sich wie Entitätenerwähnungen an die Syntax. Deskriptoren entsprechen üblicherweise [[Adjektivphrasen]](https://de.wikipedia.org/wiki/Adjektivphrase). Zum Beispiel (die DESC-Spanne hier in geschweiften Klammern):

Beispiel: "...hat \[das <u>Haus</u>, \{\[am <u>Rhein</u>\] gelegen\}\], gekauft."

Aufgrund der speziellen Eigenschaften von vormodernem Deutsch können wir mit Deskriptoren aber auch andere beschreibende Textstellen markieren. Zum Beispiel wenn bei einem Relativsatz das einleitende Pronomen fehlt:

Beispiel: "...hat \[Das <u>Haus</u>, \{\[am <u>Rhein</u>\] gelegen\}, \{zinst 5 sh. auf Martini\}\], gekauft."

Beispiel: "\[Hans Peter \{selig\}\]"


## 2.1.9. Komplizierte Fälle

### 2.1.9.1 Mehrere Personen mit nur einem genannten Nachnamen

Beispiel: "Hedwig und Bertschi Eberli"

Werden zwei Personen genannt, aber nur bei einer der Familienname
beschrieben, folgen wir den Prinzipien der textnahen Annotation.

Beispiel: "\[\[<u>Hedwig</u> /PER] und \[<u>Bertschi Eberli</u> /PER] /LST]"

Für weitere Informationen siehe [Diskussion](https://github.com/raykyn/BeNASch/issues/11)

---

[^1]: In Beispielen zeigen die eckigen Klammern eine Annotation an, eine
    Unterstreichung markiert den *head*. Etwaige weitere Annotationen im
    Beispiel werden weggelassen, wenn sie für das Beispiel nicht
    relevant sind.

[^2]: Hinter dem / steht eine allfällige Klassifizierung.

