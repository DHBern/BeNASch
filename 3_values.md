---
title: 3. Werte
layout: default
nav_order: 4
---

# 3. Werte
Werte folgen nicht denselben Regeln wie Entitätserwähnungen. Sie können
Textspannen auszeichnen, die in irgendeiner Hinsicht für die Forschung
relevant sein könnten und oft sind sie auch relevant als
Anknüpfungspunkt für Zustände und Ereignissen, wobei sie dadurch auch
mit Entitätserwähnungen verknüpft werden können.

Werte haben keine Kern-Elemente.

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
verändern, diese Art von verschachtelter Annotation wird zwar empfohlen, ist derzeit aber optional:

Beispiel mit TIME_FIN: "\[\[5 Tage /TIME_FIN\] vor St. Martins Tag
/DATE\]"

## 3.2. Optionale Werte

<Platzhalter>
