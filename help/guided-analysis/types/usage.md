---
title: Nutzungsansicht
description: Benutzerinteraktion im Lauf der Zeit messen.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: 713d70a444b3dba81a94d4f472b3ca7e0b39d742
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# [!UICONTROL Nutzung] Ansicht

Die **[!UICONTROL Nutzung]** -Ansicht bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Zeitverlauf. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse Ihre gewünschten Ereignisse misst.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Bewertung der Produktleistung**: Trends ermöglichen es Ihnen, die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum zu bewerten. Durch die Analyse von Metriken wie Benutzerinteraktionen, Adoptions- oder Konversionsraten können Sie feststellen, ob die Leistung Ihres Produkts sich verbessert, stagniert oder sinkt.
* **Funktionsbereitstellung**: Trends ermöglichen Ihnen, zu verstehen, wie Benutzer neue Funktionen oder Aktualisierungen übernehmen, die Sie veröffentlichen. Sie können bestimmen, welche Funktionen beliebt sind und welche Funktionen verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datenbasierte Entscheidungen darüber zu treffen, welche Funktionen Ihre Entwicklungsbemühungen priorisieren sollen.
* **Benutzerverhalten**: Trends können Einblicke in das Benutzerverhalten im Zeitverlauf bieten. Indem Sie bestimmte Aktionen untersuchen, die Benutzer ausführen, können Sie Muster identifizieren, in denen Benutzer abbrechen können. Sie können Einblicke aus dieser Ansicht mit [Friktion](friction.md) für noch mehr Einblicke in das Verhalten.
* **A/B-Tests und -Experimente**: Wenn Sie in Ihrem Produkt A/B-Tests durchführen, können Sie mithilfe von Trends messen, welche Tests im Laufe der Zeit am erfolgreichsten sind.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Veranstaltungen]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird je nach Diagrammtyp als farbige Linie oder Gruppe von Balken dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Trendereignis darstellt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Zeilen im Diagramm und Zeilen in der Tabelle. Sie können bis zu fünf Segmente einbeziehen.
* **[!UICONTROL Verteilung]**: Erstellen Sie eine separate Trendlinie pro Dimensionselement. Es wird eine Aufschlüsselungsdimension unterstützt.

## Diagrammeinstellungen

Die [!UICONTROL Nutzung] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die zu messende Metrik. Zu den Optionen gehören Ereignisse, Sitzungen, Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer.
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;, &quot;Balken&quot;, &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Überlagerungen

Fügen Sie dem Diagramm zusätzliche Daten hinzu.

* **[!UICONTROL Anomalien anzeigen]**: Ausführungen [Anomalieerkennung](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in der Trendanalyse. Ausreißer erscheinen als Punkte, über die Sie den Mauszeiger bewegen können, um weitere Informationen zu erhalten.
* **[!UICONTROL Trendzeilenüberlagerung]**: Fügt eine Trendlinie zum Diagramm hinzu, mit der Sie die Gesamtrichtung Ihrer Daten innerhalb des angegebenen Zeitraums anzeigen können.
   * [!UICONTROL Linear]: Ein lineares Regressionsmodell. Empfohlen für Daten, die stetig zunehmen oder abnehmen.
   * [!UICONTROL Logarithmisch]: Ein gekrümmtes Regressionsmodell. Empfohlen für Daten, die im Laufe der Zeit stufenlos verteilt werden.
   * [!UICONTROL anpassbarer Durchschnittswert]: Eine geglättete Linie, die den vorherigen Zeitraum von jedem Punkt aus durchschnittlich darstellt. Empfohlen für Daten mit regelmäßigen Zyklen. Die verfügbaren gleitenden Durchschnittszeiträume hängen vom ausgewählten Datumsbereich ab.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Zeitvergleich der Nutzung](../assets/usage-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.
