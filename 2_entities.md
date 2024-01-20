---
title: 2. Entitäten
layout: default
nav_order: 3
---

# 2. Entitäten

Bei einer Entitäten-Annotation handelt es sich genau genommen um die
Annotation von *Erwähnungen* (Mentions). Von einer *Entität* kann man
genau genommen erst sprechen, wenn bestimmt wurde, welche Erwähnungen
sich alle auf eine bestimmte Entität beziehen.

## 2.1. Erwähnungs-Klassifikation (Mention Type)

Wir unterscheiden nach ACE-Vorbild unter den Erwähnungsarten:

### 2.1.1. Eigennamen-Erwähnung (NAM)

Hierbei handelt es sich um eine Erwähnung der Entität anhand ihres
Eigennamens.

Beispiel: "\[<u>Hans Schneider</u>, der Karrer in Neuenburg
gesessen\]"[^1]

Achtung, in einem solchen Fall handelt es sich nicht um eine
Eigennamennennung:

Beispiel: "\[Der <u>Hügel</u>, Büttenberg genannt, liegt 3 Meilen
nördlich\]"

Hier ist "Hügel" das syntaktisch zentrale Wort (*head*), während die
Eigennamenerwähnung in diesem Fall als Attributivnennung zu verzeichnen
wäre (Kapitel 2.5). Die Erwähnung wäre in diesem Fall eine nominative
Erwähnung (Nächstes Kapitel).

### 2.1.2. Nominative Erwähnung (NOM)

Hierbei handelt es sich um eine Erwähnung ohne einen Eigennamen zu
verwenden.

Beispiel: "\[Der <u>Schaffner</u> des Spitals\]"

Nominative Erwähnungen zeichnen sich oft dadurch aus, dass sie
Informationen zur Entität enthalten, wie den Beruf oder eine Beziehung
zu einer anderen Entität. Sie sollten in dem Fall mit einem passenden
Subtypen gekennzeichnet werden (Kapitel 2.6.).

### 2.1.3. Pronominale Erwähnung (PRO)

Hierbei handelt es sich um eine Erwähnung anhand eines Pronomens, häufig
ergänzt mit einer Beschreibung.

Beispiel: "\[<u>Der</u>, dem der Heinzi zinst\]"

#### 2.1.3.1. Spezialfall: Selbstreferenzierung (SELF)

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

### 2.1.4. Unbekannte Erwähnung (UNK)

Aufgrund unleserlicher Schrift kann es vorkommen, dass die Erwähnung
nicht mehr zu entziffern ist, obwohl klar ist, dass es sich dabei um
eine Erwähnung handelt. Die Stelle kann dann als UNK gekennzeichnet
werden.

### 2.1.5. Präzisierung der Erwähnung

Im Falle von Nominalerwähnungen können wir zusätzliche Informationen
festhalten, indem wir die Erwähnungsart weiter präzisieren. Wir
versuchen dabei möglichst dieselben Klassen zu verwenden wie für
Beziehungen (Kapitel 4) und Deskriptoren (Kapitel 2.5.3), wobei wir noch
weitere Präzisierungen speziell zu diesem Zweck definieren.

Wenn z.B. eine Person anhand einer Verwandschaftsbeziehung erwähnt wird
("seine <u>Frau</u>"), dann beinhaltet diese Nennung zugleich
eine Beziehung. Indem wir dieselben Klassennamen verwenden, vereinfachen
wir den Annotationsprozess (siehe Annotationsanleitung).

Die passenden Präzisierungen sind abhängig von der
Entitätsklassifikation und werden aus diesem Grund in den entsprechenden
Kapiteln aufgelistet (Kapitel 2.3).

## 2.2. Ordinalität

### 2.2.1. Einzelne Entität (SGL)

Die Erwähnung betrifft eine einzelne Entität.

Beispiel: "\[<u>Heinzi Schneider</u>\]"

### 2.2.2. Mehrere Entitäten (GRP)

Die Erwähnung betrifft eine Gruppe von Entitäten.

Beispiel: "\[Die <u>Nachbarn</u> an der Gerbergassen wohnend\]"

Wichtig ist bei GRP, sich der Abgrenzung zu den ORG-Entitäten bewusst zu
sein. Bei GRP handelt es sich normalerweise um Erwähnungen im Plural.
Bei ORG handelt es sich um "feste" Gruppierungen mit klaren Grenzen, die
auch meist langfristig definiert sind. Bei Familien zum Beispiel handelt
es sich nicht um GRP vom Typus PER, sondern um ORGs.

