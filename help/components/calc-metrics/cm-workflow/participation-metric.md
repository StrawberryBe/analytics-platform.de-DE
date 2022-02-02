---
description: Mit dem Generator für berechnete Metriken kann jeder Benutzer eine Beitragsmetrik erstellen.
title: Beitragsmetrik
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 100%

---

# Beitragsmetrik

Im Folgenden wird ein einfacher Anwendungsfall beschrieben: Als Inhaber von Inhalt möchten Sie sehen, welche Seiten bei Besuchen beteiligt waren, die zu einer Bestellung geführt haben. So geht’s:

>[!NOTE]
>
>Bisher mussten Sie hierzu die Admin Tools verwenden. Sie können Teilnahmemetriken nach wie vor in der Admin Tools aktivieren, jedoch lediglich für die benutzerdefinierten Ereignisse 1–100.

Im Folgenden wird ein einfacher Anwendungsfall beschrieben: Als Inhaber von Inhalt möchten Sie sehen, welche Seiten bei Besuchen beteiligt waren, die zu E-Mail-Anmeldungen geführt haben. So geht’s:

1. Erstellen Sie eine neue Metrik im Generator für berechnete Metriken.
1. Ziehen Sie das Erfolgsereignis „Bestellungen“ in die Arbeitsfläche „Definition“.
1. Ändern Sie das [Attributionsmodell](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) dieses Ereignisses in **[!UICONTROL Beteiligung]** unter dem Zahnradsymbol für **[!UICONTROL Einstellungen]**. Wählen Sie das Lookback **[!UICONTROL Besuch]**. Die Definition sollte etwa so aussehen:

   ![](assets/participation.png)

1. Speichern Sie die Metrik.
1. Verwenden Sie die berechnete Metrik im Bericht **[!UICONTROL Seiten]**.

   ![](assets/participation-pages.png)

1. (Optional) Geben Sie die Metrik für andere Benutzer in Ihrer Organisation frei.
