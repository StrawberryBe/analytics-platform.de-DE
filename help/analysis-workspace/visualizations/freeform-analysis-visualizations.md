---
description: Darstellen Sie Ihre Daten in Analysis Workspace visuell dar.
keywords: Analysis Workspace
title: Visualisierungsübersicht
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
source-git-commit: 4f12248e196759c4c4fc494770048495c703c954
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 93%

---

# Visualisierungsübersicht

Workspace bietet eine Reihe von Visualisierungen, mit denen Sie visuelle Darstellungen Ihrer Daten generieren können, wie beispielsweise Balkendiagramme, Donutdiagramme, Histogramme, Liniendiagramme, Karten und Streudiagramme. Die meisten Visualisierungstypen sind Ihnen schon bekannt, wenn Sie Adobe Analytics verwenden. Analysis Workspace verfügt jedoch über Visualisierungseinstellungen sowie viele neue und einzigartige Visualisierungsarten mit interaktiven Funktionen.

Sie können auf Visualisierungen durch das Symbol oben links in Workspace, von einem [leeren Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md) aus oder über das Kontextmenü in Ihrem Workflow zugreifen.

![](assets/viz-rail.png)

Die folgenden Visualisierungstypen sind in Analysis Workspace verfügbar:

| Name der Visualisierung | Beschreibung |
| --- | --- |
| [Bereich](/help/analysis-workspace/visualizations/area.md) | Wie ein Liniendiagramm, aber mit einem farbigen Bereich unterhalb der Linie. Verwenden Sie ein Flächendiagramm, wenn Sie mehrere Metriken darstellen und den Bereich visualisieren möchten, der durch die Schnittmenge von zwei oder mehr Metriken gebildet wird. |
| [Balken](/help/analysis-workspace/visualizations/bar.md) | zeigt vertikale Balken, die verschiedene Werte aus einer oder mehreren Metriken darstellen. |
| [Lineardiagramm](/help/analysis-workspace/visualizations/bullet-graph.md) | zeigt, wie ein Wert, der Sie interessiert, im Vergleich zu anderen Leistungsbereichen (Zielen) liegt oder ausfällt. |
| [Kohortentabelle](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Eine *`cohort`* ist eine Personengruppe mit gemeinsamen Merkmalen innerhalb eines vorgegebenen Zeitraums. Die Kohortenanalyse ist nützlich für die Analyse von Verweildauer, Abwanderung oder Latenzzeiten. |
| [Ringdiagramm](/help/analysis-workspace/visualizations/donut.md) | Ähnlich wie bei einem Tortendiagramm zeigt diese Visualisierung Daten als Teile oder Filter eines Ganzen an. |
| [Trichteranalyse](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Fallout-Berichte zeigen, wo Besucher eine Site verlassen haben und wo sie eine vorab definierte Folge von Seiten passiert haben (d. h., wo sie verblieben sind). Kann auf mögliche oder exakte Sequenzen eingestellt werden |
| [Fluss](/help/analysis-workspace/visualizations/c-flow/flow.md) | Zeigt Kundenpfade durch Ihre Websites und Programme. |
| [Freiformtabelle](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | Eine Freiformtabelle ist nicht nur eine Datentabelle, sondern auch eine interaktive Visualisierung. Es bildet die Grundlage für die Analyse von Daten in Workspace. |
| [Histogramm](/help/analysis-workspace/visualizations/histogram.md) | Ein Histogramm fasst Besucher, Besuche oder Treffer basierend auf einem Metrikvolumen in Behälter zusammen. |
| [Horizontalbalken](/help/analysis-workspace/visualizations/horizontal-bar.md) | zeigt horizontale Balken, die verschiedene Werte aus einer oder mehreren Metriken darstellen. |
| [Linie](/help/analysis-workspace/visualizations/line.md) | stellt Metriken anhand einer Linie dar, die den Wertverlauf über einen bestimmten Zeitraum hinweg zeigt. Ein Liniendiagramm verwendet die Zeit entlang der X-Achse. |
| [Streudiagramm](/help/analysis-workspace/visualizations/scatterplot.md) | zeigt die Beziehung zwischen Dimensionselementen und bis zu drei Metriken. |
| [Zusammenfassungszahl](/help/analysis-workspace/visualizations/summary-number-change.md) | Zeigt die ausgewählte Zelle als eine große Zahl an. |
| [Zusammenfassungsänderung](/help/analysis-workspace/visualizations/summary-number-change.md) | Zeigt die Änderung zwischen den ausgewählten Zellen als eine große Zahl/Prozentzahl an. |
| [Text](/help/analysis-workspace/visualizations/text.md) | Sie können benutzerdefinierten Text zu Ihrem Workspace hinzufügen. Hilfreich zum Hinzufügen zusätzlicher Kontexte zu Ihrer Analyse und zu Einblicken, zusätzlich zum Nutzen der Beschreibungen im Bedienfeld oder in Visualisierungen |
| [Treemap](/help/analysis-workspace/visualizations/treemap.md) | Zeigt hierarchische Daten (Baumstruktur) als Gruppe verschachtelter Rechtecke an. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Verwendet Kreise zur Darstellung der Metriküberlappung von bis zu 3 Filtern. |

## Einstellungen {#settings}

Jede Visualisierung verfügt über eigene Einstellungen, die Sie verwalten können. Um auf [!UICONTROL Visualisierungseinstellungen] zuzugreifen, klicken Sie auf das Zahnradsymbol [!UICONTROL Visualisierungseinstellungen].

![](assets/settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| Visualisierungstyp | Ändern Sie den visuellen Typ, der zur Darstellung der Daten verwendet wird. |
| Granularität | Für Trend-Visualisierungen können Sie die Zeitgranularität (Tag, Woche, Monat usw.) aus dieser Dropdown-Liste ändern. Diese Änderung gilt auch für die Datenquellentabelle. |
| Prozentsatz | Zeigt Werte als Prozentzahlen an. |
| 100 % gestapelt | Mit dieser Einstellung für die Visualisierungen „Bereich gestapelt“, „Balken gestapelt“ und „Horizontalbalken gestapelt“ wandeln Sie Diagramme in „zu 100 % gestapelte“ Visualisierungen um. Beispiel: ![Gestapelt 100 %](assets/stacked_100_percent.png) |
| Legende sichtbar | Hiermit können Sie den erklärenden Text zu Details für die Visualisierung „Zusammenfassungsnummer/Zusammenfassungsänderung“ ausblenden. |
| Grenzwert für max. Anzahl Elemente | Hiermit können Sie die Anzahl der Elemente begrenzen, die in einer Visualisierung angezeigt werden. |
| Y-Achse bei null verankern | Wenn alle im Diagramm dargestellten Werte deutlich größer als null sind, wird der untere Teil der Y-Achse standardmäßig zu NICHT-NULL gemacht. Wenn Sie dieses Kontrollkästchen aktivieren, wird die Y-Achse zwangsweise auf null gesetzt (und das Diagramm neu gezeichnet). |
| Normalisierung | Erzwingt Metriken für gleiche Anteile. Dies ist hilfreich, wenn grafisch dargestellte Metriken sehr unterschiedliche Größenordnungen aufweisen. |
| Zwei Achsen anzeigen | Gilt nur, wenn Sie zwei Metriken haben – möglich sind eine Y-Achse links (für die eine Metrik) und eine rechts (für die andere). Dies ist hilfreich, wenn grafisch dargestellte Metriken sehr unterschiedliche Größenordnungen aufweisen. |
| Anomalien anzeigen | Verbessert Liniendiagramme und Freiformtabellen durch Anzeige der Anomalieerkennung. Die Anomalieerkennung in Linienvisualisierungen umfasst einen erwarteten Wert (gestrichelte Linie) und einen erwarteten Bereich (schattiertes Band). |

## Legende {#legend}

Eine Visualisierungslegende hilft Ihnen, das Datum in einer Ausgangstabelle mit der dargestellten Serie in der Visualisierung zu verknüpfen. Die Legende ist interaktiv: Sie können auf ein Legendenelement klicken, um eine Reihe in der Visualisierung ein- oder auszublenden. Dies ist hilfreich, wenn Sie die visualisierten Daten vereinfachen möchten.

Darüber hinaus können Sie Legendenbeschriftungen umbenennen, um Visualisierungen benutzerfreundlicher zu gestalten. Hinweis: Die Bearbeitung der Legenden ist für die folgenden Visualisierungen **nicht** möglich: Treemap, Aufzählung, Zusammenfassungsänderung oder -nummer, Text, Freiform, Histogramm, Kohorten- oder Flussvisualisierung.

So bearbeiten Sie eine Legendenbezeichnung:

1. klicken Sie mit der rechten Maustaste auf die Legendenbeschriftungen.
1. Klicken Sie auf **[!UICONTROL Bezeichnung bearbeiten]**.

   ![](assets/edit-label.png)

1. Geben Sie den neuen Beschriftungstext ein.
1. Drücken Sie zum Speichern die **[!UICONTROL Eingabetaste]**.

Hier finden Sie einen [Link zu einem Video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html) zu diesem Thema.

## Rechtsklick auf Menü {#right-click}

Zusätzliche Funktionen für eine Visualisierung sind verfügbar, indem Sie mit der rechten Maustaste auf die Visualisierungskopfzeile klicken. Die Einstellungen variieren je nach Visualisierung. Einige der verfügbaren Einstellungen sind:

![](assets/right-click.png)

| Einstellung | Beschreibung |
| --- | --- |
| Kopiertes Bedienfeld/kopierte Visualisierung einfügen | Sie können das kopierte Bedienfeld oder die kopierte Visualisierung an einer anderen Stelle innerhalb des Projekts oder in ein ganz anderes Projekt einfügen. |
| Visualisierung kopieren | Ermöglicht es Ihnen, mit der rechten Maustaste auf eine Visualisierung zu klicken und sie zu kopieren, sodass Sie sie an einer anderen Stelle innerhalb des Projekts oder in ein anderes Projekt einfügen können. |
| [Objekte als CSV herunterladen](/help/analysis-workspace/curate-share/download-send.md) | Laden Sie bis zu 50.000 Dimensionselemente für die ausgewählte Dimension als CSV herunter. |
| [Daten als CSV herunterladen](/help/analysis-workspace/curate-share/download-send.md) | Laden Sie die Visualisierungsdatenquelle als CSV herunter. |
| Visualisierung duplizieren | Fertigt ein exaktes Duplikat der aktuellen Visualisierung an, das Sie dann bearbeiten können. |
| Beschreibung bearbeiten | Text zur Beschreibung der Visualisierung hinzufügen (oder bearbeiten). |
| Visualisierungs-Link anfordern | Hiermit können Sie Personen zu einer bestimmten Visualisierung innerhalb eines Projekts leiten. Wenn auf den Link geklickt wird, muss sich der Empfänger anmelden, bevor er zu genau der verknüpften Visualisierung weitergeleitet wird. |
| Neu starten | (Funktioniert für Fluss, Venn, Histogramm) Löscht die Konfiguration für die aktuelle Visualisierung, damit Sie sie von Grund auf neu konfigurieren können. |

## Symbol „Visualisierung erstellen“ {#quick-viz}

Wenn Sie sich nicht sicher sind, welche Visualisierung Sie auswählen sollen, bewegen Sie den Mauszeiger über eine beliebige Tabellenzeile und klicken Sie auf das dann erscheinende Symbol **[!UICONTROL Visualisierung erstellen]**. Dies ist die schnellste Möglichkeit, eine Visualisierung hinzuzufügen. Wenn Sie darauf klicken, sucht Analysis Workspace nach der Visualisierung, die aufgrund der vorhandenen Fakten am besten zu Ihren Daten passt. Wenn Sie beispielsweise eine einzelne Zeile ausgewählt haben, wird ein Trend-Liniendiagramm erstellt. Wenn Sie drei Filterzeilen ausgewählt haben, wird ein Venn-Diagramm erstellt.

![](assets/quick-viz.png)