### 2.2.3. Negierende Erwähnung (NEG)

Die Erwähnung nennt die Entitäten auf negierende Weise. Oft unspezifisch
erwähnt.

Beispiel: "\[Kein <u>Kohlestürzer</u>\] soll hier wohnen"

## 2.3. Typus

Die Aufzählung aller Typen des Basis-Schemas findet sich unter 2.6.,
weitere Typen, die nur für bestimmte Projekte interessant sein könnten
unter 2.7.

Ein Typus kann durch weitere Subtypen genauer definiert werden, im Falle
von Geopolitischen Entitäten ist ein solcher sogar Pflicht.

## 2.4. Spezifität

### 2.4.1. Spezifische Entität (SPC)

Die Erwähnung bezieht sich auf eine spezifische "existierende" Entität.

Beispiel: "\[Das <u>Haus zum Wind</u>\]"

### 2.5.1. Unspezifische Entitäten (USPC)

Die Erwähnung bezieht sich auf keine spezifische Entität. Beispiele
wären eine undefinierte Masse von Entitäten:

Beispiel: "\[Viele <u>Leute</u>\] sagen..."

Oder die Verwendung von "man" auf unspezifische Weise:

Beispiel "Wenn \[<u>man</u>\] die Strasse Richtung Gerbergassen
geht"

## 2.5. Referenzen / Attribute / Deskriptoren / Head

In BeNASch verwenden wir zur vollständigen Informationserfassung
verschachtelte Annotationen. Zudem halten wir neben den eigentlichen
Entitätserwähnungen auch weitere Informationen zu den Entitäten fest.
Wir unterscheiden hierbei zwischen Referenzen, Attributen und
Deskriptoren. Attribute und Deskriptoren können nur innerhalb von
Referenzen und Attributen vorkommen.

### 2.5.1. Referenzen (REF)

Eine Referenz ist eine Erwähnung, die sich nicht auf dieselbe Entität
wie die darüberliegende Erwähnung bezieht.

Beispiel: "\[der <u>Schreiner</u> /REF\]"[^2]

Beispiel: "\[der <u>Schaffner</u> \[des <u>Spitals</u>
/REF\] /REF\]"

### 2.5.2. Attribute (ATT)

Bei einem Attribut handelt es sich um eine Erwähnung, die sich auf
dieselbe Entität bezieht wie die darüberliegende Erwähnung.

Beispiel: "\[<u>Heinzi Müller</u>, \[der <u>Schreiner</u>
/ATT\] /REF\]"

### 2.5.3. Deskriptoren (DESC)

Bei einem Deskriptor handelt es sich **nicht** um eine
Entitätserwähnung, sondern um eine Information zur Entität. Ein
Deskriptor enthält einen Typus, der einem Subtypus der Entität, die
darüber liegt, entspricht.

Da mögliche Deskriptoren abhängig sind von der Entitätsklassifikation,
werden sie in Kapitel 2.6 in den entsprechenden Unterkapiteln
aufgelistet.

Beispiel: "\[<u>Elisabeth von Arx</u> \[<u>selig</u>
/DESC\] /REF\]"

In diesem Beispiel wäre "selig" vom Typus "dead", welcher auch als
Subtypus bei NOM.PER-Erwähnungen genutzt werden kann, z.B. bei "der
Verstorbene". In beiden Fällen ist der Informationsgehalt, dass die
Person verstorben ist.

### 2.5.4. Listen (LST)

Listen-Elemente dienen dem Zweck, Aufzählungen von Entitäten miteinander
zu verbinden und sie einfacher in Beziehung zu setzen, z.B. mit
Attributen, die sämtliche aufgezählte Entitäten betreffen. Ein Beispiel
verdeutlicht die Nutzung:

Beispiel: "\[\[<u>Heintzi Schneider</u>\] und \[<u>Johann
Ammann</u>\], \[<u>Nachbarn</u> an \[der
<u>Eisengasse</u>\]\] /LST\]"

Eine Liste enthält Verweise auf alle Erwähnungen, die Teil von ihr sind
(im obigen Beispiel also "Heintzi Schneider" und "Johann Ammann"). Ein
Attribut kann zudem auf eine Liste verweisen, so wie sie sonst zu einer
anderen Erwähnung gehören kann.

