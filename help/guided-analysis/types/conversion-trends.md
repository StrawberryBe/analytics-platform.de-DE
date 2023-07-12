---
title: Konversions-Trends
description: Verfolgen Sie Änderungen der Konversionsrate im Zeitverlauf.
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Konversions-Trends

{{release-limited-testing}}

Die **Konversionstrends** Der Ansichtstyp bietet eine Trend-Visualisierung um Konversionsraten im Zeitverlauf. Die horizontale Achse ist immer eine Datumsgranularität, während die vertikale Achse die Konversionsrate darstellt. Verwenden dieses Ansichtstyps in Verbindung mit [Friktion](friction.md) ermöglicht es Ihnen, den gewünschten Trichter einzurichten und zu verfeinern. Anschließend können Sie diesen Ansichtstyp verwenden, um Konversionsraten für diesen Trichter im Zeitverlauf anzuzeigen. Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Optimierungsbemühungen verfolgen**: Nachdem Sie die wichtigsten Engpässe identifiziert haben, die Sie verbessern möchten, verwenden Sie [Friktion](friction.md)können Sie diesen Ansichtstyp verwenden, um zu verfolgen, wie sich diese Optimierungen auf die Konversionsrate im Zeitverlauf auswirken.
* **A/B-Test-Bewertung**: Bewerten Sie die Wirksamkeit von A/B-Tests oder -Experimenten, die im Rahmen eines Trichters durchgeführt werden. Durch den Vergleich von Konversionsraten zwischen verschiedenen Varianten können Sie einfach feststellen, welche Tests höhere Konversionsraten bieten, was zu datengesteuerten Entscheidungen führt, um welche Varianten dauerhaft implementiert werden sollen.
* **Kampagnenbewertung im Zeitverlauf**: Messen Sie die Effektivität von Marketing-Kampagnen im Zeitverlauf. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die eine bestimmte Kampagne berührt haben, und ihre Konversionsraten mit anderen Kampagnen vergleichen. Sie können auch die aktuellen Konversionsraten mit ähnlichen Kampagnen vergleichen, die in der Vergangenheit ausgeführt wurden.

![Konversions-Trends](../assets/conversion-trends.png)

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Schritte**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
* **Personen**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Trichter bietet die folgenden Diagrammeinstellungen. Sie können die Diagrammeinstellungen über das Menü zwischen dem Ansichtstyp und der Kalenderauswahl anpassen.

* **Metrik**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören Sitzungen und Benutzer.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Die einzige Option ist Line.
* **Konversion von**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem ersten Schritt oder dem vorherigen Schritt.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Zeitvergleich für Konversionstrends](../assets/conversion-trends-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
