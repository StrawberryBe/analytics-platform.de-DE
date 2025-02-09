---
title: Ansicht "Konversionstrends"
description: Verfolgen Sie Änderungen der Konversionsrate im Zeitverlauf.
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: a40cfa2498bed03c169eed10cea091574bf90730
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 1%

---

# Ansicht &quot;Konversionstrends&quot;

Die **Konversionstrends** -Ansicht bietet eine Trend-Visualisierung um Konversionsraten im Zeitverlauf. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Konversionsrate darstellt.

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Optimierungsbemühungen verfolgen**: Nachdem Sie die wichtigsten Engpässe identifiziert haben, die Sie verbessern möchten, verwenden Sie [Friktion](friction.md)können Sie diese Ansicht verwenden, um zu verfolgen, wie sich diese Optimierungen auf die Konversionsrate im Zeitverlauf auswirken.
* **A/B-Test-Bewertung**: Bewerten Sie die Wirksamkeit von A/B-Tests oder -Experimenten, die im Rahmen eines Trichters durchgeführt werden. Durch den Vergleich von Konversionsraten zwischen verschiedenen Varianten können Sie einfach feststellen, welche Tests höhere Konversionsraten bieten, was zu datengesteuerten Entscheidungen führt, um welche Varianten dauerhaft implementiert werden sollen.
* **Kampagnenbewertung im Zeitverlauf**: Messen Sie die Effektivität von Marketing-Kampagnen im Zeitverlauf. Sie können ein Segment erstellen, das sich auf Benutzer konzentriert, die eine bestimmte Kampagne berührt haben, und ihre Konversionsraten mit anderen Kampagnen vergleichen. Sie können auch die aktuellen Konversionsraten mit ähnlichen Kampagnen vergleichen, die in der Vergangenheit ausgeführt wurden.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Schritte]**: Die Ereignis-Touchpoints, die Sie verfolgen möchten. Jede Leiste im Diagramm stellt einen Schritt dar. Sie können bis zu zehn Schritte einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, über die Sie den Trichter vergleichen möchten. Jedes ausgewählte Segment teilt jeden Schritt in mehrere Balken auf. Jede Farbe stellt ein anderes Segment dar. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die Ansicht Konversionstrends bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die zu messende Metrik. Zu den Optionen gehören Sitzungen und Benutzer.
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;.
* **[!UICONTROL Konversion von]**: Bestimmt die Berechnung des Prozentsatzes von Schritt zu Schritt. Zu den Optionen gehören die Berechnung der Konvertierung aus dem ersten Schritt oder dem vorherigen Schritt.

>[!NOTE]
>
>Die **Durchschnittlich** in der Tabelle &quot;Konversionstrends&quot;unterscheidet sich von der **Ingesamt** in der [Friktionsansicht](friction.md) Tabelle. Erstere ist der Durchschnitt der Intervallspalten (z. B. der Durchschnitt der täglichen Konversionsraten), während Letztere eine aggregierte Berechnung über den gesamten Datumsbereich hinweg ist.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Zeitvergleich für Konversionstrends](../assets/conversion-trends-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
