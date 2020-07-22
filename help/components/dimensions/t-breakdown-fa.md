---
description: Schlüsseln Sie Dimensionen und Dimensionselemente in Analysis Workspace auf.
keywords: Analysis Workspace
title: Dimensionen aufschlüsseln
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 68%

---


# Dimensionen aufschlüsseln

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Schlüsseln Sie Dimensionen und Dimensionselemente in Analysis Workspace auf.

Sie können Ihre Daten für Ihre spezifischen Anforderungen unbegrenzt aufschlüsseln. Erstellen Sie Abfragen mithilfe relevanter Metriken, Dimensionen, Segmente, Zeitachsen und anderer Aufschlüsselungswerte für die Analyse.

1. [Erstellen Sie ein Projekt](/help/analysis-workspace/home.md) mit einer Datentabelle.
1. Klicken Sie in der Datentabelle mit der rechten Maustaste auf einen Zeileneintrag und wählen Sie **[!UICONTROL Aufschlüsselung]** > *`<item>`* aus.

   ![Schritt Ergebnis](assets/fa_data_table_actions.png)

   Sie können Metriken über ausgewählte Zeiträume nach Dimensionselementen oder Audiencen unterteilen. Sie können auch noch granularer aufschlüsseln.

   >[!NOTE] Die Anzahl der in der Tabelle angezeigten Aufschlüsselungen ist auf 200 beschränkt. Für das Exportieren von Aufschlüsselungen ist diese Einschränkung höher.

[Dimensionen in Analysis Workspace auf YouTube](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:54)

[Dimensionsaufschlüsselungen auf YouTube](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) (2:02)

## Attributionsmodelle auf Aufschlüsselungen anwenden

Für jede Aufschlüsselung innerhalb einer Tabelle können auch beliebige Zuordnungsmodelle angewendet werden. Dieses Zuordnungsmodell kann identisch oder anders als die übergeordnete Spalte sein. Sie können beispielsweise lineare Bestellungen für Ihre Marketing-Kanal-Dimension analysieren, aber U-förmige Bestellungen auf die spezifischen Rückverfolgungscodes in einem Kanal anwenden. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Unterteilungseinstellungen](assets/breakdown_settings.png)
