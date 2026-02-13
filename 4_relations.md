---
title: 4. Zustände und Ereignisse
layout: default
nav_order: 5
---

# 4. Zustände und Ereignisse
Über Zustände können wir weitere Informationen zu Entitäten im Text vermerken. Sie werden oft durch Attribute und Appositionen im Text annotiert, können aber auch im Freitext oder durch Kerne gegeben sein. Als Zustand sind Eigenschaften einer Entität zu bezeichnen, z.B. welche Verwandten sie hat oder dass die Entität verstorben ist. Ein Zustand, der ein Verhältnis zwischen mehreren Entitäten festhalt, wird auch als **Beziehung** bezeichnet.

Ereignisse hingegen vermerken Aktivitäten im Text. Diese finden sich öfter im Freitext, manchmal aber auch in Kernen, Attributen oder Appositionen. Beispiele für Ereignisse wäre zum Beispiel eine Transaktion oder ein Todesfall. 

Ereignisse und Zustände hängen eng miteinander zusammen. 
So kann z.B. ein "marriage"-Ereignis einen "married"-Zustand ab diesem Punkt implizieren, und ein "divorce"-Ereignis das Ende desselben Zustands.
Wir annotieren aber auch in diesem Fall textnah, d.h. nur das im Text genannte Ereignis, nicht aber der implizierte Zustand wird vermerkt.

## 4.1. Annotationsebene
Eine Beziehung oder ein Ereignis finden jeweils auf einer bestimmten syntaktischen Ebene statt, welche wir als Annotationsebene bezeichnen. Annotationen für den Zustand oder das Ereignis dürfen nur auf dieser Ebene erfolgen bzw. Entitäten/Werte auf dieser Ebene verbinden. Eine Annotationsebene kann z.B. die Dokument- oder Satzebene sein, oder die Ebene innerhalb einer Erwähnung. Falls der Zustand oder das Ereignis in einer Erwähnung stattfinden, kann die Erwähnung selbst auch ein Element der Beziehung oder des Ereignisses sein.

Beispiel: "\[\[<u>ihr</u>\] <u>Ehemann</u>\]"

| Zustand | Entität A | Entität B |
|---|---|---|
| Verheiratet | Ehemann | ihr |

Beispiel: "Es verhandelt \[\[der <u>Kinder</u>\] <u>Vogt</u>\] mit \[dem <u>Käufer</u>\]"

| Ereignis | Entität A | Entität B |
|---|---|---|
| Verhandlung | der Kinder Vogt | Käufer |

Die Erwähnung der "Kinder" liegt nicht auf derselben Annotationsbene wie das Ereignis, daher können die Kinder kein Element des Ereignisses sein. Die Verbindung zum Ereignis kann aber trotzdem festgehalten werden, indem gleichzeitig der Zustand (die Beziehung) zwischen den Kindern und dem Vogt festgehalten wird.

| Zustand | Entität A | Entität B |
|---|---|---|
| Stellvertretung | Vogt | Kinder |

## 4.2. Definition eines Zustands / eines Ereignisses
Da es unmöglich ist, alle Typen von Zuständen und Ereignissen zu vermerken, sollte ein Projekt sich auf eine Reihe von Zuständen und Ereignissen festlegen, und diese konsequent annotieren.
Wir empfehlen dazu die Basis-Typologie (notwendig um als BeNASch-konform zu gelten) plus Zustände/Ereignisse nach Forschungsschwerpunkt.
Noch in Planung ist, beispielhafte Module für bestimmte Arten von Korpora (z.B. Grundbuchdokumente) zur Verfügung zu stellen.
Wir möchten Projekte, die BeNASch verwenden, bitten ihre Auswahl an Zuständen/Ereignissen mit der Community im Github-Forum zu teilen.

Wurde festgelegt, welche Zustände und Ereignisse annotiert werden sollen, muss festgelegt werden _wie_ sie annotiert werden.
Folgende Elemente können annotiert werden:

- Textspannen 
- Trigger
- Rollen
- Zusatzinformationen

Zwingend notwendig ist die Annotation im Text von wenigstens einem Trigger, einer Rolle oder der Textspanne.

Für einfache Beziehungen zum Beispiel ist oft die Definition von zwei Rollen ausreichend:

Zustand: Verheiratet
Rolle 1: Ehepartner:in 1 (PER)
Rolle 2: Ehepartner:in 2 (PER)

Beispiel: "des Schmieds eheliche Frau"

Für komplexe Zustände oder Ereignisse ist meist die Definition eines Trigger-Elements, weiterer Rollen und etwaiger Zusatzinformationen hilfreich:

