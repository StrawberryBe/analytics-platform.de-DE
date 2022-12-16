---
title: Schätzen und Verwalten der CJA-Nutzung
description: Zeigt zwei Methoden zur Schätzung der Nutzung und eine Methode zu ihrer Verwaltung an.
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# Schätzen und Verwalten der CJA-Nutzung

Um Ihre CJA-Nutzung zu verstehen, können Sie zwei Methoden verwenden:

* Fügen Sie die Ereignisdaten für jede Verbindung hinzu (siehe **Geschätzte Verbindungsgröße** unten)
* Verwenden von Analysis Workspace zu ...

So verwalten Sie Ihre CJA-Nutzung:

* Verwenden der CJA-API

## Verbindungsgröße schätzen {#estimate-size}

Möglicherweise müssen Sie wissen, wie viele Zeilen von Ereignisdaten sich derzeit in der [!UICONTROL Customer Journey Analytics]. Gehen Sie **für jede der von Ihrem Unternehmen erstellten Verbindungen** wie folgt vor, um genaue Informationen zur Nutzung der Ereignisdatensätze (Datenzeilen) in Ihrem Unternehmen zu erhalten.

>[!NOTE]
>
>Führen Sie dies am ersten Freitag eines jeden Monats aus, da Adobe Ihren aktuellen Nutzungsbericht an diesem Tag ausführt.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.

   Dadurch wird eine Liste aller Ihrer aktuellen Verbindungen angezeigt.

1. Klicken Sie auf einen Verbindungsnamen, um zum Verbindungs-Manager zu gelangen.

1. Fügen Sie für alle erstellten Verbindungen die **[!UICONTROL verfügbaren Ereignisdaten]** hinzu. (Je nach Größe Ihrer Verbindung kann es eine Weile dauern, bis die Anzahl angezeigt wird.)

   ![Ereignisdaten](assets/event-data.png)

1. Sobald Sie über die Summe aller Ereignisdatenzeilen verfügen, suchen Sie im Customer Journey Analytics-Vertrag, den Ihr Unternehmen mit Adobe unterzeichnet hat, nach der Berechtigung für „Datenzeilen“.

   Dadurch erhalten Sie die maximale Anzahl von Datenzeilen, die im Kundenauftrag genehmigt wurden. Wenn die Anzahl der Datenzeilen, die sich aus Schritt 3 ergaben, größer ist als diese Zahl, besteht eine Überschreitung des Limits.

1. Um dieses Problem zu beheben, haben Sie mehrere Möglichkeiten:

   * Ändern Sie Ihre [Datenspeicherungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#set-rolling-window-for-connection-data-retention).
   * [Löschen Sie alle nicht verwendeten Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * [Löschen Sie einen Datensatz in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * Wenden Sie sich an Ihren Kundenbetreuer von Adobe, um eine Lizenz für eine zusätzliche Kapazität zu erwerben.
