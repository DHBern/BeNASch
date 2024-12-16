---
title: 2.2. Entitäten-Typologie
layout: default
nav_order: 2
parent: 2. Entitäten
---

# 2.2. Entitäten-Typologie

## 2.2.1. Basis-Typologie zur Entitätsklassifikation

Als Basis-Klassen definieren wir solche Kategorien, welche für alle oder
zumindest die meisten Projekte von Interesse sein sollten, und daher
immer annotiert werden sollten, wenn das volle Schema verwendet wird.

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

Wir annotieren Erwähnungen von einer oder mehrerer Personen mit der
PER-Abkürzung. Bei mehreren Personen ist die Unterscheidung zu beachten,
ab wann es sich nicht mehr um eine Gruppe von Personen handelt, die
erwähnt wird, sondern um eine Organisation im Sinne einer ORG. Oft
kann dies über die Ordinalität unterschieden werden.

Beispiel PER+GRP: "\[Die <u>Zimmerleute</u> des Spitals\]"

Beispiel ORG: "\[Die <u>Gesellschaft</u> der Schaffner des
Spitals\]"

Ein wichtiger Spezialfall ist jedoch zu beachten, wenn eine Personengruppe semantisch für die Organisation selbst steht. Ein häufiger Fall aus dem *Historischen Grundbuch der Stadt Basel* wäre z.B. die Erwähnung von Klöstern (also Organisationen) als "Die <u>Frauen von Klingenthal</u>" oder "den <u>Herren zu St. Peter</u>". Decken sich diese Erwähnungen sinngemäss mit der Erwähnung der Klöster, werden sie als Organisationen, nicht als Personengruppen, erfasst.[^1]

Dazu kommt noch die Unterscheidung von GPE.PER-Erwähnungen, welche dann
Vorrang haben, wenn Personen als Angehörige einer GPE genannt werden.

Beispiel GPE.PER: "\[Die <u>Berner\]</u> gingen..."

### 2.2.1.2.1. Erwähnungs-Präzisierungen für Personen
Hier folgen die etablierten Präzisierungen für PER-Erwähnungen. Sie sollten verwendet werden, wenn eine Entität als NOM, manchmal auch als PRO, erwähnt wird. Mehr zu Erwähnungs-Präzisierungen in Kapitel 2.3.5.

#### 2.2.1.2.1.1. func (Funktion)

Die Person wird durch eine langfristige Funktion beschrieben. *func*
dient dabei als Auffang-Subtyp, präzisere Tags wie *occ* dienen für
nähere Beschreibungen der Funktion.

Beispiele ???

#### 2.2.1.2.1.2. occ (Beruf)

Die Person wird durch ihren Beruf beschrieben. Es handelt sich hierbei
um eine Präzisierung von *func*. Ist nicht klar, ob es sich um einen
Beruf im eigentlichen Sinne handelt, sollte *func* verwendet werden.

Beispiel Erwähnungspräzisierung: "\[der <u>Schneider</u>\]
sagte..."

Beispiel Erwähnungspräzisierung: "\[<u>Ulrich</u>, \[der
<u>Zimmermann</u>\], zu \[<u>Neuenburg</u>\] gesessen\]"

#### 2.2.1.2.1.3. org-aff (Organisationszugehörigkeit)

Die Person wird durch eine passive Zugehörigkeit zu einer Organisation
beschrieben.

Beispiel Erwähnungspräzision: "\[ein <u>Bürger</u> zu
\[<u>Bern</u> /REF.NAM.GPE_ORG\] /REF.NOM_ORG_AFF.PER\]"

#### 2.2.1.2.1.4. org-job (Tätigkeit in Organisation)

Die Person wird durch eine Tätigkeit für eine Organisation beschrieben.
Es handelt sich hierbei um eine Präzisierung von *org-aff*.

Beispiel Erwähnungspräzision: "\[der <u>Schaffner</u> des
\[<u>Spitals</u>\]\]"

#### 2.2.1.2.1.5. origin (Herkunft)

Die Person wird durch einen Ort beschrieben. Dabei ist nicht klar, ob es
sich um den derzeitigen Wohnort oder Herkunftsort oder sogar einen
Beinamen handelt.

Beispiel Erwähnungspräzision: "\[Der <u>Dornacher</u>\]"

#### 2.2.1.2.1.6. owner (Besitztum)

Die Person wird durch den Besitz von etwas beschrieben.

#### 2.2.1.2.1.7. rel (Beziehung)

Die Person wird durch eine langfristige Beziehung zu einer anderen
Person oder Personengruppe (nicht ORG!) beschrieben. Kapitel 2.10.
schlägt Präzisierungen vor für Projekte, welche insbesondere
interpersonelle Beziehungen untersuchen wollen.

Beispiel Erwähnungspräzisierung: "\[<u>Greta von Arx</u>
\[\[<u>Elisabeth von Arx</u> \[<u>selige</u>\]\]
<u>Tochter</u> /ATT.NOM.REL\]\]"

#### 2.2.1.2.1.8. title (Titulierung)

Die Person wird durch einen Titel, den sie trägt, beschrieben. Dies
stellt eine Präzisierung von *func* dar. Wenn ein Titel gleichzeitig
auch eine berufliche Tätigkeit beschreibt, sollte *occ* verwendet
werden.

