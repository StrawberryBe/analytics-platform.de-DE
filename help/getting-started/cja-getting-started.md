---
title: Customer Journey Analytics – Erste Schritte
description: Customer Journey Analytics – Erste Schritte.
translation-type: tm+mt
source-git-commit: 16bca45f2576d3feef8129d558fad6f236852cb9
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 71%

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
|---|---|
| **Schritt 1: Daten in Adobe Experience Platform einbringen** | Dieser Schritt, der in der Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 1a: Schema** vorbereiten: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/home.translate.html) , um Kundenerlebnisdaten zu standardisieren und Schema [für das Kundenerlebnis-Management zu](https://docs.adobe.com/content/help/de-DE/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) definieren.</li><li>**Schritt 1b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können einen Datensatz [in Experience Platform](https://docs.adobe.com/content/help/de-DE/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md) erstellen.</li><li>**Schritt 1c: Daten in Experience Platform** einbeziehen: Verwenden Sie den vordefinierten Adobe Analytics Platform Connector, um herkömmliche Adobe Analytics-Daten in Platform zu bringen. Sie können pro Report Suite eine Quellverbindung erstellen. Siehe [Erstellen einer Quellverbindung mit Adobe Analytics](https://docs.adobe.com/content/help/de-DE/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) in der Dokumentation zu Adobe Experience Platform. Nachdem die Verbindung erstellt wurde, werden automatisch ein Zielgruppenschema und ein Datensatz erstellt, die die eingehenden Daten enthalten. Darüber hinaus werden bis zu 13 Monate historischer Daten aufgefüllt und erfasst. Wenn die erste Aufnahme abgeschlossen ist, können Sie mit `Step 2` fortfahren, um eine Verbindung zwischen diesem Analytics-Datensatz und Customer Journey Analytics herzustellen. Sie können auch andere Datentypen über [Batchverarbeitung](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[Streaming-Erfassung](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)oder über [andere Source Connectors](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)erfassen.</li></ul> |
| **Schritt 2: Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics herstellen** | Mithilfe einer Verbindung können Sie Datensätze aus der Adobe Experience Platform in Workspace integrieren. Für die Berichterstellung zu Experience Platformen-Datensätzen müssen Sie zunächst eine Verbindung zwischen Datensätzen in Experience Platform und Workspace herstellen.<br>Siehe [Verbindung erstellen](/help/connections/create-connection.md). |
| **Schritt 3: Datenansichten erstellen** | Eine Ansicht ist eine gefilterte Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenschicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 4: Berichten über kanalübergreifende Daten in Workspace erstellen** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre eingebrachten Daten zu analysieren.<br>Siehe [Grundlegende Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |
