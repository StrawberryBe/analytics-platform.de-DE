---
description: Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.
title: Zeileneinstellungen
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# Zeileneinstellungen

>[!NOTE] Sie sehen sich die Dokumentation zum Analysis Workspace in Customer Journey Analytics an. Das Funktionssatz unterscheidet sich geringfügig von dem [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.

Sie können außerdem die ausgewählte(n) Zeile(n) mit den [Rechtsklickaktionen in einer Tabelle](/help/analysis-workspace/visualizations/freeform-table.md) verwalten.

Um auf die Tabellenzeileneinstellungen zuzugreifen, klicken Sie auf das Einstellungs-Symbol neben einer Dimension, einem Segment, einer Metrik, einem Zeitraum oder einer Aufschlüsselung im jeweiligen Element:

![](assets/row-settings.png)

| Zeileneinstellung | Beschreibung |
|--- |--- |
| Datumsvergleiche | Richten Sie die Daten in allen Spalten so aus, dass sie alle in derselben Zeile beginnen.   Wenn Sie z. B. die Daten in einem Monatsvergleich zwischen Oktober und September 2016 ausrichten, beginnt die linke Spalte mit dem 1. Oktober und die rechte Spalte mit dem 1. September.<br>Standardmäßig deaktiviert. |
| Prozentsatz | Prozentsätze pro Zeile berechnen Erzwingt, dass in der Freiformtabelle die Zellprozentsätze über die Zeile anstatt für die Spalte berechnet werden. Dies ist besonders nützlich für die Trend-Darstellung von Prozentangaben.<br>Standardmäßig aktiviert, wenn Sie das Symbol „Visualisieren“ verwenden. |
| Spaltensummen | Diese Einstellungen werden nur bei [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Summe der aktuellen Zeilen als Gesamtsumme anzeigen]**: Zeigt eine clientseitige Summe der Zeilen in der Tabelle, was bedeutet, dass die Gesamtsumme die Metriken wie Besuche oder Besucher **nicht** dedupliziert.</li><li>**[!UICONTROL Gesamtsumme anzeigen]**: Zeigt eine serverseitig Summe an, d. h. die Gesamtsumme dedupliziert Metriken wie Besuche oder Besucher.</li></ul> |
| Aufschlüsselung | **[!UICONTROL Aufschlüsselung nach Position]**: Sie können Aufschlüsselungen nach fester Position in einer Freiformtabelle durchführen. Sie können z. B. festlegen, dass die ersten sieben Zeilen immer aufgeschlüsselt werden.<br>(Zuvor war die Liste mit den Werten in der Aufschlüsselung „gesperrt“. Dies konnte z. B. dazu führen, dass wenn Sie eine Aufschlüsselung des Datums nach Seite durchführten, Sie die ersten 50 Seiten für den ausgewählten Datumsbereich erhielten. Wenn Sie diesen Bericht speicherten und ihn einen Monat später erneut durchführen wollten, hätten sich die ersten 50 Seiten wahrscheinlich geändert. In Analysis Workspace werden jedoch die Ergebnisse der ursprünglichen Aufschlüsselung verwendet und dieselben Seiten angezeigt, aber mit dem aktuellen Monat als Zeitraum.)<br>Ausführung einer Aufschlüsselung anhand einer festen Position: 1. Schlüsseln Sie einige Zeilen in Ihrer Tabelle auf. 2. Klicken Sie auf das Einstellungs-Symbol (Zahnrad) neben der Tabellenzeile, die Sie fixieren möchten. 3. Aktivieren Sie das Kästchen neben „Aufschlüsselung nach Position“. 4. Ändern Sie die Sortierungsreihenfolge oder den Datumsbereich. Die Aufschlüsselungen sind jetzt an die Zeilenposition und nicht die hartcodierten Zeilen gebunden.<br>Standardmäßig deaktiviert. |