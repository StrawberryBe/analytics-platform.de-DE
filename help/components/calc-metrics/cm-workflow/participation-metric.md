---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 32%

---

# Metrik &quot;Beitrag&quot;erstellen

Die folgenden Informationen erläutern, wie Sie eine Metrik erstellen, die anzeigt, welche Seiten zu Sitzungen beigetragen haben (oder an Sitzungen teilgenommen haben), die eine Bestellung enthielten.

Diese Art von Informationen kann für jeden Inhaltsbesitzer nützlich sein.

>[!NOTE]
>
>Sie können Beitragsmetriken in den Admin Tools aktivieren, jedoch nur für benutzerspezifische Ereignisse 1-100.

1. Beginnen Sie mit der Erstellung einer Metrik, wie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nennen Sie die Metrik im Generator für berechnete Metriken &quot;Beitrag&quot;oder eine ähnliche Metrik.
1. Ziehen Sie das Erfolgsereignis „Bestellungen“ in die Arbeitsfläche „Definition“.
1. Ändern Sie das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses in **[!UICONTROL Beteiligung]** unter dem Zahnradsymbol für **[!UICONTROL Einstellungen]**. Auswählen **[!UICONTROL Sitzung]** Lookback. Die Definition sollte etwa so aussehen:

   ![](assets/participation.png)

1. Auswählen [!UICONTROL **Speichern**] , um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik im Bericht **[!UICONTROL Seiten]**.

   ![](assets/participation-pages.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie hier beschrieben: [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