Listen ähneln in ihrer Funktionsweise GRP-Erwähnungen, haben aber keinen
*head*, dieser wird durch die Aufzählung der Entitäten ersetzt. List
können Erwähnungen von verschiedenen Klassifikationen enthalten.\
\
Beispiel: "\... zinst \[\[dem Predigerkloster /ORG\] und \[<u>Johann von
Arx</u> /PER\] /LST\] ..."

Als Aufzählungen anzusehen sind Entitätenerwähnungen, welche durch
Konjunktionen (auch Kommas falls zutreffend) verbunden werden und damit
eine gemeinsame Rolle im Dokument einnehmen, z.B. als Verkäufer,
Zinsempfänger oder Ziel einer Beziehung.

#### 2.5.4.1. Optionale Spezialtypen

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

##  

## 2.6. Entitäts-Klassifikation

Als Klassen definieren wir solche Kategorien, welche für alle oder
zumindest die meisten Projekte von Interesse sein sollten, und daher
immer annotiert werden sollten, wenn das volle Schema verwendet wird.

Durch Unterklassen können die Klassen präziser definiert werden, wobei
die Verwendung von Subklassen optional ist (Siehe Kapitel 2.7),
abgesehen von den Subklassen von GPE.

### 2.6.1. Übersicht (alphabetisch)

-   GPE (Geopolitische Entitäten)

    -   GPE (im Kontext nicht unterscheidbar)

    -   LOC (im Kontext eines Ortes genannt)

    -   ORG (im Kontext einer handelnden Entität genannt)

    -   PER (Erwähnung der Bevölkerung des Gebiets)

-   LOC (Orte)

-   ORG (Organisationen)

-   PER (Personen)

###  

### 2.6.2. Personen (PER)

Wir annotieren Erwähnungen von einer oder mehrerer Personen mit der
PER-Abkürzung. Bei mehreren Personen ist die Unterscheidung zu beachten,
ab wann es sich nicht mehr um eine Gruppe von Personen handelt, die
erwähnt wird, sondern um eine Organisation im Sinne einer ORG. Meistens
kann dies über die Ordinalität unterschieden werden.\
\
Beispiel PER+GRP: "\[Die <u>Schaffner</u> des Spitals\]"

Beispiel ORG: "\[Die <u>Gesellschaft</u> der Schaffner des
Spitals\]"

Dazu kommt noch die Unterscheidung von GPE.PER-Erwähnungen, welche dann
Vorrang haben, wenn Personen als Angehörige einer GPE genannt werden.\
\
Beispiel GPE.PER: "\[Die <u>Berner\]</u> gingen..."

### 2.6.2.1 Erwähnungs-Präzisierungen und Deskriptoren für Personen

#### 2.6.2.1.1. dead (Verstorben)

Die Person wird als verstorben beschrieben.

Beispiel Erwähnungspräzisierung: "\[die <u>Verstorbene</u>\]"

Beispiel Deskriptor: "\[<u>Elisabeth von Arx</u>
\[<u>selig</u> /DESC\] /REF\]"

#### 2.6.2.1.2. func (Funktion)

Die Person wird durch eine langfristige Funktion beschrieben. *func*
dient dabei als Auffang-Subtyp, präzisere Tags wie *occ* dienen für
nähere Beschreibungen der Funktion.

Beispiele ???

#### 2.6.2.1.3. occ (Beruf)

Die Person wird durch ihren Beruf beschrieben. Es handelt sich hierbei
um eine Präzisierung von *func*. Ist nicht klar, ob es sich um einen
Beruf im eigentlichen Sinne handelt, sollte *func* verwendet werden.

Beispiel Erwähnungspräzisierung: "\[der <u>Schneider</u>\]
sagte..."

Beispiel Erwähnungspräzisierung: "\[<u>Ulrich</u>, \[der
<u>Zimmermann</u>\], zu \[<u>Neuenburg</u>\] gesessen\]"

#### 2.6.2.1.4. org-aff (Organisationszugehörigkeit)

Die Person wird durch eine passive Zugehörigkeit zu einer Organisation
beschrieben.

Beispiel Erwähnungspräzision: "\[ein <u>Bürger</u> zu
\[<u>Bern</u> /REF.NAM.GPE_ORG\] /REF.NOM_ORG_AFF.PER\]"

