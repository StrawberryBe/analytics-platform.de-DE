---
title: Optimieren der CJA-Leistung
description: Best Practices zur Optimierung der CJA-Leistung
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: 98360149433689ae89a9f093bbfad24ebc92db17
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 93%

---


# CJA-Leistung optimieren

>[!NOTE]
>
>Informationen zur Optimierung der Workspace-Leistungsfaktoren finden Sie unter [Optimieren [!UICONTROL Analysis Workspace] Leistung](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Diese Faktoren beeinflussen die CJA-Gesamtleistung:

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| Filterkomplexität | Komplizierte Filter können einen erheblichen Einfluss auf die Projektleistung haben. | Zu den Faktoren, die einem Filter Komplexität verleihen (in der Reihenfolge absteigender Auswirkungen), gehören: <ul><li>Operatoren „enthält“, „enthält beliebige von“, „stimmt überein mit“, „beginnt mit“ oder „endet mit“ </li><li>Sequentielle Filterung, insbesondere wenn Dimensionseinschränkungen (innerhalb/nachher) verwendet werden </li><li>Anzahl der eindeutigen Dimensionselemente innerhalb der Dimensionen, die im Filter verwendet werden (z. B.: Seite = &#39;A&#39;, wenn Seite 10 eindeutige Elemente hat, ist schneller als Seite = &#39;A&#39;, wenn Seite 100.000 eindeutige Elemente hat) </li><li>Anzahl der verschiedenen verwendeten Dimensionen (z. B.: Seite = „Startseite“ und Seite = „Suchergebnisse“ sind schneller als eVar 1 = „rot“ und eVar 2 = „blau“)</li><li>Viele OR-Operatoren (anstelle von AND)</li><li>Verschachtelte Container mit unterschiedlichem Umfang (z. B. Hit innerhalb des Besuchs innerhalb des Besuchers)</li></ul> | Während einige der Komplexitätsfaktoren nicht verhindert werden können, sollten Sie nach Möglichkeiten suchen, die Komplexität Ihrer Filter zu verringern. Generell gilt: Je genauer Sie mit Ihren Filterkriterien umgehen, desto besser. Beispiel:<ul><li>Bei Containern ist die Verwendung eines einzelnen Containers am oberen Rand des Filters schneller als die Verwendung einer Reihe verschachtelter Container.</li><li>Bei Operatoren ist „stimmt überein mit“ schneller als „enthält“ und „entspricht beliebigen von“ ist schneller als „enthält beliebige von“</li><li>Mit vielen Kriterien sind AND-Operatoren schneller als eine Reihe von OR-Operatoren.</li></ul> Suchen Sie nach Möglichkeiten, viele OR-Anweisungen in eine einzelne Anweisung „entspricht einem von“ zu reduzieren <br> |
| Komplexität der Visualisierung (Metriken, Filter) | Die Art der Visualisierung (z. B. Fallout oder Freiformtabelle), die zu einem Projekt hinzugefügt wird, beeinflusst die Leistung selbst nur geringfügig. Die Verarbeitungszeit wird durch die Komplexität der Visualisierung gesteigert. | U. a. machen folgende Faktoren eine Visualisierung komplexer:<ul><li>Angeforderter Datenbereich</li><li>Anzahl der angewandten Filter, z. B. als Zeilen verwendete Filter in einer Freiformtabelle</li><li>Verwendung von komplexen Filtern</li><li>[Statische Element](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) zeilen oder Spalten in Freiformtabellen</li><li>Auf Zeilen angewandte Filter in Freiformtabellen</li><li>Anzahl verwendeter Metriken, insbesondere berechneter Metriken, die Filter verwenden</li></ul> | Wenn Sie bemerken, dass Ihre Projekte langsamer als gewünscht geladen werden, sollten Sie nach Möglichkeit einige Filter durch eVars und Filter ersetzen.<br><br>Wenn Sie ständig Filter und berechnete Metriken für Datenpunkte verwenden, die für Ihr Unternehmen wichtig sind, sollten Sie versuchen, Ihre Implementierung zu verbessern, um diese Datenpunkte direkter zu erfassen. Mit einem Tag-Manager wie Adobe Experience Platform Launch und den Verarbeitungsregeln von Adobe sind Änderungen an der Implementierung schneller und leichter umzusetzen. |
| Kapazität des Rechenzentrums | Die Reporting-Kapazitäten, die Sie und andere Kunden in einem Rechenzentrum von Adobe gemeinsam nutzen. | Dies wird durch die Anzahl gleichzeitiger Abfragen von Ihrer Organisation und anderen Unternehmen innerhalb Ihres Rechenzentrums beeinflusst. | Ihre Organisation hat Anspruch auf eine bestimmte Kapazität. Ist das System nur wenig ausgelastet, überträgt Adobe mehr Kapazität auf Sie, auch über das Ihnen zustehende Maß hinaus. |
