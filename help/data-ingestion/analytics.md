---
title: Daten aus dem herkömmlichen Adobe Analytics erfassen und verwenden
description: Erläuterung der Datenerfassung aus dem herkömmlichen Adobe Analytics
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 10%

---


# Daten aus dem herkömmlichen Adobe Analytics erfassen und verwenden

In dieser Kurzanleitung wird erläutert, wie Sie die von Adobe Analytics in Customer Journey Analytics erfassten Daten verwenden können.

>[!PREREQUISITES]
>
>Adobe Analytics ist auf einer oder mehreren Ihrer Websites lizenziert und bereitgestellt. Verwenden Sie dazu eine der dokumentierten Implementierungsmethoden:
>
>- [Implementieren von Analytics unter Verwendung von Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=de)
>
>- [Analytics mithilfe der Adobe Analytics-Erweiterung implementieren](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=de)
>
>- [Analytics mit JavaScript implementieren](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


Gehen Sie dazu folgendermaßen vor:

- **Einrichten eines Quell-Connectors für Adobe Analytics** in Adobe Experience Platform. Dadurch werden Ihre aktuellen Adobe Analytics-Daten in einen Datensatz in Adobe Experience Platform aufgenommen.

- **Verbindung einrichten** in Customer Journey Analytics. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Datenansicht einrichten** in Customer Journey Analytics , um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Einrichten eines Projekts** in Customer Journey Analytics , um Ihre Berichte und Visualisierungen zu erstellen.


>[!NOTE]
>
>Dies ist eine vereinfachte Anleitung zur Erfassung von Daten mithilfe des Adobe Analytics-Quell-Connectors und zur Verwendung dieser Daten in Customer Journey Analytics.  Es wird dringend empfohlen, die zusätzlichen Informationen zu untersuchen, wenn darauf verwiesen wird.


## Einrichten eines Quell-Connectors für Adobe Analytics

Mit dem Adobe Analytics-Quell-Connector können Sie Adobe Analytics-Report Suite-Daten in Adobe Experience Platform importieren.

So erstellen Sie einen Adobe Analytics-Quell-Connector:

1. Wählen Sie in der Platform-Benutzeroberfläche die Option **[!UICONTROL Quellen]** über die linke Leiste.

2. Auswählen **[!UICONTROL Adobe Apps]** aus der Liste der [!UICONTROL KATEGORIEN].

3. Auswählen **[!UICONTROL Einrichten]** oder **[!UICONTROL Daten hinzufügen]** in der Adobe Analytics-Kachel.

   ![Quellen](./assets/sources-overview.png)

4. Auswählen **[!UICONTROL Report Suite]**. Wählen Sie aus der Liste der Report Suites die gewünschte aus.

   ![Report Suites](./assets/report-suites.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

5. Auswählen **[!UICONTROL Standardschema]** als [!UICONTROL Zielschema]. Adobe Experience Platform erstellt automatisch das Schema und den entsprechenden Datensatz, um alle Standardfelder aus der ausgewählten Adobe Analytics Report Suite zuzuordnen.

   ![Standardschema](./assets/default-schema.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

6. Benennen Sie den Datenfluss und geben Sie (optional) eine Beschreibung ein.

   ![Datenflussdetails](./assets/dataflow-detail.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

7. Überprüfen Sie die Verbindung und wählen Sie **[!UICONTROL Beenden]**.

   ![Überprüfung](./assets/review.png)


Nach der Erstellung der Verbindung wird der Datenfluss automatisch erstellt, um einen Datensatz mit den Adobe Analytics-Daten aus Ihrer Report Suite zu füllen, einschließlich der Erfassung von bis zu 13 Monaten historischen Daten.

Wenn die erste Aufnahme abgeschlossen ist, können Ihre Adobe Analytics Report Suite-Daten vom Customer Journey Analytics verwendet werden.

Siehe [Erstellen einer Adobe Analytics-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) für ein viel umfassenderes Tutorial.


## Verbindung einrichten

Um die Adobe Experience Platform-Daten in Customer Journey Analytics zu verwenden, erstellen Sie eine Verbindung, die die Daten enthält, die sich aus der Einrichtung Ihres Schemas, Datensatzes und Workflows ergeben.

Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über diese Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Adobe Experience Platform und Workspace herstellen.

So erstellen Sie Ihre Verbindung:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Verbindungen]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Neue Verbindung erstellen]**.

3. Im [!UICONTROL Verbindung ohne Titel] screen:

   Benennen und beschreiben Sie Ihre Verbindung in [!UICONTROL Verbindungseinstellungen].

   Wählen Sie die richtige Sandbox aus der [!UICONTROL Sandbox] Liste in [!UICONTROL Dateneinstellungen] und wählen Sie die Anzahl der täglichen Ereignisse aus der [!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse] Liste.

   ![Verbindungseinstellungen](./assets/cja-connections-1.png)

   Auswählen **[!UICONTROL Datensätze hinzufügen]**.

   Im [!UICONTROL Auswählen von Datensätzen] Schritt in [!UICONTROL Hinzufügen von Datensätzen]:

   - Wählen Sie den Datensatz aus, der automatisch vom Adobe Analytics-Quell-Connector erstellt wurde, sowie jeden anderen Datensatz, den Sie in Ihre Verbindung aufnehmen möchten.

      ![Hinzufügen von Datensätzen](./assets/cja-connections-2a.png)

   - Klicken Sie auf **[!UICONTROL Weiter]**.
   Im [!UICONTROL Datensatzeinstellungen] Schritt in [!UICONTROL Hinzufügen von Datensätzen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten, die in den Datensatzschemas in Adobe Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle aus der [!UICONTROL Datenquellentyp] Liste. Wenn Sie **[!UICONTROL Sonstiges]** Fügen Sie dann eine Beschreibung für Ihre Datenquelle hinzu.

      - Satz **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Aufstockung vorhandener Daten durch Datensätze]** entsprechend Ihren Vorlieben.

      ![Konfigurieren von Datensätzen](./assets/cja-connections-3.png)

   - Auswählen **[!UICONTROL Hinzufügen von Datensätzen]**.
   Wählen Sie **[!UICONTROL Speichern]** aus.

Siehe [Verbindungen - Übersicht](../connections/overview.md) Weitere Informationen zum Erstellen und Verwalten einer Verbindung und zum Auswählen und Kombinieren von Datensätzen.

## Datenansicht einrichten

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Es werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

So erstellen Sie Ihre Datenansicht:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Datenansichten]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Neue Datenansicht erstellen]**.

3. Im [!UICONTROL Konfigurieren] step:

   Wählen Sie Ihre Verbindung aus der [!UICONTROL Verbindung] Liste.

   Geben Sie einen Namen ein und beschreiben Sie (optional) Ihre Verbindung.

   ![Konfiguration der Datenansicht](./assets/cja-dataview-1.png)

   Auswählen **[!UICONTROL Speichern und fortfahren]**.

4. Im [!UICONTROL Komponenten] step:

   Fügen Sie jedes Schemafeld und/oder jede Standardkomponente hinzu, die Sie in die [!UICONTROL METRIKEN] oder [!UICONTROL Dimensionen] Komponentenfelder.

   ![Datenansichtskomponenten](./assets/cja-dataview-2.png)

   Auswählen **[!UICONTROL Speichern und fortfahren]**.

5. Im [!UICONTROL Einstellungen] step:

   ![Datenansichtseinstellungen](./assets/cja-dataview-3.png)

   Behalten Sie die Einstellungen bei und wählen Sie **[!UICONTROL Speichern und beenden]**.

Siehe [Datenansichten - Übersicht](../data-views/data-views.md) Weitere Informationen zum Erstellen und Bearbeiten einer Datenansicht, dazu, welche Komponenten in Ihrer Datenansicht verfügbar sind und wie Filter- und Sitzungseinstellungen verwendet werden.


## Einrichten eines Projekts

Analysis Workspace ist ein flexibles Browser-Tool, mit dem Sie schnell Analysen erstellen und basierend auf Ihren Daten Erkenntnisse austauschen können. Sie verwenden Workspace-Projekte, um Datenkomponenten, Tabellen und Visualisierungen zu kombinieren, um Ihre Analyse zu erstellen und sie für andere in Ihrer Organisation freizugeben.

So erstellen Sie Ihr Projekt:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Projekte]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Projekte]** in der linken Navigation.

3. Auswählen **[!UICONTROL Projekt erstellen]**.

   ![Workspace-Projekt](./assets/cja-projects-1.png)

   Auswählen **[!UICONTROL Leeres Projekt]**.

   ![Workspace - Leeres Projekt](./assets/cja-projects-2.png)

4. Wählen Sie Ihre Datenansicht aus der Liste aus.

   ![Ansicht &quot;Workspace Select Data&quot;](./assets/cja-projects-3.png).

5. Ziehen und Ablegen von Dimensionen und Metriken auf die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld] um Ihren ersten Bericht zu erstellen. Ziehen Sie als Beispiel `Program Points Balance` und `Page View` als Metriken und `email` als Dimension zu erhalten, um einen schnellen Überblick über Profile zu erhalten, die Ihre Website besucht haben und auch Teil des Treueprogramms sind, das Treuepunkte sammelt.

   ![Workspace - Erster Bericht](./assets/cja-projects-5.png)

Siehe [Übersicht über Analysis Workspace](../analysis-workspace/home.md) Weitere Informationen zum Erstellen von Projekten und Erstellen Ihrer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern.


>[!SUCCESS]
>
>Sie haben alle Schritte ausgeführt. Beginnen Sie mit der Einrichtung des Adobe Analytics-Datenquellen-Connectors und der Konfiguration dieses Connectors für Ihre Report Suite, und Ihre Adobe Analytics-Daten werden automatisch in Adobe Experience Platform hochgeladen. Sie haben eine Verbindung in Customer Journey Analytics definiert, um die erfassten Adobe Analytics-Daten und andere Daten zu nutzen. Mit Ihrer Datenansichtsdefinition können Sie festlegen, welche Dimension und Metriken verwendet werden sollen, und schließlich Ihre erste Projektvisualisierung und -analyse erstellen.







