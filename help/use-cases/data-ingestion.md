---
title: Optionen zur Datenaufnahme für Customer Journey Analytics
description: Hier erhalten Sie Informationen über die unterschiedlichen Arten der Datenaufnahme für Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 70%

---


# Optionen zur Datenaufnahme für Customer Journey Analytics

Sie haben eine Reihe von Möglichkeiten, Daten in Customer Journey Analytics aufzunehmen. Bei einigen werden Daten aus Adobe Analytics verschoben, bei anderen werden Daten direkt von Adobe Experience Platform übertragen. Dieses Informationsmaterial enthält allgemeine Schritte mit Links zu detaillierteren Informationen.

## Daten aus Adobe Analytics erfassen

Dieser Workflow nutzt den Adobe Analytics Data Connector und variiert je nachdem, ob Sie DTM oder Launch als Tag-Manager verwenden.

### Mit Dynamic Tag Management (DTM)

1. [Erstellen Sie eine Datenschicht](https://docs.adobe.com/content/help/de-DE/analytics/implementation/prepare/data-layer.html), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwenden Sie [DTM](https://docs.adobe.com/content/help/de-DE/analytics/implementation/other/dtm/dtm-implementation-overview.html), um Code für die Datenerfassung auf Ihrer Website zu implementieren, falls Sie das noch nicht getan haben. Das Dynamic Tag Management stellt eine einzige Datenschicht bereit, die Daten aus mehreren Quellen übergibt.
1. Erstellen Sie einen [Adobe Analytics-Quellen-Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Dieser Quellen-Connector nimmt Ihre Analytics-Daten in Experience Platform in einem standardisierten Framework mit dem Namen [Experience-Datenmodell (XDM)-System](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/home.html) auf.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

### Über Launch

1. [Erstellen Sie eine Datenschicht](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwenden Sie [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/de-DE/analytics/implementation/launch/overview.html), um Code für die Datenerfassung auf Ihrer Website zu implementieren, falls Sie das noch nicht getan haben. Launch ist eine Tag-Management-Lösung, mit der Sie Analytics-Code zusammen mit anderen Tagging-Anforderungen bereitstellen können. Launch bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklerteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.
1. Erstellen Sie einen [Adobe Analytics-Quellen-Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Dieser Quellen-Connector nimmt Ihre Analytics-Daten in Experience Platform in einem standardisierten Framework mit dem Namen [Experience-Datenmodell (XDM)-System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) auf.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Daten über das Adobe Experience Platform Web SDK und das Edge Network erfassen

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDKist eine clientseitige JavaScript-Bibliothek, mit der Adobe Experience Cloud-Kunden über das Adobe Experience Platform Edge Network mit den verschiedenen Diensten im Experience Cloud interagieren können. Sie können diese Erfassung mit oder ohne Start konfigurieren.

### Ohne Start

Dieser Link funktioniert nicht: https://docs.adobe.com/content/help/en/experience-platform/edge/get-started/quick-start-without-launch.html. Ist dies auch ohne Start möglich?

### Mit Start

1. [Konfigurieren Sie die AEP Web SDK-](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Erweiterung, um Daten von Webeigenschaften über das Adobe Experience Platform Edge Network an das Adobe Experience Cloud zu senden.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Daten mit Stapelverarbeitung und Streaming-Erfassung erfassen

Adobe Experience Platform bringt Daten aus mehreren Quellen zusammen, um Marketern ein besseres Verständnis des Verhaltens ihrer Kunden zu ermöglichen. Datenerfassung in Adobe Experience Platform stellt die verschiedenen Methoden, mit denen Platform Daten aus den Quellen erfasst, sowie die Art und Weise dar, wie die Daten im Data Lake zur Verwendung durch nachgelagerte Platform-Dienste persistiert werden.

### Batch-Erfassung

1. Richten Sie [Batch Ingestion](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) ein, damit Sie Daten als Stapeldateien in Adobe Experience Platform erfassen können. Daten, die aufgenommen werden, können Profildaten aus einer reduzierten Datei in einem CRM-System (z. B. eine Parquet-Datei) oder Daten sein, die einem bekannten Schema in der Experience-Datenmodell (XDM)-Registry entsprechen.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

### Streaming-Erfassung

1. Richten Sie [Streaming-Erfassung](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) ein, um Daten von Client- und serverseitigen Geräten in Echtzeit an die Experience Platform zu senden.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.

## Google Analytics-Daten zur Analyse in Customer Journey Analytics einbringen

In diesem Lernprogramm erfahren Sie, wie Sie die Daten von Google Analytics mit Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) analysieren, um detaillierte Schritte zu erhalten.[

## Verwenden Sie die Bulk Data Insertion API, um Daten in Analytics zu erhalten und dann über den Adobe Source Connector in der Experience Platform zu erfassen.

1. [Verwenden Sie die ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) API zum Einfügen von Massendaten, um serverseitige Erfassungsdaten an Adobe Analytics zu senden. Damit können Sie CSV-formatierte Dateien mit Ereignis-Daten senden.
1. [Erstellen Sie ein Adobe Analytics-Quell-](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) Connector, um diese Verbraucherdaten in Adobe Experience Platform zu importieren.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.