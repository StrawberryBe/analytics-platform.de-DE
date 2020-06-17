---
description: Sie können in Analysis Workspace Segmente aus einem Touchpoint erstellen, Segmente als Touchpoints hinzufügen und wichtige Workflows über verschiedene Segmente hinweg vergleichen.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Segmente in der Fallout-Analyse anwenden
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 16%

---


# Anwenden von Filtern in der Fallout-Analyse

>[!NOTE] Sie sehen sich die Dokumentation zum Analysis Workspace in Customer Journey Analytics an. Das Funktionssatz unterscheidet sich geringfügig von dem [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Sie können Filter aus einem Touchpoint erstellen, Segmente als Touchpoint hinzufügen und wichtige Workflows über verschiedene Filter in Analysis Workspace hinweg vergleichen.

>[!IMPORTANT] Filter, die als Checkpoints in der Trichteranalyse verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einer Trichteranalyse im Kontext des Besuchers müssen Filter, die als Checkpoints verwendet werden, besuchsbasierte oder trefferbasierte Filter sein. Bei einer besuchskontextbezogenen Trichteranalyse müssen Filter, die als Checkpoint verwendet werden, trefferbasierte Segmente sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wir haben eine Warnung zur Fallout-Visualisierung hinzugefügt, die angezeigt wird, wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen. Bestimmte ungültige Kombinationen aus Filter-Containern führen zu ungültigen Trichteranalysediagrammen, z. B.:

* Verwenden eines Besucher-basierten Filters als Touchpoint in einer Fallout-Visualisierung im Besucher-Kontext
* Verwenden eines Besucher-basierten Filters als Touchpoint in einer Fallout-Visualisierung im Besuchskontext
* Verwenden eines besuchsbasierten Filters als Touchpoint in einer Fallout-Visualisierung im Besuchskontext

## Create a filter from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, an dem Sie besonders interessiert sind und der möglicherweise für andere Berichte nützlich ist. You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Der Filter Builder wird geöffnet und mit dem vordefinierten sequenziellen Filter gefüllt, der dem ausgewählten Touchpoint entspricht:

   ![](assets/segment-builder.png)

1. Geben Sie dem Filter einen Titel und eine Beschreibung und speichern Sie ihn.

   Sie können diesen Filter jetzt in jedem beliebigen Projekt verwenden.

## Add a filter as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Wenn Sie z. B. sehen möchten, wie Ihre US-Benutzer den Trend verfolgen und den Fallout beeinflussen, ziehen Sie einfach den Filter für US-Benutzer in den Fallout:

![](assets/segment-touchpoint.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie den Filter für US-Benutzer auf einen anderen Checkpoint ziehen.

## Compare filters in fallout {#section_E0B761A69B1545908B52E05379277B56}

Sie können eine unbegrenzte Anzahl von Filtern in der Fallout-Visualisierung vergleichen.

1. Select the segments you want to compare from the [!UICONTROL Filter] rail on the left. Im vorliegenden Beispiel haben wir 2 Segmente ausgewählt: „USA-Benutzer“ und „Benutzer außerhalb der USA“.
1. Ziehen Sie sie in den Filterbereich oben.

   ![](assets/segment-drop.png)

1. Optional: Sie können „Alle Besuche“ als Standardcontainer belassen oder löschen.

   ![](assets/seg-compare.png)

1. Sie können nun den Trichteranalysebericht über die beiden Filter hinweg vergleichen, z. B., wo ein Filter einen anderen übertrifft, oder andere Einblicke.
