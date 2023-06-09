---
description: In Analysis Workspace gibt es zwei Möglichkeiten zur Verwendung von Metriken.
title: Metriken
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: a9751cad1ba49fe3e8c2c484e34d1725e063c2d4
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 23%

---

# Metriken

Mit Metriken können Sie Datenpunkte in Analysis Workspace quantifizieren. Sie werden meist als Spalten in einer Visualisierung verwendet und sind an Dimensionen gebunden.


## Metriktypen

Adobe bietet verschiedene Arten von Metriken zur Verwendung in Analysis Workspace:

* **Standardmetriken**: Beispiele für Standardmetriken sind Personen, Sitzungen, Ereignisse.

* **Berechnete Metriken** ![Symbol für berechnete Metrik](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Benutzerdefinierte Metriken, die auf Standardmetriken, statischen Zahlen oder algorithmischen Funktionen basieren.

* **Vorlagen für berechnete Metriken**  <img src="./assets/adobe-logo.svg" width="18"> : Von Adoben definierte Metriken, die sich ähnlich wie berechnete Metriken verhalten. Sie können sie unverändert in Workspace-Projekten verwenden oder eine Kopie speichern, um ihre Logik anzupassen.


![Metriken in der Benutzeroberfläche](assets/cja-metrics.png)

Sie können sehen, ob eine Metrik genehmigt wurde. ![Symbol Genehmigt](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  oder nicht. Wenn Sie weitere Details zu einer Metrik wünschen, bewegen Sie den Mauszeiger über die Metrik und wählen Sie ![Infosymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Metriken sind in ihrer Verwendung in Analysis Workspace flexibel. Ziehen Sie eine Metrik in eine leere Freiformtabelle, um die Trendansicht dieser Metrik über den Datumsbereich des Projekts anzuzeigen. Sie können auch eine Metrik ziehen, wenn eine Dimension vorhanden ist, um diese Metrik im Vergleich zu jedem Dimensionselement anzuzeigen. Wenn Sie eine Metrik auf eine vorhandene Metrik-Kopfzeile ziehen, wird sie ersetzt und durch Ziehen einer Metrik neben eine Kopfzeile können Sie beide Metriken nebeneinander sehen.

## Berechnete Metriken 

Berechnete Metriken ermöglichen es Ihnen, mithilfe einfacher Operatoren oder statistischer Funktionen einfach zu erkennen, wie sich Metriken zueinander verhalten. Es gibt mehrere Möglichkeiten, berechnete Metriken zu erstellen:

Sie können **[!UICONTROL Komponenten]** > **[!UICONTROL Berechnete Metriken]**. Dadurch gelangen Sie zum [Generator für berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md), wo Sie benutzerdefinierte Metriken aus vorhandenen Metriken erstellen können.

Um das schnelle Erstellen berechneter Metriken zu vereinfachen, wurde dem Spalten-Kontextmenü von Freiformtabellen die Option **[!UICONTROL Metrik aus Auswahl erstellen]** hinzugefügt. Diese Option wird angezeigt, wenn mindestens eine Spaltenüberschriftszelle ausgewählt ist.

![Aus Auswahl erstellen](assets/create-metric-from-selection.png)

[Berechnete Metriken: implementierungslose Metriken](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=de) (3:42)

## Vergleichen von Metriken mit verschiedenen Attributionsmodellen

Wenn Sie Attributionsmodelle schnell und einfach miteinander vergleichen möchten, klicken Sie mit der rechten Maustaste auf eine Metrik und wählen Sie **[!UICONTROL Attributionsmodelle vergleichen]**:

![Vergleichsattribution](assets/compare-attribution.png)

Dadurch können Sie Attributionsmodelle schnell und einfach miteinander vergleichen, ohne eine Metrik hereinzuziehen und sie zweifach zu konfigurieren.
