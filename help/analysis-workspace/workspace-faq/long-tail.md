---
title: Dimensionselement „Longtail“
description: Erläutert das Dimensionselement „Longtail“ und warum es in Berichten angezeigt wird.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 5603eef365365cea941ba5b261aeb56e58a84236
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 38%

---

# Kappungswarnung

Wenn Sie eine Dimension verwenden, die eine große Anzahl eindeutiger Werte enthält, wird in einigen Fällen eine Warnung angezeigt, in der **[!UICONTROL Ergebnisse gekürzt]**.  Das bedeutet, dass die Berichterstellungsarchitektur, die CJA verwendet, zu viele eindeutige Werte enthält, um sie effizient zu verarbeiten. Daher wurden die Artikel entfernt, von denen sie ausging, dass sie am wenigsten wichtig waren.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungs-Server werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungs-Server enthält alle Daten für eine bestimmte Person. Sobald die Verarbeitung abgeschlossen ist, übergibt er seine Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server eine Ergebnismenge aggregiert, die über einem Größenschwellenwert liegt, werden die Ergebnisse abgeschnitten, bevor sie zurückgesendet werden.  Dadurch wird der Netzwerk-Traffic und die Aggregation mit in Grenzen gehalten, um eine schnelle Berichterstellung zu ermöglichen.  Da die Ergebnisse nur mit der Ansicht der eigenen Daten abgeschnitten werden, ist es möglich (egal wie unwahrscheinlich), dass die in Analysis Workspace angezeigten Elemente falsche Metrikwerte aufweisen.

Basierend auf der für die Sortierung verwendeten Metrik wird ausgewählt, welche Elemente verworfen werden sollen.  Wenn es sich um eine berechnete Metrik handelt, ist es möglicherweise nicht offensichtlich, wie sie sortiert wird. Daher sind die Ergebnisse möglicherweise weniger genau.  Wenn Sie beispielsweise den Umsatz pro Besucher berechnen, werden der Gesamtumsatz und die Gesamtanzahl der Besucher zurückgegeben und aggregiert, bevor Sie die Division durchführen. Daher wählt jeder Knoten viel aus, welche Elemente entfernt werden sollen, ohne zu wissen, wie sich seine Ergebnisse auf die Gesamtsortierung auswirken.

## Unterschiede zwischen „Longtail“ und „Low-Traffic“

In früheren Versionen von Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Dimensionselemente wurden unter „Low-Traffic“ platziert, sobald eine Dimension 500.000 eindeutige Werte erreicht hatte, und es wurde eine aggressivere Filterung bei 1 Million eindeutigen Werten angewendet. Die Anzahl eindeutiger Werte wurde zu Beginn jedes Kalendermonats zurückgesetzt. Verarbeitete Daten waren dauerhaft; es gab keine Möglichkeit, vorhandene Daten aus „Low-Traffic“ zu entfernen.

In CJA werden Dimensionselemente nur abgeschnitten, wenn die Ergebnisse eines Berichts zu groß sind. Verarbeitete Daten sind nicht dauerhaft, d. h., Sie können die Kürzung reduzieren oder beseitigen, indem Sie Ihren Bericht ändern.

## Reduzieren des Dimensionselements „Longtail“

Wenn Sie die Kürzung für &quot;Long Tail&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie einen [Filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Teilmenge von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird die Kürzung &quot;Lange Warteschlange&quot;reduziert.
* Verwenden Sie eine Suche.  Wenn eine Suche verwendet wird, werden die Elemente, die nicht mit der Suche übereinstimmen, zuerst abgeschnitten, wodurch es wahrscheinlicher wird, dass Sie die gewünschten Elemente sehen.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu nutzen, der zu viele eindeutige Dimensionselemente enthält. Wenn Sie einen Filter oder eine Lookup-Datensatz-Dimension anwenden, können Sie die Kürzung &quot;Lange Warteschlange&quot;reduzieren, während Sie Ihren Bericht einfacher nutzen können.
