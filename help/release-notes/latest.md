---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8552e2e784cefc842f5105c41dcffc14192d5ceb
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 76%

---

# Aktuelle Customer Journey Analytics-Versionshinweise (CJA) (September 2022)

**Letzte Aktualisierung**: 14. September 2022

## Verwandte Ressourcen

* [Frühere CJA-Versionshinweise für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics ](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Regionenübergreifende Unterstützung für Analytics Source Connector** | Sie können jetzt Berichts-Suites aus jeder Region (Vereinigte Staaten, Vereinigtes Königreich oder Singapur) einlesen. Diese Berichts-Suites müssen jedoch derselben Organisation zugeordnet sein wie die Experience Platform-Sandbox-Instanz, in der die Source-Verbindung erstellt wird. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) | 24. August 2022 |
| **Erste Sitzungsberichte** | Erfahren Sie, ob eine bestimmte Sitzung die erste Sitzung eines Benutzers war. [Weitere Informationen](/help/data-views/data-views-usecases.md) | 24. August 2022 |
| **Experimentierbereich für CJA** | Mit diesem neuen Arbeitsbereich-Bedienfeld können CJA-Benutzer die Steigerung und Konfidenz von A/B-Experimenten aus jeder beliebigen Quelle bewerten - online, offline, aus Adobe-Lösungen, Adobe Journey Optimizer und sogar BYO-Daten (für Sie selbst). [Weitere Informationen](/help/analysis-workspace/c-panels/experimentation.md) | [Eingeschränkte Veröffentlichung](/help/release-notes/releases.md) ab 14. September 2022 |
| **Visualisierung von Combo-Diagrammen in Workspace** | Mit Combo-Diagrammen können Sie Metriken innerhalb von Workspace einfacher und intuitiver vergleichen. [Weitere Informationen](/help/analysis-workspace/visualizations/combo-charts.md) | 14. September 2022 |
| **CJA-Unterstützung für Data Governance-Beschriftungen und -Richtlinien** | Automatisiert die Integration zwischen CJA- und Adobe Experience Platform-Datenschutzbezeichnungen und -richtlinien. Datenbeschriftungen, die für von Platform verwendete Datensätze erstellt wurden, werden in CJA-Datenansichten angezeigt, um Benutzer zu stoppen oder zu warnen, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Außerdem, wenn Daten aus CJA exportiert werden (über den Workspace oder Report Builder, Export, API usw.) werden zusätzliche Warnungen oder Kennzeichnungen hinzugefügt, um die Nutzer darauf hinzuweisen, dass ein Bericht sensible Informationen enthält, die auf eine bestimmte Weise behandelt werden müssen. [Weitere Informationen](/help/data-views/data-governance.md) | 14. September 2022 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-298412

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbesserte Geolokalisierung von IPs** | 9. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics wird diesen neuen Datensatz auf **5. Oktober 2022**. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über Analytics Source Connector bereitgestellt werden, nutzen ebenfalls automatisch die neuen Zuordnungen. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
