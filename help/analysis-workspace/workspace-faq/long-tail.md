---
title: Dimensionselement "Long Tail"
description: Erläutert das Dimensionselement "Long Tail"und warum es in Berichten angezeigt wird.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Dimensionselement &quot;Long Tail&quot;

Wenn Sie eine Dimension verwenden, die eine große Anzahl eindeutiger Werte enthält, können Sie manchmal einen Wert in der Berichterstellung mit der Bezeichnung **[!UICONTROL Long Tail]**. Dieses Dimensionselement bedeutet, dass die Berichterstellungsarchitektur, die von CJA verwendet wird, zu viele eindeutige Werte enthält, um verarbeitet werden zu können.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungsserver werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungsserver enthält alle Daten für eine bestimmte Person. Sobald die Verarbeitung abgeschlossen ist, übergibt sie ihre Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server, der eine Teilmenge von Daten verarbeitet, auf mehr als 500.000 eindeutige Dimensionselemente trifft, werden die 500.000 wichtigsten Dimensionselemente seiner eigenen Teilmenge zurückgegeben. Dann wird der Rest unter &quot;[!UICONTROL Long Tail]&quot;. Der[!UICONTROL Long Tail]Das in einem Workspace-Bericht angezeigte Dimensionselement ist der aggregierte Gesamtwert der Werte jedes einzelnen Verarbeitungsservers, die 500.000 einmalige Werte überschreiten.

## Unterschiede zwischen &quot;Long Tail&quot;und &quot;Low Traffic&quot;

In früheren Versionen von Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Dimension Elemente wurden unter &quot;Geringer Traffic&quot;platziert, nachdem eine Dimension 500.000 eindeutige Werte erreicht hatte, und eine aggressivere Filterung bei einmaligen 1M-Werten angewendet wurde. Die Anzahl eindeutiger Werte wurde zu Beginn jedes Kalendermonats zurückgesetzt. Verarbeitete Daten waren dauerhaft; es gab keine Möglichkeit, vorhandene Daten aus &quot;Geringer Datenverkehr&quot;zu erhalten.

In CJA werden Dimensionselemente nur dann in &quot;Long Tail&quot;eingefügt, wenn ein einzelner Verarbeitungsserver mehr als 500.000 eindeutige Werte enthält. Die verarbeiteten Daten sind nicht dauerhaft, d. h. Sie können das Dimensionselement &quot;Langer Tail&quot;reduzieren, indem Sie Ihren Bericht ändern.

## Dimensionselement &quot;Long Tail&quot;reduzieren

Wenn Sie das Dimensionselement &quot;Long Tail&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie eine [filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Teilmenge von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird das Dimensionselement &quot;Langer Tail&quot;reduziert.
* Verwenden Sie eine Lookup-Datensatz-Dimension. Lookup-Datensatzdimensionen kombinieren Ereignis-Datensatz-Dimensionselemente, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu verwenden, der mehr als 500.000 eindeutige Dimensionselemente enthält. Wenn Sie einen Filter oder eine Lookup-Datensatz-Dimension anwenden, können Sie das Vorhandensein von &quot;Long Tail&quot;reduzieren und gleichzeitig die Nutzung Ihres Berichts vereinfachen. Die Adobe plant, diese Erfahrung im Zuge der Weiterentwicklung des CJA zu verbessern.
