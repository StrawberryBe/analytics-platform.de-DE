---
title: Dynamische und statische Dimensionselemente in Freiform-Tabellen
description: Interaktion mit dynamischen und statischen Dimensionselementen in Tabellen.
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 94%

---

# Dynamische und statische Dimensionselemente in Freiform-Tabellen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

In Freiform-Tabellen können die Zeilen und Spalten verschiedene Komponentenwerte enthalten. Diese Werte können dynamisch (zeitabhängig) oder statisch (nicht zeitabhängig) sein, je nach Analyse, die Sie erstellen möchten.

## Dynamische Dimensionselemente

Dynamische Dimensionselemente ändern sich mit der Zeit und hängen von der Metrik ab, nach der in der Freiformtabelle sortiert wird. Dynamische Dimensionselemente werden bevorzugt, wenn Sie die obersten Elemente für einen bestimmten Zeitraum analysieren möchten.

Wenn Sie eine Dimension in eine Freiform-Tabelle ablegen, werden dynamische Zeilen zurückgegeben. Sie stellen die obersten Elemente dar, die der Dimension für eine bestimmte Metrik und einen bestimmten Zeitraum entsprechen. Sie können eine Dimension auch in Freiform-Tabellenspalten ablegen und die Dimension wird automatisch in die fünf obersten Dimensionselemente erweitert.

Wenn Sie beispielsweise die Dimension „Browser-Typ“ in die Tabelle ziehen, kehren die obersten Dimensionselemente des Browser-Typs (z. B. Microsoft, Apple, Google usw.) dynamisch zu den Tabellenzeilen zurück. Wenn sie in eine Spalte abgelegt wurde, werden die obersten 5 Browsertyp-Dimensionselemente dynamisch zurückgegeben.

Dynamische Dimensionselemente verfügen über die Zeilenfilteroption und **keine** Schloss- - und X-Symbole.

![](assets/dynamic-items.png)

## Statische Dimensionselemente

Statische Dimensionselemente ändern sich nicht mit der Zeit. Es handelt sich dabei um feste Komponenten, die immer in einer Freiform-Tabelle zurückgegeben werden. Statische Dimensionselemente werden bevorzugt, wenn Sie immer dasselbe Element analysieren möchten, unabhängig davon, ob es sich um bestimmte Kampagnen oder bestimmte Wochentage handelt.

Jedes Mal, wenn Sie manuell bestimmte Komponentenwerte (Dimension, Metrik, Filter, Datumsbereich) in eine Tabelle eingeben, ist das Ergebnis eine statische Liste von Zeilen oder Spalten. Statische Dimensionselemente können auch erstellt werden, wenn Sie Folgendes ausführen:

* Klicken Sie in den Zeilen mit der rechten Maustaste und [!UICONTROL Zeigen Sie nur ausgewählte Zeilen an]
* Klicken Sie in den Spalten mit der rechten Maustaste und [!UICONTROL Machen Sie ein Element statisch]

Wenn Sie beispielsweise über bestimmte Browser-Typ-Elemente wie Microsoft und Apple ziehen, werden diese beiden Elemente immer in die Tabelle gezogen.

Statische Dimensionselemente verfügen **nicht** über die Zeilenfilteroption. Stattdessen sind für jedes Element Schloss- und X-Symbole vorhanden. Klicken Sie auf das X-Symbol, um dieses Dimensionselement aus der Tabelle zu entfernen.

![](assets/static-items.png)

## Gemischte Dimensionselemente

Dimensionselemente aus verschiedenen Dimensionen können derselben Tabelle hinzugefügt werden. In diesen Fällen steht in der Kopfzeile der Zeile „Gemischte Dimensionen“. Diese Dimensionselemente sind statisch. Fügen Sie beispielsweise bestimmte Dimensionselemente aus der Dimension „Browser-Typ“ und andere Dimensionselemente aus der Dimension „Browser“ hinzu.

![](assets/mixed-dimensions.png)

## Freiform-Gesamtzeilen

Dynamische und statische Zeilen verhalten sich in der Freiform-Gesamtzeile unterschiedlich. Standardmäßig:

* Dynamische Zeilen werden Server-seitig summiert und deduplizieren Metriken wie „Besuche“ oder „Besucher“.
* Statische Zeilen werden Client-seitig summiert und deduplizieren **keine** Metriken. Um die Gesamtzeile Server-seitig zu berechnen, ändern Sie die Zeileneinstellung auf **Gesamtsumme anzeigen**. [Weitere Infos](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html)
