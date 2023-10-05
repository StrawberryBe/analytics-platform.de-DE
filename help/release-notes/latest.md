---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 49d91b513abd545ea73c7867817cd8724b460be4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 50%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (Oktober 2023)

**Letztes Update**: 4. Oktober 2023

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 4. Oktober 2023 bis zum 24. Oktober 2023. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Vollständige Tabellen in die Cloud exportieren** | Mit dem Customer Journey Analytics Full Table Export können Sie Millionen von Workspace-Zeilen in Cloud-Ziele exportieren. <p>Der Export vollständiger Tabellen bietet eine einmalige oder geplante Bereitstellung von Datentabellen, die in Workspace entwickelt wurden und bis zu fünf Aufschlüsselungen, fünf Metriken, Filtern und berechneten Metriken in einer verketteten Tabelle unterstützen. Es ist die Entwicklung von Data Warehouse-Berichten in Adobe Analytics, mit vielen neuen, häufig angeforderten Funktionen, die heute nicht in Data Warehouse verfügbar sind.</p><p> Zu den Cloud-Exportoptionen gehören:</p><ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Weitere Informationen finden Sie unter [Customer Journey Analytics-Berichte in die Cloud exportieren](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 4. Oktober 2023 | 19. Oktober 2023 |
| **Neue Spalten verfügbar bei der Verwaltung von Komponenten** | Die folgenden neuen Spalten sind jetzt im [Manager für berechnete Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) und im [Filter-Manager](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) für das Verwalten von Komponenten verfügbar:<ul><li>Verwendet in</li><li>Zuletzt verwendet</li></ul>Mithilfe dieser Informationen können Sie feststellen, ob eine Komponente für Benutzerinnen und Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss. Sie können das Datenwörterbuch zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrem Unternehmen zu verfolgen und besser zu verstehen. | 23. September 2023 | 4. Oktober 2023 |
| **Migrieren von Adobe Analytics-Projekten und allen enthaltenen Komponenten zum Customer Journey Analytics** | Sie können Ihre Adobe Analytics-Projekte jetzt auf Customer Journey Analytics migrieren. Dadurch wird der Übergang von Adobe Analytics zu Customer Journey Analytics vereinfacht. <p>Wenn Sie Projekte zu Customer Journey Analytics migrieren, werden Assets von einer Adobe Analytics Report Suite zu einer Customer Journey Analytics-Datenansicht zugeordnet.</p> <p>Sie migrieren Projekte über die Adobe Analytics-Benutzeroberfläche zu Customer Journey Analytics. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | Nicht angegeben | 9. Oktober 2023 |
| **Adobe Product Analytics: Serie ein-/ausblenden** | Klicken Sie auf die Diagrammlegende oder Tabellenzeilen, um die Sichtbarkeit von Reihen in Ihren Visualisierungen zu steuern.  [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=en) | Nicht angegeben | 4. Oktober 2023 |
| **Anmerkungen in Adobe Product Analytics** | Die geführte Analyse unterstützt jetzt die Möglichkeit, in Customer Journey Analytics erstellte Anmerkungen anzuzeigen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en) | Nicht angegeben | 4. Oktober 2023 |
| **Reporting Activity Manager** | Mit dem Reporting Activity Manager können Sie die Berichtskapazität für jede Verbindung in Ihrem Unternehmen anzeigen. Administratoren erhalten detaillierte Einblicke in den Berichtsverbrauch, um Kapazitätsprobleme während Spitzenzeiten der Berichterstellung einfach zu diagnostizieren und zu beheben. Zu den wichtigsten Funktionen des Reporting Activity Manager gehören:<ul><li>Abbrechen aktueller Berichtsanforderungen (einschließlich Anforderungen aus geführten Analysen und vollständigen Tabellenexporten)</li><li>Einschränken nachfolgender Anforderungen für einen bestimmten Zeitraum</li></ul>Administratoren können nicht nur aktuelle Anforderungen abbrechen, sondern auch Anforderungen für einen bestimmten Zeitraum einschränken. Administratoren können Anforderungen nach Anforderung, Projekt oder Benutzer einschränken.  Weitere Informationen (in Kürze verfügbar) | 17. Oktober 2023 | 23. Oktober 2023 |

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
