---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1e147b63053f63c90d8e433d90e1bc5a4f1acd4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 35%

---

# Aktuelle Customer Journey Analytics-Versionshinweise (CJA) (Juli 2022)

**Letzte Aktualisierung**: 19. Juli 2022

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Unterstützung für numerische Felder als Suchschlüssel und Suchwerte | Nützlich, wenn Sie Zeichenfolgenwerte mit einem numerischen Feld wie COGS oder Marge auf einer Produkt-SKU klassifizieren möchten. Wenn Sie Metriken aus der Suche zulassen, können Sie diese Datenpunkte in die Berichterstellung einfließen lassen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 20. Juli 2022 |
| Bedienfeld „Gleichzeitige Medienbetrachter“ | Erkennen Sie, wo hohe Auslastungen auftraten oder wo es zu Einbrüchen kam. Erhalten Sie wertvolle Einblicke in die Qualität von Inhalten und die Interaktion mit Betrachtern und erhalten Sie Hilfe bei der Fehlerbehebung oder der Planung in Bezug auf Volumen und Skalierung. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 30. Juli 2022 |
| Panel „Verbrachte Zeit bei der Medienwiedergabe“ | Die Besuchszeit für die Medienwiedergabe bietet wertvolle Einblicke in die Interaktion mit Betrachtern und ermöglicht es Medienunternehmen, tiefere, detailliertere Einblicke durch die minütige Benutzerinteraktion durch eine erweiterte Besuchszeitanalyse mit Tagesaufteilungsfunktionen zu gewinnen. Sie können feststellen, wie viel Zeit zu einem bestimmten Zeitpunkt mit der Anzeige Ihrer Medien-Streams verbracht wurde. Sie können die Wiedergabedauer nach verschiedenen Granularitäten unterteilen, einschließlich der neuen Granularitäten von 5, 15 und 30 Minuten.  [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 30. Juli 2022 |
| Berichte zu ersten und wiederholten Sitzungen | Sie können jetzt feststellen, ob eine bestimmte Sitzung die erste Sitzung eines Benutzers war. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17. August 2022 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-288455; AN-288828; AN-289323

## Wichtige Hinweise für CJA-Administratoren

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbesserte Zuordnung von IP zu Geolocation** | 11. Juli 2022 | Der Anbieter von IP-Suchen, Digital Element, von Adobe, aktualisiert auf einen neuen verbesserten Datensatz (NetActivity Pulse) für die IP-zu-Geolocation-Zuordnung. Adobe Analytics übernimmt diesen neuen Datensatz im **Oktober 2022**, Zeitrahmen. Die neue Datenbank wird genauer sein als frühere Versionen. Einige IP-zu-Geo-Zuordnungen werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über den Analytics Source Connector bereitgestellt werden, nutzen ebenfalls automatisch die neuen Zuordnungen. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
