---
title: Nutzung von Customer Journey Analytics anzeigen und verwalten
description: Zeigt zwei Methoden zur Schätzung der Nutzung und eine Methode zur Verwaltung.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 9f2d0d00872ad18c73bf67184e44f687a0b156a3
workflow-type: ht
source-wordcount: '868'
ht-degree: 100%

---

# Nutzung von Customer Journey Analytics anzeigen und verwalten

Um Ihre CJA-Nutzung zu ermitteln, können Sie mehrere Methoden verwenden:

* Addieren Sie die Ereignisdatenzeilen für jede Verbindung. Siehe unten [Schätzen der Verbindungsgröße](#estimated size). Dies ist eine einfache Methode, um Ihre Ereigniszeilendaten pro Verbindung für einen bestimmten Zeitstempel anzuzeigen.
* Sie können Ihre Nutzung auf drei Arten anzeigen, von denen jede im Folgenden ausführlicher beschrieben wird:
   * Verwenden Sie Analysis Workspace, um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie Report Builder, um Berichte zu den Ereignissen des letzten Monats zu erstellen.
   * Verwenden Sie die CJA-API, um einen automatisierten Bericht zu erstellen.

Gehen Sie folgendermaßen vor, um Ihre CJA-Nutzung zu verwalten:

* Definieren Sie ein rollierendes Datenfenster.

## Schätzen der Verbindungsgröße {#estimate-size}

Möglicherweise benötigen Sie Informationen zur aktuellen Anzahl von Ereignisdatenzeilen in [!UICONTROL Customer Journey Analytics]. Gehen Sie **für jede der von Ihrem Unternehmen erstellten Verbindungen** wie folgt vor, um genaue Informationen zur Nutzung der Ereignisdatensätze (Datenzeilen) in Ihrem Unternehmen zu erhalten.

>[!NOTE]
>
>Machen Sie das am ersten Freitag eines jeden Monats aus, da Adobe Ihren aktuellen Nutzungsbericht an diesem Tag ausführt.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.

   Dadurch wird eine Liste aller Ihrer aktuellen Verbindungen angezeigt.

1. Klicken Sie auf einen Verbindungsnamen, um zum Verbindungs-Manager zu gelangen.

1. Addieren Sie die **[!UICONTROL verfügbaren Sätze von Ereignisdaten]** für jede Verbindung, die Ihr Unternehmen erstellt hat. (Je nach Größe Ihrer Verbindung kann es eine Weile dauern, bis die Anzahl angezeigt wird.)

   ![Ereignisdaten](./assets/event-data.png)

   >[!CAUTION]
   >
   >   Diese Anzahl beinhaltet nur Ereignisdaten, nicht aber Profil- oder Lookup-Daten. Wenn Sie über Profil- und Lookup-Daten verfügen, ist die Anzahl etwas höher. Es gibt jedoch derzeit keine Möglichkeit, Berichte über die Nutzung von Profil- und Lookup-Daten in der Benutzeroberfläche zu erstellen. Diese Funktion ist für 2023 geplant.

1. Sobald Sie über die Summe aller Ereignisdatenzeilen verfügen, suchen Sie im Customer Journey Analytics-Vertrag, den Ihr Unternehmen mit Adobe unterzeichnet hat, nach der Berechtigung für „Datenzeilen“.

   Dadurch erhalten Sie die maximale Anzahl von Datenzeilen, die im Kundenauftrag genehmigt wurden. Wenn die Anzahl der Datenzeilen, die sich aus Schritt 3 ergaben, größer ist als diese Zahl, besteht eine Überschreitung des Limits.

1. Um dieses Problem zu beheben, haben Sie mehrere Möglichkeiten:

   * Ändern Sie Ihre [Datenspeicherungseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#set-rolling-window-for-connection-data-retention).
   * [Löschen Sie alle nicht verwendeten Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * [Löschen Sie einen Datensatz in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components).
   * Wenden Sie sich an Ihren Kundenbetreuer von Adobe, um eine Lizenz für eine zusätzliche Kapazität zu erwerben.

## Erstellen eines Analysis Workspace-Projekts mit allen Ereignisdaten {#workspace-event-data}

Mit dieser Methode können Sie Ihre Nutzungsdaten sowie den Verlauf Ihrer Nutzung eingehender analysieren.

1. Bevor Sie ein Projekt in Analysis Workspace erstellen, [erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) für jede Ihrer Verbindungen, ohne Filter anzuwenden.

>[!WARNING]
>
>    Erstellen Sie keine neue Verbindung mit all Ihren Daten ausschließlich zum Zweck der Nutzungsmessung, da dadurch Ihre Nutzungswerte tatsächlich verdoppelt werden würden.

1. Erstellen Sie in Analysis Workspace neue Projekte basierend auf den einzelnen Datenansichten und rufen Sie (aus der Dropdown-Liste **[!UICONTROL Metriken]**) alle Ereignisse bis zum ersten Freitag des Monats ab, beginnend mit dem ersten Tag Ihres aktuellen CJA-Vertrags.

   ![Ereignisse](./assets/events-usage.png)

   Dadurch erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht.

1. Je nach Bedarf können Sie eine Aufschlüsselung nach Datensatz durchführen usw.

## Erstellen eines Datenblocks in Report Builder {#arb}

Erstellen Sie in Report Builder für jede Datenansicht [einen Datenblock](/help/report-builder/create-a-data-block.md) und addieren Sie sie.

## Erstellen eines automatisierten Berichts in der CJA-API {#api-report}

1. Verwenden Sie die [CJA-Reporting-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API), um **für jede Verbindung** einen Bericht zu allen Ereignisdaten zu erstellen. Richten Sie dies so ein, dass der Bericht folgendermaßen ausgeführt wird:

   * An jedem ersten Freitag eines jeden Monats
   * Zurück bis zum ersten Tag Ihres aktuellen CJA-Vertrags.

   Dadurch erhalten Sie eine gute Vorstellung davon, wie Ihre Nutzung von Monat zu Monat aussieht. Dadurch erhalten Sie die Gesamtzahl der Zeilen für alle Ihre CJA-Verbindungen.

1. Verwenden Sie Excel, um diesen Bericht weiter anzupassen.

## Verwalten der Nutzung durch Definieren eines rollierenden Datenfensters {#rolling}

Um Ihre Nutzung zu verwalten, können Sie über die [Verbindungs-Benutzeroberfläche](/help/connections/create-connection.md) die CJA-Datenspeicherung auf Verbindungsebene als rollierendes Fenster in Monaten (1 Monat, 3 Monate, 6 Monate usw.) festlegen.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

Wenn Sie die Standardeinstellung unverändert, d. h. deaktiviert, lassen, wird die Aufbewahrungsdauer durch die Datenaufbewahrungseinstellung von Adobe Experience Platform ersetzt. Wenn in Experience Platform Daten von einem Zeitraum von 25 Monaten enthalten sind, erhält CJA durch Aufstockung Daten von einem Zeitraum von 25 Monaten. Wenn Sie in Platform 10 dieser Monate löschen, werden in CJA die verbleibenden 15 Monate beibehalten.

Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine rollierenden Datenfenstereinstellungen, da keine entsprechenden Zeitstempel vorhanden sind. Wenn Ihre Verbindung Profil- oder Lookup-Datensätze enthält, werden die Daten, da sie mit Ereignis-Datensätzen verbunden sind, in Customer Journey Analytics basierend auf Ihren Datenaufbewahrungseinstellungen für die Ereignis-Datensatz-Zeitstempel beibehalten.

