---
title: 2.2. Entitäten-Typologie
layout: default
nav_order: 2
parent: 2. Entitäten
---

# 2.2. Entitäten-Typologie

## 2.2.1. Basis-Typologie zur Entitätsklassifikation

Als Basis-Klassen definieren wir solche Kategorien, welche für alle oder zumindest die meisten Projekte von Interesse sein sollten, und daher immer annotiert werden sollten, wenn das volle Schema verwendet wird.

Durch Unterklassen können die Klassen präziser definiert werden.

### 2.2.1.1. Übersicht (alphabetisch)

-   GPE (Geopolitische Entitäten)
    -   GPE (im Kontext nicht unterscheidbar)
    -   LOC (im Kontext eines Ortes genannt)
    -   ORG (im Kontext einer handelnden Entität genannt)
    -   PER (Erwähnung der Bevölkerung des Gebiets)
-   LOC (Orte)
-   ORG (Organisationen)
-   PER (Personen)

### 2.2.1.2. Personen (PER)
Wir annotieren Erwähnungen von einer oder mehrerer Personen mit der PER-Abkürzung. Bei mehreren Personen ist die Unterscheidung zu beachten, ab wann es sich nicht mehr um eine Gruppe von Personen handelt, die erwähnt wird, sondern um eine Organisation im Sinne einer ORG. Oft kann dies über die Ordinalität unterschieden werden.

Beispiel PER+GRP: "\[Die <u>Zimmerleute</u> des Spitals\]"

Beispiel ORG: "\[Die <u>Gesellschaft</u> der Schaffner des
Spitals\]"

Ein wichtiger Spezialfall ist jedoch zu beachten, wenn eine Personengruppe semantisch für die Organisation selbst steht. Ein häufiger Fall aus dem *Historischen Grundbuch der Stadt Basel* wäre z.B. die Erwähnung von Klöstern (also Organisationen) als "Die <u>Frauen</u> von Klingenthal" oder "den <u>Herren</u> zu St. Peter". Decken sich diese Erwähnungen sinngemäss mit der Erwähnung der Klöster, werden sie als Organisationen, nicht als Personengruppen, erfasst.[^1]

Dazu kommt noch die Unterscheidung von GPE.PER-Erwähnungen, welche dann Vorrang haben, wenn Personen als Angehörige einer GPE genannt werden.

Beispiel GPE.PER: "\[Die <u>Berner</u>\] gingen..."

### 2.2.1.3. Orte (LOC)
Ein Ort wird als eine Entität definiert, zu, durch oder an welche man
gehen kann. Dazu zählen natürliche, fassbare, Orte wie Flüsse oder
Berge, aber auch menschengemachte Strukturen wie Häuser, Strassen und
Brücken, sowie nicht fassbare Konzepte wie geographische Regionen, solange sie
nicht gleichzeitig politische Entitäten sind.

In Kapitel 2.2.2. finden sich Richtlinien für präzisere Klassifizierungen
von Orten, wie z.B. ein separater FAC-Tag für menschengemachte
Strukturen, sollte ein Projekt diese Unterscheidung wünschen.

### 2.2.1.4. Organisationen (ORG)
Organisationen unterscheiden sich von Gruppen, indem sie meist einen
Eigennamen besitzen und langfristige, etablierte Entitäten darstellen.
Im Gegensatz zu modernen Annotationsschemata können wir hierbei keine
Definition erklären, welche sich auf den "offiziellen" Status einer
Gruppierung bezieht. Insofern würden wir sagen, dass es sich dabei um
eine zu ihrer Zeit anerkannte Organisation handeln sollte.

In Kapitel 2.2.2. werden Richtlinien für genauere Kategorisierungen von
Organisationen genannt, welche für gewisse Projekte wünschenswert sein
könnten, z.B. REL für Religiöse Organisationen wie Klöster oder Stifte.

Organisationen können leicht mit PER.GRP verwechselt werden. ORG ist
dann angebracht, wenn sich die Erwähnung deutlich auf eine Organisation
als ganzes bezieht. So sollte "einige Augustiner" nicht als ORG
annotiert werden, sondern als PER.GRP, aber "zinst den Augustinern"
hingegen schon.

Wichtig ist auch zu bemerken, dass gewisse Orte eng mit Organisationen
verbunden sein können. So existiert ein Kloster meist sowohl als
Organisation (der Orden) wie auch als Ort (das Gebäude). Diese
Erwähnungen sind jeweils entsprechend ihres Kontexts zu annotieren.

