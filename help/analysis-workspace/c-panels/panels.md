---
description: 'null'
title: Übersicht über Bedienfelder
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 91%

---


# Übersicht über Bedienfelder

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Ein Bedienfeld ist eine Sammlung von Tabellen und Visualisierungen. Sie können auf Bedienfelder über das Symbol oben links in Workspace zugreifen. Bedienfelder sind hilfreich, wenn Sie Ihre Projekte anhand von Zeiträumen, Geschäftsbereichen, Standorten usw. organisieren möchten. Diese vier Paneltypen stehen in Analysis Workspace zum Customer Journey Analytics zur Verfügung:

* [Leeres Bedienfeld](blank-panel.md)
* [Bedienfeld „Quick Insights“](quickinsight.md)
* [Attributionsbedienfeld](attribution.md)
* [Freiform-Bedienfeld](freeform-panel.md)

Quick Insight-, Blank- und Freiform-Bedienfelder eignen sich hervorragend zum Beginn Ihrer Analyse, während sich das Bedienfeld &quot;Attribution IQ&quot;für erweiterte Analysen eignet. In Projekten steht eine `"+"`-Schaltfläche zur Verfügung, mit der Sie jederzeit leere Bedienfelder hinzufügen können.

Das standardmäßige Startbedienfeld ist das Freiform-Bedienfeld. Sie können jedoch auch das [leere Bedienfeld](/help/analysis-workspace/c-panels/blank-panel.md) als Ihren Standard festlegen.

## Dropdown-Filter in Bedienfeldern

Die Dropzone für Bedienfelder verfügt über Dropdown-Filterfunktionen. Mit diesen Filtern können Sie kontrolliert mit den Projektdaten interagieren und somit tiefgreifende Analysen durchführen, Ihre Projekte vereinfachen und/oder Erkenntnisse mit anderen teilen.

Beispiel für ein vereinfachtes Projekt: Angenommen, Sie haben für länderspezifisches Reporting mehrere Versionen eines Projekts/Bedienfelds. Jetzt können Sie diese Projekte/Bedienfelder zu einem einzigen Projekt komprimieren und stattdessen ein Dropdown für Länder hinzufügen, um verschiedene Datensätze herauszufiltern.

![](assets/dropdowns.png)

Beachten Sie:

* Sie können mehrere Komponenten (oder Dimensionselemente) miteinbeziehen und dann in einem Dropdown zwischen ihnen wechseln, um den Bedienfeldinhalt zu filtern.
* Sie können außerdem mehrere Dropdown-Listen auf demselben Bedienfeld erstellen.
* Sie können den Titel der Dropdown-Liste anpassen, indem Sie auf den Titel klicken und ihn ändern, oder den Titel ganz entfernen, indem Sie auf das „x“ daneben klicken.
* Sie können Dropdown-Filter mit jedem Komponententyp erstellen: Dimensionen, Datumsbereichen, Segmenten und Metriken. Beachten Sie, dass Dropdown-Datumsbereiche immer die Datumsbereiche des Bedienfelds überschreiben.
* Wir behalten die Komponentenfarben von der linken Leiste bei: Gelb für Dimensionen, Grün für Metriken, Blau für Segmente und Violett für Datumsbereiche.
* Die Dropzone erstellt weiterhin Hit-Segmente für Elemente, die als Segmente hineingezogen werden. Sie können sie wie gewohnt ändern, indem Sie auf das Informationssymbol (i) neben dem Segment klicken, dann das stiftförmige Bearbeitungssymbol auswählen und die Bearbeitung im Segment Builder durchführen.

**So erstellen und verwenden Sie Dropdown-Filter:**

1. Wählen Sie beliebige Elemente aus der linken Leiste aus und legen Sie sie **bei gedrückter -Taste** in der Dropzone des Bedienfelds ab.

   ![](assets/create_dropdown.png)

   Dadurch werden die Komponenten in eine Dropdown-Liste und nicht in ein Segment umgewandelt. (Sie können auch weitere Segmente hinzufügen, indem Sie die -Taste nicht gedrückt halten.)

   ![](assets/dropdown.png)

1. Wählen Sie eine der Optionen aus der Dropdown-Liste aus, um die Daten im unteren Bedienfeld zu ändern. (Sie können auch auf die Filterung von Bedienfelddaten verzichten, indem Sie **[!UICONTROL Kein Filter]** auswählen.)
1. Wenn Sie beispielsweise die Daten auch nach Marketing-Kanälen aufteilen möchten, können Sie ein weiteres Dropdown namens „Marketing-Kanal“ hinzufügen:

   ![](assets/mc_dropdown.png)

