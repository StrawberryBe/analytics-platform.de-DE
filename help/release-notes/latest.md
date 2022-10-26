---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 07842c9f1e2f4708d0881dec75c067d93611626c
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 59%

---

# Customer Journey Analytics (CJA) - Versionshinweise (Oktober/November 2022)

**Letztes Update**: 25. Oktober 2022

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Start des Rollouts](/help/release-notes/releases.md) | [Allgemeine Verfügbarkeit](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| Visualisierung der **[!UICONTROL Zusammenfassung der Schlüsselmetriken]** | Mit der Visualisierung der [!UICONTROL Zusammenfassung der Schlüsselmetriken] können Sie sehen, wie sich eine wichtige Metrik innerhalb einer bestimmten Zeitspanne entwickelt. Außerdem können Sie damit die Leistung von Metriken über zwei Zeiträume hinweg vergleichen. [Weitere Informationen](/help/analysis-workspace/visualizations/key-metric.md) | 5. Oktober 2022 | 19. Oktober 2022 |
| **Mehrwert-Variablen ohne Unterscheidung von Groß- und Kleinschreibung** | Bei Variablen mit mehreren Werten, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, werden die in `mvvar1` - `mvvar3` wird nicht mehr automatisch in Kleinbuchstaben geschrieben. Stattdessen spiegeln Daten, die über den Analytics Source Connector an Adobe Experience Platform und CJA übergeben werden, die ursprüngliche Groß-/Kleinschreibung wider, die von der Seite weitergegeben wurde. | Nicht angegeben | 24. Oktober 2022 |
| **CJA-Auditprotokoll** | Mit Customer Journey Analytics (CJA) können Sie Benutzeraktivitäten auf verschiedene Dienste und Funktionen in Form von &quot;Auditprotokollen&quot;prüfen. Diese Protokolle bilden ein Audit-Protokoll, das Ihnen bei der Fehlerbehebung helfen und Ihrem Unternehmen helfen kann, die Richtlinien der Unternehmensdatenverwaltung und die gesetzlichen Anforderungen wie den Health Insurance Portability and Accounability Act (HIPAA) effektiv zu erfüllen. Diese Protokolle waren bisher nur über die Auditprotokolle-API verfügbar. [Weitere Informationen](/help/privacy/audit-log.md) | Nicht angegeben | 26. Oktober 2022 |
| **HIPAA-Bereitschaft** | Adobe unterstützt jetzt nur noch den Empfang, die Verwendung, die Pflege oder die Übermittlung geschützter Gesundheitsinformationen in Customer Journey Analytics und anderen auf Experience Platform basierenden Anwendungen für den Gesundheitsschild. Der Gesundheitsschild richtet sich an Kunden im Gesundheitswesen, die entweder eine abgedeckte Organisation oder einen Geschäftsverband nur in den USA sind. [Weitere Infos](https://www.adobe.com/trust/compliance/hipaa-ready.html) | Nicht angegeben | 7. November 2022 |
| **Kennwortschutz für geplante Projekte** | Diese Funktion ist Teil der HIPAA-Bereitschaft und gilt nur für Kunden des Gesundheitsschilds. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password) | Nicht angegeben/ | 7. November 2022. |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

* Es wurde ein Problem behoben, bei dem aktuelle MacOS-Versionen fälschlicherweise als &quot;Macintosh&quot;bezeichnet wurden. Mit dieser Fehlerbehebung beginnt die Betriebssystemdimension mit der Nummerierung der MacOS-Version, beginnend mit MacOS 11. (AN-301834)

### Weitere  Fehlerbehebungen

AN-302367; AN-302562; AN-304036

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Standard-Landingpage** | 29. September 2023 | Die [neue Landingpage](/help/getting-started/landing.md) wurde Anfang dieses Jahres eingeführt und wird ab **Januar 2023** standardmäßig allen Benutzenden angezeigt. Die aktuelle Seite wird eingestellt, sodass nur mehr die neue Seite verwendet wird. |
| **Verbessertes IP-Geolokalisierungs-Mapping** | 29. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics hat die Einführung dieses neuen Datensatzes auf **Januar 2023** verschoben. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über den [!UICONTROL Analytics Source Connector] bereitgestellt werden, nutzen ebenfalls automatisch die neuen Mappings. |
| Bedingungen für die automatische Ausführung der **[!UICONTROL Anomalieerkennung]** | 29. September 2022 | Derzeit wird die [!UICONTROL Anomalieerkennung] automatisch für alle Spalten von Zeitreihen-Freiformtabellen ausgeführt. Um sicherzustellen, dass Daten für Analysen verfügbar sind und Projekte schneller geladen werden, nimmt Adobe Änderungen an der automatischen Ausführung der [!UICONTROL Anomalieerkennung] vor. Ab dem **26. Oktober 2022** wird die Anomalieerkennung nur für die erste Metrikspalte in einer Tabelle automatisch ausgeführt. Sie können die Spalteneinstellungen bei Bedarf so konfigurieren, dass die [!UICONTROL Anomalieerkennung] auch für andere Spalten ausgeführt wird. |

{style=&quot;table-layout:auto&quot;}


## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
