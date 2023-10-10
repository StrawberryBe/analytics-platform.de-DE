---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d55df4ea2086278a243af51b698a9822a9a04e04
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 32%

---

# Erstellen einer Metrik vom Typ „Teilnahme“

Die folgenden Informationen erläutern, wie Sie eine Metrik erstellen, die anzeigt, welche Seiten zu Sitzungen beigetragen haben (oder an Sitzungen teilgenommen haben), die eine Bestellung enthielten.

Diese Art von Informationen kann für jeden Inhaltsbesitzer nützlich sein.

>[!NOTE]
>
>Metriken mit anderen Attributionsmodellen, wie z. B. Beitrag, können auch von Administratoren als Teil einer [Datenansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de). Das folgende Beispiel zeigt, wie sie von jedem Benutzer erstellt werden können, der Zugriff auf den Generator für berechnete Metriken in Workspace hat.

1. Beginnen Sie mit der Erstellung einer Metrik, wie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nennen Sie die Metrik im Generator für berechnete Metriken &quot;Beitrag&quot;oder eine ähnliche Metrik.
1. Ziehen Sie das Erfolgsereignis „Bestellungen“ in die Arbeitsfläche „Definition“.
1. Ändern Sie das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses in **[!UICONTROL Beteiligung]** unter dem Zahnradsymbol für **[!UICONTROL Einstellungen]**. Auswählen **[!UICONTROL Sitzung]** Lookback. Die Definition sollte etwa so aussehen:

   ![](assets/participation.png)

1. Auswählen [!UICONTROL **Speichern**] , um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik im Bericht **[!UICONTROL Seiten]**.

   ![](assets/participation-pages.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie beschrieben in [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
