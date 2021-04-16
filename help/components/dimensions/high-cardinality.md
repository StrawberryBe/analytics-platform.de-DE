---
title: Dimensionen mit sehr hoher Kardinalität im Customer Journey Analytics
description: Beschreibt Best Practices für den Umgang mit Dimensionen der hohen Kardinalität in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: c086f21e1a13ef4dec4e1be63d9f462bfb32f2ea
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---


# Dimensionen mit sehr hoher Kardinalität

Customer Journey Analytics (CJA) legt keine Beschränkungen für die Anzahl der eindeutigen Werte oder Dimensionselemente fest, die innerhalb einer Dimension gemeldet werden können. Unter bestimmten Umständen können Dimensionen mit einer extrem großen Anzahl einzigartiger Elemente - auch als Dimensionen mit hoher Kardinalität bezeichnet - Auswirkungen auf das haben, worüber berichtet werden kann.

## Einschränkungen

Abhängig von der Anzahl der Ereignis in einer bestimmten CJA-Verbindung können die folgenden zwei Einschränkungen in Verbindung mit Dimensionen mit hoher Kardinalität auftreten:

### 1. Zeilenanzahl ist möglicherweise nicht genau meldebar

Zeilenzählungen mit hohen Kardinalitätsdimensionen sind möglicherweise nicht genau zu reproduzieren. In diesem Fall werden in Freiform-Tabellen die folgenden Informationen angezeigt:

![](assets/high-cardinality.png)

## 2. Berechnete Metriken können Schätzungen zurückgeben

Bei Verwendung mit hochgradig kardialen Dimensionen können einige Funktionen der berechneten Metrik Schätzungen zurückgeben, darunter: Spaltenmaximum, Spaltenminimum, Zeilenzählung, Mittel, Median, Perzentil, Quartil, Standardabweichung, Varianz, Regressionsfunktionen und T- und Z-Funktionen.

Darüber hinaus kann die Sortierung einer Tabellenspalte mit einer berechneten Metrik auf einer Schätzung basieren und nicht immer die exakte Sortierreihenfolge widerspiegeln. Es erscheint eine Warnmeldung, die Sie darüber informiert, dass Schätzungen verwendet wurden.

Beachten Sie, dass berechnete Metriken manchmal Schätzungen zurückgeben können, die Spaltensummen jedoch immer genau sind und nie auf Schätzungen basieren. Ebenso werden bei Verwendung von Standardmetriken Schätzungen nie zur Sortierung einer Spalte verwendet und spiegeln immer exakte Sortierreihenfolgen wider.

### Wenn alle Dimensionswerte berücksichtigt werden

Obwohl es Einschränkungen bei bestimmten berechneten Metriken und Zählungen von Dimensionszeilen gibt, beachten Sie, dass die folgenden Funktionen immer alle eindeutigen Werte in einer Dimension berücksichtigen. Sie berücksichtigen sie unabhängig davon, ob eine Dimension hochgradig kardinal ist oder nicht:

* Metrikzuordnung und Zuordnung von Dimensionen
* Auf eine Freiformtabelle angewendete Suchen nach Zeilenelementen
* Filter mit Dimensionen oder Dimensionselementen
* Die eindeutige Funktion für die ungefähre Anzahl in berechneten Metriken
* Logik einschließen/ausschließen, die auf eine Metrik oder Dimension in einer Data Ansicht angewendet wird
* Suchdatasets, die einer Verbindung hinzugefügt werden

## Bewährte Verfahren für das Arbeiten mit Dimensionen mit hohem Kardinalwert

Um die Warnungen oder Schätzungen zu vermeiden, die bei der Verwendung von Dimensionen mit hoher Kardinalität auftreten können, sollten Sie die Anzahl der in Ihrem Bericht berücksichtigten Zeilen mit einer der folgenden Methoden eingrenzen:

* hinzufügen Sie einen Filter auf die betreffende Spalte oder das betreffende Bedienfeld an.
* Wenden Sie eine Suche auf Ihre Freiform-Tabelle an.
* Wenden Sie eine Aufschlüsselung auf die Interessenszeilen an oder verwenden Sie die hochkarätige Dimension als Aufschlüsselungsdimension
* hinzufügen Sie Kriterien zur Datenkonfiguration der Dimension ein-/ausschließen, um die Anzahl der eindeutigen Ansichten in der Dimension einzugrenzen.

Durch die Verwendung dieser Techniken können Sie häufig unerwünschte Schätzungen oder Warnungen bei der Verwendung von hochkarätigen Dimensionen vermeiden.
