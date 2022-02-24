---
title: Dimensionselement „Longtail“
description: Erläutert das Dimensionselement „Longtail“ und warum es in Berichten angezeigt wird.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '437'
ht-degree: 100%

---

# Dimensionselement „Longtail“

Wenn Sie eine Dimension verwenden, die eine große Anzahl eindeutiger Werte enthält, sehen Sie manchmal einen Wert mit der Bezeichnung **[!UICONTROL Longtail]** im Bericht. Dieses Dimensionselement bedeutet, dass die Berichtsarchitektur, die von CJA verwendet wird, zu viele eindeutige Werte enthält, um verarbeitet werden zu können.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an mehrere Server. Die Daten pro Verarbeitungs-Server werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungs-Server enthält alle Daten für eine bestimmte Person. Sobald die Verarbeitung abgeschlossen ist, übergibt er seine Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server, der eine Teilmenge von Daten verarbeitet, auf mehr als 500.000 eindeutige Dimensionselemente trifft, werden die wichtigsten 500.000 Dimensionselemente seiner eigenen Teilmenge zurückgegeben. Der Rest wird dann unter [!UICONTROL Longtail] zurückgegeben. Das in einem Workspace-Bericht angezeigte Dimensionselement [!UICONTROL Longtail] ist der aggregierte Gesamtwert der Werte jedes einzelnen Verarbeitungs-Servers, die 500.000 eindeutige Werte überschreiten.

## Unterschiede zwischen „Longtail“ und „Low-Traffic“

In früheren Versionen von Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Dimensionselemente wurden unter „Low-Traffic“ platziert, sobald eine Dimension 500.000 eindeutige Werte erreicht hatte, und es wurde eine aggressivere Filterung bei 1 Million eindeutigen Werten angewendet. Die Anzahl eindeutiger Werte wurde zu Beginn jedes Kalendermonats zurückgesetzt. Verarbeitete Daten waren dauerhaft; es gab keine Möglichkeit, vorhandene Daten aus „Low-Traffic“ zu entfernen.

In CJA werden Dimensionselemente nur dann in „Longtail“ eingefügt, wenn ein einzelner Verarbeitungs-Server mehr als 500.000 eindeutige Werte enthält. Die verarbeiteten Daten sind nicht dauerhaft, d. h., Sie können das Dimensionselement „Longtail“ reduzieren, indem Sie Ihren Bericht ändern.

## Reduzieren des Dimensionselements „Longtail“

Wenn Sie das Dimensionselement „Longtail“ reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie einen [Filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Teilmenge von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird das Dimensionselement „Longtail“ reduziert.
* Verwenden Sie eine Lookup-Datensatzdimension. Lookup-Datensatzdimensionen kombinieren Elemente von Ereignis-Datensatzdimensionen, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu verwenden, der mehr als 500.000 eindeutige Dimensionselemente enthält. Wenn Sie einen Filter oder eine Lookup-Datensatzdimension anwenden, können Sie das Vorhandensein von „Longtail“ reduzieren und gleichzeitig die Nutzung Ihres Berichts vereinfachen. Adobe plant, dieses Erlebnis im Zuge der Weiterentwicklung von CJA zu verbessern.
