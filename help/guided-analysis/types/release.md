---
title: Versionsansicht
description: Leistung in gleichen Zeiträumen vor und nach Veröffentlichung vergleichen.
feature: Guided Analysis
source-git-commit: aca4a5091c65d7243f79551be7cee615ba98bb26
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 4%

---

# Versionsansicht

{{release-limited-testing}}

Die **Version** zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach einem bestimmten Datum. Die horizontale Achse dieses Berichts ist ein Zeitintervall, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt das Datum dar, das Sie vor und nach dem vergleichen möchten. Dieses Datum stellt in der Regel eine erhebliche Änderung am Produkt dar, mit dem Sie messen möchten, z. B. eine Aktualisierung des Produkts oder einen Kampagnen-Start.

![Version](../assets/release.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Allgemeine Leistungsbewertung:** Der Vergleich der wichtigsten Indikatoren insgesamt, wie z. B. der Umsatz, kann Ihnen dabei helfen festzustellen, ob eine Version insgesamt erfolgreich war.
* **Funktionsbereitstellung**: Wenn sich eine Produktaktualisierung auf die Verbesserung einer bestimmten Funktion konzentriert, können Sie diese Ansicht verwenden, um die Nutzung dieser Funktion vor und nach der Produktaktualisierung direkt zu vergleichen.
* **Fehlererkennung**: Das Tracking der Anzahl der Fehler vor und nach einer Version kann einen frühzeitigen Indikator für Kundenprobleme liefern. Wenn Sie unmittelbar nach einer Veröffentlichung einen Anstieg der Fehler feststellen, können Sie mit Entwicklungs- oder Entwicklungsteams zusammenarbeiten, um das Problem zu identifizieren und zu beheben, wodurch weitere Auswirkungen für Kunden vermieden werden.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Schlüsselindikatoren**: Die Ereignisse, die pro Benutzer gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **Faktoren**: Das Datum, das Sie vor und nach dem vergleichen möchten.
* **Personen**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen.

## Diagrammeinstellungen

Die Freigabeansicht bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **Metrik**: Die Metrik, die Sie messen möchten. Optionen umfassen [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Prozentsatz der Benutzer], [!UICONTROL Veranstaltungen], [!UICONTROL Sitzungen]und [!UICONTROL Benutzer].
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;.

## Datumsbereich

Die Datumsauswahl in Folgenabschätzungsberichten funktioniert anders als bei anderen Analysetypen, da sich der Bericht um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **Intervall**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Zu den gültigen Optionen gehören [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich]und [!UICONTROL Quartal]. Eine Änderung des Intervalls wirkt sich auf die für den Zeitraum vor und nach verfügbaren Optionen aus.
* **Vor- und Nach-Zeitraum**: Die Zeitdauer, die vor und nach dem in der Abfrageleiste angegebenen Datum analysiert werden soll. Die verfügbaren Optionen hängen von der [!UICONTROL Intervall] auswählen.
