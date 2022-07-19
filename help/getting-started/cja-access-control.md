---
title: CJA-Zugriffssteuerung
description: Erfahren Sie mehr über die Zugriffssteuerungsanforderungen zum Erstellen von Verbindungen, Hinzufügen von Datensätzen, Erstellen von Datenansichten usw.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 61%

---


# CJA-Zugriffssteuerung

Zum Erstellen von Verbindungen, Hinzufügen von Datensätzen usw. benötigen Sie die folgenden Berechtigungen in der [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Um auf Customer Journey Analytics zugreifen oder eine Verbindung herstellen zu können, müssen Sie als Administrator der **Customer Journey Analytics Product** im [Admin Console](https://adminconsole.adobe.com/enterprise/). Produktadministratoren erhalten die folgenden Berechtigungen:
   * Erstellen/Aktualisieren/Löschen von Verbindungen oder Ansichten
   * Projekte, Filter, berechnete Metriken oder von anderen Benutzern erstellte Filter aktualisieren/löschen
   * Freigeben eines Workspace-Projekts für alle Benutzer
* Ein Produktadministrator in Customer Journey Analytics zu werden, reicht nicht aus, um eine Verbindung zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:
   * Anzeigen von Schemata
   * Verwalten von Schemata
   * Anzeigen von Identitäts-Namespaces
   * Anzeigen von Datensätzen

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugangssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

>[!NOTE]
>
>Sie können in Customer Journey Analytics keine Berechtigungen für einzelne Metriken oder Dimensionen erteilen oder verweigern, wie Sie es im herkömmlichen Adobe Analytics tun können. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden. Dadurch können sich diese Werte auch in CJA ändern, was sich rückwirkend auch auf das Reporting auswirken kann.

## Benutzerzugriff

Nicht-Produkt-Administratoren (Benutzer) in Customer Journey Analytics können keine Datenansichten oder Verbindungen anzeigen, sie können aber Filter, Projekte und berechnete Metriken erstellen.