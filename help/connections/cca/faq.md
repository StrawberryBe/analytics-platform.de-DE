---
title: Häufig gestellte Fragen zu Analytics für verschiedene Kanal
description: Häufig gestellte Fragen zu Kanal Analytics
translation-type: tm+mt
source-git-commit: dd4e7e5cd04db6483f0e4a1f3161f23f8a5a8294
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 20%

---


# Häufig gestellte Fragen

## Wie kann ich CCA verwenden, um zu sehen, wie Menschen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension &quot;Dataset-ID&quot;verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Workspace-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte „Visualisierungen“ und ziehen Sie eine Flussvisualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie auf der linken Seite auf die Registerkarte &quot;Komponenten&quot;und ziehen Sie die Dimension &quot;Datenbestand-ID&quot;an die mittlere Position mit der Bezeichnung &quot;Dimension oder Element&quot;.
4. Dieser Flussbericht ist interaktiv. Klicken Sie auf einen der Werte, um den Fluss auf nachfolgende oder vorherige Seiten zu erweitern. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie Datenbestand-ID-Dimensionselemente umbenennen möchten, können Sie einen Nachschlagedatensatz verwenden.

## Wie weit ist der CCA-Besucher zurück?

Das Lookback-Fenster für die erneute Wiedergabe hängt von der gewünschten Häufigkeit der Daten ab. [](replay.md) Wenn Sie z. B. CCA so einrichten, dass Daten einmal wöchentlich wiedergegeben werden, beträgt das Lookback-Fenster zum erneuten Veröffentlichen 7 Tage. Wenn Sie CCA so einrichten, dass Daten jeden Tag wiedergegeben werden, beträgt das Lookback-Fenster zum erneuten Veröffentlichen 1 Tag.

## Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die transiente ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie vom gleichen Gerät stammen).

## Wie behandelt die CCA Situationen, in denen eine einzelne Person über eine große Anzahl von persistenten IDs verfügt?

In bestimmten Situationen kann ein einzelner Benutzer einer großen Anzahl von persistenten IDs zugeordnet werden. Beispiele sind das Löschen einzelner Browser-Cookies oder der private/inkognito-Modus des Browsers.

Die Anzahl der beständigen IDs ist für die transiente IDs irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass die Fähigkeit des CCA beeinträchtigt wird, über Geräte hinweg zu heften.

## Wie lange dauert es, bis der neu eingegebene Datensatz verfügbar ist, nachdem ich meinen Kundenbetreuer mit den gewünschten Informationen kontaktiert habe?

Die Live-Suche ist ca. 1 Woche nach der Adobe verfügbar und ermöglicht Cross-Kanal Analytics. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Kleine Datensätze (weniger als 1 Million Ereignis pro Tag) dauern in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignis pro Tag) eine Woche oder länger dauern können.

## Wie verarbeitet Cross-Kanal Analytics GDPR- und CCPA-Anforderungen?

Adobe bearbeitet Anfragen nach GDPR und CCPA gemäß den nationalen und internationalen Gesetzen. Adobe Angebot das [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html), Datenzugriffs- und Löschanforderungen zu senden. Die Anforderungen gelten sowohl für die ursprünglichen als auch die neu eingegebenen Datensätze.
