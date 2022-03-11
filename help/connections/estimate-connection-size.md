---
title: Schätzung der CJA-Verbindungsgröße
description: Bericht zur aktuellen Nutzung von Customer Journey Analytics
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 966274d433d8495d32823d74c5f72107bb5f383a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 48%

---

# Verbindungsgröße schätzen

Möglicherweise müssen Sie die derzeitige Anzahl von Datenzeilen in [!UICONTROL Customer Journey Analytics] kennen. Gehen Sie wie folgt vor, um eine genaue Darstellung der Nutzung der Ereignisdatensätze (Datenzeilen) in Ihrem Unternehmen zu erhalten: **für jede der von Ihrer Organisation erstellten Verbindungen**.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.

   Sie können jetzt eine Liste aller Ihrer aktuellen Verbindungen sehen.

1. Klicken Sie auf jeden Verbindungsnamen, um zum Connections Manager zu gelangen.

1. Fügen Sie die **[!UICONTROL Verfügbare Ereignisdaten]** für alle erstellten Verbindungen. (Je nach Größe Ihrer Verbindung kann es eine Weile dauern, bis die Nummer angezeigt wird.)

   ![Ereignisdaten](assets/event-data.png)

1. Sobald Sie über eine Summe aller Ereignisdatenzeilen verfügen, suchen Sie im Customer Journey Analytics-Vertrag, den Ihr Unternehmen mit Adobe unterzeichnet hat, nach der Berechtigung &quot;Datenzeilen&quot;.

   Dadurch erhalten Sie die maximale Anzahl von Datenzeilen, die im Kundenauftrag genehmigt wurden. Wenn die Anzahl der Datenzeilen, die aus Schritt 3 resultierten, größer ist als diese Zahl, tritt ein Überschuss auf.

1. Um dieses Problem zu beheben, haben Sie mehrere Möglichkeiten:

   * Ändern Sie Ihre [Datenaufbewahrungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#set-rolling-window-for-connection-data-retention).
   * [Nicht verwendete Verbindungen löschen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * [Datensatz in AEP löschen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
   * Wenden Sie sich an Ihren Kundenbetreuer von Adobe, um zusätzliche Kapazitäten zu lizenzieren.

## Über die Nutzung

Nutzungsbeschränkungen werden von Adobe regelmäßig überwacht und durchgesetzt. &quot;Datenzeilen&quot;sind die täglichen durchschnittlichen Datenzeilen, die innerhalb eines Customer Journey Analytics für die Analyse verfügbar sind.

Nehmen wir beispielsweise an, Ihr Vertrag berechtigt Sie zu einer Million Datenzeilen. Angenommen, Sie laden am 1. Tag der Verwendung von Customer Journey Analytics zwei Millionen Datenzeilen hoch. Am Tag 2 löschen Sie 1 Million Zeilen und behalten Ihre Nutzung für den Rest Ihrer Lizenzvereinbarung bei (d. h. maximal eine Million Datenzeilen). Abhängig von Ihren Vertragsbedingungen können Ihnen für Tag 1 weiterhin anteilige Übernutzungsgebühren entstehen, da Sie die Lizenzberechtigung für &quot;Datenzeilen&quot;überschritten haben.

## Diskrepanzen diagnostizieren

In einigen Fällen kann es vorkommen, dass die Gesamtanzahl der von Ihrer Verbindung erfassten Ereignisse sich von der Anzahl der Zeilen im Datensatz in [!UICONTROL Adobe Experience Platform] unterscheidet. In diesem Beispiel enthält der Datensatz „B2B Impression“ 7650 Zeilen, der Datensatz enthält jedoch 3830 Zeilen in [!UICONTROL Adobe Experience Platform]. Es kann mehrere Gründe für Diskrepanzen geben. Die folgenden Schritte können für die Diagnose hilfreich sein:

1. Schlüsseln Sie diese Dimension nach **[!UICONTROL Platform Datensatz-ID]** auf. Sie werden feststellen, dass es zwei Datensätze mit derselben Größe, aber unterschiedlichen **[!UICONTROL Platform Datensatz-IDs]** gibt. Jeder Datensatz enthält 3.825 Aufzeichnungen. Das bedeutet, dass [!UICONTROL Customer Journey Analytics] fünf Datensätze aufgrund fehlender Personen-IDs oder fehlender Zeitstempel ignoriert hat:

   ![Aufschlüsselung](assets/data-size2.png)

1. Wenn wir uns dies in [!UICONTROL Adobe Experience Platform] anschauen, gibt es keinen Datensatz mit der ID „5f21c12b732044194bffc1d0“. Jemand hat also diesen Datensatz bei der Erstellung der ersten Verbindung aus [!UICONTROL Adobe Experience Platform] gelöscht. Später wurde er erneut zu Customer Journey Analytics hinzugefügt, es wurde jedoch eine andere [!UICONTROL Platform-Datensatz-ID] von [!UICONTROL Adobe Experience Platform] generiert.

Weitere Informationen über die [Implikationen beim Löschen von Datensätzen und Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) erhalten Sie in [!UICONTROL Customer Journey Analytics] und [!UICONTROL Adobe Experience Platform].
