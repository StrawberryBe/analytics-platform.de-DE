---
title: Frequenzansicht
description: Interaktion anhand der Nutzungshäufigkeit messen.
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: 77192426a58e1560abe91b904452b9cd46c862e9
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 3%

---

# [!UICONTROL Häufigkeit] Ansicht

Die **[!UICONTROL Häufigkeit]** die Ansicht gruppiert Ereignisdaten nach der Häufigkeit, mit der ein Ereignis angezeigt wird. Die vertikale Achse dieses Berichts enthält Behälter, die die Häufigkeit des angezeigten Ereignisses bzw. der angezeigten Ereignisse darstellen. Die horizontale Achse misst die Anzahl der Benutzer oder Sitzungen für jeden Behälter.

![Häufigkeit, Screenshot](../assets/frequency-stacked.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Interaktion**: Verfolgen Sie, wie engagiert Benutzer bei jedem Ereignis sind. Sie können auf einen horizontalen Balken klicken, um ihn als Segment zu speichern. Segmente für Behälter mit geringer Interaktion können Ihnen dabei helfen festzustellen, warum Benutzer nicht mit dem Ereignis in der gewünschten Häufigkeit interagieren. Segmente für Behälter mit hoher Interaktion können Ihnen dabei helfen zu verstehen, warum Benutzer häufig mit dem Ereignis interagieren. Von dort aus können Sie andere Benutzer dazu ermutigen, ein ähnliches Verhalten anzuwenden.
* **Kundentreue**: Setzen Sie das Ereignis auf Bestellungen und die Metrik auf Benutzer. Mit diesem Bericht können Sie Benutzer nach der Anzahl der Male gruppieren, die sie innerhalb des angegebenen Datumsbereichs auf Ihrer Site gekauft haben.
* **Support-Optimierung**: Wenn Sie diesen Bericht nach der Anzahl der Support-Aufrufe oder offenen Fälle anzeigen, erhalten Sie einen Einblick, auf welche Benutzer die meisten Probleme stoßen. Anschließend können Sie ein Segment erstellen, das sich auf sein Erlebnis konzentriert, um die Probleme zu identifizieren und zu beheben.
* **Abonnementdienste**: Dieser Bericht ist für Organisationen mit Abonnementdiensten nützlich. Bei Benutzern mit geringer Interaktion kommt es häufiger zu Abwanderungen. Sie können diesen Bericht anzeigen, um das Verhalten stark engagierter Benutzer zu analysieren. Das Verständnis des Verhaltens stark engagierter Benutzer kann dazu beitragen, für wenig beteiligte Benutzer ein ähnliches Verhalten zu fördern, wodurch die Wahrscheinlichkeit verringert wird, dass sie ihr Abonnement kündigen.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Veranstaltungen]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird als separates Diagramm dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Trendereignis darstellt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Zeilen im Diagramm und Zeilen in der Tabelle. Sie können bis zu fünf Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Häufigkeit] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die zu messende Metrik. Optionen umfassen [!UICONTROL Benutzer] und [!UICONTROL Sitzungen].
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Horizontalbalken] und [!UICONTROL Gestapelte Leiste].

## Bucket-Einstellungen

Bestimmt, wie das Ereignis in Gruppen kategorisiert wird.

* **[!UICONTROL Auto-Buckets]**: Identifizieren Sie automatisch die optimale Behältergröße basierend auf der Datenverteilung.
* **[!UICONTROL Benutzerdefinierte Behälter]**: Steuern Sie, wie der Bericht Daten in Behälter gruppiert.
   * [!UICONTROL Von]: Der erste Behälter. Die Häufigkeit, die kleiner als dieser Wert ist, wird von der Berichterstellung ausgeschlossen.
   * [!UICONTROL nach]: Die Frequenz, die größer als dieser Wert ist, wird in die letzte Gruppe gruppiert.
   * [!UICONTROL Größe]: Das Behälterintervall.

## Zeitvergleich anwenden

{{apply-time-comparison}}

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Diese Einstellung wirkt sich nicht auf Trend-Ansichten wie Häufigkeit aus.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
