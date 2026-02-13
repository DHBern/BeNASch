---
title: 2.1. Entitäten
layout: default
nav_order: 1
parent: 2. Entitäten
---

# 2.1. Entitäten

## 2.1.1. Erwähnungen (*Reference*)
Eine Entitäten-Erwähnung (auch: Referenz) wird dann annotiert, wenn die Entität unter eine der festgelegten Kategorien (Kapitel 2.2.) fällt. 
In der Bestimmung der Abgrenzung der Erwähnung, d.h. welche Wörter mit zur Erwähnung gehören, folgen wir soweit möglich der syntaktischen Struktur des Satzes.
Eine Erwähnung besteht üblicherweise aus einer [[Nominalphrase]](https://de.wikipedia.org/wiki/Nominalphrase). Ein paar Beispiele um zu beschreiben, was Teil einer Erwähnung ist:

Beispiel: "\[Der alte <u>Schmied</u>\]"[^1]\
Beispiel: "\[Die <u>Witwe</u> des Schmied\]"\
Beispiel: "\[Des Schmieds <u>Witwe</u>\]"\
Beispiel: "\[Das <u>Haus</u> in der Vorstadt\]"\
Beispiel: "\[Das <u>Haus</u>, das in der Vorstadt liegt\]"

Diese Erwähnungen können teils sehr lang sein; gewisse Dokumententypen neigen dazu, ihre Informationen stark zu verschachteln. Hier ein fiktives Beispiel, das aber z.B. im *Historischen Grundbuch der Stadt Basel* nicht unüblich wäre (die eckigen Klammern markieren die relevante Erwähnung):

"Der Schaffner zu den Barfüssen hat \[Johannes Schmidlin des Gerbers <u>Behausung</u> samt der Schüren, genannt zum Roten Stern, gelegen in der Steinenvorstadt zwischen der Gerbern Zunfthaus und des Ulrich Zofingers des Schmieds Erben, zinst dem Kloster der Barfüsser 2 sh. alle Fronfasten, sonst frei\] um versessenen Zins wegen gefrönt."

## 2.1.2. Erwähnungs-Klassifikation
Die folgenden Klassifikationen sind für jede Erwähnung zu annotieren.

### 2.1.2.1. Entitäten-Klassifikation
Auf welche Art von Entität verweist die Erwähnung? 

Beispiele: Personen, Orte, Institutionen, Artefakte, etc.

Die Typologie ist in Kapitel 2.2. ersichtlich.

### 2.1.2.1. Ordinalität

### 2.1.2.1.1. Einzelne Entität (*sgl*)
Die Erwähnung betrifft eine einzelne Entität.

Beispiel: "\[<u>Heinzi Schneider</u>\]"

### 2.1.2.1.2. Mehrere Entitäten (*grp*)
Die Erwähnung betrifft eine Gruppe von Entitäten.

Beispiel: "\[Die <u>Nachbarn</u> an der Gerbergassen wohnend\]"

Wichtig ist bei GRP, sich der Abgrenzung zu den ORG-Entitäten bewusst zu sein. Bei GRP handelt es sich normalerweise um Erwähnungen im Plural. 
Bei ORG handelt es sich um "feste" Gruppierungen mit klaren Grenzen, die auch meist langfristig definiert sind. Bei Familien zum Beispiel handelt es sich nicht um GRP vom Typus PER, sondern um ORGs.

### 2.1.2.1.3. Negierende Erwähnung (*neg*)
Die Erwähnung nennt die Entitäten auf negierende Weise. Oft unspezifisch erwähnt.

Beispiel: "\[Kein <u>Kohlestürzer</u>\] soll hier wohnen"

## 2.1.2.2. Spezifität

### 2.1.2.2.1. Spezifische Entität (*spc*)
Die Erwähnung bezieht sich auf eine spezifische "existierende" Entität.

Beispiel: "\[Das <u>Haus zum Wind</u>\]"

### 2.1.2.2.2. Unspezifische Entitäten (*uspc*)
Die Erwähnung bezieht sich auf keine spezifische Entität. Beispiele wären eine undefinierte Masse von Entitäten:

Beispiel: "\[Viele <u>Leute</u>\] sagen..."

Oder die Verwendung von "man" auf unspezifische Weise:

Beispiel "Wenn \[<u>man</u>\] die Strasse Richtung Gerbergassen
geht"

## 2.1.3. Beschreibende Elemente
Für jede Entitäten-Erwähnung (und für Appositionen innerhalb von Erwähnungen) werden alle Elemente innerhalb der Erwähnung (bzw. Apposition) annotiert, die die Entität beschreiben.

### 2.1.3.1. Kern (*head*)
Der Kern (auch: Kopf) entspricht weitestgehend dem grammatikalischen Konzept des [Kerns](https://de.wikipedia.org/wiki/Kopf_(Grammatik)), bzw. Kopfes. Jede Erwähnung sollte genau einen Kern aufweisen. Kerne können keine weiteren Verschachtelungen enthalten.

Jedem Kern muss zudem ein Kern-Klasse zugewiesen werden. Diese kategorisiert den Inhalt des Kerns. Siehe Kapitel 2.2.2. für eine Übersicht der Kern-Klassen.

Beispiele (**Kern**):

| Erwähnung | Kern-Klasse |
| ------------ | ------------- |
| der Schneider **Hans** | Eigenname |
| der **Schaffner** des Spitals | Funktion / Beruf / Amt |
| der **Hügel**, Büttenberg genannt | Typus |
| die **Stadt** Braunschweig | Typus |
| **sie** | Pronomen |

### 2.1.3.2. Apposition (*app*)
Unter Appositionen sind Phrasen, die lockeren oder engen [Appositionen](https://de.wikipedia.org/wiki/Apposition) entsprechen, zu verstehen. Optional können linguistisch interessierte Projekte natürlich zwischen lockeren und engen Appositionen unterscheiden.

Appositionen teilen viele Gemeinsamkeiten mit Entitäten-Erwähnungen und können wiederum Verschachtelungen enthalten. **In Appositionen müssen beschreibende Elemente ebenfalls annotiert werden!**

Beispiele (**Apposition**):

| Erwähnung |
| ------------ |
| der **Schneider** Hans |
| Ulrich Schmied, **Bürger zu Basel** |
| Herzog Leopold **der Fünfte** |
| Johann, **der Schaffner des Spitals** |
| das Kloster **Klingental** |
| die Stadt **Braunschweig** |

### 2.1.3.3. Attribute (*att*)
BeNASch geht in seinem Verständnis von [Attributen](https://de.wikipedia.org/wiki/Attribut_(Grammatik)) aus pragmatischen Gründen weiter als die Grammatik. Wir verwenden Attribute, um jegliche Phrasen zu annotieren, die nicht in die anderen Kategorien von Beschreibungen fallen, aber trotzdem relevante Informationen enthalten, z.B. Possessivartikel. Linguistisch interessierte Projekte können optional noch genauere Infos zu den Attributen festhalten, z.B. Genitivattribut, Präpositionalattribut, Relativsatz, etc.

In zwei Ausnahmen werden Attribute nicht annotiert:

1. Appositionen klammern wir aus und annotieren diese getrennt von den anderen Attributen, wie in 2.1.3.2. beschrieben.
2. Wenn ein Attribut direkt das Objekt eines im Kern beschriebenen Zustands oder eines Ereignisses ist. Anders herum beschrieben: Geht aus dem Attribut alleine an sich keine Information hervor, sondern erst durch Verbindung mit dem Kern, wird das Attribut nicht annotiert.

Jedem Attribut muss eine Attribut-Klasse zugewiesen werden, welche besagt, welche Informationen im Attribut enthalten sind. Diese kategorisiert den Inhalt des Attributs. Siehe Kapitel 2.2.2. für eine Übersicht der Attributs-Klassen.

Beispiele (**Attribut**):

| Erwähnung | Attribut-Klasse |
| ------------ | ------------- |
| der **verstorbene** Schneider | ist_verstorben |
| der Vater Hans **selig** | ist_verstorben |
| der Schneider, **verstorben**  | ist_verstorben |
| **Uelis** Hofstatt | hat_besitzer |
| Hofstatt **von Ueli** | hat_besitzer |
| das Haus **an der Eisengasse** | liegt_angrenzend |
| das Haus, **das an der Eisengasse liegt** | liegt_angrenzend |

Beispiele, bei denen kein Attribut nach BeNASch vorliegt:

| Erwähnung | Erklärung |
| ------------ | ------------- |
| seine Frau | Die Ehebeziehung, die sich daraus ergibt, ergibt sich erst durch die Verbindung mit dem Kern. |
| der Schaffner des Spitals | Das Arbeitsverhältnis, bzw. die Repräsentation der Institution erschliesst sich erst durch den Kern. |
| der Meister Johannes Schmied | Hierbei handelt es sich um eine enge Apposition, daher liegt kein Attribut nach BeNASch vor. |

### 2.1.3.4. Numeralia (*num*)
Als Numeralia annotieren wir Phrasen, die auf die genaue Menge der Entität(en) hinweisen. Nicht annotiert werden muss der Artikel “ein”.

## 2.1.4. Listen (*lst*)
Als Listen bezeichnen wir den Spezialfall, in dem mehrere Nominalphrasen die Kerne einer äusseren Nominalphrase ersetzen, üblicherweise verbunden durch Konjunktionen. Listen helfen uns dabei, Appositionen und Attribute, welche sich auf alle Entitäten innerhalb dieser komplexen Nominalphrase beziehen, mit diesen zu verbinden.

Das BeNASch empfiehlt nach derzeitigem Standard die Annotation aller solcher Listen, aber um Schema-konformität herzustellen reicht es, nur solche Listen zu annotieren, die zwingend notwendig sind, weil sonst Appositionen und Attribute nicht korrekt mit den in den Listen enthaltenen Entitäten in Verbindung gesetzt werden könnten.

Listen sollten nur ihrer Art der Konjunktion kategorisiert werden, z.B. als “und”-Liste, “oder”-Liste, etc.

Beispiel: "\[\[<u>Heintzi Schneider</u>\] und \[<u>Johann
Ammann</u>\], \[<u>Nachbarn</u> an \[der
<u>Eisengasse</u>\]\] /LST\]"


## 2.1.5. Komplizierte Fälle

### 2.1.5.1 Mehrere Personen mit nur einem genannten Nachnamen

Beispiel: "Hedwig und Bertschi Eberli"

Werden zwei Personen genannt, aber nur bei einer der Familienname
beschrieben, folgen wir den Prinzipien der textnahen Annotation.

Beispiel: "\[\[<u>Hedwig</u> /PER] und \[<u>Bertschi Eberli</u> /PER] /LST]"

Für weitere Informationen siehe [Diskussion](https://github.com/raykyn/BeNASch/issues/11)

---

[^1]: In Beispielen zeigen die eckigen Klammern eine Annotation an, eine Unterstreichung markiert den *head*. Etwaige weitere Annotationen im Beispiel werden weggelassen, wenn sie für das Beispiel nicht relevant sind.