#### 2.6.2.1.5. org-job (Tätigkeit in Organisation)

Die Person wird durch eine Tätigkeit für eine Organisation beschrieben.
Es handelt sich hierbei um eine Präzisierung von *org-aff*.

Beispiel Erwähnungspräzision: "\[der <u>Schaffner</u> des
\[<u>Spitals</u>\]\]"

#### 2.6.2.1.6. origin (Herkunft)

Die Person wird durch einen Ort beschrieben. Dabei ist nicht klar, ob es
sich um den derzeitigen Wohnort oder Herkunftsort oder sogar einen
Beinamen handelt.

Beispiel Erwähnungspräzision: "\[Der <u>Dornacher</u>\]"

#### 2.6.2.1.7. owner (Besitztum)

Die Person wird durch den Besitz von etwas beschrieben.

#### 2.6.2.1.8. rel (Beziehung)

Die Person wird durch eine langfristige Beziehung zu einer anderen
Person oder Personengruppe (nicht ORG!) beschrieben. Kapitel 2.7.
schlägt Präzisierungen vor für Projekte, welche insbesondere
interpersonelle Beziehungen untersuchen wollen.

Beispiel Erwähnungspräzisierung: "\[<u>Greta von Arx</u>
\[\[<u>Elisabeth von Arx</u> \[<u>selige</u>\]\]
<u>Tochter</u> /ATT.NOM.REL\]\]"

#### 2.6.2.1.9. title (Titulierung)

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

### 2.6.3. Orte (LOC)

Ein Ort wird als eine Entität definiert, zu, durch oder an welche man
gehen kann. Dazu zählen natürliche, fassbare, Orte wie Flüsse oder
Berge, aber auch menschengemachte Strukturen wie Häuser, Strassen und
Brücken, sowie nicht fassbare Konzepte wie geographische Regionen, die
nicht gleichzeitig politische Entitäten sind.

In Kapitel 2.7. finden sich Richtlinien für präzisere Klassifizierungen
von Orten, wie z.B. ein separater FAC-Tag für menschengemachte
Strukturen, sollte ein Projekt diese Unterscheidung wünschen.

### 2.6.3.1. Erwähnungs-Präzisierungen und Deskriptoren für Orte

TODO

### 2.6.4. Organisationen (ORG)

Organisationen unterscheiden sich von Gruppen, indem sie meist einen
Eigennamen besitzen und langfristige, etablierte Entitäten darstellen.
Im Gegensatz zu modernen Annotationsschemata können wir hierbei keine
Definition erklären, welche sich auf den "offiziellen" Status einer
Gruppierung bezieht. Insofern würden wir sagen, dass es sich dabei um
eine zu ihrer Zeit anerkannte Organisation handeln sollte.

In Kapitel 2.7. werden Richtlinien für genauere Kategorisierungen von
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

### 2.6.4.1. Erwähnungs-Präzisierungen und Deskriptoren für Organisationen

TODO

###  

### 2.6.5. Geopolitische Entitäten (GPE)

Geopolitische Entitäten unterscheiden sich von anderen Entitäten in der
Hinsicht, dass dieselbe Entität sowohl in ihrer Rolle als Ort, als
Organisation oder auch als Personengruppe referenziert werden kann. Wir
verwenden in jedem Kontext die Annotation *GPE*, aber versehen diese mit
einem entsprechenden Subtyp. Dieses Problem wird in den ACE-Guidelines
genauer besprochen, wir fassen es hier aber nochmal zusammen.

#### 2.6.5.1. GPE

In manchen Fällen wird die GPE direkt referenziert. In diesem Fall
verwenden wir GPE.GPE als Annotation.

Beispiel: "Es unterschreiben \[die <u>Orte</u>
\[<u>Basel</u>\], \[<u>Bern</u>\],
\[<u>Zürich</u>\]\]"

#### 2.6.5.2. LOC

Wird die GPE im Sinne einer LOC genannt, verwenden wir GPE.LOC.

Beispiel: "\[<u>Ulrich</u> \[der <u>Schneider</u>\]
gesessen zu \[<u>Neuenburg</u>\]\]"

Wir verwenden in diesem Fall die Subtypen, welche auch für LOC-Entitäten
gelten.

