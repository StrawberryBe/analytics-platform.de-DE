---
title: Optionen zur Datenaufnahme für Customer Journey Analytics
description: Hier erhalten Sie Informationen über die unterschiedlichen Arten der Datenaufnahme für Customer Journey Analytics.
translation-type: ht
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

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

1. [Erstellen Sie eine Datenschicht](https://docs.adobe.com/content/help/de-DE/analytics/implementation/prepare/data-layer.html), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwenden Sie [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/de-DE/analytics/implementation/launch/overview.html), um Code für die Datenerfassung auf Ihrer Website zu implementieren, falls Sie das noch nicht getan haben. Launch ist eine Tag-Management-Lösung, mit der Sie Analytics-Code zusammen mit anderen Tagging-Anforderungen bereitstellen können. Launch bietet Integrationen mit anderen Lösungen und Produkten und ermöglicht die Bereitstellung von benutzerdefiniertem Code. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklerteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen.
1. Erstellen Sie einen [Adobe Analytics-Quellen-Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Dieser Quellen-Connector nimmt Ihre Analytics-Daten in Experience Platform in einem standardisierten Framework mit dem Namen [Experience-Datenmodell (XDM)-System](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/home.html) auf.
1. Verwenden Sie [Customer Journey Analytics](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-overview/cja-getting-started.html), um eine oder mehrere Verbindungen und Datenansichten zu erstellen, die in Ihr kanalübergreifendes Reporting einfließen werden.
