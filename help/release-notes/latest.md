---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1482cc7b9da01b60e15d2e48b1156b603e20c6e3
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 97%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (Oktober 2023)

**Letztes Update**: 17. Oktober 2023

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 4. Oktober 2023 bis zum 24. Oktober 2023. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Zeilenanzahl-Metriken für Lookup- und Profildatensätze** | Diese Metriken waren zuvor nur für Ereignis-Datensätze verfügbar. | 16. Oktober 2023 |
| **Exportieren von vollständigen Tabellen in die Cloud** | Mit dem Export von vollständigen Tabellen aus Customer Journey Analytics können Sie Millionen von Workspace-Zeilen in Cloud-Ziele exportieren. <p>Der Export vollständiger Tabellen bietet einen einmaligen oder geplanten Versand von Datentabellen, die in Workspace entwickelt wurden. Dabei werden bis zu fünf Aufschlüsselungen, fünf Metriken, Filter und berechnete Metriken in einer verketteten Tabelle unterstützt. Es ist die Weiterentwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind.</p><p> Zu den Cloud-Exportoptionen gehören:</p><ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Weitere Informationen finden Sie unter [Exportieren von Customer Journey Analytics-Berichten in die Cloud](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=de). | 4. Oktober 2023 | 19. Oktober 2023 |
| **Neue Spalten verfügbar bei der Verwaltung von Komponenten** | Die folgenden neuen Spalten sind jetzt im [Manager für berechnete Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=de) und im [Filter-Manager](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=de) für das Verwalten von Komponenten verfügbar:<ul><li>Verwendet in</li><li>Zuletzt verwendet</li></ul>Mithilfe dieser Informationen können Sie feststellen, ob eine Komponente für Benutzerinnen und Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss. Sie können das Datenwörterbuch zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrem Unternehmen zu verfolgen und besser zu verstehen. | 23. September 2023 | 4. Oktober 2023 |
| **Migrieren von Adobe Analytics-Projekten und allen enthaltenen Komponenten zu Customer Journey Analytics** | Sie können Ihre Adobe Analytics-Projekte jetzt zu Customer Journey Analytics migrieren. Dadurch wird der Übergang von Adobe Analytics zu Customer Journey Analytics vereinfacht. <p>Wenn Sie Projekte zu Customer Journey Analytics migrieren, werden Assets aus einer Report Suite inAdobe Analytics einer Customer Journey Analytics-Datenansicht zugeordnet.</p> <p>Sie migrieren Projekte über die Adobe Analytics-Benutzeroberfläche zu Customer Journey Analytics. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=de)</p> | Nicht angegeben | 9. Oktober 2023 |
| **Adobe Product Analytics: Reihe ein-/ausblenden** | Klicken Sie auf die Diagrammlegende oder Tabellenzeilen, um die Sichtbarkeit von Reihen in Ihren Visualisierungen zu steuern.  [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=de) | Nicht angegeben | 4. Oktober 2023 |
| **Anmerkungen in Adobe Product Analytics** | Die geführte Analyse unterstützt jetzt die Möglichkeit, in Customer Journey Analytics erstellte Anmerkungen anzuzeigen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=de) | Nicht angegeben | 4. Oktober 2023 |
| **Reporting Activity Manager** | Reporting Activity Manager zeigt die Berichtskapazität für jede Verbindung in Ihrer Organisation an. Er bietet Admins detaillierte Einblicke in die Berichtsnutzung und hilft ihnen, Kapazitätsprobleme bei Spitzen während der Berichterstellung mühelos zu diagnostizieren und zu beheben. Zu den wichtigsten Funktionen von Reporting Activity Manager gehören:<ul><li>Abbrechen aktueller Berichtsanfragen (einschließlich Anfragen aus geführten Analysen und Exporten von vollständigen Tabellen)</li><li>Einschränken nachfolgender Anfragen für einen bestimmten Zeitraum</li></ul>Admins können nicht nur aktuelle Anfragen abbrechen, sondern auch Anfragen für einen bestimmten Zeitraum einschränken. Admins können Anfragen nach Anfrage, Projekt oder Benutzerin bzw. Benutzer einschränken.  [Weitere Informationen](/help/reporting-activity-manager/reporting-activity-overview.md) | 17. Oktober 2023 | 23. Oktober 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Nicht angegeben | nicht angegeben | Nicht angegeben |

{style="table-layout:auto"}

## Mitteilungen über das Ende der Nutzungsdauer (EOL)

| Ende der Nutzungsdauer eines Produkts oder einer Funktion | Datum hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Migration auf OAuth Server-zu-Server-Anmeldeinformationen für Adobe I/O** | 11. Mai 2023 | Kundinnen und Kunden von Adobe Analytics-API, Customer Journey Analytics-API und Livestream, die JWT-Anmeldeinformationen für Adobe I/O verwenden, müssen bis zum **1. Januar 2025** auf OAuth Server-zu-Server-Anmeldeinformationen für Adobe I/O migrieren. Adobe I/O lässt die Erstellung neuer JWT-Anmeldeinformationen ab dem 1. Mai 2024 nicht mehr zu. Kunden und Kundinnen, die JWT verwenden, müssen neue OAuth Server-zu-Server-Anmeldeinformationen erstellen oder ihre bestehende JWT-Anmeldeinformationen zu OAuth Server-zu-Server-Anmeldeinformationen migrieren. Kunden und Kundinnen müssen außerdem ihre Client-Anwendungen aktualisieren, um die neuen OAuth Server-to-Server-Anmeldeinformationen zu verwenden. <ul><li>[Migration von Dienstkonto-Anmeldeinformationen (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Verwenden der neuen OAuth Server-zu-Server-Anmeldeinformationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Häufig gestellte Fragen (FAQ)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
