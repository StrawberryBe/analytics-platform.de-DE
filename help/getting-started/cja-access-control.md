---
title: CJA-Zugriffssteuerung
description: Erfahren Sie mehr über die Zugriffskontrollanforderungen für die drei Zugriffsebenen in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# CJA-Zugriffssteuerung

Customer Journey Analytics (CJA) wird durch drei Zugriffsebenen oder drei Benutzerrollen gesteuert: Produktadministratorrolle, Produktprofil-Administratorrolle und Benutzerzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

## Produkt-Admin-Rolle

Produktadministratoren haben die Berechtigung, alle in Customer Journey Analytics erforderlichen Aufgaben auszuführen. Sie müssen als Produktadministrator zum **Customer Journey Analytics-Produktprofil** im [Admin Console](https://adminconsole.adobe.com/enterprise/) unter Customer Journey Analytics > Registerkarte &quot;Admins&quot;> &quot;Admin hinzufügen&quot;. Produktadmins erhalten die folgenden Berechtigungen:

* Erstellen/Aktualisieren/Löschen von Verbindungen oder Datenansichten
* Aktualisieren/Löschen von Projekten, Filtern, Berechnungsmetriken oder von durch andere Benutzer erstellten Filtern
* Freigeben von Workspace-Projekten für alle Benutzenden

Nur Produktadmin in Customer Journey Analytics zu werden, reicht nicht aus, um eine Verbindung zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:

* Datenmodellierung: Schemas anzeigen, Schemas verwalten
* Daten-Management: Datensätze anzeigen, Datensätze verwalten
* Datenaufnahme: Quellen verwalten
* Anzeigen von Identity-Namespaces

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

## Administratorrolle für Produktprofil

Diese Rolle ähnelt der Rolle &quot;Produkt-Admin&quot;, hat jedoch einen eingeschränkteren Umfang. Ein Produktprofil ist ein Satz von Berechtigungen. Beispielsweise kann ein Produktprofil-Administrator Mitgliedern eines Produktprofils Zugriff auf alle oder bestimmte Datenansichten gewähren. Für Reporting-Tools können diese Administratoren die folgenden Berechtigungen hinzufügen:

![Admin Console-Berechtigungen](assets/permissions.png)

## Zugriff auf Benutzerebene

Nicht-Produktadministratoren (Benutzer) in Customer Journey Analytics können keine Datenansichten oder -verbindungen erstellen, bearbeiten oder anzeigen. Benutzer können Filter, Projekte, Zielgruppen und berechnete Metriken mit speziellen Berechtigungen in der Admin Console erstellen.

## Workspace-Projektkuratierung

Weitere Informationen dazu, wie Sie Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) auf Workspace-Projektebene einschränken und wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden. Dadurch können sich diese Werte auch in CJA ändern, was sich rückwirkend auch auf das Reporting auswirken kann.

