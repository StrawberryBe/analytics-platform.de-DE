---
title: Längs-Enddimensionselement
description: Erläutert das Dimensionselement "Long Tail"und warum es in Berichte angezeigt wird.
translation-type: tm+mt
source-git-commit: 3dc9d0d0a1f65a4205120895c35aa508f080c25d
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Längs-Enddimensionselement

Wenn Sie eine Dimension verwenden, die eine große Anzahl individueller Werte enthält, können Sie manchmal einen Wert in Berichte mit der Bezeichnung **[!UICONTROL Langzeit]** sehen. Dieses Dimensionselement bedeutet, dass die Berichte-Architektur, die von CJA verwendet wird, zu viele eindeutige Werte enthalten hat, um verarbeitet werden zu können.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an eine Reihe von Servern. Daten pro Verarbeitungsserver werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungsserver enthält alle Daten für eine bestimmte Person. Nach Abschluss der Verarbeitung übergibt es eine Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn bei jedem einzelnen Server, der eine Teilmenge der Daten verarbeitet, mehr als 500.000 individuelle Dimensionselemente auftreten, werden die Top-500.000-Dimensionselemente der eigenen Untergruppe zurückgegeben. Dann wird der Rest unter &quot;[!UICONTROL Long Tail]&quot;zurückgegeben. Das in einem Workspace-Bericht angezeigte Dimensionselement &quot;[!UICONTROL Long Tail]&quot;ist die aggregierte Summe der Werte jedes einzelnen Verarbeitungsservers, die 500 K einzigartige Werte überschritten haben.

## Unterschiede zwischen &quot;Long Tail&quot;und &quot;Low Traffic&quot;

In früheren Versionen von Adobe Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Elemente der Dimension wurden unter &quot;Geringe Traffic&quot;platziert, nachdem eine Dimension 500 K einzigartige Werte erreicht hatte, und eine aggressivere Filterung bei 1-M-Werten angewendet. Die Anzahl der individuellen Werte wurde zu Beginn jedes Kalendermonats zurückgesetzt. die verarbeiteten Daten dauerhaft waren; Es gab keine Möglichkeit, vorhandene Daten aus &quot;geringer Traffic&quot;zu erhalten.

In CJA werden Dimensionselemente nur dann in &quot;Long Tail&quot;eingefügt, wenn ein einzelner Verarbeitungsserver mehr als 500 K eindeutige Werte enthält. Verarbeitete Daten sind nicht dauerhaft, d. h., Sie können das Dimensionselement &quot;Langzeit&quot;verringern, indem Sie Ihren Bericht ändern.

## Dimensionselemente für &quot;Langes Tail&quot;reduzieren

Wenn Sie das Dimensionselement &quot;Langzeit-Tail&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie einen [filter](/help/components/filters/create-filters.md). Filter werden angewendet, wenn jeder Server eine Teilmenge der Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird das Dimensionselement &quot;Langzeit-Zahl&quot;reduziert.
* Verwenden Sie eine Dimension für den Nachschlagedataset. Suchdatenaset-Dimensionen kombinieren Ereignis-Dataset-Dimensionselemente, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu verwenden, der mehr als 500 K einzigartige Dimensionselemente enthält. Wenn Sie ein Segment oder eine Nachschlagedataset-Dimension anwenden, können Sie das Vorhandensein von &quot;Long Tail&quot;reduzieren, während Sie Ihren Bericht benutzerfreundlicher gestalten. Die Adobe plant, diese Erfahrung zu verbessern, da die CJA weiter entwickelt wird.
