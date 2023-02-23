---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4e41bda273f0f7e93941bb00b55bffc6b357ac1f
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 79%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (Februar 2023)

**Letzte Aktualisierung**: 23. Februar 2023

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Start des Rollouts](/help/release-notes/releases.md) | [Allgemeine Verfügbarkeit](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Aktualisierung für CJA-Zielgruppen** | Nachdem Sie eine Zielgruppe erstellt haben, erstellt Adobe für jede neue CJA-Zielgruppe ein Experience Platform-Streaming-Segment. Ein Streaming-Segment wird nur dann erstellt, wenn für Ihre Organisation Streaming-Segmentierung eingerichtet ist. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=de#after-audience-created) | Nicht angegeben | 3. Februar 2023 |
| **Ausblenden von Datumsbereichen für den Vergleich in mobilen Scorecards** | Bei mobilen Scorecards können Sie jetzt Vergleichsdatumsbereiche ausblenden. | Nicht angegeben | 8. Februar 2023 |
| **Kalenderaktualisierungen in Workspace** | <ul><li>Datumsangaben im Ankerbereich: Sie können die Datumsbereichskomponenten relativ zum Bedienfeldkalender festlegen. [Weitere Informationen](/help/components/date-ranges/calendar.md)</li><li>Aktualisierungen des Kalenderstils: Die Kalenderstile in der gesamten Benutzeroberfläche wurden aktualisiert, um einen konsistenteren und benutzerfreundlicheren Workflow zu bieten.</li><li>Aktualisierungen der Kalenderformel: Wenn Sie relative Datumswerte verwenden, spiegeln alle Kalenderformeln den Beginn des Datumsbereichs des Bedienfelds wider. [Weitere Informationen](/help/components/date-ranges/calendar.md)</li></ul> | Nicht angegeben | 8. Februar 2023 |
| **Aktualisierungen des Datumsbereichs des Bedienfelds** | In Workspace wurden die folgenden Verbesserungen hinzugefügt:<ul><li>Ab der Februar-Version basieren die Komponenten- und Datenvorschau auf dem Datumsbereich des Bedienfelds und nicht auf den letzten 90 Tagen. </li><li>Alle in der linken Leiste aufgelisteten Komponenten sind basierend auf dem Datumsbereich des Bedienfelds verfügbar.</li><li>Alle Datumsvorschauen im Segment und in den Generator für berechnete Metriken basieren auf dem Datumsbereich des Bedienfelds (sofern nicht von den Komponentenmanagern zugegriffen wird, die über kein verknüpftes Bedienfeld verfügen, basieren sie weiterhin auf den letzten 90 Tagen).</li><li>Bei jeder Datenvorschau werden Daten oder Komponenten basierend auf dem Datumsbereich des Bedienfelds angezeigt.</li></ul> | Nicht angegeben | 8. Februar 2023 |
| **Zeilen-/Spaltenfilter für Adobe Analytics Source Connector-Streaming** | Analytics Source Connector in Adobe Experience Platform ermöglicht jetzt das Filtern von Analytics-Daten, mit denen Profile im [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) vorausgefüllt werden.<p>Die Filterung auf Zeilenebene hilft, die Anzahl der mit Profilen verknüpften Ereignisse zu reduzieren. Die Filterung auf Spaltenebene hilft, die Vielfalt der Ereignisse selbst zu reduzieren, und ermöglicht es Ihnen so, die Nutzung von Profilberechtigungen zu optimieren. Diese Filterung gilt nur für Daten, die an das Echtzeit-Kundenprofil und den [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de) gesendet werden.<p>**Die Filterung wirkt sich nicht auf die Daten aus, die zur Verwendung in Anwendungen wie Customer Journey Analytics an Data Lake gesendet werden**. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de#filtering-for-profile) | Nicht angegeben | Geplant für den 29. März 2023 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen in Customer Journey Analytics

AN-309106

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Keine aktuellen Hinweise | nicht angegeben | Nicht angegeben |

{style=&quot;table-layout:auto&quot;}

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
