---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d2aec8976d7d81c28a6b9b76c58fec0fc2c3b360
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 100%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (September 2022)

**Letzte Aktualisierung**: 14. September 2022

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Sie sollten sie deshalb regelmäßig lesen.

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics ](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Regionenübergreifende Unterstützung für Analytics Source Connector** | Sie können jetzt Berichts-Suites aus jeder Region (Vereinigte Staaten, Vereinigtes Königreich oder Singapur) einlesen. Diese Berichts-Suites müssen jedoch derselben Organisation zugeordnet sein wie die Experience Platform-Sandbox-Instanz, in der die Source-Verbindung erstellt wird. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) | 24. August 2022 |
| **Erste Sitzungsberichte** | Stellen Sie fest, ob es sich bei einer bestimmten Sitzung um die allererste Sitzung einer Person handelte. [Weitere Informationen](/help/data-views/data-views-usecases.md) | 24. August 2022 |
| **Experimentier-Bedienfeld für CJA** | Mit diesem neuen Workspace-Bedienfeld können CJA-Benutzende den Anstieg und die Konfidenz von A/B-Experimenten bewerten, die aus beliebigen Quellen stammen – online, offline, Adobe-Lösungen, Adobe Journey Optimizer und sogar BYO-Daten (bring-your-own). [Weitere Informationen](/help/analysis-workspace/c-panels/experimentation.md) | [Eingeschränkte Veröffentlichung](/help/release-notes/releases.md) ab 14. September 2022 |
| **Visualisierung von Kombinationsdiagrammen in Workspace** | Mit Kombinationsdiagrammen können Sie Metriken innerhalb von Workspace einfacher und intuitiver vergleichen. [Weitere Informationen](/help/analysis-workspace/visualizations/combo-charts.md) | 14. September 2022 |
| **CJA-Unterstützung für Data Governance-Beschriftungen und -Richtlinien** | Automatisiert die Integration zwischen CJA- und Adobe Experience Platform-Datenschutzbezeichnungen und -richtlinien. Datenbeschriftungen, die für von Platform verwendete Datensätze erstellt wurden, werden in CJA-Datenansichten angezeigt, um Benutzer zu stoppen oder zu warnen, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Außerdem, wenn Daten aus CJA exportiert werden (über den Workspace oder Report Builder, Export, API usw.) werden zusätzliche Warnungen oder Kennzeichnungen hinzugefügt, um die Nutzer darauf hinzuweisen, dass ein Bericht sensible Informationen enthält, die auf eine bestimmte Weise behandelt werden müssen. [Weitere Informationen](/help/data-views/data-governance.md) | 14. September 2022 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-298412

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbesserte Geolokalisierung von IPs** | 9. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics wird diesen neuen Datensatz am **5. Oktober 2022** übernehmen. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über Analytics Source Connector bereitgestellt werden, nutzen ebenfalls automatisch die neuen Zuordnungen. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
