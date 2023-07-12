---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste Versionshinweise zu Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2b0d091484c3c80d97de2952f4200d166ab5cd8a
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 37%

---

# Aktuelle Adobe Customer Journey Analytics-Versionshinweise (Juli 2023)

**Letzte Aktualisierung**: 10. Juli 2023

Adobe Customer Journey Analytics-Versionen funktionieren auf einer [kontinuierlicher Versand](releases.md) , was einen skalierbareren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Neue oder aktualisierte Funktionen

| Funktion | Beschreibung | [Rollout-Beginn](releases.md) | [Allgemeine Verfügbarkeit](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics ist eine neue Möglichkeit, mit kanalübergreifenden Daten und Einblicken in Customer Journey Analytics zu interagieren. Diese neuen Funktionen ermöglichen es Produkt-Teams, Daten und Erkenntnisse selbst mithilfe geführter Analyse-Workflows in ihrem Produkterlebnis bereitzustellen. Teams können:<ul><li>im Lauf der Zeit Muster in der Benutzerinteraktion erkennen</li><li>Verfolgen Sie das Wachstum und die Beibehaltung der &#x200B; des Produkts.</li><li>Reibungsbereiche im Produkt identifizieren</li><li>Messen Sie die Auswirkungen von Feature-Versionen &#x200B; und der ersten Verwendung.</li><li>Entdecken Sie aussagekräftige Segmente von Anwendern, die während ihres gesamten Journey mit dem Produkt interagieren und es fördern &#x200B;</li><li>Verbindung zu Analysis Workspace für eine tiefer gehende Analyse und Zusammenarbeit mit Analysten herstellen</li></ul>Adobe Product Analytics ist ein kostenpflichtiges Add-on für Customer Journey Analytics. Wenden Sie sich an Ihr Adobe Account Team, wenn Sie diese Funktion nutzen möchten. [Weitere Informationen](/help/guided-analysis/overview.md) | Nicht angegeben | 17. Juli 2023 |
| **Abgeleitete Felder** | Dies stellt die erste Version abgeleiteter Felder dar. Mit einem abgeleiteten Feld können Sie mithilfe eines anpassbaren Regel-Builders spontan (häufig komplexe) Datenmanipulationen definieren. Sie können das abgeleitete Feld als Komponente (Metrik oder Dimension) in Datenansichten weiter definieren und dann das abgeleitete Feld als Komponente in Workspace verwenden.<p>Diese Version unterstützt eine Vorlage für Marketing-Kanäle und die folgenden Funktionen:</p><ul><li>Verketten</li><li>Fall wenn</li><li>Suchen und Ersetzen</li><li>Nachschlagen</li><li>URL-Parsen</li></ul> <p>[Weitere Informationen](/help/data-views/derived-fields/derived-fields.md)</p> | 10. Mai 2023 | 2. August 2023 |
| **Erweiterte Suchunterstützung für Profil- und Suchdaten** | Bietet die Möglichkeit, Datensätze als Suchen von Feldern in Profil- oder Lookup-Datensätzen hinzuzufügen. Zuvor wurden nur Ereignis-Datensätze unterstützt. [Weitere Informationen] | 21. Juni 2023 | 12. Juli 2023 |
| **Report Builder-Verbesserungen** | <ul><li>Filtern Sie aus einer Zelle nach mehreren Datenblöcken. Sie können die Filter für mehrere Datenblöcke aus einer Zelle ändern. Verwenden Sie eine vordefinierte Zelle, weisen Sie sie mehreren Datenblöcken zu und aktualisieren Sie die Daten anhand der in der Zelle definierten Filter. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Zeilen- und Spaltenüberschriften ein- und ausblenden. Sie können Tabellenüberschriften von Datenblöcken ein- oder ausblenden oder Zeilen- und Spaltenüberschriften verwenden, um die Tabelle neu zu formatieren und Datenblöcke in einem Bericht auszurichten. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | Nicht angegeben | 19. Juli 2023 |
| **Experience Edge-Geo-Suchen** | Adobe Experience Edge fügt einen Geo-Suchdienst hinzu, der allen Experience Edge-Benutzern (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medien Analytics, Adobe Experience Platform usw.) einheitliche geografische Daten bereitstellt. | Nicht angegeben | 26. Juli 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444 AN-323116

## Wichtige Hinweise für Customer Journey Analytics-Administratoren

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Änderungen bei der Verarbeitung von Daten durch Customer Journey Analytics** | 22. Juni 2023 | Wir haben kürzlich die Art und Weise geändert, wie wir Daten in Customer Journey Analytics verarbeiten.<ul><li>Alle Ereignisdaten mit einem Zeitstempel unter 24 Stunden werden gestreamt.</li><li>Alle Ereignisdaten mit einem Zeitstempel, der älter als 24 Stunden ist (auch wenn sie sich im gleichen Batch wie neuere Daten befinden) werden als Aufstockung betrachtet und mit einer niedrigeren Priorität erfasst.</li></ul> |

{style="table-layout:auto"}

## Mitteilungen über das Ende der Nutzungsdauer (EOL)

| Ende der Nutzungsdauer eines Produkts oder einer Funktion | Datum hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Migration zu Adobe I/O OAuth Server-zu-Server-Anmeldeinformationen** | 11. Mai 2023 | Adobe Analytics-API-, Customer Journey Analytics-API- und Livestream-Kunden, die Adobe I/O-JWT-Anmeldeinformationen verwenden, müssen zu Adobe I/O OAuth Server-zu-Server-Anmeldeinformationen migrieren, indem Sie **1. Januar 2025**. Adobe I/O lässt die Erstellung neuer JWT-Anmeldeinformationen ab dem 1. Mai 2024 nicht zu. Kunden und Kundinnen, die JWT verwenden, müssen neue OAuth Server-zu-Server-Anmeldeinformationen erstellen oder ihre bestehende JWT-Anmeldeinformationen zu OAuth Server-zu-Server-Anmeldeinformationen migrieren. Kunden und Kundinnen müssen außerdem ihre Client-Anwendungen aktualisieren, um die neuen OAuth Server-to-Server-Anmeldeinformationen zu verwenden. <ul><li>[Migration von Dienstkonto-Anmeldeinformationen (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Verwenden der neuen OAuth Server-zu-Server-Anmeldeinformationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Häufig gestellte Fragen (FAQ)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Verwandte Ressourcen

* [Frühere Versionshinweise für Customer Journey Analytics 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
