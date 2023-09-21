---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 82%

---

# Aktuelle Versionshinweise zu Adobe Customer Journey Analytics (September 2023)

**Letzte Aktualisierung**: 13. September 2023

Diese Versionshinweise beziehen sich auf den Veröffentlichungszeitraum vom 13. September 2023 bis zum 3. Oktober 2023. Versionen von Adobe Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Unterstützung für A4T-Klassifizierungen im Analytics Source Connector** | Das Feld `_experience.decisioning.propositions.scopeDetails.correlationID` ist jetzt im Quell-Connector-Schema von Adobe Analytics verfügbar. Dieses Feld wird zur Unterstützung von A4T-Klassifizierungen verwendet und wird ab September 2023 ausgefüllt. | | Nicht angegeben | 12. September 2023 |
| **Aktualisierungen für abgeleitete Felder** | Die folgenden Aktualisierungen wurden an der Funktionalität von abgeleiteten Feldern vorgenommen:<ul><li>Die Funktion [!UICONTROL Lookup] wurde in [!UICONTROL Klassifizieren] umbenannt und verfügt jetzt über weitere Aktionen zum Hochladen von CSV-Daten. **(Veröffentlichung am 27. September 2023)**</li><li>Beim Definieren eines abgeleiteten Felds stehen zusätzliche Funktionen zur Verfügung: [!UICONTROL Zuschneiden], [!UICONTROL Kleinschreibung] und [!UICONTROL Lookup].</li><li>Definitionen von abgeleiteten Feldern unterstützen jetzt auch Felder aus [!UICONTROL Lookup]- und [!UICONTROL Profil]-Datensätzen.</li></ul>[Weitere Informationen](/help/data-views/derived-fields/derived-fields.md) | Nicht angegeben | 13. September 2023 |
| **Neue Funktionen in Adobe Product Analytics** | <ul><li>**Anomalieerkennung**: Vergleichen Sie Ereignisse mit erwarteten Werten, die aus historischen Trends abgeleitet wurden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**Ansicht für Trends bei der Nutzungshäufigkeit**: Messen Sie die Benutzerakzeptanz Ihrer Funktionen anhand der Nutzungshäufigkeit. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html?lang=de)</li><li>**Benutzereinstellungen**: Konfigurieren Sie eine Reihe von Benutzereinstellungen, z. B. Farbpaletten und Zahlenformat. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=de)</li></ul> | Nicht angegeben | 18. September 2023 |
| **Geräte-Lookups für Experience Edge** | Aktivieren Sie die automatische Datenerfassung zum Gerätetyp über das Experience Platform Edge-Netzwerk. Dieser Experience Edge-Dienst kommt Customer Journey Analytics sowie anderen Experience Platform-Apps zugute. (Link zur Dokumentation folgt) | Nicht angegeben | 27. September 2023 |
| **Neue Spalten verfügbar bei der Verwaltung von Komponenten** | Die folgenden neuen Spalten sind jetzt im [Manager für berechnete Metriken](/help/components/calc-metrics/cm-workflow/cm-manager.md) und [Filter Manager](/help/components/filters/manage-filters.md) beim Verwalten von Komponenten:<ul><li>Verwendet in</li><li>Zuletzt verwendet</li></ul><p>Diese Informationen können Ihnen dabei helfen festzustellen, ob eine Komponente für Benutzer in Ihrer Organisation nützlich ist, wo sie verwendet wird und ob sie gelöscht oder geändert werden muss. Sie können das Datenwörterbuch zusammen mit diesen Informationen verwenden, um die Verwendung von Komponenten in Ihrem Unternehmen zu verfolgen und besser zu verstehen.</p> | 20. September 2023 | 4. Oktober 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


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
