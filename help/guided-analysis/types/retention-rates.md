---
title: Retentionsquoten
description: Messen, wie viele Benutzende weiterhin Ihr Produkt nutzen.
feature: Guided Analysis
keywords: Produktanalyse
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 2%

---

# Retentionsquoten

Die **[!UICONTROL Treuerate]** zeigt den Prozentsatz der Benutzer an, die nach ihrer anfänglichen Interaktion innerhalb des gewünschten Datumsbereichs zurückkehren. Die horizontale Achse stellt die Anzahl der Tage seit der ersten Interaktion eines Benutzers dar. Die vertikale Achse stellt den Prozentsatz der Benutzer dar, die wieder interagieren.

Diese Analyse zählt Benutzer anhand von zwei wichtigen Ereignissen:

* Das erste Mal, dass ein Benutzer mit dem Ereignis innerhalb des Datumsbereichs interagiert
* Die letzte Interaktion eines Benutzers mit dem Ereignis innerhalb des analysierten Datumsbereichs

Der Behälter &quot;Tag 0&quot;für die Dauer stellt das erste Mal dar, dass ein Benutzer mit dem Ereignis interagiert, und entspricht immer genau 100 %. Die Zeit, die zwischen der anfänglichen Interaktion und der rückkehrenden Interaktion vergeht, bestimmt, unter welcher Position der Benutzer erscheint.

* Wenn ein Benutzer innerhalb des gewünschten Datumsbereichs (die anfängliche Interaktion) nur einmal mit dem Ereignis interagiert, werden diese nur im Bereich &quot;Tag 0&quot;für die Dauer angezeigt.
* Wenn ein Benutzer mehrere Tage mit dem Ereignis interagiert, nachdem er sich erstmals für die Aufnahme in die Analyse qualifiziert hat, werden diese im Behälter für die neueste qualifizierende Dauer und in allen dazugehörigen Zeitspannen-Behältern angezeigt.
* Wenn ein Benutzer das Ereignis im konfigurierten Datumsbereich mehrmals aktiviert, werden nur die ersten und letzten Ereignisse in die Analyse aufgenommen.

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Kohortenanalyse**: Gruppieren Sie Benutzer basierend auf Ereignissen wie Anmeldungen oder Käufen in Kohorten. Sie können die Treue dieser Gruppen vergleichen und bestimmen, wie das Benutzererlebnis dieser Gruppe verbessert werden kann.
* **Abonnement-Dienstanalyse**: Wenn Ihr Produkt ein Abonnement oder ein anderes Modell für den wiederkehrenden Umsatz verwendet, können Sie den Prozentsatz der Benutzer sehen, die Ihr Produkt optimal nutzen. Diejenigen, die Ihr Produkt oder Ihre Dienstleistung nicht verwenden, werden mit höherer Wahrscheinlichkeit abwandern, sodass Sie diese Benutzer identifizieren und sich darauf konzentrieren können.
* **Benutzerinteraktion**: Evaluieren Sie, wie bestimmte Typen von Benutzern mit Ihrem Produkt interagieren, und vergleichen Sie, wie oft sie zurückkehren. Ein bestimmtes Segment mit einer höheren Aufbewahrungskurve als andere bietet Ihnen Einblicke in die Verbesserung potenzieller untergeordneter Erlebnisse, über die es möglicherweise verfügt.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Start- und Rückkehrereignis]**: Die Ereigniskriterien, mit denen ein Benutzer interagieren muss, um sich für die Aufnahme in Ihre Analyse zu qualifizieren. Ein Ereignis wird unterstützt, Sie können jedoch Eigenschaftenfilter einbeziehen.
* **[!UICONTROL Personen]**: Die Segmente, die Sie messen möchten. Jedes ausgewählte Segment fügt der Kohortentabelle eine Zeile hinzu. Sie können bis zu drei Segmente einbeziehen.

## Diagrammeinstellungen

Die [!UICONTROL Treuerate] Die Ansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Wie Sie Benutzer beibehalten messen möchten. Optionen umfassen [!UICONTROL Benutzer beibehalten] und [!UICONTROL Prozentsatz der einbehaltenen Benutzer].
* **[!UICONTROL Diagrammtyp]**: Der Visualisierungstyp, den Sie verwenden möchten. Optionen umfassen [!UICONTROL Balken] und [!UICONTROL Linie].

## Einstellungen für die Dauer

Damit können Sie steuern, wie die Analyse Benutzer nach der Anzahl der verstrichenen Tage anzeigt.

* **[!UICONTROL Automatische Dauer]**: Legen Sie automatisch Dauern basierend auf der Länge des Datumsbereichs und der Nähe zum aktuellen Tag fest, in dem sich der Datumsbereich befindet.
* **[!UICONTROL Benutzerdefinierte Dauer]**: Legen Sie die gewünschten verstrichenen Tage manuell fest. Sie können vier Zeiträume festlegen.

Sie können keine Dauer festlegen, die länger dauert, bis ein Benutzer mit einem Ereignis interagiert und sich für den Behälter der letzten Dauer qualifiziert, bevor er den aktuellen Tag erreicht. Wenn das aktuelle Datum beispielsweise der 30. September ist und der konfigurierte Datumsbereich zwischen dem 1. September und dem 30. September liegt, beträgt die maximale Dauer für diesen Datumsbereich 14 Tage.

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Aufbewahrungsdaten anzeigen möchten. Gültige Optionen sind &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf automatisch festgelegte Dauer-Tage auswirken.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie die Kalenderauswahl verwenden, um einen festen Datumsbereich auszuwählen.

Wenn Sie einen Datumsbereich auswählen, der nahe am aktuellen Tag liegt, werden Benutzer, die sich anfangs zu nah am aktuellen Tag engagieren, nicht einbezogen. Diese Analyse gibt allen Benutzern immer die Möglichkeit, in alle Zeitspannen-Buckets aufgenommen zu werden. Eine Meldung unter der Kalenderauswahl enthält Informationen zum Datumsbereich, in dem Benutzer interagieren, und zum Intervall, das nur für wiederkehrende Benutzer reserviert ist:

* **Analysieren der ersten [Datumsbereich] der Kohorte [Datumsbereich]**: Wenn ein Benutzer innerhalb dieses Datumsbereichs mit dem Ereignis interagiert, werden diese in die Analyse einbezogen. Dieser Datumsbereich garantiert allen Benutzern ausreichend Zeit, um sich für alle Zeitspannen-Behälter zu qualifizieren. Dieser Datumsbereich kann sich von Ihrer Auswahl unterscheiden, wenn er nahe dem aktuellen Tag liegt.
* **Das endgültige [Datumsbereich] ist für den Abschluss der Analyse reserviert.**: Wenn ein Benutzer innerhalb dieses Intervalls zum ersten Mal mit dem Ereignis interagiert, erfolgt dies wie folgt: **not** in die Analyse einbezogen werden. Benutzer, die innerhalb dieses Intervalls anfänglich mit dem Ereignis interagieren, können sich nicht für alle Zeitspannen-Behälter qualifizieren oder außerhalb des gewünschten Datumsbereichs liegen.

## Kohortentabelle

Die Tabelle unter dem Diagramm bietet eine aggregierte Ansicht (ähnlich den Diagrammdaten) und eine vollständige Kohortentabelle. Die vollständige Kohortentabelle enthält Details zu den einzelnen Datumsintervallen und zur Interaktion der Benutzer.
