---
title: Wert der Dimension "Langer Ton"
description: Erläutert den Dimensionswert "Long Tail"und warum er in Berichte angezeigt wird.
translation-type: tm+mt
source-git-commit: 8f59697b2bb282a1057267131343229e12dd5111
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Wert der Dimension &quot;Langer Ton&quot;

Wenn Sie eine Dimension verwenden, die eine große Anzahl individueller Werte enthält, können Sie manchmal einen Wert in Berichte mit der Bezeichnung &quot;Langzeit-Tail&quot;sehen. Dieser Dimensionswert bedeutet, dass die Berichte-Architektur, die von CJA verwendet wird, zu viele eindeutige Werte enthalten hat, um verarbeitet werden zu können.

## CJA-Verarbeitungsarchitektur und eindeutige Werte

CJA verarbeitet Berichte zum Zeitpunkt ihrer Ausführung und verteilt den kombinierten Datensatz an eine Reihe von Servern. Daten pro Verarbeitungsserver werden nach Personen-ID gruppiert, d. h., ein einzelner Verarbeitungsserver enthält alle Daten für eine bestimmte Person. Nach Abschluss der Verarbeitung übergibt es eine Teilmenge der verarbeiteten Daten an einen Aggregator-Server. Alle Teilmengen verarbeiteter Daten werden kombiniert und in Form eines Workspace-Berichts zurückgegeben.

Wenn ein einzelner Server, der eine Teilmenge von Daten verarbeitet, auf mehr als 500.000 individuelle Dimensionswerte stößt, gibt er die Top-500.000-Dimensionswerte seiner eigenen Untergruppe zurück und gibt dann den Rest unter &quot;Long Tail&quot;zurück. Der in einem Workspace-Bericht angezeigte Dimensionswert &quot;Long Tail&quot;ist der aggregierte Gesamtwert der Werte der einzelnen Verarbeitungsserver, die 500.000 einzigartige Werte überschritten haben.

## Unterschiede zwischen &quot;Long Tail&quot;und &quot;Low Traffic&quot;

In früheren Versionen von Adobe Analytics wurde eine andere Verarbeitungsarchitektur verwendet. Die Daten wurden zum Zeitpunkt ihrer Erfassung verarbeitet. Dimensionswerte wurden unter &#39;geringer Traffic&#39; platziert, nachdem eine Dimension 500 K einzigartige Werte erreicht hatte, und eine aggressivere Filterung bei 1-M-eindeutigen Werten angewendet. Die Anzahl der individuellen Werte wurde zu Beginn jedes Kalendermonats zurückgesetzt. die verarbeiteten Daten dauerhaft waren; Es gab keine Möglichkeit, vorhandene Daten aus &quot;geringer Traffic&quot;zu erhalten.

In CJA werden Dimensionswerte nur dann in &quot;Long Tail&quot;gesetzt, wenn ein einzelner Verarbeitungsserver mehr als 500 K eindeutige Werte enthält. Verarbeitete Daten sind nicht dauerhaft, d. h., Sie können den Dimensionswert &quot;Langzeit&quot;durch Ändern Ihres Berichts reduzieren.

## Den Dimensionswert &quot;Langer Tail&quot;verringern

Wenn Sie den Dimensionswert &quot;Langzeit-Tail&quot;reduzieren möchten, empfiehlt Adobe Folgendes:

* Verwenden Sie ein Segment. Segmente werden angewendet, wenn jeder Server eine Teilmenge von Daten verarbeitet. Wenn Sie die Anzahl der eindeutigen Werte, die sie zurückgeben, begrenzen, wird der Dimensionswert &quot;Langer Tail&quot;verringert.
* Verwenden Sie eine Dimension für den Nachschlagedataset. Die Suchdatenaset-Dimensionen kombinieren Ereignis-Dataset-Dimensionswerte, die die Anzahl der zurückgegebenen eindeutigen Werte begrenzen.

Insgesamt ist es schwierig, einen Bericht zu verwenden, der mehr als 500 K einzigartige Dimensionswerte enthält. Wenn Sie ein Segment oder eine Nachschlagedataset-Dimension anwenden, können Sie das Vorhandensein von &quot;Long Tail&quot;reduzieren, während Sie Ihren Bericht benutzerfreundlicher gestalten. Adobe plant, diese Erfahrung zu verbessern, da CJA weiter entwickelt wird.
