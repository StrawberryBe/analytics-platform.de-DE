---
title: Optionen zur Datenaufnahme für Customer Journey Analytics
description: Verstehen Sie, wie Sie Daten auf verschiedene Weise in Customer Journey Analytics erfassen können.
translation-type: tm+mt
source-git-commit: a48ebc2fbd4cb43de4424e9c1805504752a44fce
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 32%

---


# Optionen zur Datenaufnahme für Customer Journey Analytics

Sie haben eine Reihe von Möglichkeiten, Daten in Customer Journey Analytics zu integrieren. Einige von ihnen gehen davon aus, dass Sie traditionelle Adobe Analytics-Daten verschieben möchten, andere gehen davon aus, dass Sie Daten direkt von Adobe Experience Platform erfassen. Dieser Verweis enthält allgemeine Schritte, die Sie ausführen müssen.

## Daten aus dem traditionellen Adobe Analytics erfassen

Dieser Arbeitsablauf nutzt den Adobe Analytics Data Connector und variiert je nachdem, ob Sie DTM oder Launch als Tag-Manager verwenden.

### Über Dynamisches Tag-Management (DTM)

1. [Erstellen einer Datenschicht](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwendung [DTM](https://docs.adobe.com/content/help/de-DE/analytics/implementation/other/dtm/dtm-implementation-overview.html) , um Code für die Datenerfassung auf Ihrer Site zu implementieren, falls noch nicht geschehen. Das Dynamic Tag Management stellt eine einzige Datenschicht bereit, die Daten aus mehreren Quellen übergibt.
1. Erstellen Sie eine [Adobe Analytics-Quellanschluss](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Dieser Source Connector erfasst Ihre Analytics-Daten in einer standardisierten Umgebung mit dem Namen [Erlebnis-Datenmodell (XDM)-System](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/home.html).
1. Verwendung [Customer Journey Analytics](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-overview/cja-getting-started.html) , um eine oder mehrere Ansichten für Verbindungen und Daten zu erstellen, die Ihren Kanal-Berichte informieren.

### Über Start

1. [Erstellen einer Datenschicht](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), wenn Sie das noch nicht getan haben. Eine Datenschicht ist ein Framework von JavaScript-Objekten auf Ihrer Website, die alle in Ihrer Implementierung verwendeten Variablenwerte enthalten. Sie ermöglicht eine bessere Kontrolle und einfachere Wartung Ihrer Implementierung.
1. Verwendung [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) , um Code für die Datenerfassung auf Ihrer Site zu implementieren, falls noch nicht geschehen. Launch ist eine Tag-Management-Lösung, mit der Sie Analytics-Code zusammen mit anderen Tagging-Anforderungen bereitstellen können. Starten Sie Angebot-Integrationen mit anderen Lösungen und Produkten und können Sie benutzerdefinierten Code bereitstellen. Alle diese Aufgaben können ausgeführt werden, ohne dass Entwicklungsteams in Ihrer Organisation Code auf Ihrer Website aktualisieren müssen..
1. Erstellen Sie eine [Adobe Analytics-Quellanschluss](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) in Adobe Experience Platform. Dieser Source Connector erfasst Ihre Analytics-Daten in einer standardisierten Umgebung mit dem Namen [Erlebnis-Datenmodell (XDM)-System](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Verwendung [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) , um eine oder mehrere Ansichten für Verbindungen und Daten zu erstellen, die Ihren Kanal-Berichte informieren.
