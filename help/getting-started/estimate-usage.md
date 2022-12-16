---
title: Schätzen und Verwalten der CJA-Nutzung
description: Zeigt zwei Methoden zur Schätzung der Nutzung und eine Methode zu ihrer Verwaltung an.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# Schätzen und Verwalten der CJA-Nutzung

Um Ihre CJA-Nutzung zu verstehen, können Sie zwei Methoden verwenden:

* Fügen Sie die Ereignisdatenzeilen für jede Verbindung hinzu. (Siehe **Geschätzte Verbindungsgröße** unten)
* Verwenden Sie Analysis Workspace, um Berichte zu den Ereignissen des letzten Monats zu erstellen. (Siehe **Workspace-Projekt mit allen Ereignisdaten erstellen** unten.)

So verwalten Sie Ihre CJA-Nutzung:

* Verwenden Sie die CJA-API. (Siehe **Erstellen eines Berichts in der CJA-API** unten.)

## Verbindungsgröße schätzen {#estimate-size}

Möglicherweise müssen Sie wissen, wie viele Zeilen von Ereignisdaten sich derzeit in der [!UICONTROL Customer Journey Analytics]. Gehen Sie **für jede der von Ihrem Unternehmen erstellten Verbindungen** wie folgt vor, um genaue Informationen zur Nutzung der Ereignisdatensätze (Datenzeilen) in Ihrem Unternehmen zu erhalten.

>[!NOTE]
>
>Führen Sie dies am ersten Freitag eines jeden Monats aus, da Adobe Ihren aktuellen Nutzungsbericht an diesem Tag ausführt.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.

   Dadurch wird eine Liste aller Ihrer aktuellen Verbindungen angezeigt.

1. Klicken Sie auf einen Verbindungsnamen, um zum Verbindungs-Manager zu gelangen.

1. Fügen Sie die **[!UICONTROL Verfügbare Ereignisdaten]** für jede Verbindung, die Ihr Unternehmen erstellt hat. (Je nach Größe Ihrer Verbindung kann es eine Weile dauern, bis die Anzahl angezeigt wird.)

   ![Ereignisdaten](assets/event-data.png)

   >[!CAUTION]
   >
   >   Diese Anzahl gilt nur für Ereignisdaten, nicht aber für Profil- oder Suchdaten. Wenn Sie über Profil- und Suchdaten verfügen, ist die Anzahl etwas höher. Es gibt jedoch derzeit keine Möglichkeit, Berichte über die Nutzung von Profil- und Suchdaten in der Benutzeroberfläche zu erstellen. Diese Funktion ist für 2023 geplant.

1. Sobald Sie über die Summe aller Ereignisdatenzeilen verfügen, suchen Sie im Customer Journey Analytics-Vertrag, den Ihr Unternehmen mit Adobe unterzeichnet hat, nach der Berechtigung für „Datenzeilen“.

   Dadurch erhalten Sie die maximale Anzahl von Datenzeilen, die im Kundenauftrag genehmigt wurden. Wenn die Anzahl der Datenzeilen, die sich aus Schritt 3 ergaben, größer ist als diese Zahl, besteht eine Überschreitung des Limits.

1. Um dieses Problem zu beheben, haben Sie mehrere Möglichkeiten:

   * Ändern Sie Ihre [Datenspeicherungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#set-rolling-window-for-connection-data-retention).
   * [Löschen Sie alle nicht verwendeten Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * [Löschen Sie einen Datensatz in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * Wenden Sie sich an Ihren Kundenbetreuer von Adobe, um eine Lizenz für eine zusätzliche Kapazität zu erwerben.

## Workspace-Projekt mit allen Ereignisdaten erstellen {#workspace-event-data}

1. Bevor Sie das Projekt in Workspace erstellen, [Datenansicht erstellen](/help/data-views/create-dataview.md) , bei dem Daten von ALLEN Verbindungen abgerufen werden und keine Filter angewendet werden. Mit anderen Worten, es enthält alle Ihre Daten.

1. Erstellen Sie in Workspace ein neues Projekt und ziehen Sie alle Ereignisse (aus dem **[!UICONTROL Metriken]** Dropdown) für den vorherigen Monat.

   ![Ereignisse](assets/events-usage.png)

1. tun

## Erstellen eines Berichts in der CJA-API {#api-report}

Verwenden Sie die [CJA-Reporting-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) , um einen Bericht zu allen Ereignisdaten auszuführen.