Beispiel Erwähnungspräzisierung (Gleich zweimal):
"\[\[<u>Herr</u>\] <u>Hans von Sehen</u>,
\[<u>Ritter</u>\]\]"

Manche Titel sind nur durch Kontext als solche erkennbar. Im obigen
Beispiel wird "Herr" als Titel annotiert, da Hans von Sehen im
unmittelbaren Kontext als Adliger erkennbar ist und "Herr" ihn als
solchen auszeichnet. Gerade in späteren Dokumenten wird "Herr" hingegen
als generelle Anrede verwendet, in welchem Fall es nicht als Titel zu
annotieren ist.

### 2.2.1.3. Orte (LOC)

Ein Ort wird als eine Entität definiert, zu, durch oder an welche man
gehen kann. Dazu zählen natürliche, fassbare, Orte wie Flüsse oder
Berge, aber auch menschengemachte Strukturen wie Häuser, Strassen und
Brücken, sowie nicht fassbare Konzepte wie geographische Regionen, solange sie
nicht gleichzeitig politische Entitäten sind.

In Kapitel 2.10. finden sich Richtlinien für präzisere Klassifizierungen
von Orten, wie z.B. ein separater FAC-Tag für menschengemachte
Strukturen, sollte ein Projekt diese Unterscheidung wünschen.

### 2.2.1.3.1. Erwähnungs-Präzisierungen für Orte

Bisher gab es keinen Bedarf dafür.

### 2.2.1.4. Organisationen (ORG)

Organisationen unterscheiden sich von Gruppen, indem sie meist einen
Eigennamen besitzen und langfristige, etablierte Entitäten darstellen.
Im Gegensatz zu modernen Annotationsschemata können wir hierbei keine
Definition erklären, welche sich auf den "offiziellen" Status einer
Gruppierung bezieht. Insofern würden wir sagen, dass es sich dabei um
eine zu ihrer Zeit anerkannte Organisation handeln sollte.

In Kapitel 2.10. werden Richtlinien für genauere Kategorisierungen von
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

### 2.2.1.4.1. Erwähnungs-Präzisierungen und Deskriptoren für Organisationen

Bisher gab es keinen Bedarf dafür.

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

Beispiel: "Es unterschreiben \[die <u>Orte</u>
\[<u>Basel</u>\], \[<u>Bern</u>\],
\[<u>Zürich</u>\]\]"

#### 2.2.1.5.2. LOC

Wird die GPE im Sinne einer LOC genannt, verwenden wir GPE.LOC.

Beispiel: "\[<u>Ulrich</u> \[der <u>Schneider</u>\]
gesessen zu \[<u>Neuenburg</u>\]\]"

Wir verwenden in diesem Fall die Subtypen, welche auch für LOC-Entitäten
gelten.

#### 2.2.1.5.3. ORG

Wird die GPE im Sinne einer ORG genannt, verwenden wir GPE.ORG.

Beispiel: "\[<u>Bürger</u> zu \[<u>Basel</u>\]\]

Wir verwenden in diesem Fall die Subtypen, welche auch für ORG-Entitäten
gelten.

#### 2.2.1.5.4. PER

Wird die Bevölkerung einer Stadt referenziert, verwenden wir GPE.PER.

Beispiel: "\[Die <u>Berner</u>\]"

## 2.2.2. Optionale Entitäts-Klassen

### 2.2.2.1. LOC-Subtypen

#### 2.2.2.1.1. Menschengemachte Strukturen (FAC)

Mit FAC werden Orte annotiert, die von Menschen geschaffen wurden. Das
schliesst sowohl Gebäude als auch Strassen und Plätze ein.

Beispiel: "\[Die <u>Behausung</u> in \[der <u>S. Alban
Vorstatt</u>\]\]"

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
betreffen (dazu ist GPE_ORG da), sondern nur Teile der Regierung, selbst
wenn diese eine führende Position innehaben.

Beispiel: "\[Mr . <u>Lienhart Bientz</u> \[der
<u>Rebman</u>\], \[des <u>Rats</u> /NOM.ORG_GOV\]\]"

#### 2.2.2.2.2. Religiöse Organisationen (REL)

Unter REL fallen Organisationen wie Stifte und Klöster.

Beispiel: "\... zinst von eigenschaft zu \[<u>S. Claren</u>\]"

#### 2.2.2.2.3. Zünfte, Berufsverbände (OCC)

Mit OCC werden Erwähnungen, die auf Zünfte und Berufsverbände verweisen,
annotiert.

#### 2.2.2.2.4. Familien (FAM)

### 2.2.2.3. PER: *rel*-Präzisierungen

#### 2.2.2.3.1. Verwandtschaft (family)

Unter diese Präzisierung fallen Bezeichnung, die der heutigen Definition
einer familiären Beziehung entsprechen, also Geschwister, Eltern,
Kinder, etc. Für die Bezeichnung einer Person durch die Ehe oder festen
Partnerschaft zu einer anderen Person gibt es zudem den Tag *married*

#### 2.2.2.3.2. Verheiratet (married)

Unter married fallen Beschreibungen von Personen durch feste
Partnerschaften oder Ehe.

Beispiel: "\[<u>Jerg Holzman</u>\], und \[\[<u>seine</u>\]
<u>Frau</u> /NOM.PER.married\]"

---

[^1]: [[Diskussion: Personengruppen, die ORGs repräsentieren]](https://github.com/raykyn/BeNASch/issues/2)