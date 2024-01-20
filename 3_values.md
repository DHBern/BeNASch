---
title: Werte
layout: default
nav_order: 4
---

# 3. Werte

Werte folgen nicht denselben Regeln wie Entitätserwähnungen. Sie können
Textspannen auszeichnen, die in irgendeiner Hinsicht für die Forschung
relevant sein könnten und oft sind sie auch relevant als
Anknüpfungspunkt für Beziehungen und Ereignissen, wobei sie dadurch auch
mit Entitätserwähnungen verknüpft werden können.

Werte haben keine *head*-Elemente.

Dieses Schema sieht keine Vorgaben zur Normalisierung der annotierten
Werte vor.

## 3.1. Basis-Werte

### 3.1.1. Geldwerte und Äquivalente (MONEY)

Die MONEY-Annotation umfasst Zahlungsmittel in verschiedenen Formen.
Wichtig dabei ist, dass die annotierte Textspan im Kontext eines
Zahlungsmittels vorkommt. Abgaben werden z.B. oft in Naturalien gegeben,
diese werden auch mit MONEY annotiert in diesem Fall.

Beispiel (nur MONEY annotiert): "\... zinst von eigenschaft zu S. Claren
\[8 sh.\] \[2 ring brot\] ze wysung und \[5 sh.\] erschatz"

### 3.1.2. Zeiteinheiten (TIME)

Zeiteinheiten müssen weiter präzisiert werden:

#### 3.1.2.1. Finite Zeiteinheiten (FIN)

Beispiel: "in \[5 Tagen\]"

#### 3.1.2.2. Sich wiederholende Zeitangabe (REC)

Beispiel: "\... zinset \[jährl\] von eigenschaft ..."

### 3.1.3. Datumsangaben (DATE)[^4]

Beispiel: "\[an St. Martins Tag\]"

Datumsangaben können TIME_FIN-Werte enthalten, welche den Datumswert
verändern:

Beispiel mit TIME_FIN: "\[\[5 Tage /TIME_FIN\] vor St. Martins Tag
/DATE_FIN\]"

Sie können auch durch TIME_REC als sich wiederholend gekennzeichnet
werden.

Beispiel mit TIME_FIN + TIME_REC: "\[\[jährl.\] \[5 Tage\] vor St.
Martins Tag\]

## 3.2. Optionale Werte

### 3.2.1 Zinsen, regelmässige Abgaben (TAX)

Dieses System haben wir insbesondere für Grundbuchquellen entworfen, um
die Zinsverhältnisse festzuhalten. Erstens sei erwähnt, dass
Zinsverhältnisse als Teil der Beschreibung einer FAC-Entität (oder LOC,
falls FAC nicht benutzt wird) gelten.

Beispiel: "Eine Behausung an der Gerbergass, \[ gibt jährl. von
Eigenschaft wegen dem Spital 5ß TAX\]."

Informationen, die wir hier annotieren sind die Frequenz der Abgabe
("jährlich",FREQUENCY), die Begründung der Abgabe ("von Eigenschaft
wegen", CAUSE), die begünstigte Partei ("dem <u>Spital</u>",
BENEFICIARY) und die Menge der Abgabe ("5ß", AMOUNT). Zudem könnte hier
auch noch das Datum der Abgabe verzeichnet sein, z.B. als "zu
Pfingsten", was dann mit DATE annotiert würde. Bei den oben erwähnten
Werten wie "CAUSE" handelt es sich um Werte, die TAX genauer
beschreiben, und nicht unabhängig von TAX verwendet werden können.

Eine TAX-Annotation stellt üblicherweise sowohl eine Beschreibung der
betroffenen Entität wie auch eine Beziehung zur anderen Partei dar.
Werden Abgaben an mehrere Entitäten geliefert, sind mehrere
TAX-Annotationen zu tätigen. Aus diesem Grund ist es auch möglich
mehrere Werte demselben Wert, z.B. mehrere CAUSE, demselben TAX-Wert
zuzuweisen, aber nie mehrere BENEFICIARY. In der Annotationsanleitung
geben wir Tipps, wie dies relativ einfach zu bewerkstelligen ist
innerhalb des Annotationsprogramm und die geteilten Informationen nicht
mehrfach annotiert werden müssen.

Beispiel: "\...gibt jährl. von der Eigenschaft wegen dem Spital 5ß, dem
Gottshaus St. Leonhard 2ß 6ȡ und der Carthaus 5ß Bodenzins"

Dieses Beispiel sollte in insgesamt drei TAX-Werten resultieren:

| FREQUENCY | CAUSE | BENEFICIARY | AMOUNT | DATE |
|---|---|---|---|---|
| jährl. | von der Eigenschaft wegen | dem Spital | 5ß | N/A |
| jährl. | von der Eigenschaft wegen | Gottshaus S. Leonhard | 2ß 6ȡ | N/A |
| jährl. | von der Eigenschaft wegen | der Carthaus | 5ß | N/A |