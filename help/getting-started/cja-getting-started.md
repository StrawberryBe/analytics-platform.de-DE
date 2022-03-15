---
title: Customer Journey Analytics – Erste Schritte
description: Machen Sie sich mit den Voraussetzungen und dem Workflow vertraut, die für die Implementierung von Customer Journey Analytics erforderlich sind.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: d0ffd1117bb9876820f28ad982a7dc9061bf0c77
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 82%

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
| **Schritt 1: Wenn Sie von Adobe Analytics zu CJA migrieren, lesen Sie das Administratorhandbuch.** | [Entwicklung von Adobe Analytics zu Customer Journey Analytics](/help/getting-started/aa-to-cja.md) |
| **Schritt 2: Daten in Adobe Experience Platform einbringen** | Dieser Schritt, der in der Adobe Experience Platform ausgeführt wird, umfasst mehrere Unterschritte:<ul><li>**Schritt 2a: Datenschema vorbereiten**: Verwenden Sie das [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), um Kundenerlebnisdaten zu standardisieren und um Schemas [für das Customer Experience Management zu](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) definieren.</li><li>**Schritt 2b: Erstellen Sie einen Datensatz basierend auf dem Schema**: Daten in Platform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können [Datensatz in Experience Platform erstellen](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html).</li><li>**Schritt 2c: Daten in Experience Platform erfassen**: Hier haben Sie mehrere Möglichkeiten. Anzeigen der [Anwendungsfälle für die Datenerfassung](/help/use-cases/data-ingestion.md) für weitere Informationen. |
| **Schritt 3: Verbindungen zwischen Platform-Datensätzen und Customer Journey Analytics herstellen** | Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Experience Platform und Arbeitsbereich herstellen.<br>Siehe [Verbindung erstellen](/help/connections/create-connection.md). |
| **Schritt 4: Datenansichten erstellen** | Eine Datenansicht ist eine „gefilterte“ Ansicht der Daten. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen.<br>Siehe [Datenansicht erstellen](/help/data-views/create-dataview.md). |
| **Schritt 5: Berichte über kanalübergreifende Daten in Arbeitsbereich erstellen** | Nachdem Sie Verbindungen und Datenansichten erstellt haben, nutzen Sie die leistungsstarken und flexiblen Funktionen von Analysis Workspace, um Ihre erfassten Daten zu analysieren.<br>Siehe [Einfache Analyse durchführen](/help/analysis-workspace/perform-basic-analysis.md) und [Erweiterte Analyse durchführen](/help/analysis-workspace/perform-adv-analysis.md). |
