---
title: CJA-Zugriffssteuerung
description: Erfahren Sie mehr über Zugriffssteuerungsanforderungen zum Erstellen von Verbindungen, Hinzufügen von Datensätzen, Erstellen von Datenansichten usw.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: ht
source-wordcount: '241'
ht-degree: 100%

---

# CJA-Zugriffssteuerung

Um auf Customer Journey Analytics zugreifen und Aufgaben durchführen zu können, müssen Sie in [Admin Console](https://adminconsole.adobe.com/enterprise/) als Admin zum **Customer Journey Analytics-Produktprofil** hinzugefügt werden. Produktadmins erhalten die folgenden Berechtigungen:

* Erstellen/Aktualisieren/Löschen von Verbindungen oder Datenansichten
* Aktualisieren/Löschen von Projekten, Filtern, Berechnungsmetriken oder von durch andere Benutzer erstellten Filtern
* Freigeben von Workspace-Projekten für alle Benutzenden

## Erforderliche Adobe Experience Platform-Berechtigungen

Nur Produktadmin in Customer Journey Analytics zu werden, reicht nicht aus, um eine Verbindung zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:

* Anzeigen von Schemata
* Verwalten von Schemata
* Anzeigen von Identitäts-Namespaces
* Anzeigen von Datensätzen

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden. Dadurch können sich diese Werte auch in CJA ändern, was sich rückwirkend auch auf das Reporting auswirken kann.

## Benutzerzugriff

Nicht-Produkt-Admins (Benutzende) in Customer Journey Analytics können keine Datenansichten oder Verbindungen anzeigen, sie können aber Filter, Projekte und berechnete Metriken erstellen.

