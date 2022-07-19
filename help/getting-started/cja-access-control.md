---
title: CJA-Zugriffssteuerung
description: Erfahren Sie mehr über die Zugriffssteuerungsanforderungen zum Erstellen von Verbindungen, Hinzufügen von Datensätzen, Erstellen von Datenansichten usw.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 39%

---

# CJA-Zugriffssteuerung

Um auf Customer Journey Analytics zuzugreifen und Aufgaben auszuführen, müssen Sie als Administrator der **Customer Journey Analytics-Produktprofil** im [Admin Console](https://adminconsole.adobe.com/enterprise/). Produktadministratoren erhalten die folgenden Berechtigungen:

* Erstellen/Aktualisieren/Löschen von Verbindungen oder Datenansichten
* Projekte, Filter, berechnete Metriken oder von anderen Benutzern erstellte Filter aktualisieren/löschen
* Freigeben von Workspace-Projekten für alle Benutzer

## Erforderliche Adobe Experience Platform-Berechtigungen

Allein als Produktadministrator in Customer Journey Analytics zu fungieren reicht nicht aus, um eine Verbindung zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:

* Anzeigen von Schemata
* Verwalten von Schemata
* Anzeigen von Identitäts-Namespaces
* Anzeigen von Datensätzen

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugangssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

## Zugriff auf einzelne Metriken oder Dimensionen gewähren

Sie können in Customer Journey Analytics keine Berechtigungen für einzelne Metriken oder Dimensionen erteilen oder verweigern, wie Sie es im herkömmlichen Adobe Analytics tun können. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden. Dadurch können sich diese Werte auch in CJA ändern, was sich rückwirkend auch auf das Reporting auswirken kann.

## Benutzerzugriff

Nicht-Produktadministratoren (Benutzer) in Customer Journey Analytics können keine Datenansichten oder Verbindungen anzeigen, sie können jedoch Filter, Projekte und berechnete Metriken erstellen.

