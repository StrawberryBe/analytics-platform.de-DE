---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# Erstellen einer Metrik vom Typ „Teilnahme“

In diesem Artikel wird erläutert, wie Sie eine Metrik erstellen, die zeigt, wie einzelne Werte für eine ausgewählte Dimension (z. B. Seitenansichten, Marketing-Kanal, App-Version) zu Sitzungen beigetragen haben (oder an Sitzungen teilgenommen haben), die eine Bestellung enthielten.

Diese Art von Informationen kann für jeden Inhaltsbesitzer nützlich sein.

>[!NOTE]
>
>Metriken mit anderen Attributionsmodellen, wie z. B. Beitrag, können auch von Administratoren als Teil einer [Datenansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de). Das folgende Beispiel zeigt, wie sie von jedem Benutzer erstellt werden können, der Zugriff auf den Generator für berechnete Metriken in Workspace hat.

1. Beginnen Sie mit der Erstellung einer Metrik, wie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nennen Sie die Metrik im Generator für berechnete Metriken &quot;Beitrag&quot;oder eine ähnliche Metrik.
1. Ziehen Sie das Erfolgsereignis „Bestellungen“ in die Arbeitsfläche „Definition“.
1. Auswählen ![Fanggerät](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) für die [!DNL Orders] Metriken.
1. Wählen Sie im angezeigten Popup-Fenster **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** , um die [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) des Ereignisses **[!UICONTROL Beitrag]** und wählen **[!UICONTROL Sitzung]** für die [!UICONTROL Lookback]. Auswählen **[!UICONTROL Anwenden]** zur Bestätigung.

   Im Feld &quot;Definition&quot; ![Ereignis](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Bestellungen** aktualisiert auf ![Ereignis](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Bestellungen (Partizipation|Sitzung)**.

   ![](assets/participation-setup.png)



1. Auswählen [!UICONTROL **Speichern**] , um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik in Ihrem Bericht. Unter der berechneten Metrik wird in einem Bericht verwendet, um anzuzeigen, welche Kundenebene zu Sitzungen beigetragen hat (oder an solchen teilgenommen hat), die eine Bestellung enthielten.

   ![](assets/participation-pages-customer-tier.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie beschrieben in [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
