---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 04ceeb9e9a048a224ea957ad42bc54cbd4b3f249
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 89%

---

# Customer Journey Analytics – Erste Schritte

Befolgen Sie diesen Workflow, um Customer Journey Analytics zu implementieren. Einige erste Aufgaben werden in Adobe Experience Platform und einige in Customer Journey Analytics ausgeführt.

## Voraussetzungen

Customer Journey Analytics ist für Kunden verfügbar, die

* Kunden mit Adobe Analytics [Select, Prime oder Ultimate](https://www.adobe.com/de/analytics/compare-adobe-analytics-packages.html) sind und
* für [Adobe Experience Platform](https://www.adobe.com/de/experience-platform.html) bereitgestellt werden und
* die Customer Journey Analytics-SKU erworben haben.

## Workflow

| Aufgabe | Details |
| --- | --- |
| **Schritt 1: Daten in Adobe Experience Platform einbringen** | Dieser Schritt, der in der Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 1a: Datenschema vorbereiten**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu standardisieren und um Schemas [für das Customer Experience Management zu](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) definieren.</li><li>**Schritt 1b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können [Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Schritt 1c: Daten in Experience Platform aufnehmen**: Verwenden Sie den nativen Adobe Analytics Platform Connector, um herkömmliche Adobe Analytics-Daten in Platform zu importieren. Sie können pro Report Suite eine Quellverbindung erstellen. Siehe [Erstellen einer Quellverbindung mit Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) in der Dokumentation zu Adobe Experience Platform. Nachdem die Verbindung erstellt wurde, werden automatisch ein Zielgruppenschema und ein Datensatz erstellt, die die eingehenden Daten enthalten. Darüber hinaus werden bis zu 13 Monate historischer Daten aufgefüllt und erfasst. Wenn die erste Aufnahme abgeschlossen ist, können Sie mit `Step 2` fortfahren, um eine Verbindung zwischen diesem Analytics-Datensatz und Customer Journey Analytics herzustellen. Sie können auch andere Datentypen über die [Batch-Aufnahme](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en), [die Streaming-Aufnahme](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en) oder über [andere Source Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) aufnehmen.</li></ul> |
| **Schritt 2: Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics herstellen** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Verbindung erstellen](/help/connections/create-connection.md). |
| **Schritt 3: Datenansichten erstellen** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 4: Berichte über kanalübergreifende Daten in Arbeitsbereich erstellen** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |
