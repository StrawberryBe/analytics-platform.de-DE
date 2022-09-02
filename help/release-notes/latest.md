---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6e22766b1730a34fc6219f66174e2dbd575cfa14
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 99%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (August 2022)

**Letzte Aktualisierung**: 25. August 2022

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Bedienfeld „Gleichzeitige Medienbetrachter“** | Erkennen Sie, wo hohe Auslastungen auftraten oder wo es zu Einbrüchen kam. Erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern und erhalten Sie Hilfe bei der Fehlerbehebung oder der Planung in Bezug auf Volumen und Skalierung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=de) | 9. August 2022 |
| **Panel „Verbrachte Zeit bei der Medienwiedergabe“** | Die mit Medienwiedergabe verbrachte Zeit bietet wertvolle Einblicke in die Interaktion mit Betrachtenden und ermöglicht es Medienunternehmen, tiefere, detailliertere Einblicke mit der minütigen Benutzerinteraktion durch erweiterte Zeitanalysen mit Funktionen zur Tageszeiteneinteilung zu gewinnen. Sie können feststellen, wie viel Zeit zu einem bestimmten Zeitpunkt mit der Anzeige Ihrer Medien-Streams verbracht wurde. Sie können die Wiedergabedauer nach verschiedenen Granularitäten unterteilen, einschließlich der neuen Granularitäten von 5, 15 und 30 Minuten.  [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=de) | 9. August 2022 |
| **Zielgruppenveröffentlichung im Echtzeit-Kundenprofil** | Ermöglicht Ihnen das Veröffentlichen von in Customer Journey Analytics entdeckten Zielgruppen in Adobe Experience Platform/Echtzeit-Kundenprofilen für Kunden-Targeting und Personalisierung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=de) | 17. August 2022 |
| **CJA-Unterstützung für Data Governance-Beschriftungen und -Richtlinien** | Automatisiert die Integration zwischen CJA- und Adobe Experience Platform-Datenschutzbezeichnungen und -richtlinien. Datenbeschriftungen, die für von Platform verwendete Datensätze erstellt wurden, werden in CJA-Datenansichten angezeigt, um Benutzer zu stoppen oder zu warnen, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Außerdem, wenn Daten aus CJA exportiert werden (über den Workspace oder Report Builder, Export, API usw.) werden zusätzliche Warnungen oder Kennzeichnungen hinzugefügt, um die Nutzer darauf hinzuweisen, dass ein Bericht sensible Informationen enthält, die auf eine bestimmte Weise behandelt werden müssen. [Weitere Informationen](/help/data-views/data-governance.md) | 17. August 2022 |
| **Unterstützung von Datumsfeldern in CJA** | Ermöglicht CJA die Berichterstellung über Datums- und Uhrzeitfelder. [Weitere Informationen](/help/data-views/data-views-usecases.md#date) | 17. August 2022 |
| **Regionenübergreifende Unterstützung für Analytics Source Connector** | Sie können jetzt Berichts-Suites aus jeder Region (Vereinigte Staaten, Vereinigtes Königreich oder Singapur) einlesen. Diese Berichts-Suites müssen jedoch derselben Organisation zugeordnet sein wie die Experience Platform-Sandbox-Instanz, in der die Source-Verbindung erstellt wird. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) | 24. August 2022 |
| **Erste Sitzungsberichte** | Sie können jetzt feststellen, ob es sich bei einer bestimmten Sitzung um die allererste Sitzung einer Person handelte. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) | 24. August 2022 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-297141

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbesserte Geolokalisierung von IPs** | 11. Juli 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics übernimmt diesen neuen Datensatz im Zeitrahmen **Oktober 2022**. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über Analytics Source Connector bereitgestellt werden, nutzen ebenfalls automatisch die neuen Zuordnungen. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