Zustand: Rentenverhältnis
Trigger: muss annotiert werden
Rolle 1: Rentenzahler (PER / ORG)
Rolle 2: Rentenempfänger (PER / ORG)
Rolle 3: Belastete Liegenschaft (LOC)
Rolle 4: Zahlungsintervall (TIME.REC)
Rolle 5: Zahlungsbetrag (MONEY)
Zusatz: Zahlungsgrund (z.B. "von eigenschaft")
Zusatz: Information zu Ablösbarkeit (z.B. "ist ablösbar")

Beispiel: "er zinst von dem Haus zum Bären von eig. jährlich dem Kloster zu den Barfüssen 3 sh."

Die Annotation von Triggern ist für das Verständnis von Zuständen und Ereignissen nicht notwendig, kann aber aus linguistischem Interesse sinnvoll sein, und ist in der Annotationspraxis hilfreich. 
Zudem können Trigger von maschinellen System zur besseren Annotation von Zuständen und Ereignissen genutzt werden.

Manche Zustände oder Ereignisse könnten auch völlig von Entitäten unabhängig sein, oder eine nähere Annotation der Rollen ist nicht im Forschungsinteresse des Projekts.
In diesem Fall bietet sich entweder die Annotation des Triggers oder der Textspanne am ehesten an:

Ereignis: Wetterereignis
Textspanne: muss annotiert werden.

Beispiel: "heute stürmte es stark."

## 4.3. Beschreibung der Elemente

### 4.3.1. Textspanne
Die Textspanne sollte das syntaktische Element umfassen, in welchem das Ereignis/der Zustand stattfindet, und in welchem daher auch alle anderen Elemente liegen. Diese Textspannen-Annotation ist nicht den Regeln der Entitätenannotation unterworfen und darf sich z.B. mit anderen Textspannen-Annotationen schneiden.

Beispiel: "\[Elsa hat auf das Haus 5 Gld. <u>geboten</u>\] und \[am Dienstag hat sie es <u>gekauft</u>.\]"

Beispiel: "\[\[Elsa hat auf das Haus 5 Gld. <u>geboten</u>\] und es <u>gekauft</u>.\]"

### 4.3.2. Trigger
Der <b>Trigger</b> sollte den zentralen Begriff des Zustands oder des Ereignisses markieren, wobei wir der Konsistenz wegen dazu raten den Trigger auf den linguistischen Kopf der syntaktischen Einheit, welche den Zustand oder das Ereignis ausmacht, zu setzen. Dies ist auf Satz- oder Dokumentebene meist das Prädikat, in Erwähnungsebenen üblicherweise der Kern. In seltenen Fällen oder bestimmten Texttypen kann es sein, dass kein Trigger auszumachen ist. In diesem Fall kann der Trigger auch weggelassen werden.

Beispiel Satzebene: "\[das Kloster hat wegen versessener Zinsen Uelis Haus <u>gefrönt</u>.\]"

Beispiel Erwähnungsebene: "\[seine <u>Frau</u>\]

{: .note}
Erwähnungspräzisierungen implizieren oft eine Beziehung oder ein Ereignis, ein Fakt, den wir uns während der Annotation zu Nutze machen können.

### 4.3.3. Rollen
Rollen werden Entitäten, Werten oder anderen Ereignissen zugewiesen. 
Grundsätzlich wird angenommen, dass das Vorkommen einer Rolle nicht notwendig ist, damit ein Zustand oder Ereignis vermerkt wird.
Kommt sie aber vor und ist in der Projektdefinition vermerkt, muss sie annotiert werden.
Es wird auch immer angenommen, dass eine Rolle mehrmals vorkommen kann und dann mehrmals annotiert wird.
In der Projektdefinition können diese Spezifikationen aber weiter präzisiert werden, z.B. kann für einen "Verheiratet"-Zustand festgelegt werden, dass nur genau zwei PER-Entitäten an der Beziehung teilnehmen.
Solche Präzisierung können nützlich sein um Fehler – insbesondere in maschinell generierten – Datensätzen festzustellen.

Beispiel: "\[Hans von Oltingen mit Zustimmung Franzen Oltingers seines Vaters <u>verkauft</u> an Peter Schützen den Rebmann das Haus und den Garten für 163 fl.\]"

| Rolle | Entität/Wert |
|---|---|
| Verkäufer | Hans von Oltingen |
| Käufer | Peter Schützen |
| Gibt Zustimmung zum Verkauf | Franzen Oltingers |
| Kaufobjekt | das Haus |
| Kaufobjekt | den Garten |
| Kaufpreis | 163 fl. |

### 4.3.4. Zusatzinformationen
Zusatzinformationen werden direkt als Textspannen annotiert und können (mehrere) Entitäten oder Werte umfassen. Diese Entitäten oder Werte sollten aber nicht gleichzeitig Rollen einnehmen. Zusatzinformationen sollten auch klassifiziert werden.

