---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: e7019722871dfac60408748aa183ca6d76f4993a
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 6%

---

# Erstellen einer Beitragsmetrik

In diesem Artikel wird erläutert, wie Sie eine Beitragsmetrik erstellen. Eine Beitragsmetrik zeigt an, wie einzelne Werte für eine Dimension (wie Seitenansichten, Marketingkanal) zu Sitzungen beitragen oder an Sitzungen teilnehmen, die eine bestimmte Metrik enthalten (z. B. Bestellungen).

Diese Art von Informationen kann für jeden Inhaltsbesitzer nützlich sein.

>[!NOTE]
>
>Metriken mit anderen Attributionsmodellen, wie z. B. Beitrag, können auch von Administratoren als Teil einer [Datenansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de). Siehe [Einstellungen der Attribution-Komponente](../../../data-views/component-settings/attribution.md) für weitere Details.<br/>Das folgende Beispiel zeigt, wie eine Beitragsmetrik von jedem Benutzer erstellt werden kann, der Zugriff auf den Generator für berechnete Metriken in Workspace hat.


1. Beginnen Sie mit der Erstellung einer Metrik, wie unter [Metriken erstellen](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Benennen Sie die Metrik im Generator für berechnete Metriken. `Participation` oder etwas Ähnliches.
1. Ziehen Sie eine Metrik, die beispielsweise ein Erfolgsereignis enthält. [!DNL Orders]in die [!UICONTROL Definition] Arbeitsfläche.
1. Auswählen ![Fanggerät](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) für die Metrik.
1. Wählen Sie im angezeigten Popup-Fenster **[!UICONTROL Nicht standardmäßiges Attributionsmodell verwenden]** , um die [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) des Ereignisses **[!UICONTROL Beitrag]** und wählen **[!UICONTROL Sitzung]** für die [!UICONTROL Lookback]. Auswählen **[!UICONTROL Anwenden]** zur Bestätigung.

   Im Feld Definition wird die ausgewählte Metrik durch Anhängen aktualisiert.  **(Partizipation|Sitzung)** auf ihren Namen.

   ![](assets/participation-setup.png)



1. Auswählen [!UICONTROL **Speichern**] , um die Metrik zu speichern.
1. Verwenden Sie die berechnete Metrik in Ihrem Bericht. Verwenden Sie beispielsweise die berechnete [!DNL Orders (Session Participation)] Metrik (wie in Schritt 5 definiert) in einem Bericht zu zeigen, an welcher Kundenebene Sitzungen beteiligt waren, die eine Bestellung enthielten.

   ![](assets/participation-pages-customer-tier.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei, wie beschrieben in [Berechnete Metriken freigeben](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
