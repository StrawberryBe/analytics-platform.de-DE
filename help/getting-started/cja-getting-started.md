---
title: Customer Journey Analytics - Erste Schritte
description: Customer Journey Analytics - Erste Schritte
translation-type: tm+mt
source-git-commit: 1aebe79040b6c8b9eb8a336e158f5ce6d2ea16a4

---


# Customer Journey Analytics - Erste Schritte

Zur Implementierung von Customer Journey Analytics müssen Sie diesen Arbeitsablauf befolgen. Einige erste Aufgaben werden in Adobe Experience Platform und einige in Customer Journey Analytics ausgeführt.

## Voraussetzungen

Customer Journey Analytics ist für Kunden verfügbar, die

* Adobe Analytics [Select-, Prime- oder Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) -Kunden
* für die [Adobe Experience Platform bereitgestellt werden](https://www.adobe.com/experience-platform.html)
* Haben Sie die SKU für Customer Journey Analytics erworben

## Arbeitsablauf

| Aufgabe | Wird durchgeführt | Details |
|---|---|---|
| **Schritt 1: Vorbereiten des Datenschemas** | Adobe Experience Platform | Verwenden Sie das [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) , um Kundenerlebnisdaten zu standardisieren und Schemata für das Kundenerlebnis-Management zu definieren. |
| **Schritt 2: Erstellen eines Datensatzes basierend auf dem Schema** | Adobe Experience Platform | Daten in Plattform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können einen Datensatz [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)erstellen.<br>Obwohl das Schema für Datensätze, die in Customer Journey Analytics importiert werden können, flexibel ist, muss es einigen grundlegenden Regeln entsprechen. Am besten stellen Sie sicher, dass Ihre Daten diese Anforderungen erfüllen, bevor Sie sie in die Plattform hochladen. (Beachten Sie, dass das Schema sowohl Metriken als auch Dimensionen enthält.)<br>Es gibt drei Datentypen, die mit Customer Journey Analytics kompatibel sind:<ul><li>**Ereignisdaten**: Daten, die Ereignisse in der Zeit darstellen (z. B. Webbesuche, Interaktionen, Transaktionen, POS-Daten, Umfragedaten, Anzeigenimpressionsdaten usw.). Dies sind typische Clickstream-Daten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel. Mit Ereignisdaten können Sie die gewünschte ID verwenden.</li><li>**Suchdaten**: Diese Daten werden zum Nachschlagen von Werten oder Schlüsseln in Ihren Ereignis- oder Profildaten verwendet. Sie können beispielsweise Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten Produktnamen zuordnen.</li><li>**Profildaten**: Daten, die in den Ereignisdaten auf Ihre Besucher, Benutzer oder Kunden angewendet werden. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen.</li></ul> |
| **Schritt 3: Erstellen von Verbindungen zwischen Plattformdatensätzen und Customer Journey Analytics** | Customer Journey Analytics | Siehe [Erstellen einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 4: Datenansichten erstellen** | Customer Journey Analytics | Siehe [Erstellen einer Datenansicht](/help/data-views/create-dataview.md). |
| **Schritt 5: Kanalübergreifende Daten in Workspace melden** | Customer Journey Analytics | Siehe [Durchführen einer grundlegenden Analyse](/help/projects/perform-basic-analysis.md) und [Durchführen einer erweiterten Analyse](/help/projects/perform-adv-analysis.md). |

## Vorbereiten des Datenschemas

[Schema mit dem Schema-Editor erstellen](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)


