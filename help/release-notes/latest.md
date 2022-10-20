---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a3d47318d74df161cf9054b849c9eb8ef09e60c4
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 90%

---

# Versionshinweise zu Customer Journey Analytics (CJA) (Oktober 2022)

**Zuletzt aktualisiert**: 18. Oktober 2022

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Experimentier-Bedienfeld** | Mit diesem neuen Workspace-Bedienfeld können CJA-Benutzende den Anstieg und die Konfidenz von A/B-Experimenten mit beliebigen Quellen bewerten – online, offline, Adobe-Lösungen, Adobe Journey Optimizer und sogar eigenen Daten. [Weitere Informationen](/help/analysis-workspace/c-panels/experimentation.md) | 5. Oktober 2022 |
| Visualisierung der **[!UICONTROL Zusammenfassung der Schlüsselmetriken]** | Mit der Visualisierung der [!UICONTROL Zusammenfassung der Schlüsselmetriken] können Sie sehen, wie sich eine wichtige Metrik innerhalb einer bestimmten Zeitspanne entwickelt. Außerdem können Sie damit die Leistung von Metriken über zwei Zeiträume hinweg vergleichen. Weitere Informationen | Schrittweiser Rollout ab 5. Oktober 2022 |
| **Unterstützung von Datumsfeldern in CJA** | Ermöglicht CJA die Berichterstellung über Datums- und Uhrzeitfelder. [Weitere Informationen](/help/data-views/data-views-usecases.md#date) | 5. Oktober 2022 |
| **Mobile App: Benutzerdefinierte Detailansichten** | Benutzerdefinierte Detailansichten ermöglichen es Ihnen, Informationen an Ihre Zielgruppe noch zielgerichteter auszuwählen, damit diese nicht abgelenkt wird. Sie können das Layout der Detailansicht jeder Scorecard-Kachel ändern, und Text hinzufügen, um Endbenutzenden zu helfen, die Daten besser zu verstehen. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=de) | 5. Oktober 2022 |
| **Bei Variablen mit mehreren Werten wird zwischen Groß- und Kleinschreibung unterschieden** | Bei Variablen mit mehreren Werten, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, werden die in `mvvar1` - `mvvar3` wird nicht mehr automatisch in Kleinbuchstaben geschrieben. Stattdessen spiegeln Daten, die über den Analytics Source Connector an Adobe Experience Platform und CJA übergeben werden, die ursprüngliche Groß-/Kleinschreibung wider, die von der Seite weitergegeben wurde. | 24. Oktober 2022 |

{style=&quot;table-layout:auto&quot;}

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Standard-Landingpage** | 29. September 2023 | Die [neue Landingpage](/help/getting-started/landing.md) wurde Anfang dieses Jahres eingeführt und wird ab **Januar 2023** standardmäßig allen Benutzenden angezeigt. Die aktuelle Seite wird eingestellt, sodass nur mehr die neue Seite verwendet wird. |
| **Verbessertes IP-Geolokalisierungs-Mapping** | 29. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics hat die Einführung dieses neuen Datensatzes auf **Januar 2023** verschoben. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über den [!UICONTROL Analytics Source Connector] bereitgestellt werden, nutzen ebenfalls automatisch die neuen Mappings. |
| Bedingungen für die automatische Ausführung der **[!UICONTROL Anomalieerkennung]** | 29. September 2022 | Derzeit wird die [!UICONTROL Anomalieerkennung] automatisch für alle Spalten von Zeitreihen-Freiformtabellen ausgeführt. Um sicherzustellen, dass Daten für Analysen verfügbar sind und Projekte schneller geladen werden, nimmt Adobe Änderungen an der automatischen Ausführung der [!UICONTROL Anomalieerkennung] vor. Ab dem **26. Oktober 2022** wird die Anomalieerkennung nur für die erste Metrikspalte in einer Tabelle automatisch ausgeführt. Sie können die Spalteneinstellungen bei Bedarf so konfigurieren, dass die [!UICONTROL Anomalieerkennung] auch für andere Spalten ausgeführt wird. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
