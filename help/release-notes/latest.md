---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 94b3e7417b82e9ae3ad080884d4c184bee412c2c
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 91%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (Juli 2022)

**Letzte Aktualisierung**: 5. August 2022

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Unterstützung für numerische Felder als Suchschlüssel und Suchwerte | Dies ist nützlich, wenn Sie Zeichenfolgenwerte mit einem numerischen Feld wie COGS oder Marge für eine Produkt-SKU klassifizieren möchten. Wenn Sie Metriken aus der Suche zulassen, können Sie diese Datenpunkte in das Reporting einfließen lassen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#numeric) | 20. Juli 2022 |
| **Zielgruppenveröffentlichung im Echtzeit-Kundenprofil** | Ermöglicht Ihnen das Veröffentlichen von in Customer Journey Analytics entdeckten Zielgruppen in Adobe Experience Platform/Echtzeit-Kundenprofil für Kunden-Targeting und Personalisierung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=de) | 5. August 2022 |
| Bedienfeld „Gleichzeitige Medienbetrachter“ | Erkennen Sie, wo hohe Auslastungen auftraten oder wo es zu Einbrüchen kam. Erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern und erhalten Sie Hilfe bei der Fehlerbehebung oder der Planung in Bezug auf Volumen und Skalierung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=de) | **9. August 2022** |
| Panel „Verbrachte Zeit bei der Medienwiedergabe“ | Die mit Medienwiedergabe verbrachte Zeit bietet wertvolle Einblicke in die Interaktion mit Betrachtenden und ermöglicht es Medienunternehmen, tiefere, detailliertere Einblicke mit der minütigen Benutzerinteraktion durch erweiterte Zeitanalysen mit Funktionen zur Tageszeiteneinteilung zu gewinnen. Sie können feststellen, wie viel Zeit zu einem bestimmten Zeitpunkt mit der Anzeige Ihrer Medien-Streams verbracht wurde. Sie können die Wiedergabedauer nach verschiedenen Granularitäten unterteilen, einschließlich der neuen Granularitäten von 5, 15 und 30 Minuten.  [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=de) | **9. August 2022** |
| Reporting über neue und wiederholte Sitzungen | Sie können jetzt feststellen, ob es sich bei einer bestimmten Sitzung um die allererste Sitzung einer Person handelte. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) | 17. August 2022 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-288455; AN-288828; AN-289323

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbesserte Geolokalisierung von IPs** | 11. Juli 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics übernimmt diesen neuen Datensatz im Zeitrahmen bis zum **Oktober 2022**. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über Analytics Source Connector bereitgestellt werden, nutzen ebenfalls automatisch die neuen Zuordnungen. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