Beispiel: "das Haus, \[<u>zinst</u> jährlich \{zur Weisung\} ein Brot.\]" / "zur Weisung" --> Zinsgrund

Beispiel: "\[er <u>schuldet</u> 300 fl. Kapital \{für jeden fl. 6 sh.\]\}" / "für jeden fl. 6 sh." --> Geldumrechnung

## 4.4. Unter-Zustand / Unter-Ereignisse
Es kann vorkommen, dass mehrere Ereignisse oder Zustände an demselben Trigger hängen. Ein Beispiel für einen solchen Fall:

"\[...\] das Haus, \[<u>zinst</u> jährl. dem Spital 2 sh. zu eigen 1 brot zur wysung, dann dem Kloster zu Barfüssen 1 sh. 2 pfennig ablösbar mit 30 fl.\]"

Wir definieren in diesem Fall alle Informationen innerhalb der Spanne demselben Ereignis oder derselben Beziehung zugehörig. Aber wir unterscheiden sie trotzdem in verschiedene Unter-Ereignisse oder Unter-Zustände. In diesem Fall würden sich drei Unter-Ereignisse auszeichnen lassen:

Für alle Unter-Ereignisse:

| Rolle/Trigger/Zusatzinfo | Entität/Wert/Spanne |
|---|---|
| Trigger | "zinst" |
| Objekt | Haus[^1] |
| Intervall | jährl. |

Unter-Ereignis 1.1:

| Rolle/Trigger/Zusatzinfo | Entität/Wert/Spanne |
|---|---|
| Empfänger | Spital |
| Betrag | 2 sh. |
| Zinsgrund | "zu eigen" |

Unter-Ereignis 1.2:

| Rolle/Trigger/Zusatzinfo | Entität/Wert/Spanne |
|---|---|
| Empfänger | Spital |
| Betrag | 1 brot |
| Zinsgrund | "zur wysung" |

Unter-Ereignis 2:

| Rolle/Trigger/Zusatzinfo | Entität/Wert/Spanne |
|---|---|
| Empfänger | Kloster zu Barfüssen |
| Betrag | 1 sh. 2 pfennig |
| Betrag zur Ablösung | 30 fl. |

## 4.5. Klassifikation
Die wichtigste Klassifikation jedes Ereignisses und jeder Beziehung ist die <b>Ereignis- bzw. Zustandsklasse</b>. Diese beschreibt die inhaltliche Bedeutung der Annotation. Eine Liste von vorgeschlagenen Klassen und deren Beschreibung findet sich in der Typologie (TODO: Verlinken).

Weiter sollten folgende Klassifikationen ausgezeichnet werden (in fett jeweilige default-Werte):

<b>Polarität:</b>

| Klasse | Beschreibung |
|---|---|
| <b>pos</b> | |
| neg | Verneinung des Ereignisses / des Zustands. |

<b>Zeitform:</b>

| Klasse | Beschreibung |
|---|---|
| <b>pres</b> | Gegenwart, entspricht der "textual anchor time", d.h. auch Verben die eine Vergangenheitsform aufweisen, können ein Ereignis oder einen Zustand im "pres" beschreiben. |
| past | Ereignis / Zustand explizit in der Vergangenheit, auch in Bezug auf die "textual anchor time". |
| fut | Ereignis / Zustand explizit der Zukunft. Die Unsicherheit von künftigen Ereignissen oder Zuständen ist damit schon abgedeckt, es braucht also keine weitere Angaben zur Modalität (siehe unten). |
| unspec | Nicht klar |

<b>Modalität:</b>

| Klasse | Beschreibung |
|---|---|
| <b>ass</b> | Ereignis / Zustand wird als Fakt beschrieben. |
| claim | Ereignis / Zustand wird als Behauptung beschrieben. |
| rumor | Ereignis / Zustand wird als Gerücht beschrieben. |
| hypo | Ereignis / Zustand wird als Möglichkeit beschrieben. |
| requ | Ereignis / Zustand wird als Befehl beschrieben. |
| prop | Ereignis / Zustand wird als Vorschlag beschrieben. |
| desi | Ereignis / Zustand wird als Wunsch beschrieben. |
| prom | Ereignis / Zustand wird als Versprechen beschrieben. |
| other | Ereignis / Zustand wird nicht als Fakt beschrieben, passt aber in keine andere Kategorie |

## 4.6. Vollständige Beispiele
_coming soon_

[^1]: Die Beziehung ist hier in einem Attribut beschrieben. In diesem Fall kann auch die darüberliegende Annotation, auf die sich der Attribut bezieht, mit einer Rolle versehen werden.
