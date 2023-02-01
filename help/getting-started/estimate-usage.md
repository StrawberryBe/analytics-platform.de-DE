---
title: Schätzen und Verwalten der CJA-Nutzung
description: Zeigt zwei Methoden zur Schätzung der Nutzung und eine Methode zu ihrer Verwaltung an.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: d38e4c4cd589e6708b0a6b5856da341344f6440e
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 37%

---

# Anzeigen und Verwalten der CJA-Nutzung

Um Ihre CJA-Nutzung anzuzeigen, können Sie mehrere Methoden verwenden:

* Fügen Sie die Ereignisdatenzeilen für jede Verbindung hinzu. Siehe [Geschätzte Verbindungsgröße](#estimated size) unten. Auf diese Weise können Sie Ihre Ereigniszeilendaten für jede Verbindung für einen bestimmten Zeitstempel anzeigen.
* Zeigen Sie Ihre Nutzung auf drei Arten an, von denen jede im Folgenden ausführlicher beschrieben wird:
   * Verwenden Sie Analysis Workspace, um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie Report Builder , um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie die CJA-API, um einen automatisierten Bericht zu erstellen.

So verwalten Sie Ihre CJA-Nutzung:

* Definieren Sie ein rollierendes Datenfenster.

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

Mit dieser Methode können Sie Ihre Nutzungsdaten sowie den Verlauf Ihrer Nutzung eingehender analysieren.

1. Bevor Sie das Projekt in Workspace erstellen, [Datenansicht erstellen](/help/data-views/create-dataview.md) für jede Ihrer Verbindungen, ohne dass Filter angewendet werden.

>[!WARNING]
>
>    Erstellen Sie keine neue Verbindung, die alle Ihre Daten ausschließlich zur Nutzungsmessung umfasst, da dies Ihre Nutzung effektiv verdoppeln würde.

1. Erstellen Sie in Workspace neue Projekte basierend auf den einzelnen Datenansichten und rufen Sie alle Ereignisse ab (aus dem **[!UICONTROL Metriken]** -Dropdown-Liste) bis zum ersten Freitag des Monats, beginnend mit dem ersten Tag Ihres aktuellen CJA-Vertrags.

   ![Ereignisse](assets/events-usage.png)

   So erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht.

1. Je nach Bedarf können Sie einen Drilldown nach Datensatz durchführen usw.

## Erstellen eines Datenblocks in Report Builder {#arb}

Im Report Builder [einen Datenblock erstellen](/help/report-builder/create-a-data-block.md) für jede Datenansicht und summieren Sie sie.

## Erstellen eines automatisierten Berichts in der CJA-API {#api-report}

1. Verwenden Sie die [CJA-Reporting-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) , um einen Bericht zu allen Ereignisdaten auszuführen, **für jede Verbindung**. Richten Sie dies so ein, dass der Bericht ausgeführt wird

   * jeden ersten Freitag eines jeden Monats.
   * zurück zum ersten Tag Ihres aktuellen CJA-Vertrags.

   So erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht. Sie erhalten die Gesamtzahl der Zeilen für alle CJA-Verbindungen.

1. Verwenden Sie Excel, um diesen Bericht weiter anzupassen.

## Nutzung verwalten durch Definieren eines rollierenden Datenfensters {#rolling}

Um Ihre Nutzung zu verwalten, wird die [Verbindungs-Benutzeroberfläche](/help/connections/create-connection.md) ermöglicht die Definition der CJA-Datenbeibehaltung als rollierendes Fenster in Monaten (1 Monat, 3 Monate, 6 Monate usw.) auf Verbindlichkeitsebene.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

Wenn Sie die Standardeinstellung unverändert, d. h. deaktiviert, lassen, wird die Aufbewahrungsdauer durch die Datenaufbewahrungseinstellung von Adobe Experience Platform ersetzt. Wenn in Experience Platform Daten von einem Zeitraum von 25 Monaten enthalten sind, erhält CJA durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in CJA die verbleibenden 15 Monate beibehalten.

Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung Profil- oder Lookup-Datensätze enthält, da sie mit Ereignis-Datensätzen verbunden sind, werden die Daten in Customer Journey Analytics basierend auf Ihren Datenaufbewahrungseinstellungen für die Ereignis-Datensatz-Zeitstempel beibehalten.

