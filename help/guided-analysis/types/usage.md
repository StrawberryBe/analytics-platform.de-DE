---
title: Nutzungsansicht
description: Benutzerinteraktion im Lauf der Zeit messen.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
feature: Guided Analysis
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# [!UICONTROL Nutzung] Ansicht

Die **[!UICONTROL Nutzung]** -Ansicht bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Zeitverlauf. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse Ihre gewünschten Ereignisse misst.

![Nutzung](../assets/usage.png)

## Siehe [!UICONTROL Nutzung] Ansicht in Aktion

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Bewertung der Produktleistung**: Trends ermöglichen es Ihnen, die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum zu bewerten. Durch die Analyse von Metriken wie Benutzerinteraktionen, Adoptions- oder Konversionsraten können Sie feststellen, ob die Leistung Ihres Produkts sich verbessert, stagniert oder sinkt.
* **Funktionsbereitstellung**: Trends zeigen Ihnen, wie Benutzer neue Funktionen oder Aktualisierungen übernehmen, die Sie veröffentlichen. Sie können bestimmen, welche Funktionen beliebt sind und welche Funktionen verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datenbasierte Entscheidungen darüber zu treffen, welche Funktionen Ihre Entwicklungsbemühungen priorisieren sollen.
* **Benutzerverhalten**: Trends können Einblicke in das Benutzerverhalten im Zeitverlauf bieten. Indem Sie bestimmte Aktionen untersuchen, die Benutzer ausführen, können Sie Muster identifizieren, in denen Benutzer abbrechen können. Sie können Einblicke aus dieser Ansicht mit [Friktion](friction.md) für noch mehr Einblicke in das Verhalten.
* **A/B-Tests und -Experimente**: Wenn Sie in Ihrem Produkt A/B-Tests durchführen, können Sie mithilfe von Trends messen, welche Tests im Laufe der Zeit am erfolgreichsten sind.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Veranstaltungen]**: Die Ereignisse, die Sie messen möchten. Jedes ausgewählte Ereignis wird je nach Diagrammtyp als farbige Linie oder Gruppe von Balken dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Trendereignis darstellt. Sie können bis zu fünf Ereignisse einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment verdoppelt die Anzahl der Zeilen im Diagramm und Zeilen in der Tabelle. Sie können bis zu fünf Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Nutzung] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören Ereignisse, Sitzungen, Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer.
* **[!UICONTROL Diagrammtyp]**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;, &quot;Balken&quot;, &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Zeitvergleich der Nutzung](../assets/usage-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie mit der Kalenderauswahl einen festen Datumsbereich auswählen.
