---
title: 4. Beziehungen und Ereignisse
layout: default
nav_order: 4
---

# 4. Beziehungen und Ereignisse
Aus praktischen Gründen lohnt es sich zwar meistens zwischen Beziehungen und Ereignissen zu unterscheiden, die Grenzen sind jedoch manchmal nicht klar auszumachen. Sowohl Beziehungen wie auch Ereignisse repräsentieren Zusammenhänge zwischen Entitäten (und/oder Werten). Ereignisse stellen ein konkretes Geschehnis dar und keinen Zustand. Die Beziehung "married" würde z.B. den Zustand des Verheiratet-Seins beschreiben, während das Ereignis "marriage" spezifisch den Beginn der Heirat markiert.
In BeNASch annotieren wir Beziehungen und Ereignisse mit derselben Methode.

Wir unterscheiden zwischen zwei Komplexitätsstufen der Annotation. Ein Projekt sollte für jede Beziehungs- und Ereignis-Klasse, die verwendet wird, bestimmen, ob die einfache Annotation ausreicht, oder von der vollen Annotation Gebrauch gemacht werden sollte. 

{: .note }
Die einfache Annotation ist Teil des offiziellen BeNASch-Schemas und ihre Verwendung bedeutet keinen Bruch mit dem Schema.

## 4.1 Annotationsebene
Eine Beziehung oder ein Ereignis finden jeweils auf einer bestimmten syntaktischen Ebene statt, welche wir als Annotationsebene bezeichnen. Annotationen für die Beziehung oder das Ereignis dürfen nur auf dieser Ebene erfolgen bzw. Entitäten/Werte auf dieser Ebene verbinden. Eine Annotationsebene kann z.B. die Dokument- oder Satzebene sein, oder die Ebene innerhalb einer Erwähnung. Falls die Beziehung oder das Ereignis in einer Erwähnung stattfinden, kann die Erwähnung selbst auch ein Element der Beziehung oder des Ereignisses sein.

Beispiel: "\[\[<u>ihr</u>\] <u>Ehemann</u>\]"

| Beziehungstyp | Entität A | Entität B |
|---|---|---|
| Verheiratet | Ehemann | ihr |

Beispiel: "Es verhandelt \[\[der <u>Kinder</u>\] <u>Vogt</u>\] mit \[dem <u>Käufer</u>\]"

| Ereignistyp | Entität A | Entität B |
|---|---|---|
| Verhandlung | der Kinder Vogt | Käufer |

Die Erwähnung der "Kinder" liegt nicht auf derselben Annotationsbene wie das Ereignis, daher können die Kinder kein Element des Ereignisses sein. Die Verbindung zum Ereignis kann aber trotzdem festgehalten werden, indem gleichzeitig die Beziehung zwischen den Kindern und dem Vogt festgehalten wird.

| Beziehungstyp | Entität A | Entität B |
|---|---|---|
| Stellvertretung | Vogt | Kinder |


## 4.2. Einfache Annotation
Die einfache Annotation umfasst lediglich drei Elemente:

- Entität/Wert A
- Entität/Wert B
- Klassifikation

Manche Beziehungen sind gerichtet, zum Beispiel eine
Besitzverhältnis-Beziehung. Andere sind symmetrisch, z.B. eine
Eheleute-Beziehung. Bei gerichteten Beziehungen ist die Erwähnung A die
sogenannte *from*-Partei und die Erwähnung B die *to*-Partei. Die
Beziehung sollte so gelesen werden können "\<from\> is
\<Beziehungs-Klasse\> by/to/of \<to\>".

Diese einfache Annotation kann bereits viele Fälle abdecken, z.B. Beziehungen wie "Bertha, Hansis Frau" oder "Bertha heiratet Hansi".

## 4.3. Volle Annotation
Die volle Annotation ermöglicht die Annotation von komplexeren Konstruktionen und umfasst die folgenden Elemente:

- Textspanne
- Trigger
- Entitäten/Werte gemäss definierten Rollen
- Zusatzinformationen
- Klassifikation

Die <b>Textspanne</b> sollte das syntaktische Element umfassen, in welchem das Ereignis stattfindet, und in welchem daher auch alle anderen Elemente liegen. Diese Textspannen-Annotation ist nicht den Regeln der Entitätenannotation unterworfen und darf sich z.B. mit anderen Textspannen-Annotationen schneiden.

Beispiel: "\[Elsa hat auf das Haus 5 Gld. <u>geboten</u>\] und \[am Dienstag hat sie es <u>gekauft</u>.\]"

Beispiel: "\[\[Elsa hat auf das Haus 5 Gld. <u>geboten</u>\] und es <u>gekauft</u>.\]"

Der <b>Trigger</b> sollte den zentralen Begriff der Beziehung oder des Ereignisses markieren, wobei wir der Konsistenz wegen dazu raten den Trigger auf den linguistischen Kopf der syntaktischen Einheit, welche die Beziehung oder das Ereignis ausmacht, zu setzen. Dies ist auf Satz- oder Dokumentebene meist das Prädikat, in Erwähnungsebenen üblicherweise der <i>Head</i>. In seltenen Fällen oder bestimmten Texttypen kann es sein, dass kein Trigger auszumachen ist. In diesem Fall kann der Trigger auch weggelassen werden.

Beispiel Satzebene: "\[das Kloster hat wegen versessener Zinsen Uelis Haus <u>gefrönt</u>.\]"

Beispiel Erwähnungsebene: "\[seine <u>Frau</u>\]

{: .note }
Erwähnungspräzisierungen implizieren oft eine Beziehung oder ein Ereignis, ein Fakt, den wir uns während der Annotation zu Nutze machen können.

Jede Beziehung und jedes Ereignis definiert in seiner vollen Annotation <b>Rollen</b>, welche Entitäten oder Werten zugewiesen werden. Es definiert auch, wie oft eine Rolle jeweils vorkommen kann, und ob gewisse Rollen optional sind. Zudem existiert eine Zahl generischer Rollen, welche alle Beziehungen oder Ereignisse (optional) aufweisen.

Beispiel: "\[Hans von Oltingen mit Zustimmung Franzen Oltingers seines Vaters <u>verkauft</u> an Peter Schützen den Rebmann das Haus und den Garten für 163 fl.\]"

| Rolle | Entität/Wert |
|---|---|
| Verkäufer | Hans von Oltingen |
| Käufer | Peter Schützen |
| Gibt Zustimmung zum Verkauf | Franzen Oltingers |
| Kaufobjekt | das Haus |
| Kaufobjekt | den Garten |
| Kaufpreis | 163 fl. |

<b>Zusatzinformationen</b> werden direkt als Textspanne annotiert und können (mehrere) Entitäten oder Werte umfassen. Diese Entitäten oder Werte sollten aber nicht gleichzeitig Rollen einnehmen. Zusatzinformationen sollten auch klassifiziert werden.

Beispiel: "das Haus, \[<u>zinst</u> jährlich \{zur Weisung\} ein Brot.\]" / "zur Weisung" --> Zinsgrund

Beispiel: "\[er <u>schuldet</u> 300 fl. Kapital \{für jeden fl. 6 sh.\]\}" / "für jeden fl. 6 sh." --> Geldumrechnung

## 4.4. Unter-Beziehungen / Unter-Ereignisse
Es kann vorkommen, dass innerhalb einer Ereignisspanne (oder Beziehungsspanne) mehrere Sachverhalte beschrieben werden. Ein Beispiel für einen solchen Fall:

"\[...\] das Haus, \[<u>zinst</u> jährl. dem Spital 2 sh. zu eigen 1 brot zur wysung, dann dem Kloster zu Barfüssen 1 sh. 2 pfennig ablösbar mit 30 fl.\]"

Wir definieren in diesem Fall alle Informationen innerhalb der Spanne demselben Ereignis oder derselben Beziehung zugehörig. Aber wir unterscheiden sie trotzdem in verschiedene Unter-Ereignisse oder Unter-Beziehungen. In diesem Fall würden sich drei Unter-Ereignisse auszeichnen lassen:

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
Die wichtigste Klassifikation jedes Ereignisses und jeder Beziehung ist die <b>Ereignis- bzw. Beziehungsklasse</b>. Diese beschreibt die inhaltliche Bedeutung der Annotation. Eine Liste von vorgeschlagenen Klassen und deren Beschreibung findet sich in der Typologie (TODO: Verlinken).

Weiter sollten folgende Klassifikationen ausgezeichnet werden (in fett jeweilige default-Werte):

<b>Polarität:</b>

| Klasse | Beschreibung |
|---|---|
| <b>pos</b> | |
| neg | Verneinung des Ereignisses / der Beziehung. |

<b>Zeitform:</b>

| Klasse | Beschreibung |
|---|---|
| <b>pres</b> | Gegenwart, entspricht der "textual anchor time", d.h. auch Verben die eine Vergangenheitsform aufweisen, können ein Ereignis oder eine Beziehung im "pres" beschreiben. |
| past | Ereignis / Beziehung explizit in der Vergangenheit, auch in Bezug auf die "textual anchor time". |
| fut | Ereignis / Beziehung explizit der Zukunft. Die Unsicherheit von künftigen Ereignissen ist damit schon abgedeckt, es braucht also keine weitere Angaben zur Modalität (siehe unten). |
| unspec | Nicht klar |

<b>Modalität:</b>

| Klasse | Beschreibung |
|---|---|
| <b>ass</b> | Ereignis / Beziehung wird als Fakt beschrieben. |
| claim | Ereignis / Beziehung wird als Behauptung beschrieben. |
| rumor | Ereignis / Beziehung wird als Gerücht beschrieben. |
| hypo | Ereignis / Beziehung wird als Möglichkeit beschrieben. |
| requ | Ereignis / Beziehung wird als Befehl beschrieben. |
| prop | Ereignis / Beziehung wird als Vorschlag beschrieben. |
| desi | Ereignis / Beziehung wird als Wunsch beschrieben. |
| prom | Ereignis / Beziehung wird als Versprechen beschrieben. |
| other | Ereignis / Beziehung wird nicht als Fakt beschrieben, passt aber in keine andere Kategorie |

## 4.6. Vollständige Beispiele
TODO

[^1]: Die Beziehung ist hier in einem Deskriptor beschrieben. In diesem Fall kann auch die darüberliegende Annotation, auf die sich der Deskriptor bezieht, mit einer Rolle versehen werden.
