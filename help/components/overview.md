---
title: Was sind Komponenten in Customer Journey Analytics?
description: Erfahren Sie, welche Komponenten CJA anbietet und wie Sie sie für die Berichterstellung verwenden können.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: e8778520581ea6d1cf59285bc8a6c178904d44e2
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 57%

---

# Komponentenübersicht

Komponenten sind Funktionen in Customer Journey Analytics, die in Berichten verwendet werden können oder Berichtsfunktionen ergänzen. Sie können diese Komponenten wie folgt verwalten:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei [analytics.adobe.com](https://analytics.adobe.com) an.
2. Navigieren Sie oben im Menü zu [!UICONTROL Komponenten] > [!UICONTROL Komponenten].

Sie können die folgenden Komponenten verwalten:

* [**Anmerkungen**](/help/components/annotations/overview.md): Informieren Sie andere Benutzerinnen und Benutzer in Ihrem Unternehmen über die kontextbezogene Bedeutung von Daten und Erkenntnissen.
* [**Filter:**](filters/filters-overview.md) Schließen Sie Teile Ihrer Daten aus, um sich auf gebräuchliche Dimensionselemente zu konzentrieren
* [**Berechnete Metriken:**](calc-metrics/calc-metr-overview.md) Verwenden Sie Metriken und Formeln als neue Komponenten für die Berichterstellung
* [**Datumsbereiche:**](date-ranges/create.md) Passen Sie die von Analysis Workspace angebotenen Datumsbereiche an und präzisieren Sie diese
* [**Projekte:**](/help/analysis-workspace/home.md) Organisieren und verwalten Sie Ihre Projekte in Analysis Workspace

## Analysis Workspace-Komponenten

Komponenten in Analysis Workspace bestehen aus Metriken, Dimensionen, Segmenten und Zeitgranularitäten, die Sie per Drag-and-Drop auf ein Projekt anwenden können. Wenn Sie benutzerdefinierte Komponenten erstellen, z. B. benutzerdefinierte Datumsbereiche, werden sie diesen Feldern hinzugefügt.

Klicken Sie in der linken Leiste auf das Symbol **[!UICONTROL Komponenten]**, um auf das Bedienfeld „Komponenten“ zuzugreifen. Sie können zwischen Bedienfeldern (leeres Bedienfeld, [Freiform-Bedienfeld](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) oder dem Bedienfeld [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) und Komponenten mithilfe der Symbole auf der linken Leiste oder mithilfe von [Tastaturbefehlen](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) wechseln.

![](assets/components.png)

Siehe [Erstellen eines Projekts](/help/analysis-workspace/home.md), um Informationen über die Verwendung von Komponenten in einem Projekt zu erhalten.

## Komponentenaktionen

Sie können Komponenten (separat oder mehrere gleichzeitig) auf verschiedene Weisen verwalten. Klicken Sie mit der rechten Maustaste auf eine Komponente oder klicken Sie oben in der Komponentenliste auf **[!UICONTROL Aktionen]**.

>[!NOTE]
>
>Diese Aktionen beziehen sich nicht auf Zeitkomponenten.

| Komponentenaktion | Beschreibung |
| --- | --- |
| Tag | Organisieren oder verwalten Sie Komponenten, indem Sie Tags darauf anwenden. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Filter] oder [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Projekte] |
| Favorit | Fügen Sie die Komponente Ihrer Favoritenliste hinzu. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Filter] oder [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Projekte] |
| Genehmigen | Genehmigen Sie die Komponente, um sie zu autorisieren. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Filter] oder [!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Projekte] |
| Freigeben | Gilt nur für Filter. |
| Löschen | Gilt nur für Filter. |

Sehen Sie sich das Video zum Erstellen von Metriken, Filtern und Daten an:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Komponenten verwalten {#actions}

Sie können Komponenten direkt in der linken Leiste verwalten.

1. Klicken Sie mit der rechten Maustaste auf eine Komponente.

   Oder

   Wählen Sie eine Komponente aus und wählen Sie dann die **Aktion** (3-Punkt) oben in der Komponentenliste.

   >[!TIP]
   >
   >   Sie können mehrere Komponenten auswählen, indem Sie die Umschalttaste gedrückt halten oder die Befehlstaste (Mac) oder die Strg-Taste (Windows) gedrückt halten.


   ![](assets/component-actions.png)

   | Komponentenaktion | Beschreibung |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organisieren oder verwalten Sie Komponenten, indem Sie Tags darauf anwenden. Sie können dann in der linken Leiste nach Tags suchen, indem Sie auf den Filter klicken oder „#“ eingeben. Tags fungieren auch als Filter in den Komponenten-Managern. |
   | [!UICONTROL **Favorit**] | Fügen Sie die Komponente Ihrer Favoritenliste hinzu. Genauso wie nach Tags können Sie in der linken Leiste auch nach Favoriten suchen und diese in den Komponenten-Managern als Filter verwenden. |
   | [!UICONTROL **Genehmigen**] | Markieren Sie Komponenten als „Genehmigt“, um Ihren Benutzern zu signalisieren, dass die Komponente vom Unternehmen genehmigt ist. Genauso wie nach Tags können Sie in der linken Leiste nach dem Status „Genehmigt“ suchen und diesen in den Komponenten-Managern als Filter verwenden. |
   | [!UICONTROL **Freigeben**] | Freigeben von Komponenten für Benutzer in Ihrer Organisation. Diese Option ist nur für benutzerdefinierte Komponenten verfügbar, z. B. Filter oder berechnete Metriken. |
   | [!UICONTROL **Löschen**] | Löschen Sie Komponenten, die Sie nicht mehr benötigen. Diese Option ist nur für benutzerdefinierte Komponenten verfügbar, z. B. Filter oder berechnete Metriken. |

Benutzerdefinierte Komponenten können auch über ihre jeweiligen Komponenten-Manager verwaltet werden. Beispiel: die [Filter verwalten](/help/components/filters/manage-filters.md).

## Suchen, Filtern und Sortieren der Komponentenliste

Sie können die Komponentenliste in der linken Leiste von Analysis Workspace suchen, filtern und sortieren, um eine bestimmte Komponente schnell zu finden.

### Durchsuchen der Komponentenliste

1. Wählen Sie die **Komponenten** icon ![Symbol &quot;Komponenten&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in der linken Leiste.

2. Geben Sie im Suchfeld den Namen der Komponente ein, die Sie in Ihrem Projekt verwenden möchten.

   Der Komponententyp kann sowohl durch Farbe als auch durch Symbol identifiziert werden. **Dimensionen** ![Symbol &quot;Dimension&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) orange sind, **Filter** ![Filtersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) blau sind, **Datumsbereiche** ![Symbol für Datumsbereich](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) violett sind und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. Das Symbol Adobe ![Symbol &quot;Adobe&quot;](assets/default-calc-metric-icon.png) gibt entweder eine Vorlage für berechnete Metriken oder eine Filtervorlage an und das Symbol für den Taschenrechner ![Symbol &quot;Rechner&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) eine berechnete Metrik angezeigt, die von einem Analytics-Administrator in Ihrer Organisation erstellt wurde.

3. Wählen Sie die Komponente aus, wenn sie in der Dropdown-Liste angezeigt wird.

### Filtern der Komponentenliste

1. Wählen Sie die **Komponenten** icon ![Symbol &quot;Komponenten&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in der linken Leiste.

2. Wählen Sie die **Filter** icon ![Symbol &quot;Datenwörterbuchfilter&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   Oder

   Geben Sie das Rautenzeichen (#) in das Suchfeld ein.

3. Wählen Sie eine der folgenden Filteroptionen aus, um die Liste der Komponenten zu filtern:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Genehmigt**] | Nur Komponenten anzeigen, die von Admins als genehmigt markiert wurden. |
   | [!UICONTROL **Favoriten**] | Nur Komponenten anzeigen, die sich in Ihrer Favoritenliste befinden. Informationen zum Hinzufügen von Komponenten zur Favoritenliste finden Sie unter [Komponenten verwalten](#manage-components). |
   | [!UICONTROL **Dimensionen**] | Nur Komponenten anzeigen, die Dimensionen sind. |
   | [!UICONTROL **Metriken**] | Nur Komponenten anzeigen, die Metriken sind. |
   | [!UICONTROL **Filter**] | Nur Komponenten anzeigen, die Filter sind. |
   | [!UICONTROL **Datumsbereiche**] | Zeigt nur Komponenten an, die Datumsbereiche sind. |
   | [!UICONTROL **Alle anzeigen**] | Alle Komponenten anzeigen. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Nicht genehmigt**] | Nur Komponenten anzeigen, die von Admins noch nicht als genehmigt markiert wurden. Für Admins beim Identifizieren von Komponenten hilfreich, die überprüft und genehmigt werden müssen. Diese Option steht nur Admins zur Verfügung. |

4. (Optional) Um die Liste weiter zu verfeinern, können Sie die Komponentenliste sortieren, wie hier beschrieben: [Sortieren der Komponentenliste](#sort-the-component-list).

### Sortieren der Komponentenliste

{{release-limited-testing-section}}

1. (Optional) Wenden Sie alle Filter auf die Komponentenliste an, wie unter [Filtern der Komponentenliste](#filter-the-component-list).

2. Wählen Sie die **Komponenten** icon ![Symbol &quot;Komponenten&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in der linken Leiste.

3. Wählen Sie die **Sortieren** icon ![Symbol &quot;Komponenten sortieren&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)und wählen Sie eine der folgenden Filteroptionen aus, um die Liste der Komponenten zu sortieren:

   {{components-sort-options}}

## Berechtigungen für Komponentenzugriff

In Analysis Workspace können Administratoren [kuratieren](/help/analysis-workspace/curate-share/curate.md), welche Komponenten Benutzern beim Reporting zur Verfügung stehen.
