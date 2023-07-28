---
title: Ergebnisse - abgeschnittenes Dimensionselement
description: Erläutert das Dimensionselement "Ergebnisse abgeschnitten"und warum es in Berichten angezeigt wird.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: f0fa126a23e6c99f89db82c91c98b6628d43a983
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 12%

---

# Ergebnisse - abgeschnittenes Dimensionselement

Wenn Sie eine Dimension verwenden, die viele eindeutige Werte enthält, sind die Berichtsergebnisse möglicherweise zu groß für die Verarbeitung.  Um Verlangsamungen im gesamten System zu vermeiden, werden die Ergebnisse abgeschnitten, indem Elemente entfernt werden, die als am wenigsten wichtig gelten.  Dies wird in einem Freiform-Bedienfeld durch Hinzufügen der Wörter &quot;größer als&quot;im Paginierungsanzeiger angezeigt, z. B. &quot;Zeilen: 1-400 von mehr als 9.819.653&quot;.

In einigen Fällen, z. B. nach einer berechneten Metrik, ist es unmöglich festzustellen, welche Dimensionselemente am wenigsten wichtig sind.  In diesem Fall wird ein Warnsymbol auf der berechneten Metrik platziert, das dieses Problem erklärt und zu [einige Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/dimensions/high-cardinality.html?lang=en).

## Verarbeitungsarchitektur und eindeutige Werte für Customer Journey Analytics

Customer Journey Analytics verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungs-Server werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungs-Server enthält alle Daten für eine bestimmte Person. Nach Abschluss der Verarbeitung übergibt der Server seine Untergruppe verarbeiteter Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server eine Ergebnismenge aggregiert, die über einem Größenschwellenwert liegt, werden die Ergebnisse abgeschnitten, bevor sie zurückgesendet werden. Diese Optimierung hält den Netzwerk-Traffic und die Aggregation innerhalb von Grenzen, um eine schnelle Berichterstellung zu ermöglichen. Da jeder Verarbeitungsserver Ergebnisse nur mit der Ansicht seiner eigenen Daten abschneidet, können die in Analysis Workspace angezeigten Elemente Metrikwerte aufweisen, die geringfügig abgeschnitten sind.

Der Server wählt basierend auf der für die Sortierung verwendeten Metrik aus, welche Dimensionselemente verworfen werden sollen. Wenn die Sortiermetrik eine berechnete Metrik ist, verwendet der Server Metriken innerhalb der berechneten Metrik, um zu bestimmen, welche Dimensionselemente abgeschnitten werden sollen. Da berechnete Metriken mehrere Metriken unterschiedlicher Wichtigkeit enthalten können, können die Ergebnisse weniger präzise sein. Beispielsweise werden bei der Berechnung von &quot;Umsatz pro Person&quot;der Gesamtbetrag der Einnahmen und die Gesamtzahl der Personen zurückgegeben und aggregiert, bevor die Division durchgeführt wird. Daher wählt jeder Knoten aus, welche Elemente entfernt werden sollen, ohne zu wissen, wie sich ihre Ergebnisse auf die Gesamtsortierung auswirken.

## Unterschiede zu &quot;Geringer Traffic&quot;

In früheren Versionen von Adobe Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zu dem Zeitpunkt verarbeitet, zu dem sie erfasst wurden. Dimension Elemente wurden unter &quot;Geringer Traffic&quot;platziert, nachdem eine Dimension 500.000 individuelle Werte erreicht hatte, und eine aggressivere Filterung auf eine Million eindeutiger Werte angewendet. Die Anzahl &quot;Einzelwert&quot;wurde zu Beginn jedes Kalendermonats zurückgesetzt. Verarbeitete Daten waren dauerhaft; es gab keine Möglichkeit, vorhandene Daten aus „Low-Traffic“ zu entfernen.

Im Customer Journey Analytics werden Dimensionselemente nur abgeschnitten, wenn die Ergebnisse eines Berichts zu groß sind. Verarbeitete Daten sind nicht dauerhaft, d. h., Sie können die Kürzung reduzieren oder beseitigen, indem Sie Ihren Bericht ändern.

## Dimensionselement &quot;Ergebnisse gekürzt&quot;reduzieren

Wenn Sie die Anzahl der Ereignisse im Dimensionselement &quot;Ergebnisse gekürzt&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie eine [Filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Untergruppe von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird das Dimensionselement &quot;Ergebnisse gekürzt&quot;reduziert.
* Verwenden Sie eine Suche. Wenn eine Suche verwendet wird, werden die Elemente, die nicht mit der Suche übereinstimmen, aus den Berichtsergebnissen entfernt, wodurch es wahrscheinlicher wird, dass Sie die gewünschten Elemente sehen.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.
