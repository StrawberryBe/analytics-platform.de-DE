---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a3d47318d74df161cf9054b849c9eb8ef09e60c4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Customer Journey Analytics (CJA) - Versionshinweise (Oktober 2022)

**Letztes Update**: 18. Oktober 2022

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics ](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Experimentierbereich** | Mit diesem neuen Arbeitsbereich-Bedienfeld können CJA-Anwender den Anstiegund die Konfidenz von A/B-Experimenten aus beliebigen Quellen bewerten – online, offline, aus Adobe-Lösungen, Adobe Journey Optimizer und sogar BYO-Daten. [Weitere Informationen](/help/analysis-workspace/c-panels/experimentation.md) | 5. Oktober 2022 |
| Visualisierung der **[!UICONTROL Zusammenfassung einer Schlüsselmetrik]** | Durch die Visualisierung der [!UICONTROL Zusammenfassung einer Schlüsselmetrik] können Sie sehen, wie sich eine wichtige Metrik innerhalb eines einzigen Zeitraums entwickelt. Außerdem können Sie damit die Leistung von Metriken über zwei Zeiträume hinweg vergleichen. Weitere Informationen | Schrittweiser Rollout ab 5. Oktober 2022 |
| **Unterstützung von Datumsfeldern in CJA** | Ermöglicht CJA die Berichterstellung über Datums- und Uhrzeitfelder. [Weitere Informationen](/help/data-views/data-views-usecases.md#date) | 5. Oktober 2022 |
| **Mobile App: Benutzerdefinierte Detailansichten** | Benutzerdefinierte Detailansichten ermöglichen es Ihnen, noch zielgerichteter zu entscheiden, welche Informationen Sie für Ihre Zielgruppe freigeben, damit diese sich auf das Wichtigste konzentrieren kann. Sie können das Layout der Detailansicht ändern, die jeder Scorecard-Kachel zugeordnet ist, und Text hinzufügen, um Endbenutzerinnen und -benutzern zu helfen, die Daten besser zu verstehen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=de) | 5. Oktober 2022 |
| **Bei Variablen mit mehreren Werten wird zwischen Groß- und Kleinschreibung unterschieden** | Bei Variablen mit mehreren Werten, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, werden die in `mvvar1` - `mvvar3` wird nicht mehr automatisch in Kleinbuchstaben geschrieben. Stattdessen spiegeln Daten, die über den Analytics Source Connector an Adobe Experience Platform und CJA übergeben werden, die ursprüngliche Groß-/Kleinschreibung wider, die von der Seite weitergegeben wurde. | 24. Oktober 2022 |

{style=&quot;table-layout:auto&quot;}

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Standard-Landingpage** | 29. September 2023 | Die [neue Landingpage](/help/getting-started/landing.md) wurde Anfang dieses Jahres eingeführt und wird ab **Januar 2023** zum Standarderlebnis für alle Benutzerinnen und Benutzer. Die aktuelle Seite wird dann nicht mehr unterstützt und alle müssen das neue Erlebnis nutzen. |
| **Verbesserte Geolokalisierung von IPs** | 29. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics hat die Annahme dieses neuen Datensatzes auf **Januar 2023**. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über die [!UICONTROL Analytics Source Connector] nutzt auch automatisch die neuen Zuordnungen. |
| Bedingungen für die automatische Ausführung der **[!UICONTROL Anomalieerkennung]** | 29. September 2022 | Die [!UICONTROL Anomalieerkennung] wird automatisch für alle Spalten von Zeitreihen-Freiformtabellen ausgeführt. Um sicherzustellen, dass Daten für Analysen verfügbar sind und Projekte schneller geladen werden, ändert die Adobe die Vorgehensweise [!UICONTROL Anomalieerkennung] automatisch ausgeführt werden. Ab dem **26. Oktober 2022** wird die Anomalieerkennung nur für die erste Metrikspalte in einer Tabelle automatisch ausgeführt. Sie können die Spalteneinstellungen für die Ausführung konfigurieren [!UICONTROL Anomalieerkennung] auf andere Spalten, falls erforderlich. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
