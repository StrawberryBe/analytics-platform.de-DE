---
title: Dimensionen mit sehr hoher Kardinalität in Customer Journey Analytics
description: Beschreibt Best Practices für den Umgang mit Dimensionen mit hoher Kardinalität in Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
translation-type: ht
source-git-commit: 8ae1cb5a84b26258fb30f6e630744b2e36a48e5c
workflow-type: ht
source-wordcount: '455'
ht-degree: 100%

---

# Dimensionen mit sehr hoher Kardinalität

Customer Journey Analytics (CJA) legt keine Beschränkungen für die Anzahl der eindeutigen Werte oder Dimensionselemente fest, die innerhalb einer Dimension gemeldet werden können. Unter bestimmten Umständen können Dimensionen mit einer extrem großen Anzahl einzigartiger Elemente – auch als Dimensionen mit hoher Kardinalität bezeichnet – Auswirkungen auf das haben, worüber berichtet werden kann.

## Einschränkungen

Je nach der Anzahl der Ereignisse in einer bestimmten CJA-Verbindung können die folgenden zwei Einschränkungen in Verbindung mit Dimensionen mit hoher Kardinalität auftreten:

### 1. Zeilenanzahl ist möglicherweise nicht genau zu reproduzieren.

Zeilenanzahl mit Dimensionen mit hoher Kardinalität ist möglicherweise nicht genau zu reproduzieren. In diesem Fall geben Freiform-Tabellen eine Anzeige wie folgt an:

![](assets/high-cardinality.png)

### 2. Berechnete Metriken können Schätzungen für einige Funktionen und für die Sortierreihenfolge verwenden.

Bei Verwendung mit hochgradig kardinalen Dimensionen können einige Funktionen der berechneten Metrik Schätzungen zurückgeben, darunter: Spaltenmaximum, Spaltenminimum, Zeilenanzahl, Mittelwert, Median, Perzentil, Quartil, Standardabweichung, Varianz, Regressionsfunktionen und T- und Z-Funktionen.

Darüber hinaus kann die Sortierung einer Tabellenspalte mit einer berechneten Metrik auf einer Schätzung basieren und ggf. nicht immer die exakte Sortierreihenfolge widerspiegeln. Es erscheint eine Warnmeldung, die Sie darüber informiert, dass Schätzungen verwendet wurden.

Beachten Sie, dass berechnete Metriken manchmal Schätzungen zurückgeben können, die Spaltensummen jedoch immer genau sind und nie auf Schätzungen basieren. Ebenso werden bei Verwendung von Standardmetriken nie Schätzungen verwendet, sondern immer exakte Sortierreihenfolgen wiedergegeben.

### Bei Berücksichtigung aller Dimensionswerte

Auch wenn bestimmte berechnete Metriken und die Anzahl von Dimensionszeilen eingeschränkt ist, beachten Sie, dass die folgenden Funktionen immer alle eindeutigen Werte in einer Dimension berücksichtigen, unabhängig davon, ob eine Dimension hochgradig kardinal ist oder nicht:

* Metrikattribution und Zuordnung von Dimensionen
* Auf eine Freiformtabelle angewendete Suchen nach Zeilenelementen
* Filter mit Dimensionen oder Dimensionselementen
* Die ungefähre Anzahl an eindeutigen Funktionen in berechneten Metriken
* Logik ein-/ausschließen, die auf eine Metrik oder Dimension in einer Datenansicht angewendet wird
* Suchdatensätze, die einer Verbindung hinzugefügt werden

## Best Practices für das Arbeiten mit Dimensionen mit hoher Kardinalität

Um die Warnungen oder Schätzungen zu vermeiden, die bei der Verwendung von Dimensionen mit hoher Kardinalität auftreten können, sollten Sie die Anzahl der in Ihrem Bericht berücksichtigten Zeilen mithilfe einer der folgenden Methoden eingrenzen:

* Fügen Sie der betroffenen Spalte oder dem betroffenen Bedienfeld einen Filter hinzu.
* Wenden Sie eine Suche auf Ihre Freiform-Tabelle an.
* Wenden Sie eine Aufschlüsselung auf die relevanten Zeilen an oder verwenden Sie die Dimension mit hoher Kardinalität als Aufschlüsselungsdimension.
* Fügen Sie Ein-/Ausschlusskriterien zur Konfiguration der Datenansicht der Dimension hinzu, um die Anzahl der in der Dimension vorhandenen eindeutigen Werte einzugrenzen.

Durch die Verwendung dieser Techniken können Sie häufig unerwünschte Schätzungen oder Warnungen bei der Verwendung von Dimensionen mit hoher Kardinalität vermeiden.
