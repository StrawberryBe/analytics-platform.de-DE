---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2dab438b956513eaff3f05d2ff8de2fff43d9977
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 75%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (August 2023)

**Letzte Aktualisierung**: 9. August 2023

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 9. August bis 13. September 2023. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder-Verbesserungen** | <ul><li>Laden Sie geplante Aufgaben vom Tab Verlauf herunter, auf dem Sie den Verlauf geplanter Aufgaben anzeigen können. Laden Sie die Arbeitsmappe von dieser Aufgabe herunter. </li><li>Startdatum als Dimension: Ermöglicht es Benutzern, das Startdatum des Datenblocks als Dimension in der Datenblock-Ausgabe zu platzieren. </li></ul> | Nicht angegeben | 17. August 2023 |
| **Währungsumrechnung** | Kunden-Journey bietet die Möglichkeit, mehrere Währungen zu unterstützen. In den Datenansichtseinstellungen können Sie eine Währung in eine andere Währung konvertieren. [Weitere Informationen](/help/data-views/component-settings/format.md) | Nicht angegeben | 31. August 2023 |
| **Unterstützung für A4T-Klassifizierungen im Analytics Source Connector** | Wir fügen eine Korrelations-ID hinzu, um die Zuordnung von Classification-Daten zu Adobe Target-Aktivitäten und Erlebnisereignissen zu erleichtern. | Nicht angegeben | 31. August 2023 |
| **Reporting Activity Manager** | Bietet Administratoren detaillierte Einblicke in den Berichtsverbrauch für jede Verbindung, sodass Administratoren während Spitzenzeiten der Berichterstellung mühelos Kapazitätsprobleme diagnostizieren und beheben können. | Nicht angegeben | 6. September 2023 |
| **Zugriff von PowerBI und Tableau auf Customer Journey Analytics-Datenansichten** | Der SQL-Connector für Adobe Customer Journey Analytics ermöglicht den SQL-Zugriff auf Datenansichten, die Sie in Customer Journey Analytics definiert haben. Dateningenieurinnen oder -ingenieure und -analystinnen oder -analysten, die mit Power BI, Tableau oder anderen Tools für Business Intelligence und Visualisierung vertraut sind, können jetzt Berichte und Dashboards auf der Basis derselben Datenansichten erstellen, die Customer Journey Analytics-Benutzende für ihre Analysis Workspace-Projekte verwenden. [Weitere Informationen](/help/data-views/sql-connector.md) | Nicht angegeben | 13. September 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Wichtige Hinweise für Customer Journey Analytics-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Änderungen bei der Verarbeitung von Daten durch Customer Journey Analytics** | 22. Juni 2023 | Wir haben kürzlich die Art und Weise geändert, wie Daten in Customer Journey Analytics verarbeitet werden.<ul><li>Alle Ereignisdaten mit einem Zeitstempel unter 24 Stunden werden gestreamt.</li><li>Alle Ereignisdaten mit einem Zeitstempel, der älter als 24 Stunden ist (auch wenn sie sich im gleichen Batch wie neuere Daten befinden) werden als Aufstockung betrachtet und mit einer niedrigeren Priorität aufgenommen.</li></ul> |

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
