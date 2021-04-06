---
description: Sie können Filter aus einem Touchpoint erstellen, Filter als Touchpoint hinzufügen und Workflows über verschiedene Filter in Analysis Workspace hinweg vergleichen.
keywords: Trichteranalyse und Filter;Filter in der Fallout-Analyse;Filter in Fallout vergleichen
title: Filter in Fallout-Analyse anwenden
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# Filter in Fallout-Analyse anwenden

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

Sie können Filter aus einem Touchpoint erstellen, Filter als Touchpoint hinzufügen und Workflows über verschiedene Filter in Analysis Workspace hinweg vergleichen.

>[!IMPORTANT]
>
>Filter, die als Checkpoints in der Trichteranalyse verwendet werden, müssen einen Container verwenden, der auf einer niedrigeren Ebene als der Gesamtkontext der Fallout-Visualisierung liegt. Bei einer Trichteranalyse im Kontext des Besuchers müssen Filter, die als Checkpoints verwendet werden, besuchsbasierte oder trefferbasierte Filter sein. Bei einem Besuchskontext-Fallout müssen als Checkpoint verwendete Filter trefferbasierte Filter sein. Wenn Sie eine ungültige Kombination verwenden, beträgt der Fallout 100 %. Wir haben eine Warnung zur Fallout-Visualisierung hinzugefügt, die angezeigt wird, wenn Sie einen inkompatiblen Filter als Touchpoint hinzufügen. Bestimmte ungültige Kombinationen aus Filter-Containern führen zu ungültigen Trichteranalysediagrammen, z. B.:

* Verwenden eines Besucher-basierten Filters als Touchpoint in einer Fallout-Visualisierung im Besucher-Kontext
* Verwenden eines Besucher-basierten Filters als Touchpoint in einer Fallout-Visualisierung im Besuchskontext
* Verwenden eines besuchsbasierten Filters als Touchpoint in einer Fallout-Visualisierung im Besuchskontext

## Erstellen eines Filters aus einem Touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Erstellen Sie einen Filter aus einem bestimmten Touchpoint, an dem Sie besonders interessiert sind und der möglicherweise für andere Berichte nützlich ist. Dazu klicken Sie mit der rechten Maustaste auf den Touchpoint und wählen **[!UICONTROL Filter aus Touchpoint erstellen]**.

   ![](assets/segment-from-touchpoint.png)

   Der Filter Builder wird geöffnet und mit dem vordefinierten sequenziellen Filter gefüllt, der dem ausgewählten Touchpoint entspricht:

   ![](assets/segment-builder.png)

1. Geben Sie dem Filter einen Titel und eine Beschreibung und speichern Sie ihn.

   Sie können diesen Filter jetzt in jedem beliebigen Projekt verwenden.

## hinzufügen eines Filters als Touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Wenn Sie z. B. sehen möchten, wie Ihre US-Benutzer den Trend verfolgen und den Fallout beeinflussen, ziehen Sie einfach den Filter für US-Benutzer in den Fallout:

![](assets/segment-touchpoint.png)

Oder Sie erstellen einen AND-Touchpoint, indem Sie den Filter für US-Benutzer auf einen anderen Checkpoint ziehen.

## Filter im Fallout {#section_E0B761A69B1545908B52E05379277B56} vergleichen

Sie können eine unbegrenzte Anzahl von Filtern in der Fallout-Visualisierung vergleichen.

1. Wählen Sie die zu vergleichenden Filter in der Leiste [!UICONTROL Filter] links aus. In unserem Beispiel haben wir 2 Filter ausgewählt: US-Benutzer und Nicht-US-Benutzer.
1. Ziehen Sie sie in den Filterbereich oben.

   ![](assets/segment-drop.png)

1. Optional: Sie können „Alle Besuche“ als Standardcontainer belassen oder löschen.

   ![](assets/seg-compare.png)

1. Sie können nun den Trichteranalysebericht über die beiden Filter hinweg vergleichen, z. B., wo ein Filter einen anderen übertrifft, oder andere Einblicke.
