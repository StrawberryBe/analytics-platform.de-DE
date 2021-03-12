---
title: Komponentenübersicht
description: Erfahren Sie, welche Komponenten CJA anbietet und wie Sie sie für die Berichterstellung verwenden können.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# Komponentenübersicht

Komponenten sind Funktionen in Customer Journey Analytics, die in Berichten verwendet werden können oder Berichtsfunktionen ergänzen. Sie können diese Komponenten wie folgt verwalten:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldedaten bei [analytics.adobe.com](https://analytics.adobe.com) an.
2. Navigieren Sie oben im Menü zu [!UICONTROL Komponenten] > [!UICONTROL Komponenten].

Sie können die folgenden Komponenten verwalten:

* [**Filter:**](filters/filters-overview.md) Schließen Sie Teile Ihrer Daten aus, um sich auf gebräuchliche Dimensionselemente zu konzentrieren
* [**Berechnete Metriken:**](calc-metrics/calc-metr-overview.md) Verwenden Sie Metriken und Formeln als neue Komponenten für die Berichterstellung
* [**Datumsbereiche:**](date-ranges/overview.md) Passen Sie die von Analysis Workspace angebotenen Datumsbereiche an und präzisieren Sie diese
* [**Projekte:**](/help/analysis-workspace/home.md) Organisieren und verwalten Sie Ihre Projekte in Analysis Workspace

## Analysis Workspace-Komponenten

Komponenten in Analysis Workspace bestehen aus Metriken, Dimensionen, Segmenten und Zeitgranularitäten, die Sie per Drag-and-Drop in einem Projekt platzieren können. Wenn Sie benutzerdefinierte Komponenten erstellen, z. B. benutzerdefinierte Datumsbereiche, werden sie diesen Feldern hinzugefügt.

Klicken Sie in der linken Leiste auf das Symbol **[!UICONTROL Komponenten]**, um auf das Bedienfeld „Komponenten“ zuzugreifen. Sie können zwischen Bedienfeldern (leeres Bedienfeld, [Freiform-Bedienfeld](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) oder dem Bedienfeld [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualisierungen](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) und Komponenten mithilfe der Symbole auf der linken Leiste oder mithilfe von [Tastaturbefehlen](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) wechseln.

![](assets/components.png)

Siehe [Erstellen eines Projekts](/help/analysis-workspace/home.md), um Informationen über die Verwendung von Komponenten in einem Projekt zu erhalten.

## Komponentenaktionen

Sie können Komponenten (separat oder mehrere gleichzeitig) auf verschiedene Weisen verwalten. Klicken Sie mit der rechten Maustaste auf eine Komponente oder klicken Sie oben in der Komponentenliste auf **[!UICONTROL Aktionen]**.

>[!NOTE]
>
>Diese Aktionen beziehen sich nicht auf Zeitkomponenten.

| Komponentenaktion | Beschreibung |
|--- |--- |
| Tag | Organisieren oder verwalten Sie Komponenten, indem Sie Tags darauf anwenden. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise „Analysen“ > „Komponenten“ > „Segmente“ oder „Analysen“ > „Komponenten“ > „Projekte“. |
| Favorit | Fügen Sie die Komponente Ihrer Favoritenliste hinzu. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise „Analysen“ > „Komponenten“ > „Segmente“ oder „Analysen“ > „Komponenten“ > „Projekte“. |
| Genehmigen | Genehmigen Sie die Komponente, um sie zu autorisieren. Dies wird dann bei der jeweiligen Komponentenverwaltung angezeigt, beispielsweise „Analysen“ > „Komponenten“ > „Segmente“ oder „Analysen“ > „Komponenten“ > „Projekte“. |
| Freigeben | Gilt nur für Segmente. |
| Löschen | Gilt nur für Segmente. |

Sehen Sie sich das Video zum Erstellen von Metriken, Segmenten und Daten an:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Berechtigungen für Komponentenzugriff

Administratoren können (über [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) kuratieren, welche Komponenten in Berichte Benutzern zur Verfügung stehen. Die folgende Tabelle zeigt, wie sich diese Komponentenzugriffsberechtigungen verhalten:

| Kurationstyp | Admin kann | Der Eigentümer des Nicht-Admin-Projekts (oder die Bearbeitungsrolle) kann | Rolle &quot;Nicht-Admin-Duplikat&quot; |
| --- | --- | --- | --- |
| **Komponenten &quot;ausgeblendet&quot;aus einer Ansicht** | Alle für Berichte verfügbaren Komponenten zur Ansicht von Daten (ausgeblendete Komponenten erfordern Klicken auf &quot;Alle anzeigen&quot;) | Nicht verfügbar für Berichte | Nicht verfügbar für Berichte |
| **Komponenten, die zu einer Ansicht hinzugefügt oder daraus entfernt wurden** | Nur Komponenten, die der Ansicht hinzugefügt wurden (ausgeblendet oder nicht ausgeblendet). Administratoren können keine Berichte zu Feldern oder Komponenten erstellen, die nicht von der Ansicht definiert sind. | Nur Komponenten, die der Datenkomponente hinzugefügt wurden, oder Komponenten, die dem Ansicht gehören oder für ihn freigegeben wurden. Ausgeblendete Komponenten sind nicht verfügbar (wie VRS-Kuration). | Nur Komponenten, die dem DV hinzugefügt wurden, werden nicht ausgeblendet und wurden in die Projektkuration aufgenommen. |
| **Kuratierte Komponenten in einem Projekt** | Alle für Berichte verfügbaren Komponenten zur Ansicht von Daten (ausgeblendete Komponenten erfordern Klicken auf &quot;Alle anzeigen&quot;) | Alle nicht ausgeblendeten Datenkomponenten (Ansicht durch Klicken auf &quot;Alle anzeigen&quot;) | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |
| **Kuratiertes Projekt mithilfe einer Ansicht mit verborgenen Komponenten** | Alle für den Berichte verfügbaren Datenkomponenten (ausgeblendete und nicht kuratierte Komponenten müssen auf &quot;Alle anzeigen&quot;klicken) | Alle nicht kuratierten Projektkomponenten, alle nicht verborgenen Komponenten der Ansicht von Daten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |

