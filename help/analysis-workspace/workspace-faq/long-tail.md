---
title: Dimensionselement „Longtail“
description: Erläutert das Dimensionselement „Longtail“ und warum es in Berichten angezeigt wird.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 8618690187a0cc35fd59cc8bef9ad1147cadf8b0
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 31%

---

# Long-Tail-Dimensionselement

Wenn Sie eine Dimension verwenden, die eine große Anzahl eindeutiger Werte enthält, wird in einigen Fällen eine Warnung angezeigt, in der **[!UICONTROL Ergebnisse gekürzt]**.  Das bedeutet, dass die Berichterstellungsarchitektur, die CJA verwendet, zu viele eindeutige Werte enthält, um sie effizient zu verarbeiten. Dies hat zur Folge. Es entfernte die Artikel, die es für am wenigsten wichtig hielt.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungs-Server werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungs-Server enthält alle Daten für eine bestimmte Person. Nach Abschluss der Verarbeitung übergibt der Server seine Untergruppe verarbeiteter Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server eine Ergebnismenge aggregiert, die über einem Größenschwellenwert liegt, werden die Ergebnisse abgeschnitten, bevor sie zurückgesendet werden. Dadurch bleiben der Netzwerk-Traffic und die Aggregation innerhalb von Grenzen, um eine schnelle Berichterstellung zu ermöglichen.  Da die Ergebnisse nur mit der Ansicht der eigenen Daten abgeschnitten werden, ist es möglich (auch wenn es unwahrscheinlich ist), dass die in Analysis Workspace angezeigten Elemente falsche Metrikwerte aufweisen.

Der Server wählt basierend auf der für die Sortierung verwendeten Metrik aus, welche Elemente verworfen werden sollen.  Wenn es sich um eine berechnete Metrik handelt, ist es möglicherweise nicht offensichtlich, wie sie sortiert wird. Daher sind die Ergebnisse möglicherweise weniger genau.  Beispielsweise werden bei der Berechnung von &quot;Umsatz pro Besucher&quot;der Gesamtumsatz und die Gesamtanzahl der Besucher zurückgegeben und aggregiert, bevor die Division durchgeführt wird. Daher wählt jeder Knoten häufig, welche Elemente entfernt werden sollen, ohne wirklich zu wissen, wie sich ihre Ergebnisse auf die Gesamtsortierung auswirken.

## Unterschiede zwischen „Longtail“ und „Low-Traffic“

In früheren Versionen von Adobe Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Dimensionselemente wurden unter „Low-Traffic“ platziert, sobald eine Dimension 500.000 eindeutige Werte erreicht hatte, und es wurde eine aggressivere Filterung bei 1 Million eindeutigen Werten angewendet. Die Anzahl &quot;Einzelwert&quot;wurde zu Beginn jedes Kalendermonats zurückgesetzt. Verarbeitete Daten waren dauerhaft; es gab keine Möglichkeit, vorhandene Daten aus „Low-Traffic“ zu entfernen.

In CJA werden Dimensionselemente nur abgeschnitten, wenn die Ergebnisse eines Berichts zu groß sind. Verarbeitete Daten sind nicht dauerhaft, d. h., Sie können die Kürzung reduzieren oder beseitigen, indem Sie Ihren Bericht ändern.

## Reduzieren des Dimensionselements „Longtail“

Wenn Sie die Kürzung für &quot;Long Tail&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie einen [Filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Teilmenge von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird die Kürzung &quot;Lange Warteschlange&quot;reduziert.
* Verwenden Sie eine Suche. Wenn eine Suche verwendet wird, werden die Elemente, die nicht mit der Suche übereinstimmen, zuerst abgeschnitten, sodass es wahrscheinlicher wird, dass Sie die gewünschten Elemente sehen.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu nutzen, der zu viele eindeutige Dimensionselemente enthält. Wenn Sie einen Filter oder eine Lookup-Datensatz-Dimension anwenden, können Sie die Kürzung &quot;Lange Warteschlange&quot;reduzieren, während Sie Ihren Bericht einfacher nutzen können.
