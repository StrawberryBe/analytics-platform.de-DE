---
description: Das Datenwörterbuch in Analysis Workspace ermöglicht es Benutzenden, die verschiedenen Komponenten in Analysis Workspace zu katalogisieren und im Auge zu behalten, einschließlich ihres Verwendungszwecks, welche genehmigt sind, welche Duplikate sind usw.
title: Datenwörterbuch anzeigen
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: b38b5b54ebbf301a3e59156d484bf5d69974b4a4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 48%

---

# Komponenteninformationen im Datenwörterbuch anzeigen

Mit dem Datenwörterbuch können Sie Informationen über eine Komponente anzeigen, einschließlich der Komponentenbeschreibung, ähnlicher Komponenten, anderer Komponenten, mit denen eine Komponente häufig verwendet wird, und mehr.

So zeigen Sie Informationen zu einer Komponente im Datenwörterbuch an:

1. Wechseln Sie zum Analysis Workspace-Projekt, das die Komponente enthält, die Sie anzeigen möchten.

1. Wählen Sie das Symbol [!UICONTROL **Datenwörterbuch**] in der linken Leiste von Analysis Workspace. (Alternative Möglichkeiten für den Zugriff auf das Datenwörterbuch sind unter „Zugriff auf das Datenwörterbuch“ in [Datenwörterbuch – Überblick](/help/components/data-dictionary/data-dictionary-overview.md) beschrieben.)

   Das Fenster „Datenwörterbuch“ wird angezeigt.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Stellen Sie sicher, dass die Datenansicht mit der Komponente, die Sie anzeigen möchten, im Dropdown-Menü ausgewählt ist. Standardmäßig wird die Datenansicht angezeigt, in der Sie sich bereits befinden.

1. (Optional) Geben Sie im Suchfeld den Namen der Komponente ein, die Sie anzeigen möchten.

   Der Komponententyp kann sowohl durch Farbe als auch durch Symbol identifiziert werden. **Dimensionen** ![Symbol &quot;Dimension&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) orange sind, **Segmente** ![Segmentsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) blau sind, **Datumsbereiche** ![Symbol für Datumsbereich](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) violett sind und **Metriken** ![Metriksymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sind grün. Das Symbol Adobe ![Symbol &quot;Adobe&quot;](assets/default-calc-metric-icon.png) gibt entweder eine Vorlage für berechnete Metriken oder eine Segmentvorlage an und das Symbol für den Rechner ![Symbol &quot;Rechner&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) eine berechnete Metrik angezeigt, die von einem Analytics-Administrator in Ihrer Organisation erstellt wurde.

{{dd-filter-criteria}}

1. (Optional) Wählen Sie die **Sortieren** icon ![Symbol &quot;Komponenten sortieren&quot;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)und wählen Sie eine der folgenden Filteroptionen aus, um die Liste der Komponenten zu sortieren:

   {{components-sort-options}}

1. Wählen Sie aus der Komponentenliste die Komponente aus, die Sie anzeigen möchten.

   Es werden die folgenden Informationen über die Komponente angezeigt:

   {{dd-component-information}}

1. (Optional) Ziehen Sie eine Komponente aus dem Datenwörterbuch in Analysis Workspace.
