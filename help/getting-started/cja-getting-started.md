---
title: Customer Journey Analytics - Erste Schritte
description: Customer Journey Analytics - Erste Schritte
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 10%

---


# Customer Journey Analytics - Erste Schritte

Zur Implementierung von Customer Journey Analytics müssen Sie diesen Arbeitsablauf befolgen. Einige erste Aufgaben werden in Adobe Experience Platform und einige in Customer Journey Analytics durchgeführt.

## Voraussetzungen

Customer Journey Analytics ist für Kunden verfügbar, die

* Are Adobe Analytics [Select, Prime, or Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) customers, and
* für die [Adobe Experience Platform](https://www.adobe.com/de/experience-platform.html)bereitgestellt werden und
* Haben Sie die SKU für Customer Journey Analytics erworben

## Workflow

| Aufgabe | Details |
|---|---|---|
| **Schritt 1: Daten in Adobe Experience Platform abrufen** | Dieser Schritt, der in Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<br>**Schritt 1a: Schema **vorbereiten: Verwenden Sie das[Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html), um Kundenerlebnisdaten zu standardisieren und Schema[für das Kundenerlebnis-Management zu](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)definieren.<br>**Schritt 1b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Plattform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können einen Datensatz [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)erstellen.<br>**Schritt 1c: Daten in die Erlebnisplattform **aufnehmen: Verwenden Sie den vordefinierten Adobe Analytics Platform Connector, um herkömmliche Adobe Analytics-Daten in eine Plattform zu integrieren. Sie können pro Report Suite eine Quellverbindung erstellen. Siehe[Erstellen einer Quellverbindung mit Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)in der Dokumentation zu Adobe Experience Platform. Nachdem die Verbindung erstellt wurde, wird automatisch ein Zielgruppe-Schema und ein Dataset erstellt, die die eingehenden Daten enthalten. Darüber hinaus erfolgt die Datensicherung und erfasst bis zu 13 Monate historische Daten. When the initial ingestion completes, you can proceed with`Step 2`to create a connection between this Analytics dataset and Customer Journey Analytics.<br>Sie können auch andere Datentypen über[Batchaufnahme](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[Streaming-Erfassung](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)oder über[andere Quell-Connectors](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)erfassen. |
| **Schritt 2: Verbindungen zwischen Plattformdatensätzen und Customer Journey Analytics erstellen** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Workspace integrieren. Um einen Bericht über Experience Platform-Datensätze zu erstellen, müssen Sie zunächst eine Verbindung zwischen Datensätzen in Experience Platform und Workspace herstellen.<br>Siehe [Erstellen einer Verbindung](/help/connections/create-connection.md). |
| **Step 3: Create data views** | Eine Ansicht ist eine gefilterte Ansicht der Daten. Sie können verschiedene Ansichten für die gleiche Verbindung erstellen, mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw. Sie können mehrere Ansichten für einen Datensatz erstellen.<br>Siehe [Erstellen einer Ansicht](/help/data-views/create-dataview.md). |
| **Schritt 4: Berichte zu Ihren Daten über Kanal in Workspace** | Nachdem Sie Verbindungen und Ansichten erstellt haben, analysieren Sie die Daten, die Sie mit der Leistungsfähigkeit und Flexibilität von Analyse Workspace eingebracht haben.<br>Siehe [Durchführen einer grundlegenden Analyse](/help/projects/perform-basic-analysis.md) und [Durchführen einer erweiterten Analyse](/help/projects/perform-adv-analysis.md). |