### 2.2.1.5. Geopolitische Entitäten (GPE)
Geopolitische Entitäten unterscheiden sich von anderen Entitäten in der
Hinsicht, dass dieselbe Entität sowohl in ihrer Rolle als Ort, als
Organisation oder auch als Personengruppe referenziert werden kann. Wir
verwenden in jedem Kontext die Annotation *GPE*, aber versehen diese mit
einem entsprechenden Subtyp. Dieses Problem wird in den ACE-Guidelines
genauer besprochen, wir fassen es hier aber nochmal zusammen.

#### 2.2.1.5.1. GPE
In manchen Fällen wird die GPE direkt referenziert. In diesem Fall
verwenden wir GPE.GPE als Annotation.

Beispiel: "Es unterschreiben \[die <u>Orte</u> \[<u>Basel</u>\], \[<u>Bern</u>\], \[<u>Zürich</u>\]\]"

#### 2.2.1.5.2. LOC
Wird die GPE im Sinne einer LOC genannt, verwenden wir GPE.LOC.

Beispiel: "\[<u>Ulrich</u> \[der <u>Schneider</u>\] gesessen zu \[<u>Neuenburg</u>\]\]"

Wir verwenden in diesem Fall die Subtypen, welche auch für LOC-Entitäten
gelten.

#### 2.2.1.5.3. ORG
Wird die GPE im Sinne einer ORG genannt, verwenden wir GPE.ORG.

Beispiel: "\[<u>Bürger</u> zu \[<u>Basel</u>\]\]

Wir verwenden in diesem Fall die Subtypen, welche auch für ORG-Entitäten gelten.

#### 2.2.1.5.4. PER
Wird die Bevölkerung einer Stadt referenziert, verwenden wir GPE.PER.

Beispiel: "\[Die <u>Berner</u>\]"

## 2.2.2. Optionale Entitäts-Klassen

### 2.2.2.1. LOC-Subtypen

#### 2.2.2.1.1. Menschengemachte Strukturen (FAC)
Mit FAC werden Orte annotiert, die von Menschen geschaffen wurden. Das
schliesst sowohl Gebäude als auch Strassen und Plätze ein.

Alle ORG-Subtypen können wiederum als Unterkategorien von FAC betrachtet werden, und verwendet werden um die jeweiligen Organisation-Gebäude zu annotieren (z.B. wäre ein Kloster im LOC-Sinne ein LOC_FAC_REL).

Beispiel: "\[Die <u>Behausung</u> in \[der <u>S. Alban Vorstatt</u>\]\]"

#### 2.2.2.1.2. Wasserkörper (WAT)

#### 2.2.2.1.3. Natürliche Region (GEO)
Natürliche Regionen sind definiert durch geologische oder ökologische
Eigenheiten. Dazu zählen z.B. Berge, Gebirge, aber auch Wälder.

#### 2.2.2.1.4. Künstliche Region (REG)
Künstliche Regionen definieren sich nicht primär durch geologische oder
ökologische Eigenheiten, stellen aber auch keine geopolitischen
Entitäten dar. Denkbar wären hier z.B. "das Zürichgau".

#### 2.2.2.1.5. Himmelskörper (ASTR)
Mit ASTR werden Erwähnungen von Himmelskörpern gekennzeichnet. "Die
Sonne", "Der Mond".

#### 2.2.2.1.6. Grenze (BOR)
Mit BOR werden Orte gekennzeichnet, die Grenzen zwischen anderen Orten
darstellen, insbesondere zwischen GPEs.

### 2.2.2.2. ORG-Subtypen

#### 2.2.2.2.1. Regierungsorganisationen (GOV)
Mit GOV werden Erwähnungen annotiert, die nicht Regierungen als ganzes
betreffen (dazu verwenden wir GPE_ORG), sondern nur Teile der Regierung, selbst
wenn diese eine führende Position innehaben.

Beispiel: "\[Mr. <u>Lienhart Bientz</u> \[der <u>Rebman</u>\], \[des <u>Rats</u> /ORG_GOV\]\]"

#### 2.2.2.2.2. Religiöse Organisationen (REL)
Unter REL fallen Organisationen wie Stifte und Klöster.

Beispiel: "\... zinst von eigenschaft zu \[<u>S. Claren</u>\]"

#### 2.2.2.2.3. Zünfte, Berufsverbände (OCC)
Mit OCC werden Erwähnungen, die auf Zünfte und Berufsverbände verweisen,
annotiert.

#### 2.2.2.2.4. Familien (FAM)

### 2.2.2.3. PER-Subtypen
Für Personen existieren derzeit keine Subtypen.

## 2.2.3. Kern-Klassen
Mit diesen Klassen werden die Kerne der Erwähnungen kategorisiert.
Diese Liste ist nicht abschliessend und kann bei Bedarf für jedes Projekt erweitert werden, in den Projektspezifikationen ist jedoch festzuhalten, unter welche hier gelistete Klasse fällt, sofern möglich.

Kern-Klassen für PER-Erwähnungen:

| Klasse | Beschreibung | Beispiel |
| ------------ | ------------- | ------------- |
| Eigenname (*nam*)         | Kern ist ein Eigenname.   | Schneider **Hans Schmid** |
| Pronomen (*pro*)          | Kern ist ein Pronomen.    | **er** |
| Selbstreferenz (*self*)    | Kern ist ein Pronomen, durch welches sich der oder die Autor*in selbst referenziert. Unterklasse von Pronomen.   | **wir** |
| Beziehung (*rel*) | Ein catch-all für zwischenmenschliche Beziehungen verschiedener Art. Eine Präzisierung durch eine der im folgenden genannten Unterklassen empfiehlt sich.   | die **Nachbarn** an der Eisengasse |
| Verwandschaftsbeziehung (*fam*) | Kern beschreibt die Person anhand einer Verwandschaftsbeziehung. Je nach Projektinteresse empfiehlt sich eine feinere Unterscheidung. Unterklasse von Beziehung.   | sein **Vater** |
| Funktion (*func*) | Ein catch-all für Berufe, Ämter und ähnliches. Eine Präzisierung durch eine der im folgenden genannten Unterklassen empfiehlt sich.   | der **Schmied** |
| Beruf (*occ*) | Der Kern beschreibt eine berufliche Tätigkeit. Unterklasse von Funktion.   | der **Schneider** |
| Titel (*title*) | Der Kern beschreibt einen Titel. Unterklasse von Funktion.   | der **Herzog** von Österreich |
| Vertretung (*repr*) | Der Kern beschreibt eine Repräsentation einer anderen Entität. Unterklasse von Funktion.   | der **Vogt** der Kinder |
| Organisations-Affiliation (*org-aff*) | Der Kern beschreibt eine Zugehörigkeit zu einer Organisation oder GPE.ORG .   | **Bürger** zu Basel |
| Ortsbezug (*loc*) | Der Kern wird beschrieben durch einen Ort (LOC oder GPE). | der **Dornacher** |
| Besitzerverhältnis (*owner*) | Der Kern beschreibt den Besitz von etwas. | der **Inhaber** des Wirtshauses |

Kern-Klassen für ORG-Erwähnungen (und GPE.ORG):

| Klasse | Beschreibung | Beispiel |
| ------------ | ------------- | ------------- |
| Eigenname (*nam*)         | Kern ist ein Eigenname.   | das **Steinenkloster** |
| Pronomen (*pro*)          | Kern ist ein Pronomen.    | **jene** |
| Selbstreferenz (*self*)    | Kern ist ein Pronomen, durch welches sich der oder die Autor*in selbst referenziert. Unterklasse von Pronomen.   | **wir** |
| Typus (*type*) | Ein catch-all für Kerne, die die Art der Organisation wiedergeben. | das **Kloster** in der Steinenvorstadt |

Kern-Klassen für LOC-Erwähnungen (und GPE.LOC):

| Klasse | Beschreibung | Beispiel |
| ------------ | ------------- | ------------- |
| Eigenname (*nam*)         | Kern ist ein Eigenname.   | der **Steinenhügel** |
| Pronomen (*pro*)          | Kern ist ein Pronomen. oder ein ortsbezogenes Adverb.    | **dort** |
| Selbstreferenz (*self*)    | Kern verweist auf einen Ort, der nach Leseart dem gegenwärtigen Ort entspricht. Unterklasse von Pronomen.   | **hier** |
| Typus (*type*) | Ein catch-all für Kerne, die die Art der Ort wiedergeben. | die **Strasse** vor dem Stadttor |

## 2.2.4. Attributs-Klassen
Mit diesen Klassen werden Attribute kategorisiert. Die Klassen beschreiben üblicherweise die Information, welche das Attribut über die Entität enthält. Es gibt keine exklusiven Attributs-Klassen. Attributen können dieselben Klassen wie Kerne, aber auch Klassen von Zuständen und Ereignissen erhalten. Siehe Kapitel 4 für Zustände und Ereignisse.

Beispiel einer Kern-Klasse als Attribut:

| Hans, **der als Schneider arbeitet** | occ |

Beispiel eines Zustands *arbeitet_für* als Attribut:

| Hans, **der als Schneider für den Herzog arbeitet** |


---

[^1]: [[Diskussion: Personengruppen, die ORGs repräsentieren]](https://github.com/raykyn/BeNASch/issues/2)