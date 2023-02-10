---
description: Sie können Anomalien in einer Tabelle oder einem Liniendiagramm anzeigen.
title: Anomalien in Analysis Workspace anzeigen
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: ht
source-wordcount: '460'
ht-degree: 100%

---

# Anomalien in Analysis Workspace anzeigen

Sie können Anomalien in einer Tabelle oder einem Liniendiagramm anzeigen.

## Anzeigen von Anomalien in einer Tabelle {#section_869A87B92B574A38B017A980ED8A29C5}

Sie können Anomalien in einer Zeitreihen-Freiformtabelle anzeigen.

1. Wählen Sie das Symbol für die Spalteneinstellungen in der Spaltenüberschrift aus und stellen Sie sicher, dass die Option [!UICONTROL **Anomalien**] in der Optionsliste ausgewählt ist. Weitere Informationen finden Sie unter [Spalteneinstellungen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicken Sie auf eine Stelle außerhalb des Einstellungsmenü, um die aktualisierte Tabelle anzuzeigen.

   ![](assets/anomaly_detected.png)

1. In der Tabelle werden Anomalien wie folgt angezeigt:

   Ein **dunkelgraues Dreieck** wird in der oberen rechten Ecke jeder Zeile angezeigt, in der eine Datenanomalie erkannt wird.

   Die farbige **senkrechte Linie** in jeder Zeile zeigt den erwarteten Wert an. Der **farbige Bereich** in jeder Zeile zeigt den tatsächlichen Wert an. Das Verhältnis zwischen Linie (erwarteter Wert) und farbigem Bereich (tatsächlicher Wert) bestimmt, ob eine Anomalie vorliegt. (Eine Anomalie wird durch die fortschrittlichen statistischen Verfahren festgestellt, die im Abschnitt [In der Anomalieerkennung verwendete statistische Verfahren](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) beschrieben werden.)

1. Wählen Sie das graue Dreieck in der oberen rechten Ecke einer Zeile aus, um Details zur Anomalie anzuzeigen. Dadurch wird das Maß (in Prozent) angezeigt, in dem der tatsächliche Wert über oder unter dem erwarteten Wert liegt.

## Anzeigen von Anomalien in einem Liniendiagramm {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Anomalien können ausschließlich in Liniendiagrammen visualisiert werden.

Gehen Sie folgendermaßen vor, um Anomalien in einem Liniendiagramm darzustellen:

1. Wählen Sie das Einstellungssymbol in der Visualisierungskopfzeile aus und stellen Sie sicher, dass die Option [!UICONTROL **Anomalien anzeigen**] in der Optionsliste ausgewählt ist. Weitere Informationen finden Sie unter [Linie](/help/analysis-workspace/visualizations/line.md).

1. (Optional) Damit das Diagramm anhand des Konfidenzintervalls skaliert werden kann, wählen Sie das Einstellungssymbol in der Visualisierungskopfzeile und dann die Option **[!UICONTROL Skalierung der Y-Achse durch Anomalien zulassen]** aus.

   Diese Option ist standardmäßig nicht aktiviert, da das Diagramm dadurch unter Umständen weniger gut lesbar wird.

1. Klicken Sie auf eine Stelle außerhalb des Einstellungsmenü, um das aktualisierte Liniendiagramm anzuzeigen.

   ![](assets/anomaly_linechart.png)

   Anomalien werden im Liniendiagramm wie folgt dargestellt:

   Ein **weißer Punkt** wird in der Zeile angezeigt, wo eine Datenanomalie erkannt wurde. (Eine Anomalie wird durch die fortschrittlichen statistischen Verfahren festgestellt, die im Abschnitt [In der Anomalieerkennung verwendete statistische Verfahren](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) beschrieben werden.)

   Der **hell schattierte Bereich** ist das Konfidenzband bzw. der erwartete Bereich, in dem Werte auftreten sollten. Jeder Wert außerhalb dieses erwarteten Bereichs ist eine Anomalie.

   Wenn das Liniendiagramm mehrere Metriken enthält, werden nur die Anomalien angezeigt. Bewegen Sie den Mauszeiger über die einzelnen Anomalien, um das Konfidenzband für die jeweilige Metrik einzublenden.

   Die **gestrichelte Linie** stellt den erwarteten Wert dar.

1. Klicken Sie auf eine Anomalie (weißer Punkt), um die folgenden Informationen anzuzeigen:

   * Das Datum, an dem die Anomalie auftrat

   * Der Rohdatenwert der Anomalie

   * Der Prozentwert über oder unter dem erwarteten Wert, der durch eine durchgezogene grüne Linie dargestellt wird.

