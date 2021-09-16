---
title: Standardkomponentenreferenz
description: Details und Informationen zu allen Standardkomponenten, die Sie jeder Datenansicht hinzufügen können.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 58%

---


# Standardkomponentenreferenz

Die meisten Dimensionen und Metriken in CJA basieren auf Schemaelementen aus Ihrem Adobe Experience Platform-Datensatz. Es stehen jedoch mehrere Komponenten zur Verfügung, die unabhängig von der verwendeten Verbindung zu einer Datenansicht hinzugefügt werden können.

[!UICONTROL Standardkomponenten] sind Komponenten, die nicht aus Datensatz-Schemafeldern, sondern vom System generiert werden. Einige Systemkomponenten sind erforderlich, um die Berichterstellungsfunktionen in Analysis Workspace zu erleichtern, während andere Systemkomponenten optional sind.

![Standard-Komponenten](assets/standard-components.png)

## Erforderliche Standardkomponenten

Diese erforderlichen Standardkomponenten werden standardmäßig jeder Datendatei-Ansicht hinzugefügt. Sie sind von wesentlicher Bedeutung für die Berichterstellungsfunktionen, die Customer Journey Analytics bietet.

| Name der Komponente | Dimension oder Metrik | Hinweise |
| --- | --- | --- |
| [!UICONTROL Personen] | Metrik | Basiert auf der in einer [!UICONTROL Verbindung] angegebenen Personen-ID. |
| [!UICONTROL Sitzungen] | Metrik | Basiert auf den Sitzungseinstellungen der Datenansicht. |
| [!UICONTROL Ereignisse] | Metrik | Die Anzahl der Zeilen aus allen Ereignis-Datensätzen in einer [!UICONTROL Verbindung]. |
| [!UICONTROL Minute] | Dimension | Die Minute, in der ein bestimmtes Ereignis aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Minute im Datumsbereich und das letzte Dimensionselement die letzte Minute im Datumsbereich. |
| [!UICONTROL Stunde] | Dimension | Die Stunde, in der ein bestimmtes Ereignis aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Stunde im Datumsbereich und das letzte Dimensionselement die letzte Stunde im Datumsbereich. |
| [!UICONTROL Tag] | Dimension | Der Tag, an dem ein bestimmtes Ereignis eingetreten ist. Das erste Dimensionselement ist der erste Tag im Datumsbereich und das letzte Dimensionselement der letzte Tag im Datumsbereich. |
| [!UICONTROL Woche] | Dimension | Die Woche, in der ein bestimmtes Ereignis stattgefunden hat. Das erste Dimensionselement ist die erste Woche im Datumsbereich und das letzte Dimensionselement die letzte Woche im Datumsbereich. |
| [!UICONTROL Monat] | Dimension | Der Monat, in dem ein bestimmtes Ereignis aufgetreten ist. Das erste Dimensionselement ist der erste Monat im Datumsbereich und das letzte Dimensionselement der letzte Monat im Datumsbereich. |
| [!UICONTROL Quartal] | Dimension | Das Quartal, in dem ein bestimmtes Ereignis eingetreten ist. Das erste Dimensionselement ist das erste Quartal im Datumsbereich und das letzte Dimensionselement das letzte Quartal im Datumsbereich. |
| [!UICONTROL Jahr] | Dimension | Das Jahr, in dem ein bestimmtes Ereignis stattgefunden hat. Das erste Dimensionselement ist das erste Jahr im Datumsbereich und das letzte Dimensionselement das letzte Jahr im Datumsbereich. |

## Optionale Standardkomponenten

Optionale Standardkomponenten sind auf der Registerkarte **[!UICONTROL Datenansichten]** > **[!UICONTROL Datenansicht bearbeiten]** > **[!UICONTROL Komponenten]** > Registerkarte **[!UICONTROL Standardkomponenten]** verfügbar.

| Name der Komponente | Dimension oder Metrik | Hinweise |
| --- | --- | --- |
| [!UICONTROL Sitzung beginnt] | Metrik | Die Anzahl der Ereignisse, die das erste Ereignis einer Sitzung waren. Bei Verwendung in einer Filterdefinition (wie beispielsweise „[!UICONTROL Sitzung beginnt] existiert“) wird nur das erste Ereignis jeder Sitzung gefiltert. |
| [!UICONTROL Sitzung endet] | Metrik | Die Anzahl der Ereignisse, die das letzte Ereignis einer Sitzung waren. Ähnlich wie [!UICONTROL Sitzung beginnt] kann dies auch in einer Filterdefinition verwendet werden, um bis zum letzten Ereignis jeder Sitzung zu filtern. |
| [!UICONTROL Aufgewendete Zeit (Sekunden)] | Metrik | Addiert die Zeit zwischen zwei verschiedenen Werten für eine Dimension. |
| [!UICONTROL Aufgewendete Zeit pro Ereignis] | Dimension | Fügt die Metrik [!UICONTROL Besuchszeit] in [!UICONTROL Ereignis] -Behälter zusammen. |
| [!UICONTROL Aufgewendete Zeit pro Sitzung] | Dimension | Fügt die Metrik [!UICONTROL Besuchszeit] in [!UICONTROL Sitzung] Behälter zusammen. |
| [!UICONTROL Aufgewendete Zeit pro Person] | Dimension | Fügt die Metrik [!UICONTROL Besuchszeit] in [!UICONTROL Personen] Behälter zusammen. |
| [!UICONTROL Batch-ID] | Dimension | Stellt den Experience Platform-Batch dar, zu dem ein [!UICONTROL Ereignis] gehört hat. |
| [!UICONTROL Datensatz-ID] | Dimension | Stellt den Experience Platform-Datensatz dar, zu dem ein [!UICONTROL Ereignis] gehört hat. |
