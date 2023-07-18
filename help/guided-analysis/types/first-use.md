---
title: Erste Ansicht
description: Messen der Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren.
feature: Guided Analysis
source-git-commit: 4121c199e4a5050d84f57c69d7fb1d7b05007fcd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 3%

---

# [!UICONTROL Erste Verwendung] Ansicht

Die **[!UICONTROL Erste Verwendung]** zeigt einen Vergleich der Leistung von Schlüsselindikatoren, bevor und nachdem ein Benutzer eine Produktfunktion zum ersten Mal verwendet hat. Die horizontale Achse dieses Berichts ist ein relatives Zeitintervall vor und nach dem Ereignis, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms stellt den Tag 0 für den Zeitpunkt dar, zu dem eine Funktion von einem bestimmten Benutzer zum ersten Mal verwendet wird. Da Benutzer nicht immer Funktionen am selben Tag übernehmen und Ihre Rollouts mehrere Tage dauern können, bedeutet Tag 0 für jeden einzelnen Benutzer etwas Anderes.

Siehe [!UICONTROL Erste Verwendung] Ansicht in Aktion

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Analyse neuer Funktionen**: Wenn Sie eine neue Funktion in Ihrem Produkt starten, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Anzeige der neuen Funktion durch die Benutzer abgeschnitten wurden.
* **Schrittweise Rollouts**: Da die Analyse nach der ersten Verwendung der Funktion anstelle eines festen Datums sucht, ist diese Ansicht besonders hilfreich, wenn Sie den Rollout Ihrer Funktionen über einen bestimmten Zeitraum schrittweise durchführen.
* **Neue Produktversionsanalyse**: Wenn Sie eine neue Version Ihres Produkts starten, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Veröffentlichung der neuen Version durch die Benutzer abgeschnitten wurden. Wählen Sie &quot;Beliebiges Ereignis&quot;als Erstes aus und filtern Sie es nach der Eigenschaft Versionsnummer .
* **Verbesserungen vorhandener Funktionen**: Wenn Sie Verbesserungen an einer vorhandenen Funktion in Ihrem Produkt vornehmen, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Veröffentlichung der Benutzer mit diesen neuen Verbesserungen ausgeführt wurden. Sie können diese Analyse je nach Funktionsinstrumentierung auf verschiedene Arten durchführen. 1) Wählen Sie ein Ereignis aus, das die Verbesserung als Ihr Erstverwendungsereignis darstellt, und/oder 2) Wählen Sie das Datum aus, an dem die Änderungen mit dem Rollout begonnen haben, und/oder 3) Segmentieren Sie die Analyse der Gruppe von Personen, die sich der Verbesserung aussetzen.
* **Kampagneneffizienz**: Wenn ein Benutzer von einer Kampagne durchklickt, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der Interaktion des Benutzers mit dieser Kampagne abgeschnitten haben.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Schlüsselindikatoren]**: Die Ereignisse, die pro Benutzer gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **[!UICONTROL Faktoren]**: Für diese Ansicht gibt es zwei Faktoren:
   * **[!UICONTROL Datum]**: Wie weit Sie zurücklegen möchten, um nach dem ersten aufgetretenen Nutzungsereignis zu suchen.
   * **[!UICONTROL Ereignis]**: Das Ereignis, nach dem Sie die Analyse zum ersten Mal verwenden möchten, um sie zu zentrieren.
* **[!UICONTROL Personen]**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen.

## Diagrammeinstellungen

Die Ansicht Erste Verwendung bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **[!UICONTROL Metrik]**: Die Metrik, die Sie messen möchten. Optionen umfassen [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Veranstaltungen], [!UICONTROL Sitzungen]und [!UICONTROL Benutzer].
* **[!UICONTROL Diagrammtyp]**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;.

## Datumsbereich

Die Datumsauswahl in der Impact-Analyse funktioniert anders als bei anderen Analysetypen, da sich die Analyse um das in der Abfrageleiste angegebene Datum dreht. Die folgenden Optionen sind verfügbar:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Zu den gültigen Optionen gehören [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich]und [!UICONTROL Quartal]. Eine Änderung des Intervalls wirkt sich auf die für den Zeitraum vor und nach verfügbaren Optionen aus.
* **[!UICONTROL Vor- und Nach-Zeitraum]**: Die Zeitdauer, die vor und nach dem ersten in der Abfrageleiste angegebenen Anwendungsereignis analysiert werden soll. Die verfügbaren Optionen hängen von der [!UICONTROL Intervall] auswählen.
