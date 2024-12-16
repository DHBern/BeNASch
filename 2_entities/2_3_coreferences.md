---
title: 2.3. Koreferenzen
layout: default
nav_order: 3
parent: 2. Entitäten
---

# 2.3. Koreferenzen
Koreferenzen helfen uns, aus Erwähnungen Entitäten herzuleiten. Eine Koreferenz ist immer eine gerichtete Verbindung von einer Erwähnung zu einer anderen. Wir unterscheiden zwischen direkten Koreferenzen, die zwingend annotiert werden müssen, und indirekten Koreferenzen, deren Annotation optional ist. Wir empfehlen, die Unterscheidung dieser beiden Arten von Koreferenzen einzuhalten.

## 2.3.1. Direkte Koreferenzen
Eine direkte Koreferenz bedeutet, dass eine Erwähnung nur dann Sinn ergibt, wenn eine Koreferenz existiert. Das gilt zum Beispiel für (fast) alle Pronomina und Nominativnennungen mit expliziten Begriffen wie "vorgenannten".

Beispiele für direkte Koreferenzen:

"Hans Jakob kauft das Haus und er bezahlt 30 Gulden."
Hans Jakob <= er

"Der Schaffner des Steinenklosters fröhnt das Haus wegen der vergessenen Zinsen, so dem vorgenannten Kloster jedes Jahr 3 sh. gezinst wird."
des Steinenklosters <= dem vorgenannten Kloster

## 2.3.2. Indirekte Koreferenzen
Eine indirekte Koreferenz hält fest, dass es sich bei zwei Erwähnungen um Referenzen auf dieselbe Entität handelt, diese Information erfordert aber Kontextwissen oder ist zu gewissem Grad Spekulation.

"Der Schaffner des Steinenklosters fröhnt das Haus wegen der vergessenen Zinsen, so dem Kloster jedes Jahr 3 sh. gezinst wird." 
des Steinenklosters <= dem Kloster

"Der Herr Friedrich zog nach Italien. Der Herzog focht dort viele Kämpfe."
Der Herr Friedrich <= Der Herzog