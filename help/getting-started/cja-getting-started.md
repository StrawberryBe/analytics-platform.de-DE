---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 91%

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
| **Schritt 1: Wenn Sie von Adobe Analytics zu CJA migrieren, erfahren Sie, was zu tun ist.** | Siehe [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). |
| **Schritt 2: Andere Daten in Adobe Experience Platform abrufen** | Dieser Schritt, der in Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 2a: Bereiten Sie Ihr Datenschema vor**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu [standardisieren und um Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für das Customer Experience Management zu definieren.</li><li>**Schritt 2b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können [einen Datensatz in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=de) erstellen.</li><li>**Schritt 2c: Nehmen Sie Daten in Experience Platform auf**: Hier haben Sie mehrere Möglichkeiten. Weitere Informationen dazu finden Sie in den [Anwendungsfällen für die Datenaufnahme](/help/use-cases/data-ingestion/data-ingestion.md). |
| **Schritt 3: Erstellen Sie Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Verbindung erstellen](/help/connections/create-connection.md). |
| **Schritt 4: Erstellen Sie Datenansichten** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 5: Erstellen Sie Berichte über kanalübergreifende Daten im Arbeitsbereich** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |
