---
description: Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoint hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.
keywords: Fallout und Filter;Filter in Fallout-Analyse;Filter in Fallout vergleichen
title: Filter in Fallout-Analyse anwenden
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 13%

---

# Filter in Fallout-Analyse anwenden

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Sie können in Analysis Workspace Filter aus einem Touchpoint erstellen, Filter als Touchpoint hinzufügen und wichtige Workflows über verschiedene Filter hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in Fallout verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einem Besucherkontext-Fallout müssen Filter, die als Checkpoints verwendet werden, besuchs- oder trefferbasierte Filter sein. Bei einem besuchskontextbezogenen Fallout müssen Filter, die als Checkpoint verwendet werden, trefferbasierte Filter sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wir haben eine Warnung zur Fallout-Visualisierung hinzugefügt, die angezeigt wird, wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen. Bestimmte ungültige Filter-Container-Kombinationen führen zu ungültigen Fallout-Diagrammen, z. B.:

* Verwenden eines besucherbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung des Besucherkontexts
* Verwenden eines besucherbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung für Besuche
* Verwenden eines besuchsbasierten Filters als Touchpoint innerhalb einer Fallout-Visualisierung für Besuche

## Erstellen eines Filters aus einem Touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, der besonders für Sie von Interesse ist und der sich für andere Berichte nützlich sein kann. Klicken Sie dazu mit der rechten Maustaste auf den Touchpoint und wählen Sie **[!UICONTROL Filter aus Touchpoint erstellen]** aus.

   ![](assets/segment-from-touchpoint.png)

   Der Filter Builder wird geöffnet und vorab mit dem vordefinierten sequenziellen Filter gefüllt, der mit dem ausgewählten Touchpoint übereinstimmt:

   ![](assets/segment-builder.png)

1. Geben Sie dem Filter einen Titel und eine Beschreibung und speichern Sie ihn.

   Sie können diesen Filter jetzt in jedem beliebigen Projekt verwenden.

## Filter als Touchpoint hinzufügen {#section_17611C1A07444BE891DC21EE8FC03EFC}

Wenn Sie z. B. sehen möchten, wie Ihre US-Benutzer Trend verfolgen und den Fallout beeinflussen, ziehen Sie einfach den Filter für US-Benutzer in den Fallout:

![](assets/segment-touchpoint.png)

Alternativ können Sie einen AND-Touchpoint erstellen, indem Sie den Filter für US-Benutzer auf einen anderen Checkpoint ziehen.

## Filter im Fallout vergleichen {#section_E0B761A69B1545908B52E05379277B56}

Sie können eine unbegrenzte Anzahl von Filtern in der Fallout-Visualisierung vergleichen.

1. Wählen Sie die zu vergleichenden Filter in der Leiste [!UICONTROL Filter] auf der linken Seite aus. In unserem Beispiel haben wir 2 Filter ausgewählt: US-Benutzer und Nicht-US-Benutzer.
1. Ziehen Sie sie in die Dropzone Filter oben.

   ![](assets/segment-drop.png)

1. Optional: Sie können „Alle Besuche“ als Standardcontainer belassen oder löschen.

   ![](assets/seg-compare.png)

1. Sie können jetzt den Fallout über die beiden Filter hinweg vergleichen, z. B. wo ein Filter eine bessere Leistung erzielt, oder andere Einblicke.
