---
title: Customer Journey Analytics - Erste Schritte
description: Customer Journey Analytics - Erste Schritte
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# Customer Journey Analytics - Erste Schritte

Zur Implementierung von Customer Journey Analytics müssen Sie diesen Arbeitsablauf befolgen. Einige erste Aufgaben werden in Adobe Experience Platform und einige in Customer Journey Analytics durchgeführt.

| Aufgabe | Wird durchgeführt | Details |
|---|---|---|
| **Schritt 1: Daten in Adobe Experience Platform abrufen** | Adobe Experience Platform |  |
| **Schritt 2: Schema vorbereiten** | Adobe Experience Platform | Verwenden Sie das [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) , um Kundenerlebnisdaten zu standardisieren und Schema für das Kundenerlebnis-Management zu definieren. |
| **Schritt 3: Erstellen eines Datensatzes basierend auf dem Schema** | Adobe Experience Platform | Daten in Plattform bestehen aus Datensätzen wie E-Mail-Datensätzen, CRM-Datensätzen, POS-Datensätzen, dem Adobe Analytics-Datensatz usw. Jeder Datensatz besteht aus einem Schema und Datenstapeln. Sie können einen Datensatz [in Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)erstellen.<br>Obwohl das Schema für Datensätze, die in Customer Journey Analytics importiert werden können, flexibel ist, muss es einigen Grundregeln entsprechen. Am besten stellen Sie sicher, dass Ihre Daten diese Anforderungen erfüllen, bevor Sie sie in die Plattform hochladen. (Beachten Sie, dass Schema sowohl Metriken als auch Dimensionen enthält.)<br>Es gibt drei Datentypen, die mit Customer Journey Analytics kompatibel sind:<ul><li>**Ereignis-Daten**: Daten, die zeitliche Ereignis darstellen (z. B. Webbesuche, Interaktionen, Transaktionen, POS-Daten, Daten zur Umfrage, Daten zu Anzeigenimpressionen usw.). Dies sind typische Clickstream-Daten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel. Mit Ereignis-Daten können Sie die gewünschte ID verwenden.</li><li>**Suchdaten**: Diese Daten werden zum Nachschlagen von Werten oder Schlüsseln in Ihren Ereignis- oder Profil-Daten verwendet. Sie können beispielsweise Suchdaten hochladen, die numerische IDs in Ihren Ereignis-Daten Produktnamen zuordnen.</li><li>**Profil-Daten**: Daten, die in den Ereignis-Daten auf Ihre Besucher, Benutzer oder Kunden angewendet werden. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen.</li></ul> |
| **Schritt 3: Erstellen von Verbindungen zwischen Plattformdatensätzen und Customer Journey Analytics** | Customer Journey Analytics | Siehe [Erstellen einer Verbindung](/help/connections/create-connection.md). |
| **Schritt 4: Ansichten erstellen** | Customer Journey Analytics | See [Create a data view](/help/data-views/create-dataview.md). |
| **Schritt 5: Berichte zu Ihren Daten über Kanal in Workspace** | Customer Journey Analytics | Siehe [Durchführen einer grundlegenden Analyse](/help/projects/perform-basic-analysis.md) und [Durchführen einer erweiterten Analyse](/help/projects/perform-adv-analysis.md). |

## Voraussetzungen

Customer Journey Analytics ist für Kunden verfügbar, die

* Adobe Analytics [Select-, Prime- oder Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) -Kunden und
* für die [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)bereitgestellt werden und
* Haben Sie die SKU für Customer Journey Analytics erworben

## Schema vorbereiten

[Erstellen eines Schemas mit dem Schema-Editor](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Schritt 1: Daten in Adobe Experience Platform abrufen

Bevor Sie Experience Platform-Daten in CJA nutzen können, müssen Sie diese Daten in Platform erfassen. Es gibt mehrere Möglichkeiten, dies zu tun:

* Wenn Sie Ihre vorhandenen Adobe Analytics-Daten einbringen möchten, verwenden Sie den Adobe Analytics Platform Connector.
* Um andere Daten einzufügen, verwenden Sie Dateien im .csv- oder Parquet-Format, um


## Schritt 1 a: Integrieren Sie Ihre vorhandenen Analytics-Daten in Adobe Experience Platform

Verwenden Sie den Adobe Analytics Platform Connector, um herkömmliche Analytics-Daten in eine Plattform zu integrieren. Sie können pro Report Suite eine Quellverbindung erstellen. Siehe [Erstellen einer Quellverbindung mit Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) in der Dokumentation zu Adobe Experience Platform.

Nachdem die Verbindung erstellt wurde, wird automatisch ein Zielgruppe-Schema und ein Dataset erstellt, die die eingehenden Daten enthalten. Darüber hinaus erfolgt die Datensicherung und erfasst bis zu 13 Monate historische Daten. Nach Abschluss der ersten Erfassung können Sie mit Schritt x fortfahren, um eine Verbindung zwischen diesem Analytics-Datensatz und Customer Journey Analytics zu erstellen.

## Schritt 1 b: Schema erstellen




