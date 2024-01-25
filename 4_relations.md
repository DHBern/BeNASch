---
title: 4. Beziehungen
layout: default
nav_order: 4
---

# 4. Beziehungen

Eine Beziehung (*relation*) definiert das Verhältnis zwischen zwei
Entitäten. In BeNASch versuchen wir, entsprechend dem Ziel der
Vollständigkeit, alle Verbindungen zwischen Entitäten im Text
abzudecken. Dabei werden jedoch standardmässig nur Beziehungen vermerkt,
die im Text explizit gegeben sind. Falls ein Projekt auch Beziehungen
vermerken möchte, die mehr Interpretation seitens des Interpretierenden
benötigen, verwenden Sie spezielle Marker wie in Kapitel 4.4.
beschrieben.

Eine Beziehung besteht aus drei Elementen:

-   Erwähnung A
-   Erwähnung B
-   Klassifizierung

Bemerke, dass Beziehungen im Schema Erwähnungen, nicht Entitäten,
verbinden. Erst in einem nächsten Schritt können Entitäten aus ihren
Erwähnungen aggregiert werden.

Manche Beziehungen sind gerichtet, zum Beispiel eine
Besitzverhältnis-Beziehung. Andere sind symmetrisch, z.B. eine
Eheleute-Beziehung. Bei gerichteten Beziehungen ist die Erwähnung A die
sogenannte *from*-Partei und die Erwähnung B die *to*-Partei. Die
Beziehung sollte so gelesen werden können "\<from\> is
\<Beziehungs-Klasse\> by/to/of \<to\>".

## 4.1. Koreferenzen

Koreferenzen stellen eine besondere Art von Beziehungen dar. Sie
verbinden zwei Erwähnungen derselben Entität miteinander.

## 4.2. Mögliche Beziehungen nach Klassifizierung

In den folgenden Tabellen sind sortiert nach der Klassifizierung von A.
Manche Beziehungs-Klassen sind deshalb mehrmals vermerkt. In der
Beschreibung ist auch vermerkt, welche Klassifizierungen für B in Frage
kommen. Dabei ist zu bemerken, dass GPEs immer entsprechend ihrer
Unterklassifizierung in Frage kommen, z.B. kann eine GPE_LOC eine LOC in
einer Beziehung ersetzen, die eine LOC erfordert.

Eine andere Darstellung der Beziehungen macht hier vielleicht später
mehr Sinn.

### 4.2.1. PER

| Beziehungs-Klasse | Kürzel | Beschreibung |
|---|---|---|
| Verortung | loc | A kommt von, befindet sich in oder wohnt in B. Diese Beziehung erfasst grob die Beziehung zwischen einer Person und einem Ort. B muss eine LOC sein. <br> Beispiel: Beispiel: "\[<u>Heinzi</u> von \[<u>Dornach</u>\]\]" <br> Erwähnung A: "Heinzi" (PER) <br> Erwähnung B: "Dornach" (GPE_LOC) |
| Organisationszugehörigkeit | org-aff | A ist Mitglied in/Teil von/zugehörig in B. Dies beschreibt in erster Linie eine passive Zugehörigkeit zu einer Organisation. B muss eine ORG sein. <br> Beispiel: "\[<u>Heinzi</u> \[<u>Burger</u> zu \[<u>Basel</u>\]\]\]" <br> Erwähnung A: "Burger" (PER) <br> Erwähnung B: "Basel" (GPE_ORG) |
| Herkunft | origin | A stammt ursprünglich aus B. Eine Präzisierung von *loc*. B muss eine LOC sein. <br> Beispiel: "\[<u>Heinzi</u>, aus dem \[<u>Thurgau</u>\] stammend]" <br> Erwähnung A: "Heinzi" (PER) <br> Erwähnung B: "Thurgau" (GPE_LOC) |
| Besitztum | owner | A gehört B. B muss eine LOC (üblicherweise LOC_FAC) oder PER (Leibeigenschaft, Sklaverei) sein. |
| Personenbeziehung | rel | A ist ein Freund von/Familie von/Arbeitskollege von B. Eine weit gefasste Beziehung, die häufig präzisiert wird. B muss eine PER sein. |
| Familiäre Beziehung | fam | A ist ein Familienmitglied von B. Eine Präzisierung von *rel*. B muss eine PER sein. |

### 4.2.2. ORG

| Beziehungs-Klasse | Kürzel | Beschreibung |
|---|---|---|
| Verortung | loc | A hat seine Basis/ist ansässig in B. Diese Beziehung erfasst grob die Beziehung zwischen einer Organisation und einem Ort. B muss eine LOC sein. |

### 4.2.3. LOC

| Beziehungs-Klasse | Kürzel | Beschreibung |
|---|---|---|
| Verortung | loc | A liegt nahe/in/um B. Diese Beziehung erfasst grob die topologische Beziehung zwischen zwei Orten. B muss eine LOC sein. |
| Teil von | part-of | A ist ein Teil von B. B muss eine LOC sein. Diese Beziehung sollte nicht verwendet werden, um zu beschreiben, dass z.B. ein Haus in einer Stadt liegt, das wird per *loc* beschrieben. Es wäre aber z.B. angebracht, um zu beschreiben, dass ein bestimmtes Gebäude Teil eines Hofes ist. |

Als Erwähnung B kann LOC auch noch in folgenden Beziehungen auftreten:
*owner*

## 4.3. Optionale Beziehungen

## 4.4. Nicht-Explizite Beziehungen
TODO
