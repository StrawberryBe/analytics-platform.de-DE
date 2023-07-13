---
title: Erste Ansicht
description: Messen der Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren.
feature: Guided Analysis
source-git-commit: 9fa4b894e69a25b26632a93f00a655eec8e8aa86
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 5%

---

# Erste Ansicht

{{release-limited-testing}}

Die **Erste Verwendung** -Ansicht zeigt einen Vergleich der Leistung von Schlüsselindikatoren vor und nach der erstmaligen Bearbeitung eines bestimmten Ereignisses durch einen Benutzer. Die horizontale Achse dieses Berichts ist ein relatives Zeitintervall vor und nach dem Ereignis, während die vertikale Achse die gewünschten Schlüsselindikatoren misst. Ein vertikaler Balken in der Mitte des Diagramms gibt an, wann das Ereignis für einen bestimmten Benutzer eintrat.

![Version](../assets/first-use.png)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Analyse neuer Funktionen**: Wenn Sie eine neue Funktion in Ihrem Produkt starten, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der erstmaligen Anzeige der neuen Funktion durch die Benutzer abgeschnitten wurden.
* **Kampagneneffizienz**: Wenn ein Benutzer eine bestimmte Kampagne anzeigt, können Sie vergleichen, wie die Schlüsselindikatoren vor und nach der Anzeige oder Interaktion des Benutzers mit dieser Kampagne abgeschnitten wurden.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Schlüsselindikatoren**: Die Ereignisse, die pro Benutzer gemessen werden sollen. Jeder ausgewählte Schlüsselindikator wird als farbige Linie dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Ereignis darstellt. Sie können bis zu drei Ereignisse einbeziehen.
* **Faktoren**: Für diese Ansicht gibt es zwei Faktoren:
   * **Datum**: Wie weit zurück Sie zum ersten Mal suchen möchten, wenn ein Ereignis berührt wurde.
   * **Ereignis**: Das Ereignis, das Sie vor und nach dem Berühren vergleichen möchten.
* **Personen**: Das Segment, das Sie messen möchten. Das ausgewählte Segment filtert Ihre Daten so, dass sie sich nur auf die Personen konzentrieren, die Ihren Segmentkriterien entsprechen.

## Diagrammeinstellungen

Die Ansicht Erste Verwendung bietet die folgenden Diagrammeinstellungen, die im Menü über dem Diagramm angepasst werden können:

* **Metrik**: Die Metrik, die Sie messen möchten. Optionen umfassen [!UICONTROL Ereignisse pro Benutzer], [!UICONTROL Veranstaltungen], [!UICONTROL Sitzungen]und [!UICONTROL Benutzer].
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;.

## Datumsbereich

Datumsauswahlen in Wirkungsberichten funktionieren anders als andere Analysetypen, da sich der Bericht um ein bestimmtes Ereignis dreht, das zum ersten Mal berührt wird (spezifiziert in der Abfrageleiste). Die folgenden Optionen sind verfügbar:

* **Intervall**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Zu den gültigen Optionen gehören [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich]und [!UICONTROL Quartal]. Eine Änderung des Intervalls wirkt sich auf die für den Zeitraum vor und nach verfügbaren Optionen aus.
* **Vor- und Nach-Zeitraum**: Die Zeitdauer, die vor und nach dem in der Abfrageleiste angegebenen berührten Ereignis analysiert werden soll. Die verfügbaren Optionen hängen von der [!UICONTROL Intervall] auswählen.
