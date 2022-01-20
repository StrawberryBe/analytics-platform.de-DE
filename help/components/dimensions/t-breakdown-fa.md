---
description: Schlüsseln Sie Dimensionen und Dimensionselemente in Analysis Workspace auf.
keywords: Analysis Workspace
title: Dimensionen aufschlüsseln
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
source-git-commit: 0176f10ffed85786b0bfa77204ca7a19d9c39ba7
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 53%

---

# Aufschlüsseln von Dimensionen im Workspace

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=de). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Schlüsseln Sie Dimensionen und Dimensionselemente in Analysis Workspace auf.

Aufschlüsseln Ihrer Daten auf unbegrenzte Weise für Ihre spezifischen Anforderungen; Abfragen mit relevanten Metriken, Dimensionen, Filtern, Zeitlinien und anderen Analyseaufschlüsselungswerten erstellen.

1. [Erstellen Sie ein Projekt](/help/analysis-workspace/home.md) mit einer Datentabelle.
1. Klicken Sie in der Datentabelle mit der rechten Maustaste auf einen Zeileneintrag und wählen Sie **[!UICONTROL Aufschlüsselung]** > *`<item>`* aus.

   ![Ergebnis des Schritts](assets/fa_data_table_actions.png)

   Sie können Metriken nach Dimensionselementen oder Zielgruppenfiltern über ausgewählte Zeiträume aufschlüsseln. Sie können auch noch granularer aufschlüsseln.

   >[!NOTE]
   >
   >Die Anzahl der in der Tabelle angezeigten Aufschlüsselungen ist auf 200 beschränkt. Für das Exportieren von Aufschlüsselungen ist diese Einschränkung höher.

**Video: Dimensionen in Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: Aufschlüsselung der Dimensionen**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Attributionsmodelle auf Aufschlüsselungen anwenden

Auf jede Aufschlüsselung innerhalb einer Tabelle kann auch ein beliebiges Attributionsmodell angewandt werden. Dieses Attributionsmodell kann mit der übergeordneten Spalte identisch sein oder sich von ihr unterscheiden. Sie können beispielsweise lineare Bestellungen in Ihrer Dimension „Marketing-Kanäle“ analysieren, jedoch U-förmige Bestellungen auf spezifische Trackingcodes in einem Kanal anwenden. Bewegen Sie zum Bearbeiten des auf eine Aufschlüsselung angewendeten Attributionsmodells einfach den Mauszeiger auf das Aufschlüsselungsmodell und klicken Sie auf **[!UICONTROL Bearbeiten]**:

![Aufschlüsselungseinstellungen](assets/breakdown_settings.png)

Dies ist das erwartete Verhalten beim Anwenden von Attributionsmodellen auf Aufschlüsselungen oder deren Bearbeitung:

* Wenn Sie eine Attribution anwenden, wenn keine anderen Attribute vorhanden sind, gilt die Attribution für die gesamte Spaltenstruktur.

* Wenn Sie eine Aufschlüsselung hinzufügen, nachdem eine Attribution angewendet wurde, wird für die hinzugefügte Aufschlüsselung der Standardwert verwendet (wenn diese Dimension einen Standardwert aufweist). Andernfalls wird die Aufschlüsselung aus der übergeordneten Spalte verwendet. Einige Dimensionen haben eine Standardzuordnung. Beispielsweise verwenden Zeitdimensionen und Referrer Same Touch. Die Dimension &quot;Produkt&quot;verwendet &quot;Letztkontakt&quot;. Andere Dimensionen haben keine Standardeinstellung und verwenden die Zuordnung der übergeordneten Spalte.

* Wenn sich bereits Attribute in der Spaltenstruktur befinden, wirkt sich eine Änderung der Attribution nur auf die Zuordnung aus, die Sie bearbeiten.

## Videos

Hinzufügen von Dimensionen und Metriken zu Ihrem Projekt in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Arbeiten mit Dimensionen in einer Freiformtabelle:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Aufschlüsselung der Dimension nach Position:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