#### 2.6.5.3. ORG

Wird die GPE im Sinne einer ORG genannt, verwenden wir GPE.ORG.

Beispiel: ?

Wir verwenden in diesem Fall die Subtypen, welche auch für ORG-Entitäten
gelten.

#### 2.6.5.4. PER

Wird die Bevölkerung einer Stadt referenziert, verwenden wir GPE.PER.

Beispiel: "\[Die <u>Berner</u>\]"

## 2.7. Optionale Entitäts-Klassen

### 2.7.1. LOC-Subtypen

#### 2.7.1.1. Menschengemachte Strukturen (FAC)

Mit FAC werden Orte annotiert, die von Menschen geschaffen wurden. Das
schliesst sowohl Gebäude als auch Strassen und Plätze ein.

Beispiel: "\[Die <u>Behausung</u> in \[der <u>S. Alban
Vorstatt</u>\]\]"

#### 2.7.1.2. Wasserkörper (WAT)

#### 2.7.1.3. Natürliche Region (GEO)

Natürliche Regionen sind definiert durch geologische oder ökologische
Eigenheiten. Dazu zählen z.B. Berge, Gebirge, aber auch Wälder.

#### 2.7.1.4. Künstliche Region (REG)

Künstliche Regionen definieren sich nicht primär durch geologische oder
ökologische Eigenheiten, stellen aber auch keine geopolitischen
Entitäten dar. Denkbar wären hier z.B. "das Zürichgau".

#### 2.7.1.5. Himmelskörper (ASTR)

Mit ASTR werden Erwähnungen von Himmelskörpern gekennzeichnet. "Die
Sonne", "Der Mond".

#### 2.7.1.6. Grenze (BOR)

Mit BOR werden Orte gekennzeichnet, die Grenzen zwischen anderen Orten
darstellen, insbesondere zwischen GPEs.

### 2.7.2. ORG-Subtypen

#### 2.7.2.1. Regierungsorganisationen (GOV)

Mit GOV werden Erwähnungen annotiert, die nicht Regierungen als ganzes
betreffen (dazu ist GPE_ORG da), sondern nur Teile der Regierung, selbst
wenn diese eine führende Position innehaben.

Beispiel: "\[Mr . <u>Lienhart Bientz</u> \[der
<u>Rebman</u>\], \[des <u>Rats</u> /NOM.ORG_GOV\]\]"

#### 2.7.2.2. Religiöse Organisationen (REL)

Unter REL fallen Organisationen wie Stifte und Klöster.

Beispiel: "\... zinst von eigenschaft zu \[<u>S. Claren</u>\]"

#### 2.7.2.3. Zünfte, Berufsverbände (OCC)

Mit OCC werden Erwähnungen, die auf Zünfte und Berufsverbände verweisen,
annotiert.

#### 2.7.2.4. Familien (FAM)

### 2.7.3. PER: *rel*-Präzisierungen

#### 2.7.3.1. Verwandtschaft (family)

Unter diese Präzisierung fallen Bezeichnung, die der heutigen Definition
einer familiären Beziehung entsprechen, also Geschwister, Eltern,
Kinder, etc. Für die Bezeichnung einer Person durch die Ehe oder festen
Partnerschaft zu einer anderen Person gibt es zudem den Tag *married*

#### 2.7.3.2. Verheiratet (married)

Unter married fallen Beschreibungen von Personen durch feste
Partnerschaften oder Ehe.

Beispiel: "\[<u>Jerg Holzman</u>\], und \[\[<u>seine</u>\]
<u>Frau</u> /NOM.PER.married\]"

### 2.7.4. Ereignis-Entitäten (EVENT)[^3]

Wenn Ereignisse auf Entitäten-Stufe annotiert werden sollen, kann das
durch den EVENT-Tag getan werden. Es geht hierbei nicht um beschriebene
Ereignisse wie in der Ereignis-Extraktion (Kapitel 5), sondern z.B. um
Erwähnungen von Festen, Messen, Katastrophen oder militärischen
Geschehnissen.

Es bietet sich an, Unterkategorien für Ereignisse zu definieren.

Beispiel: "Zu S. Andreas Tag begeht man \[meiner lieben Frauen
<u>Jahrzeit</u>\]"

## 2.8. Komplizierte Fälle

\<Platzhalter für Beschlüsse, die im Git gefällt werden\>